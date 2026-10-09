# Home Bar changelog

The working file is always `Home Bar.html` in the folder above. Before each change the previous version is copied here as `Home Bar v{N} {date} {note}.html`, so each archived file is the final state of that version. Those archived copies stay on the owner's PC and are not in the Git repository, because versions up to v18 carry a personal starting list; from v19 the Git history holds every version.

## v23, 2026-10-09: Easy extras, Champagne flute, two Amaretto Sours
- The six recipes dropped in v22 are back as easy extras: Cuba Libre, Screwdriver, White Russian, Black Russian, Tequila Sunrise and Pimm's Cup. 57 recipes in all.
- Amaretto Sour checked online. The 1974 original is amaretto, lemon and sugar; the version on the essentials list (amaretto, cask-proof bourbon, lemon, rich syrup, egg white) is Jeffrey Morgenthaler's from 2012. "Amaretto Sour" is now the original and "Amaretto Sour (Morgenthaler)" the bourbon and egg white one.
- Essentials: Champagne flute under Glassware, for French 75, Champagne Cocktail and Bellini. An existing Essentials list gets it once, not ticked, when the app opens or a backup is restored; delete it and it stays deleted.

## v22, 2026-10-09: 50 essential cocktails
- The built-in list is now 50 essential cocktails in seven groups: spirit-forward (Old Fashioned to Godfather), sours and daisies (Daiquiri to White Lady), highballs and fizzes (Tom Collins to Whiskey Highball), equal-parts and bitter (Last Word to Black Manhattan), sparkling (French 75 to Bellini), tiki (Mai Tai to Painkiller) and modern classics (Espresso Martini to Brandy Alexander). Martini is now Dry Martini.
- Dropped from the old list: Cuba Libre, Screwdriver, White Russian, Black Russian, Tequila Sunrise and Pimm's Cup.
- Matching is generous where it is safe: sugar counts as simple syrup, fresh limes and lemons count as their juice, any sparkling wine counts as Prosecco, Cointreau or curaçao as triple sec, aquafaba as egg white, cognac as brandy, pastis or Pernod as absinthe. Optional garnishes (nutmeg, an Islay float) are left out.
- Starting list: new categories Amari & herbal and Store cupboard, and new generic items Overproof rum, Mezcal, Pisco, Maraschino liqueur, Crème de violette, Crème de cacao, Drambuie, Falernum, Green and Yellow Chartreuse, Bénédictine, Absinthe, Averna, Amaro Nonino, Lillet Blanc, Prosecco, Peychaud's bitters, Grapefruit soda, Cranberry, Grapefruit, Pineapple and Tomato juice, Cream of coconut, Peach purée, Double cream, Orgeat, Raspberry syrup, Cinnamon syrup, Espresso, Worcestershire sauce, Hot sauce and Orange flower water. Every one of the 50 can be made from the starting list.
- An existing bar list is untouched. "Restore missing defaults" in Settings adds the new generic names.
- Essentials: glassware descriptions updated for the new drinks.

## v21, 2026-10-09: Alcohol-free versions count in cocktails
- The separate Non-alcoholic spirits category is gone. An alcohol-free product now sits in the category of the drink it replaces (an alcohol-free gin under Gin) and carries an alcohol-free flag, shown as a green 0% tag on the Bar tab. It counts towards Make now, One ingredient away and Buy next like the regular version.
- On first opening, and when restoring an older backup, anything in a Non-alcoholic spirits category is flagged and moved to its drink's category when the name says what it is (gin, whisky, rum, vodka, tequila, brandy, aperitif, liqueur, bitters). Anything the name does not give away stays where it is, flagged, to move by hand with the Category picker.
- Bottle sheet: an Alcohol-free (0%) switch. Bar tab: a 0% filter.
- Names with "0.0", "0%", "alcohol-free", "non-alcoholic" or "zero proof" are flagged automatically when added by hand, from a photo or from Ideas. Photo scan asks Gemini whether each product is alcohol-free and offers a 0% chip on new items to correct it.
- Prompts: tasting notes, How to make and Surprise me name alcohol-free products as such. How to make gives the regular recipe plus a swap line when you have both versions, and says whether the drink ends up alcohol-free when you only have the alcohol-free one.
- Starting list: Alcohol-free gin is now under Gin.

