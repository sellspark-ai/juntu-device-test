Juntu Google check (built from sellspark-ai/juntu google-check-1 ce932d74)

A one-page device check for Juntu's Google Drive and YouTube designs, used on the iPad with throwaway Google test
accounts. index.html holds the page's code and styles; manifest.webmanifest lets it be added to the Home Screen.
It does not use the Juntu app (app/) or its storage.

The page contacts only Google: accounts.google.com (sign-in), openidconnect.googleapis.com and www.googleapis.com
(YouTube and Drive calls and uploads), apis.google.com and docs.google.com (only when the Picker check is tapped).
It uploads only its own test data: a 4 second synthetic test video (always private) and tiny generated files in a
Drive folder named "Juntu device check". Tokens and account emails stay in the page's memory and are never shown or
copied. "Copy results" copies a short report with no email, token or configured value. One key is kept in this
site's localStorage: gcheck-youtube-session-v1 (check C16, the address of a private test upload session).

The page carries the project's OAuth client IDs, Picker API key and project number, as every browser sign-in page
does; they are restricted to this site in the Google Cloud project.
