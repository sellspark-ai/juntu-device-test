Juntu (slice 2: one Short end to end, with subtitles)

index.html is the Juntu app as one page: its code, styles, fonts (also the 12 subtitle fonts, which the export burns
into the video) and the export engine are inside the file. The only
other files the page loads are its Home Screen icons and web manifest, which sit next to it:
apple-touch-icon.png, favicon.svg, icon-192.png, icon-512.png, icon-maskable-512.png, manifest.webmanifest.
It contacts no other server. THIRD-PARTY-NOTICES.txt (the licences of the bundled libraries), this README and
SHA256SUMS.txt are in the same folder; the page does not link to them.

Videos, photos and music you pick stay on this device, in the browser's storage for this site (IndexedDB). Nothing is
uploaded and file names are not stored. A photo the browser cannot read directly (for example some HEIC files) is
kept as a JPEG copy. Where the browser does not store files in IndexedDB as they are (Safari Private Browsing),
the app stores their bytes in pieces instead and shows one line that nothing is kept after the tab closes. If a file cannot be added, the message shows why, with a "Copy details" button: tapping it
copies one line to the clipboard (kind, type, size, codec, the step that failed and the error; no file names), and
nothing is copied or sent otherwise. After a preview play of 2 s or more, a small "Preview check" label on the
video does the same for playback counters (frames shown, counted two ways, and dropped; seeks, waits; no file names). A small export-settings cache in the site's localStorage
(juntu-route-cache-v1) remembers which video encoder works on this device; it holds the browser's user agent and
the measured encoder speeds, and also never leaves the device. Subtitle styles you save with "Save this style" are
kept in the site's localStorage (juntu-saved-styles-v1) so they can be used in other Shorts; subtitle text is
stored only inside the Short's own history in IndexedDB and never leaves the device. The height you drag the
timeline to is remembered per orientation in localStorage (juntu-layout-v1, two numbers, nothing personal). Exports are saved through the Share sheet ("Save Video" puts them in Photos).