## v20, 2026-10-09: Change category
- Bottle sheet and Essentials sheet: a Category picker under the stock switch moves the item to another category, or to a new one via "New category…". Notes, link, tasting notes and stock state stay with it. An emptied custom category disappears from the list.
- Moving a bottle into or out of Non-alcoholic spirits changes whether it counts towards cocktails, as before for items added there.

## v19, 2026-10-09: Generic starting list
- A new install starts with generic names (London dry gin, Scotch whisky, Coffee liqueur, Aromatic bitters and so on), all marked as not in stock, the same way the Essentials list starts. Every built-in recipe can still be matched from them. An existing list is untouched; restore a backup to bring back a specific bar.
- Eggs added to the fresh list.
- Note: "Restore missing defaults" in Settings now adds the generic names, so after restoring a personal backup it would add generic entries alongside your own bottles.

## v18, 2026-10-09: Bar kit in the prompts
- Surprise me and How to make now tell Gemini which Essentials you have ticked and which you do not. Drinks are picked to suit the kit; where a usual tool is missing Gemini gives a workaround with your kit or ordinary kitchen things, or picks another drink, and serves it in a glass you own.
- Surprise me's closing line can now name one missing piece of kit instead of a bottle, when that would unlock more drinks.
- With nothing ticked on the Essentials tab the prompts are unchanged, so an untouched checklist does not rule out shaken drinks.

