Juntu (slice 1: one Short end to end)

index.html is the Juntu app as one page: its code, styles, fonts and the export engine are inside the file. The only
other files the page loads are its Home Screen icons and web manifest, which sit next to it:
apple-touch-icon.png, favicon.svg, icon-192.png, icon-512.png, icon-maskable-512.png, manifest.webmanifest.
It contacts no other server. THIRD-PARTY-NOTICES.txt (the licences of the bundled libraries), this README and
SHA256SUMS.txt are in the same folder; the page does not link to them.

Videos, photos and music you pick stay on this device, in the browser's storage for this site (IndexedDB). Nothing is
uploaded and file names are not stored. Exports are saved through the Share sheet ("Save Video" puts them in Photos).
