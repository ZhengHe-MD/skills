# Cut list, rendering, and verification

## Inspect and freeze

Use media probes such as `ffprobe` to read duration, orientation, dimensions, frame rate/time base, colour properties, and audio streams. Select the court-audio track deliberately. Inspect local encoder capabilities before choosing settings.

Save a manifest containing:

- Source path and a reliable content fingerprint, stream selection, and timestamp origin.
- Mode, routine checklist, ordered clip IDs, and internal selection reasons.
- Source start-inclusive/end-exclusive boundaries, frame indices or presentation timestamps with their time base, and expected frame counts and durations.
- Output timeline positions, timing policy, audio sample rate, encoder settings, and tool versions.
- Review uncertainties and verification results; rejected candidates stored separately.

Check that all intervals are positive, within the source, ordered, and non-overlapping. A cache key must cover source identity, selected bounds, streams, and rendering settings; times alone can silently reuse another recording's media.

For constant frame rate, align boundaries to the actual frame grid and derive duration from selected frame count divided by frame rate. For variable frame rate, use actual presentation timestamps or record an explicit conversion to an output frame grid. Preserve source audio/video offsets when mapping both streams onto that timeline. Derive audio sample boundaries from the same cumulative timeline with rational arithmetic, avoiding rounding drift between segments.

## Render

Keep the source unchanged and intermediate images/media outside deliverables. Preserve the source's framing, orientation, and colour interpretation. Make and inspect a short trial export when the media format or rendering path differs from a previously verified one.

For exact cuts, encode selected video intervals with consistent settings and timestamps starting at zero. Decode corresponding audio to PCM, join the PCM intervals, then encode the final audio once. This avoids a separate AAC priming delay at every join. Concatenate compatible encoded video segments without a second video encode. Check codec configuration, dimensions, pixel format, colour properties, and time base before reusing segments from an earlier edit. Use a fresh source render for changed boundaries; ordinary keyframe-limited stream copying is insufficient for arbitrary exact cuts.

The approved reference used a macOS FFmpeg path: HEVC `hevc_videotoolbox`, Main 10, `p010le` input, 12 Mb/s, `hvc1` MP4 with fast-start, and 48 kHz PCM intermediates encoded once to stereo AAC at 256 kb/s. This matched a 1920 × 1080, constant-30-fps, BT.2020/HLG source. It retained the HLG base picture, but did not recreate Dolby Vision dynamic metadata or include the additional spatial-audio track.

Treat that profile as an example for matching media. Derive frame/sample counts from the new source; the reference's 1,600 samples per video frame applies only at 48 kHz and 30 fps. Match SDR/HDR tags and bit depth to the actual picture. If tone mapping or dropping source features is necessary, make that choice explicit and verify the resulting image rather than merely changing tags.

## Acceptance checks

Complete these checks on the final assembled file:

- Intended dimensions, orientation, frame rate/timing policy, colour signalling, and audio stream are present.
- Every rendered segment and the assembled output match manifest frame counts and durations. Audio sample accounting matches the chosen timeline; any container/codec duration tolerance is justified.
- Presentation timestamps form the expected timeline without unintended gaps or duplicates, and decode timestamps progress correctly across joins. Account for frame reordering rather than requiring packet-order presentation timestamps to be monotonic.
- The entire video and audio decode without errors.
- Exported opening, routine samples, joins, and ending retain the intended framing and contain no unintended overlays, blank frames, or colour changes.
- Court sound aligns at widely separated points, including near the end. Listen with visible action or compare output audio against the corresponding source audio at mapped times. Matching durations alone does not establish synchronization.
- The chosen mode's coverage and boundary checks still match the export.

Fix failures and rerun affected checks before delivery. Technical integrity cannot establish editorial correctness; the visual review remains necessary. Save actual checks and limitations, distinguishing measured results from assumptions. Reproducibility means the same selections and timing, not guaranteed identical hardware-encoder bytes.