## v17, 2026-10-08: Automatic model fallover
- Every Gemini call starts with the model chosen in Settings. If Google answers with quota reached (429), busy (503), another server error or model not found (404), the app tries the other free-tier text models in turn and stops at the first that answers: 3.8 Flash, 3.7 Flash, 3.6 Flash, 3.5 Flash, 3.5 Flash-Lite, 3.1 Flash-Lite, 3 Flash Preview, 2.5 Flash-Lite (Google's pricing page, 2026-10-08; free quotas are counted per model). Connection failures, timeouts and key errors do not fall over.
- A model that was busy or out of quota is skipped for five minutes; one that was not found is skipped until the page is reopened. If everything is skipped the preferred model is tried anyway.
- While falling over the answer box says "Thinking… trying 3.7 Flash". An answer from a stand-in gets a grey line underneath naming the model and why the usual one was passed over. The Settings Test does the same. If every model fails the message says so, with the Copy prompt / Open Gemini fallback as before.
- Settings lists the stand-in order under the model box.

## v16, 2026-10-08: Copy works at content:// addresses
- Bug: every Copy chip failed on the phone with "Could not copy on this device". Cause: opening the file from a file manager gives Chrome a content:// address, which is not a secure context, so the modern clipboard API does not exist there (and neither does the share sheet). Copy now falls back to the old selection-based copy, and if that is refused too it opens a "Copy by hand" sheet with the text preselected.
- Settings: the backup text no longer promises the share sheet; where sharing is unavailable it explains the content:// cause and how opening the file at a file:/// address in Chrome brings sharing and the clipboard back (export first, restore there, since Chrome keeps data per address).

## v15, 2026-10-08: Saved recipes in Make now, Essentials detail sheet
- My recipes: "Add to Make now" asks Gemini once to read a saved recipe's ingredients as generic keys. The recipe then appears (marked ★) in Make now / One ingredient away / Further away, feeds Buy next, and is listed on the bottle sheets of what it uses. "Remove from Make now" undoes it. Backups carry the ingredient keys.
- Essentials: tap a name for a detail sheet with the Have toggle, an editable "what it is for" line, Gemini "How to use it" tips (cached on the device, Share/Copy), and your own notes. Tips follow renames and are pruned on delete; Reset everything clears them; backups include them.
- Bottle sheet: saved recipes that are in Make now now arrive via the ingredient match, the rest by text match (looser, see v14), without double counting.

## v14, 2026-10-08: Backup reminder, share, robustness
- Backup reminder on the Bar tab when something changed since the last backup and it is 30+ days old, or 25+ saves have piled up, or there has never been one. "Later" snoozes it for a week. Settings shows the last backup date. Restoring a backup counts as being backed up.
- Share chips (Android share sheet) beside every Copy: recipes, saved recipes, tasting notes, ideas, shopping list. Falls back to Copy where sharing is unavailable or fails; a cancelled share is reported as such.
- Gemini calls time out after 60 seconds with their own message instead of hanging on "Thinking…".
- Buttons that call Gemini (How to make, Surprise me, tasting notes, Test) are disabled while the call runs, so a second tap cannot start a second request. Photo scan ignores a second photo while one is being read.
- Fixes: a bulk notes run finishing on another tab no longer redraws that tab; folded categories still show their hits under the Low / In stock / Out filters; Reset everything also clears cached Gemini answers and saved recipes (wording updated); Clear key keeps a custom model name; Edit mode switches off when changing tabs; restored links must be http(s).
- Bottle sheet matches saved recipes more loosely: full name, first two words, or a brand-like first word ("Johnnie Walker Black Label 12 Year Old..." is found from "Johnnie Walker").

## v13, 2026-10-08: Rename, share export, add ingredient, housekeeping
- Edit mode on the Bar and Essentials tabs: tap a name to rename it inline. Tasting notes follow the new name. Duplicate names are refused.
- Export backup uses the Android share sheet when the browser supports sharing files, so the backup can go straight to OneDrive. Falls back to a download elsewhere.
- Ideas tab: after a Surprise me run that used a free-text ingredient, one chip adds that ingredient to the bar list (with a category picker).
- Deleting a bottle also removes its cached tasting notes.
- Bulk tasting notes update the progress line in place instead of redrawing the whole Bar tab after every bottle.
- This changelog added.

## v12, 2026-10-08: Full backup, saved recipes, tailored recipes
- Backup export now includes items, essentials, saved recipes, cached Gemini answers (tasting notes, recipes, last ideas) and preferences. The API key is never included. Restore accepts both the new format and the old item-only format.
- Saved recipes: Save chips on each Surprise me drink and on How to make answers. A "My recipes" section on the Cocktails tab lists them with Copy and two-tap Delete. The bottle detail sheet lists saved recipes that mention the bottle.
- How to make passes the actual bottles in stock so Gemini tailors the recipe to them.

## v11, 2026-10-08: Mood and Style rows
- Surprise me returns exactly two recipes and gains a Style row (Long, Short, Bittersweet, Dry, Fizzy, Creamy, Fruity) alongside Mood.

## v10, 2026-10-08: Copy prompt fallback
- Any Gemini failure (including 503 high demand) or missing key shows the exact prompt with Copy prompt and Open Gemini, so it can be pasted into the Gemini app.

## v9, 2026-10-08: ml recipe layout
- Recipes and ideas are laid out as Ingredients then Method, with all liquids in ml.

## v8, 2026-10-08: Surprise me free text
- Free-text box on the Ideas tab for an odd ingredient the AI should work into the drinks.

## v7, 2026-10-08: Bulk tasting notes
- "Get notes for everything in stock" button, one bottle at a time, with Stop and automatic pauses on quota errors.

## v6, 2026-10-08: Running low, tasting notes
- Running low flag per bottle, Low filter, Running low list and shopping list copy on the Cocktails tab.
- Bottle detail sheet: cocktails using it, Gemini tasting notes, your own notes, a link.

## v5, 2026-10-08: Essentials tab
- Equipment and glassware checklist with a line on what each is for.

## v4, 2026-10-08: Settings tab, Buy next, photo, search, dark
- Settings tab (appearance, Gemini key and model with Test, backup, defaults).
- Buy next suggestions, photo scan with review sheet, word-start search, collapsible categories, dark mode.

## v3, 2026-10-08: Gemini 3.8 default
- Default model changed to gemini-3.8-flash.

## v2, 2026-10-08: Gemini API
- Claude artifact calls replaced by the Gemini REST API with the user's own key kept in browser storage.

## v1, 2026-10-08: Original Claude artifact
- Starting point exported from Claude.ai: Bar, Cocktails and Ideas tabs.
