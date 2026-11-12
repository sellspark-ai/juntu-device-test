Juntu (slice 2: one Short end to end, with subtitles)

index.html is the Juntu app as one page: its code, styles, fonts (also the 16 subtitle fonts, which the export burns
into the video) and the export engine are inside the file. The only
other files the page loads are its Home Screen icons and web manifest, which sit next to it:
apple-touch-icon.png, favicon.ico, favicon.svg, icon-192.png, icon-512.png, icon-maskable-512.png, manifest.webmanifest.
It contacts no other server, except Google when you connect YouTube or Google Drive (below). THIRD-PARTY-NOTICES.txt (the licences of the bundled libraries), this README and
SHA256SUMS.txt are in the same folder; the page does not link to them.

Videos, photos and music you pick stay on this device, in the browser's storage for this site (IndexedDB). Nothing is
uploaded and file names are not stored. A photo the browser cannot read directly (for example some HEIC files) is
kept as a JPEG copy. Where the browser does not store files in IndexedDB as they are (Safari Private Browsing),
the app stores their bytes in pieces instead and shows one line that nothing is kept after the tab closes. If a file cannot be added, the message shows why, with a "Copy details" button: tapping it
copies one line to the clipboard (kind, type, size, codec, the step that failed and the error; no file names), and
nothing is copied or sent otherwise. After a preview play of 2 s or more, a small "Preview check" label on the
video does the same for playback counters (frames shown, counted two ways, and dropped; seeks, waits; transitions played, how many started late, how long the next video took to start, waits and jumps inside
transitions, and how often a video was refused sound; no file names). A small export-settings cache in the site's localStorage
(juntu-route-cache-v1) remembers which video encoder works on this device; it holds the browser's user agent and
the measured encoder speeds, and also never leaves the device. Subtitle styles you save with "Save this style" are
kept in the site's localStorage (juntu-saved-styles-v1) so they can be used in other Shorts; subtitle text is
stored only inside the Short's own history in IndexedDB and never leaves the device. The height you drag the
timeline to is remembered per orientation in localStorage (juntu-layout-v1, two numbers, nothing personal).
Voice recordings use the microphone only while you record; they are stored on this device like your videos and
never leave it. The measured microphone delay, the "Hear your Short" choice and whether the microphone
explanation was shown are kept in localStorage (juntu-voice-latency-v1, juntu-voice-prefs-v1,
juntu-voice-asked-v1). Transitions between clips are stored inside the Short (no new storage key); during a transition
the preview plays two videos at once. Exports are saved through the Share sheet ("Save Video" puts them in Photos).

YouTube and Google Drive (only after you tap Connect; with no Google values in the build the Connect buttons say
Google isn't set up and nothing calls Google). Google's sign-in window (accounts.google.com) gives the page a token
that stays in memory; Juntu then talks only to Google's own servers (www.googleapis.com, openidconnect.googleapis.com
and, for Drive's file picker, apis.google.com and docs.google.com). YouTube and Drive are two separate connections,
each may use its own Google account, and Disconnect on one leaves the other alone. Upload to YouTube sends the
exported Short you chose, with the title, who can watch and the made-for-kids answer you picked; nothing else. While
it uploads, a hidden copy of that Short is kept in this site's storage (a separate database, juntu-google) so the
upload can go on after Juntu was closed; the copy is deleted once YouTube has the file. Kept in localStorage:
juntu-youtube-auth-v1 (the connected account's id, email and channel name, and the token with its expiry),
juntu-youtube-prefs-v1 (the last privacy and made-for-kids answers), juntu-youtube-upload-v1 (while an upload runs:
Google's upload address, the size, the bytes sent and when, the title and the Short's id; no token).
The YouTube video id of an uploaded Short is kept with the Short in IndexedDB (youtube:<id>).
