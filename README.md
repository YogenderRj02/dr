# Drone Progress Tracker

Drone photos ka EXIF metadata, projects, kaam, missions aur GCP track karne wala web app.

## GitHub par chalane ke steps
1. Is repo me `index.html` aur `data/drone-data.json` upload karo.
2. Settings > Pages me branch `main` aur folder `/ (root)` select karo.
3. GitHub > Settings > Developer settings > Fine-grained token banao (sirf is repo ka Contents: read/write).
4. Page kholo, "GitHub sync" me `owner/repo`, branch `main`, path `data/drone-data.json` aur token daalo.
5. "Push to GitHub" se data repo me save hota hai, "Pull from GitHub" se wapas aata hai.

## KML files
- "KML" tab se `.kml` upload karo. File repo me `kml/<project-naam>/` folder me save hoti hai (GitHub sync settings zaroori).
- Points, lines aur polygons Dashboard map par violet rang me dikhte hain.
- KML ke points ko "Points ko GCP banao" se GCP list me import kar sakte ho.
- KML ka parsed geometry `data/drone-data.json` me bhi rehta hai, isliye Pull karne par map wapas ban jata hai.

## Map, coverage aur auto-assign
- Dashboard ka map satellite/street basemap, KML, photo thumbnails (KML ke upar), GCP aur photo footprint dikhata hai. Pan, zoom (wheel ya pinch) aur "Fit" button hai. Basemap ke liye internet chahiye.
- Photos ki thumbnails `drone-data.json` me save hoti hain (har photo ~2 KB), isliye bahut photos par file badi ho jati hai.
- Area coverage: KML polygon = kaam ka area. Har photo ka footprint = height x factor. Polygon ka jitna hissa footprints se dhaka, wahi % kaam complete maana jata hai.
- Missions tab me "date se auto-assign" photo ki date ko mission ki date se match karta hai (upload par bhi apne aap chalta hai).

## Extra features
- Dashboard: progress ring, "Dhyan do" alerts, coverage trend (din ke hisaab se) aur map par "Baaki area" (lal) overlay.
- Photos tab: file search, mission filter aur CSV export.
- Header: Theme (dark/light) toggle aur Print / PDF (report ke roop me print hota hai).

## GCP KML aur map se status
- GCP tab me GCP ki KML upload karo: saare points GCP ban jate hain (status planned).
- GCP tab (aur Dashboard) ke map par saare GCP dikhte hain, zoom karne par naam bhi. Rang: lal = planned, narangi = marked, neela = coordinates collect ho gaye, hara = verified.
- Map par kisi GCP par click/tap karo, neeche status ke buttons aate hain.
