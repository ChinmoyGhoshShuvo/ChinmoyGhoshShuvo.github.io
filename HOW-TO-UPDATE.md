# How to update your website

Your website is just a few files:

| File | What it is |
|---|---|
| `index.html` | All the words on the page, and which images go where |
| `style.css` | The look (colours, fonts, layout). You rarely need to touch this. |
| `Chinmoy_Ghosh_CV.pdf` | The CV people download |
| `images/` | The pictures and the two short videos |
| `.nojekyll` | An empty file that tells GitHub to show the files as they are. Leave it alone. |

You never need to install anything. You can edit everything in GitHub's website, in your browser.

**A few rules that keep things working**

- Change only the words between the tags. A tag is anything inside `< >`.
- Keep quotes `" "` in pairs, and don't delete a `>` or a `</...>`.
- Lines between `<!--` and `-->` are **comments**: notes that visitors never see. The templates are inside comments.
- After each change, wait 1–5 minutes and refresh **https://ChinmoyGhoshShuvo.github.io**. If you still see the old version, press **Ctrl + F5**.
- If something breaks, GitHub keeps every old version. See "Undo a mistake" at the end.

---

## How to edit a file on GitHub (you'll use this in every section below)

1. Go to **https://github.com/ChinmoyGhoshShuvo/ChinmoyGhoshShuvo.github.io**.
2. Click the file name, for example **index.html**.
3. Click the **pencil icon** (✏️, "Edit this file") at the top right of the file.
4. Make your change. To find a spot quickly, click inside the text and press **Ctrl + F**, then type a word to search for, e.g. `KEY NUMBERS`.
5. Click the green **Commit changes…** button (top right). A small window opens.
6. Write a short message, e.g. `Turn on ML research entry`, and click **Commit changes** again.

## How to upload files on GitHub (for photos, new images, a new CV)

1. Go to **https://github.com/ChinmoyGhoshShuvo/ChinmoyGhoshShuvo.github.io**.
2. To put a file inside the `images` folder, first click the **images** folder to open it.
3. Click **Add file** (top right) → **Upload files**.
4. Drag the file from File Explorer into the box, or click **choose your files**.
5. Scroll down, write a short message (e.g. `Add photo`) and click the green **Commit changes** button.

If a file with the same name already exists, uploading replaces it.

---

## 1. Add a job, a certificate or change the key numbers

The page now has two extra sections and a row of numbers. Each has a ready-made template written in a comment just above it in **index.html**.

- **A new job:** search for `TEMPLATE: copy one <li class="tl__item">`. Copy one job block (from `<li class="tl__item` to its `</li>`), paste it at the top of the list and change the words. Keep `tl__item--now` only on jobs you still hold; it makes the dot pulse.
- **A new certificate:** scan it in landscape, resize it to about 1600 px wide and under 300 KB, give it a simple name starting with `cert-` (for example `cert-green-voice.jpg`) and upload it into **images**. Then search for `TEMPLATE: copy one <article class="cert">`, copy one certificate block, paste it after the last one, and change the file name (it appears twice), the `width`/`height`, the `alt` description and the words.
- **The key numbers** (17 projects, 3 ongoing research projects, 2+ years, IELTS 7.5): search for `KEY NUMBERS`. Change the number in `data-count="…"` **and** the number between the tags, so both match. When you add a project, add 1 to the projects number.

The moving parts (fade-ins, the map-frame sweep, the counting numbers, the timeline line and the progress bar) work on their own. You don't need to touch the script at the bottom of the page.

## 2. Change your photo

Your photo is `images/photo.jpg`: a 4:5 portrait crop, 760 × 950 px. It shows to the right of your name on a laptop, and above your name on a phone.

To replace it:
1. Crop the new photo to a portrait shape (4:5, e.g. 760 × 950 px) with your face in the upper third. In Windows **Photos**, use **Edit → Crop**, choose the **4:5** ratio, then **… → Resize image**.
2. Keep it **under 200 KB** and name it exactly **`photo.jpg`** (all lowercase).
3. Upload it into the **images** folder. It replaces the old one (see "How to upload files").
4. If the new photo isn't 760 × 950 px, open **index.html**, search for `photo.jpg`, and change `width="760" height="950"` to the new size. Right-click the file in File Explorer → **Properties → Details** shows it.

