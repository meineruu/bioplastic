# Bioplastic Anthocyanin pH Scanner

## Description / Overview
A camera-based tool that reads the color of a BPF (butterfly pea flower)
bioplastic indicator film and estimates the pH of whatever it's touching,
then reports whether it falls in a safe range for food or drink contact.

It's built for scientists and lab researchers working with anthocyanin-based
bioplastic pH indicators who want a fast, low-cost way to turn a color
reading into a pH estimate without a benchtop meter.

## Demo
Open `index.html` in a browser (or the deployed Vercel link) on a phone or
laptop with a camera. Point it at the BPF film, take a shot, and confirm,
the pH level and a safety verdict appear immediately below.

## Installation
This is a static site so it doesn't need build step and dependencies to install.

**Run locally:**
```bash
git clone <your-repo-url>
cd ph-scanner
python3 -m http.server 8000
```
Then open `http://localhost:8000` in your browser. Camera access works on
`localhost` without HTTPS.

**Deploy to Vercel:**
```bash
npm i -g vercel
cd ph-scanner
vercel --prod
```
Or import the repo at [vercel.com/new](https://vercel.com/new), no build
settings needed, Vercel serves it as-is.

> Camera access requires HTTPS in production. Vercel provides this
> automatically.

## Usage
1. Open the app and allow camera access when prompted.
2. Point the camera at the BPF indicator film so it fills the frame.
3. Tap the shutter button to take the photo.
4. Review the shot, then tap **Gunakan foto ini** to confirm (or
   **Ambil ulang** to retake).
5. The result card updates with:
   - **pH level** — an estimated numeric reading
   - **Kelayakan makanan/minuman** — a verdict: too acidic, safe to
     consume, or too alkaline
6. No camera? Use **atau unggah foto dari galeri** to analyze an existing
   photo instead.

## Features
- Live camera capture with a guided 3:4 viewfinder, or photo upload as a
  fallback
- Shot review step, confirm or retake before analysis runs
- Color sampling from the center of the frame, converted to a pH estimate
  via a hue-to-pH curve calibrated against a BPF-polymer reference chart
- Automatic verdict against three pH bands (acidic / safe / alkaline)
- Visual pH gradient strip with a live marker showing where the reading
  falls
- Fully client-side, no server and data leaves the device
- Responsive and mobile-first layout

## Tech Stack / Built With
- HTML5 (`<video>` / `getUserMedia` for camera capture, `<canvas>` for
  pixel sampling)
- CSS3 (custom properties, no framework)
- Vanilla JavaScript (RGB → HSL conversion, hue-to-pH interpolation)
- [Inter](https://fonts.google.com/specimen/Inter) via Google Fonts
- Deployed on [Vercel](https://vercel.com) as a static site

## Contributing
Issues and pull requests are welcome, in particular, additional reference
chart calibrations for other bioplastic batches or lighting conditions
would be valuable. Please open an issue first to discuss larger changes.

## License
MIT — free to use, modify, and distribute. 

## Credits / Acknowledgments
- pH-to-color calibration based on a "Colour change of BPF-Polymer film in
  different pH solution" reference chart from MDPI.
