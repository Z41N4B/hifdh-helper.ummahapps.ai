# Hifdh Helper

A free Qur'an memorisation tracker and planner, live at https://hifdh-helper.ummahapps.ai/

This file tells Claude (and anyone else working on the site) how the project works. It is part of the Ummah Apps family, listed at https://ummahapps.ai/.

## How this site works
- A plain static site: HTML, CSS and JavaScript with no build step and no server code. Most of the app is in `index.html`.
- It is hosted on GitHub Pages. Pushing to `main` puts it live within a minute or two. Keep the `CNAME` file, or the custom domain stops working.
- Nothing is uploaded. All progress is saved in the browser on the user's own device (localStorage, cookies or IndexedDB). There are no accounts, analytics or paid services.
- `README.md` gives a short summary only. Most details are in `index.html` itself, so read the relevant part of it before changing anything.

## Saved progress is precious
Learners may have months of progress saved on their devices. Never rename or remove a storage key, cookie or data field without code that moves the old data across. Old saved data must still load. When a data shape changes, test with data saved by the old version.

## Writing style
- Use plain, simple English everywhere: on screen, in the README and in commit messages. Many users are children, parents, or people whose first language isn't English.
- Commit messages are one short sentence saying what changed for the user, for example "Go to the next question by itself 2 seconds after a right answer".
- Keep Arabic fully vowelled (harakat) unless the app has a setting to hide the vowels.

## Religious content
- Never make up or paraphrase Qur'an text, hadith wording or duas. Use only wording that is already in the app or that the owner provides, and keep the source (for example the Sahih al-Bukhari or Sahih Muslim number on sunnah.com).
- Follow the Prophet's name with "peace be upon him" (or ﷺ).
- If unsure whether something is religiously correct, ask the owner instead of guessing.

## Search engines and AI tools (SEO and GEO)
When a feature, count or description changes, also update what describes it: the meta description, the JSON-LD and the FAQ in `index.html`, `llms.txt`, and the date in `sitemap.xml`.

## Before saying a change is done
- Run the site locally and check the change in the browser preview, including on a phone-sized screen.
- Check the browser console for errors.
- Ask the owner before committing or pushing, because pushing makes it live for everyone.

## Hifdh Helper
- `sw.js` is a network-first service worker, so it can be installed and works offline. If you add a file the app needs offline, add it to `CORE` in `sw.js`.
- `ar.js` holds the Arabic version of the interface. When English text on screen changes, change the Arabic too, with correct Arabic counting and number forms.
- There is no `serve.js`. Run it locally with any static server from this folder, for example `npx serve .`
