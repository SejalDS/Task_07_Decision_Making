# Deep Fake Interview – Process Documentation (Syracuse Women’s Lacrosse 2024)

## Goal
Transform the Syracuse Women’s Lacrosse 2024 narrative insights into a concise, clearly labeled synthetic audio interview for coursework.

## Narrative Source
- Derived from my 2024 LLM prompt Q&A summary: shooting efficiency (46.8% vs 38.6%), most impactful scorer (Emma Tyrrell, 92 points), draw-control dominance (Katelyn Mashewske, 234 DCs), team draw edge (384 vs 334), emphasis on improving defense to gain two more wins, and Natalie Smith as a defensive “game changer.”

## Deliverables
- `transcript_2024.txt` – the interview script (Host & Coach).
- (You will generate) `deepfake_interview_2024.mp3` – final audio.
- (Optional) `captions_2024.srt` – subtitles file if submitting video.

## Free Tools Used / Suggested
- **edge-tts** (CLI) – free Microsoft neural voices.  
  - Install: `pip install edge-tts`  
  - Example: `edge-tts --text "Line here" --voice en-US-AriaNeural --write-media line_0.mp3`
- **Audacity** – free editor for sequencing clips and normalizing.  
- **(Optional)** Coqui TTS – open-source alternative (`pip install TTS`).  
- **(Optional)** Shotcut – for video assembly & captions if you produce MP4.

## Workflow
1. **Script** the interview (see `transcript_2024.txt`).
2. **Generate TTS** with two voices (e.g., en-US-AriaNeural for Host, en-US-GuyNeural for Coach).
3. **Sequence & Mix** in Audacity: trim silences, add 300–500 ms gaps, normalize to −1 dB.
4. **Export** final audio as `deepfake_interview_2024.mp3`.
5. **(Optional video)**: add a static background, lower-thirds (“AI-generated”), and subtitles; export MP4.

## Reproduction (One-File Script Approach)
Create `generate_interview_2024.py` locally with the following:

```python
import os

lines = [
    ("en-US-AriaNeural", "Coach, headline takeaway from the 2024 season?"),
    ("en-US-GuyNeural", "Shot conversion. We finished at roughly forty-six point eight percent, while opponents were around thirty-eight point six. We created and finished good looks."),
    ("en-US-AriaNeural", "If you’re chasing two more wins next year, what’s the lever—offense or defense?"),
    ("en-US-GuyNeural", "Defense. Our attack produced, but tightening opponent efficiency—limiting clean looks, better closeouts—can flip close results our way."),
    ("en-US-AriaNeural", "Name one player who defined offensive impact."),
    ("en-US-GuyNeural", "Emma Tyrrell. She led with ninety-two points—seventy goals and twenty-two assists—and was constantly involved, taking one hundred thirty-five shots and helping on draws."),
    ("en-US-AriaNeural", "Possession was a theme—who owned the circle?"),
    ("en-US-GuyNeural", "Katelyn Mashewske. Two hundred thirty-four draw controls. That volume of extra possessions sets the tone for tempo and pressure."),
    ("en-US-AriaNeural", "Give me one team metric that clearly tilted in your favor."),
    ("en-US-GuyNeural", "Draw controls overall—three hundred eighty-four to three hundred thirty-four. More first touches means more chances to control pace and get our sets."),
    ("en-US-AriaNeural", "If the focus is defense, who’s your ‘game changer’ profile?"),
    ("en-US-GuyNeural", "Natalie Smith. Thirty-six ground balls and thirty-six draws, plus she contributes on offense. With some role tuning—matchups and on-ball disruption—she can swing key possessions."),
    ("en-US-AriaNeural", "Final word on priorities for the off‑season?"),
    ("en-US-GuyNeural", "Keep our shooting quality, train late-clock defense and interior help, and convert our possession edge into scoreboard separation."),
    ("en-US-AriaNeural", "Appreciate it, coach—see you next season."),
]

for i, (voice, text) in enumerate(lines):
    os.system(f'edge-tts --text "{text}" --voice {voice} --write-media line_{i}.mp3')

with open("inputs_2024.txt", "w") as f:
    for i in range(len(lines)):
        f.write(f"file 'line_{i}.mp3'\n")

# Requires ffmpeg installed: macOS (brew install ffmpeg), Windows (choco install ffmpeg), Ubuntu (sudo apt-get install ffmpeg)
os.system("ffmpeg -f concat -safe 0 -i inputs_2024.txt -c copy deepfake_interview_2024.mp3")
print("✅ deepfake_interview_2024.mp3 generated")
```

Run:
```bash
pip install edge-tts
# Install ffmpeg (see comment in script)
python generate_interview_2024.py
```

## Iterations & Notes
- Adjust TTS **rate** or **pitch** via per-line flags if needed (Edge TTS supports SSML in the Python API).
- If words like “G+A−TO” sound odd, rewrite as “G plus A minus T O” (done in this script).
- Keep the **disclaimer** at the top and visible labeling if you render video.

## Ethics & Labeling
- This is clearly labeled **AI-generated** for academic purposes.
- No real-person voice cloning; generic synthetic voices only.
- Names appear only as part of a statistical recap and are not impersonations.
