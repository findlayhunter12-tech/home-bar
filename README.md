# Home Bar

A small web app for keeping track of a home bar: what bottles you have, what you can make with them, and ideas for what to mix next. It is a single HTML file with no install, no build step and no server. It was made for an Android phone but works in any modern browser.

## What it does

- **Bar.** Your bottles and mixers by category. Tick what is in stock, flag what is running low, search, and rename or delete in Edit mode. Tap a bottle for tasting notes, the cocktails that use it, your own notes, a link, and to move it to another category. Alcohol-free versions sit with the drink they replace, carry a 0% tag, and count towards cocktails.
- **Add from photo.** Take a picture of a shelf and Gemini lists the bottles it can read. You review them before anything is saved.
- **Cocktails.** 50 essential cocktails, from the Old Fashioned to tiki and modern classics, plus a few easy extras, sorted into what you can make now, what is one ingredient away, and what is further off. Also a running-low shopping list, "Buy next" suggestions for the bottle that unlocks the most drinks, and your saved recipes.
- **How to make.** Gemini writes a recipe for the exact bottles you have, in ml, with a method that suits your bar kit.
- **Ideas.** "Surprise me" suggests two drinks from your stock, steered by mood (Refreshing, Strong, Sour...) and style (Long, Short, Fizzy...). It can work in something odd you want to use up. Keep the ones you like.
- **Essentials.** A checklist of equipment and glassware with what each is for, plus Gemini tips on using it. How to make and Surprise me use this list, so they suggest workarounds for tools you do not have.
- **Settings.** Light and dark themes, your Gemini key, and a full backup to a file that you can restore on any device.

## Getting started

1. Open it at **[findlayhunter12-tech.github.io/home-bar](https://findlayhunter12-tech.github.io/home-bar/)**, or download `Home Bar.html` and open the file in a browser.
2. On the Bar and Essentials tabs, tick what you own. A new install starts with a generic list with nothing ticked. Add your own bottles by name or from a photo.
3. For the AI features, add a Gemini API key in Settings (see below). Everything else works without one.

### On an Android phone

The simplest way is the hosted address above: sharing and copy work there, and Chrome's "Add to Home screen" gives it an icon. Updates arrive by themselves.

If you use a downloaded copy instead, Chrome treats the page differently depending on how it is opened:

- **Opened from a file manager**, the page gets a `content://` address. The app works, but the share sheet and automatic copy are not available. Copy falls back to a "copy by hand" box.
- **Opened from Chrome's address bar**, at for example `file:///sdcard/Download/Home%20Bar.html`, sharing and copy both work.

Chrome keeps the app's data separately for each address. If you switch from one to the other, export a backup first and restore it at the new address. To update the app later, overwrite the file at the same path and your data stays.

## Gemini (optional)

The AI features call Google's Gemini API directly from your browser with your own key.

1. Get a free key at [Google AI Studio](https://aistudio.google.com/apikey).
2. Paste it into Settings and press Test.

Things to know:

- The key is stored only in your browser's local storage. It is never written into the HTML file or into backups.
- The default model is `gemini-3.8-flash`. If a model is out of quota, busy or unavailable, the app tries the other free-tier Flash and Flash-Lite models in turn and tells you which one answered. Free quotas are counted per model, so this keeps things working on busy days.
- If Gemini cannot answer at all, the app shows the exact prompt with a copy button, so you can paste it into the Gemini app instead.
- Your prompts, which include your stock list, go to Google under the terms of your API key. On the free tier Google may use them to improve its products. Check Google's terms if that matters to you.
- If you only use the hosted address, you can restrict the key in Google's settings to that address (`https://findlayhunter12-tech.github.io/*`) and to the Gemini API only. A restricted key will not work from a downloaded copy.

## Your data

Everything you enter stays on your device, in the browser's local storage: stock, notes, saved recipes, cached Gemini answers and preferences. There is no account, no server and no tracking. The app talks only to the Gemini API, and only when you use an AI feature.

That also means clearing the browser's site data deletes it. Use Settings, then Export backup now and then. The app reminds you when a backup is due. Backups are plain JSON files and never include your API key.

## Files

| File | What it is |
| --- | --- |
| `Home Bar.html` | The whole app: HTML, CSS and JavaScript in one file |
| `index.html` | Sends the hosted address on to `Home Bar.html` |
| `Archive/CHANGELOG.md` | What changed in each version |
| `LICENSE` | MIT licence |

The version number is shown in Settings, under About.

## Licence

MIT. You are free to use, change and share it; keep the copyright notice in copies. See `LICENSE`.
