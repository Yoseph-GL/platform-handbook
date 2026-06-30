# HTML Advanced: Audio and Video

## Architecture / Rationale

The `<audio>` and `<video>` elements embed media directly into web pages. They work without plugins or external players.

- `<audio>` plays sound files. Use the `controls` attribute to show play/pause buttons.
- `<video>` plays video files. Add `controls` and `width`/`height`.
- Both support multiple `<source>` elements for different file formats.

## Query / Code Blocks

```html
<!-- Audio player -->
<audio controls>
    <source src="audio/podcast.mp3" type="audio/mpeg">
    <source src="audio/podcast.ogg" type="audio/ogg">
    Your browser does not support audio.
</audio>

<!-- Video player -->
<video controls width="640" height="360" poster="video/thumbnail.jpg">
    <source src="video/demo.mp4" type="video/mp4">
    <source src="video/demo.webm" type="video/webm">
    Your browser does not support video.
</video>
```

## Performance / Optimization Notes

- Always provide multiple formats (MP4 + WebM, MP3 + OGG) for cross-browser compatibility.
- Add the `poster` attribute to video. It shows an image before the video starts playing.
- Do not set `autoplay` without `muted`. Most browsers block unmuted autoplay.
