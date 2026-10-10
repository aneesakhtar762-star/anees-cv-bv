# ATS Resume Checker

Upload a resume (PDF, DOCX or TXT) and get an ATS score out of 100, a score breakdown, missing keywords, prioritized improvements and rewrite examples. Optionally paste a job description for a more accurate keyword match.

Built with Streamlit and Google's `gemini-3.8-flash` model.

## Run locally

```bash
pip install -r requirements.txt
export GEMINI_API_KEY="your-key"      # Windows PowerShell: $env:GEMINI_API_KEY="your-key"
streamlit run app.py
```

Get a free API key at https://aistudio.google.com/apikey. If no key is set, the app asks for one in the sidebar.

## Deploy on Streamlit Community Cloud

1. Push `app.py`, `requirements.txt` and `README.md` to a GitHub repository.
2. Go to https://share.streamlit.io and sign in with GitHub.
3. Click **Create app**, pick the repo, branch `main` and main file `app.py`.
4. Open **Advanced settings > Secrets** and add:
   ```toml
   GEMINI_API_KEY = "your-key"
   ```
5. Click **Deploy**.

## Notes

- Scanned/image-only resumes can't be read (an ATS can't read them either). Use a text-based PDF or DOCX.
- The score is an AI estimate, not the output of a real ATS. Use it as guidance.
- Never commit your API key to GitHub. Use Streamlit Secrets.# anees-cv-bv