## 3. Add a new academic project card

The Khulna ecosystem services (P-08), Khulna carbon footprint (P-09) and Economic Zones (P-10) cards are already on the page. Economic Zones is a text-only card for now; to give it a picture or a report link, follow the steps below.

For a new project:

**a) Prepare the image**
- Use the project's main image (listed in its `card_v2.md` under "Main image").
- Make a copy. Don't change the original in your project folder.
- Name it after the repository, e.g. `khulna-carbon-footprint-mapping.jpg`.
- Keep it **under about 300 KB** and at least **1200 px** on the long side. In Windows **Photos → … → Resize image**, choose a custom size of about 1600 px wide and a quality of about 80%.
- Upload it into the **images** folder.

**b) Paste the card**
1. Open **index.html** for editing and search for `TEMPLATE: to add an academic project`.
2. The template sits right under that line, between `<article class="entry entry--wide">` and `</article>`. Select and copy those lines, starting at `<article` and ending at `</article>`.
3. Search for `END OF ACADEMIC PROJECTS` and paste your copy on a new line **just above** it.
4. Change the parts written in capitals or as placeholders:
   - `REPO-NAME` → the repository name (it appears twice in the image line and once in the button line);
   - `width="1600" height="900"` → your image's real size;
   - `alt="…"` → one sentence describing the image, for people who can't see it;
   - `P-08` → the next number (P-11, P-12, …);
   - `Studio project` → the label you want, e.g. `Studio project (URP 4142)`;
   - `Project title` → the title from `card_v2.md`;
   - `Summary from card_v2.md.` → the summary from `card_v2.md`;
   - `Group · Tool one · Tool two` → group or individual, then 2–4 tools.
   - the button says `View details`. Change it to `View details &amp; code` **only** if the repository contains the project's own analysis code (for example a `code/` folder). A script that only redraws the README charts does not count.
5. Commit the change.

**Layout variety:** `class="entry entry--wide"` puts the image on the left, and `class="entry entry--wide entry--flip"` puts it on the right. Alternate between them. For a tall map, use `class="entry entry--side"`.

**If the project has a PDF report instead of a repository** (e.g. Economic Zones):
- upload the PDF to the top level of the website repository (not inside `images`), with a simple name such as `economic-zones-report.pdf`;
- in the button line, use `href="economic-zones-report.pdf"` and change the button text to `View report (PDF)`.
- Keep the PDF small if you can (ideally under 10 MB); GitHub refuses single files over 25 MB when uploaded in the browser.

## 4. Replace the CV

1. Name your new CV file exactly **`Chinmoy_Ghosh_CV.pdf`**.
2. Upload it to the **top level** of the repository (not inside `images`). GitHub replaces the old one.
3. Commit. The "Download CV" buttons don't need any change.

Note: your CV contains your phone number and home address. The website page itself never shows them, but anyone who downloads `Chinmoy_Ghosh_CV.pdf` can see them. If you'd prefer not to share those publicly, upload a version without them.

## 5. Upload changes you made on your computer

If you edited files in `E:\Everything\website-raw\` on your computer instead of on GitHub:

1. Go to **https://github.com/ChinmoyGhoshShuvo/ChinmoyGhoshShuvo.github.io**.
2. Click **Add file → Upload files**.
3. Drag in the changed files (e.g. `index.html`). For images, open the `images` folder on GitHub first, then upload there.
4. Write a short message and click **Commit changes**.
5. Wait 1–5 minutes, then refresh the website.

To check the progress, click the **Actions** tab in the repository. A green tick means the site has been updated. A red cross means something went wrong; click it to see why, or ask for help.

---

## Undo a mistake

1. In the repository, click the file (e.g. `index.html`), then **History** (clock icon, top right).
2. Click the version from before your mistake, then the **…** menu → **View file**, and copy all the text (click the copy icon).
3. Open the current file for editing, select everything (**Ctrl + A**), paste (**Ctrl + V**), and commit.

## Preview on your computer before uploading

Open File Explorer → `E:\Everything\website-raw` → double-click `index.html`. It opens in your browser just as it will look online.
