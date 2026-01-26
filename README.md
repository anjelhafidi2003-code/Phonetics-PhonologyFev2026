
Minimal Colab example using **whisper.cpp** to transcribe **a WAV** file and export **sub-token data** to a CSV: 

# Requirements - Do this step before our session, please :) 
- Google Colab (**You need a Gmail account.**) 
- You need one `.wav` file in the language of your choice.  
**notes**   
a) No longer than 30 seconds.
b) Non-English languages are welcome — Whisper supports them!
c) You can even record yourself!

## Output files
After running the notebook cells you will get:
- `/content/out.json` (full transcription + sub-tokens)
- `/content/tokens.csv` (one row per sub-token)

- `token` (text)
- `start_ms`, `end_ms` (token timestamps in ms, when available)
- `p` (token probability)
- `id` (Whisper vocabulary token id)

It uses:
- `-ojf` to output full JSON (includes tokens + probabilities)
- `-dtw base` for token-level timestamp alignment (experimental alignment)


## Notes
- Use `-l auto` for automatic language detection, or set `-l fr`, `-l ar`, `-l zh`, etc.
- Some tokens can have `start_ms == end_ms` (often punctuation/space or uncertain alignment).
