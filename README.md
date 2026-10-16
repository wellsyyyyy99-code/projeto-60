# Projeto 60: São Paulo Sprint 🇧🇷

This is a 60-episode Portuguese audio story, built automatically into podcast episodes, Anki flashcards and transcripts. It starts on 16 October with Episode 1 and ends with Episode 60 on 14 December. On 17 December, you fly.

## Setup (about 20 minutes, the same steps you did before)

1. **New repo:** on GitHub, go to **+ → New repository**, name it `projeto-60`, and set it to **Public**. Click **uploading an existing file** and drag in the **contents** of this folder. Then **Commit**.
2. **Robot file:** `.github` won't upload by dragging. Go to **Add file → Create new file**, type the name `.github/workflows/build.yml`, paste in everything from `workflow-copy.yml`, and **Commit**.
3. **Pages:** go to **Settings → Pages → Source** and choose **GitHub Actions**.
4. **Build:** go to **Actions → Build Projeto 60 → Run workflow**, leave it at 0, and wait for a ✅ (about 5 minutes).
5. **Your site:** `https://<your-username>.github.io/projeto-60/`. It has the transcripts, decks and feed link.
6. **Podcast app:** add `…/projeto-60/feed.xml`. Turn auto-download on and sort oldest first.
7. **Anki:** import `pack-00` (sound rules) and `pack-01` (episodes 1–3). Then set the options for the **Projeto 60** deck: 25 new cards/day, 400 max reviews, FSRS on, retention 0.90. **Sync**.
8. **Claude Project:** create one called "Projeto 60", paste `prompts/master_prompt.txt` into its instructions, and upload `packs/pack-01.json` to it.

## Twice a week (about 5 minutes each)

- **Sunday:** generate the Mon–Wed pack.
- **Wednesday:** generate the Thu–Sun pack.

The **Packs** tab in your tracker shows each pack number and its date.

1. In the Claude Project, send: `Generate pack N. My mistake log: …`
2. Copy the reply from `{` to `}`. On GitHub, go to `packs` → **Add file → Create new file**, name it `pack-NN.json` (two digits, e.g. `pack-02.json`), paste, and **Commit**.
3. Wait about 5 minutes, then import the new deck into Anki and **Sync**. New episodes appear in your podcast app on their own.
4. Upload the same JSON file to the Claude Project, so the story stays consistent and phrases get recycled.

## How the episodes work

Each episode: listen twice, shadow every line (slow, then story speed), then one final listen with no transcript.

**The speed ladder:** the robot speeds the story up automatically as the episode numbers rise.

| Episodes | Speed |
|---|---|
| 1–10 | −25% |
| 11–20 | −15% |
| 21–30 | −8% |
| 31–40 | normal |
| 41–50 | +6% |
| 51–60 | +12% |

## Speaking practice built into every episode

Each episode now has two extra sections:

- **Be George:** the story plays with gaps where George speaks. Say his lines before you hear them.
- **Your turn:** characters ask *you* questions. Answer out loud, then hear an example answer.

The transcript page for each episode has the questions, a 🎯 **Speaking mission**, and a 🎙️ **AI voice prompt** you can copy straight into Claude voice mode.

Anki also gets **"Answer aloud"** cards: you hear a question and answer it out loud before flipping.

Pack 00 includes **"As 20 perguntas da Mãe"**: the 20 questions Gabi's mum is most likely to ask.

## If something goes wrong

- **Red ❌ on the run:** click it and find the line starting with ❌. It's usually a copy-paste issue, so regenerate the pack and paste again.
- **Voice service hiccup:** press **Re-run jobs**.
- **Rebuild everything:** run the workflow manually with **force = 1**.
