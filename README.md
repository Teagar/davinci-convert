# davinci-convert

CLI tool to convert videos to DaVinci Resolve friendly DNxHD/DNxHR format with progress bar and ETA.

## Why I built it

While editing on Arch Linux, I ran into video and audio files that DaVinci Resolve would not accept correctly. After a lot of research and testing, I found a video and audio combination that worked for my workflow without those errors. But converting every video meant typing the same long FFmpeg command over and over. I built `davinci-convert` to make that repeatable: give it a file (or a folder) and let the tool handle the conversion, with a progress bar and ETA.

By default, the script uses DNxHD video (`dnxhd`, 36 Mbps, `yuv422p`) and PCM 16-bit stereo audio at 48 kHz in a `.mov` file. It also offers DNxHR profiles and an option to remove audio. Compatibility can depend on the DaVinci Resolve version, source media and system setup; these defaults reflect the workflow I tested, not a guarantee for every installation.

## Usage

```bash
davinci-convert input.mp4
davinci-convert -i input.mp4
davinci-convert input.mp4 -o output.mov
davinci-convert -b folder/
```
