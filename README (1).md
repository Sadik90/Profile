# Sadik Bhattarai – Portfolio Website

A single-file portfolio page. Everything (HTML, CSS, JavaScript, and your profile photo) lives in one file: `scholar-view-dynamic.html`.

## 1. What you need

- A modern web browser (Chrome, Edge, Firefox, or Safari)
- An internet connection (the page loads Tailwind CSS and Google Fonts from the web)
- Optional: Python 3 (only if you want to run a local server; see step 3)

## 2. Run it on your computer (quickest way)

1. Put these files in the same folder:
   - `scholar-view-dynamic.html`
   - `sadik_cv.pdf` (your CV, used by the "View CV" button)
   - any certificate images you add later (see section 5)
2. Double-click `scholar-view-dynamic.html`. It opens in your default browser.

That's it. No install is needed.

## 3. Run it with a local server (recommended for testing)

Some browsers restrict local files. A local server avoids that.

Open a terminal in the folder with the files, then run one of these:

```bash
# Python 3 (macOS, Linux, Windows)
python -m http.server 8000
```

Then open **http://localhost:8000/scholar-view-dynamic.html** in your browser.

Stop the server with `Ctrl + C`.

## 4. Put it online (free)

**GitHub Pages**

1. Create a GitHub repository, for example `sadik-portfolio`.
2. Rename `scholar-view-dynamic.html` to `index.html`.
3. Upload `index.html` and `sadik_cv.pdf` to the repository.
4. Go to **Settings → Pages**, choose the `main` branch and `/ (root)` folder, then save.
5. Your site will be at `https://<your-username>.github.io/sadik-portfolio/`.

## 5. Edit the content

All text, numbers, links, and lists are stored in one block at the top of the page's script, called `const DATA = { ... }`.

Open the HTML file in any text editor (VS Code, Notepad, TextEdit) and search for `const DATA`. Edit the values inside the quotes. For example:

- **Publications:** each entry in `publications` has `title`, `authors`, `venue`, `year`, `type`, and an optional `link`. Types can be `Journal`, `Conference`, `Preprint`, or `Manuscript`.
- **Awards and certificates:** each entry in `awards` has `title`, `category` (`research`, `content`, or `oral`), `featured`, `issuer`, `year`, and `image`.
- **Roles:** each entry in `roles` has `icon`, `status`, `org`, `title`, `text`, `tags`, and `tone` (`gold`, `cyan`, `orange`, or `blue`).

### Adding a certificate image

Save the image next to the HTML file (for example `certs/research-award.jpg`), then set the entry's `image` value to the path:

```js
image: "certs/research-award.jpg",
```

When running locally, relative paths like this work. (The Claude artifact version needs images embedded as data links instead.)

### Changing your profile photo

The photo is embedded in the file as `photo: "data:image/jpeg;base64,..."`. To use a separate file instead, replace that value with a path such as `"sadik.jpg"` and keep the image beside the HTML file.

## 6. Features

- Mobile menu on small screens
- Publications search and type filter
- Contact form with validation (the form checks input but does not send email; connect it to a form service such as Formspree or Google Forms to receive messages)
- Animated lab stage in the hero: coding, machine learning training, mathematical modelling, molecular docking, MD simulation, and wet lab, shown one after another
- Butterflies, scroll-based colour changes, and blinking section eyes (these switch off automatically for visitors who prefer reduced motion)

## 7. Troubleshooting

| Problem | Fix |
|---|---|
| Page looks unstyled | Check your internet connection; Tailwind CSS loads from the web. |
| "View CV" does nothing | Make sure `sadik_cv.pdf` is in the same folder as the HTML file, with that exact name. |
| Image missing | Check the path in `image:` matches the file name and folder exactly (case-sensitive on Linux and GitHub Pages). |
| Animations feel too fast or too strong | Change `STAGE_MS` (scene length in milliseconds) or the butterfly `FLYERS` settings in the script. |

## 8. Credits

Built with Tailwind CSS (CDN) and Google Fonts (Sora, JetBrains Mono, Cormorant Garamond).
