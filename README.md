# Royal Palace — Live Wedding Invitation (Just For You · JFY-WED-ROYAL-PALACE)
Static site: index.html + styles.css + script.js + assets/. No build step, no server code. Host on any static host.
Data: edit assets/sample-data.js (window.JFY_DATA) or pass `#data=<base64 JSON>` in the URL, or postMessage {type:'jfy:data', data}.
Tokens: {{key}} / {{key|long|short|time|dm|initial}}. `data-optional` hides empty fields. `data-fit` shrinks long names.
Events: JFY_DATA.events = [{name,date:'YYYY-MM-DDTHH:MM',venue,map_url,note,dress,image}] (any count).
RSVP: client-side confirmation + WhatsApp prefilled message (rsvp_whatsapp); also postMessage 'jfy:rsvp', window.JFYBridge.onRsvp(json) for the Android WebView, optional POST to rsvp_endpoint.
URL flags: ?skip=1 (skip the call screen), ?autoplay=1 (auto-answer after load), ?music=0.
Credits: Music "There is Romance" — Kevin MacLeod (incompetech.com), CC BY 4.0. Fonts: Pinyon Script, Great Vibes, Cormorant Garamond, Marcellus, Josefin Sans (SIL OFL). Artwork: original AI-generated illustrations + hand-coded SVG ornaments made for Just For You.

## Editor (edit.html)
Form for names, parents, date/time, venue + map link, events (add/remove), photos (shrunk and embedded in the link), messages, RSVP WhatsApp, music and gallery toggles. Live preview in a phone frame. "Create my invitation" builds index.html#data=z.<deflate-raw base64url JSON> with Copy, WhatsApp share, and native share. A draft is saved in localStorage. Opening edit.html#data=... re-edits an existing link.
