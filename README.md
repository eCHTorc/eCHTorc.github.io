# eCHT — editable static website

This is a plain HTML and CSS version of https://echtorc.github.io, converted on November 11, 2026. No Jekyll, Ruby, npm, templates, or build command is required. All 51 source content pages, their text, 65 legacy URLs, and the original files and images are retained. Dates and event information are preserved as written in the source.

## Preview on your computer

Open Terminal and run:

```sh
cd ~/Desktop/echtorc-static
ipython -m http.server 8000
```

Visit http://localhost:8000/ in your browser. Leave Terminal running. After editing and saving a file, refresh the browser. If a CSS change does not appear, do a hard refresh (Command-Shift-R). Stop the server with Control-C.

If IPython is unavailable, `python3 -m http.server 8000` works too. Start the server in this folder, where `index.html` is located. Links beginning with `/` refer to this server's root; opening the HTML files directly with `file://` is not the intended preview method.

## Edit content

Open the HTML file in any text editor. Find the comment `EDIT PAGE CONTENT BELOW` and edit the HTML inside `<main id="content">`. Save and refresh; there is no generation step.

| What to change | File |
| --- | --- |
| Home page and current activities | `index.html` |
| Research talks and abstracts | `research-seminar/index.html` |
| Reading seminar list | `reading-seminars/index.html` |
| Course list | `courses/index.html` |
| Minicourses | `minicourses/index.html` |
| About us | `who-we-are/index.html` |
| Code of conduct | `code-of-conduct/index.html` |
| Dormant activities | `dormant-activities/index.html` |
| Fonts, colors, spacing, responsive layout | `styles.css` |
| PDFs and other downloadable materials | `files/` |
| Logos and icons | `images/` |

Individual course and seminar pages have their own folders. A complete file list appears below. The content is directly in each HTML file, including all research talk schedules; there are no separate data files to rebuild.

To add a talk, copy an existing talk's table and accompanying abstract within `research-seminar/index.html`, then edit the copied text and links. To add a page, copy an existing content folder, update its title and main content, and link to it from the relevant list page.

Navigation and footer markup are repeated in each page so the site needs no JavaScript or HTML includes for its content. To change the global navigation or footer, use your editor's Find and Replace across the HTML files. Files containing only “Page moved” preserve old URLs; edit the destination page instead.

## Put it on GitHub Pages

Back up your existing repository first. Replace the old website source with the contents of this folder, including the hidden `.nojekyll` file. Do not put the whole folder inside the repository; `index.html` should be at the repository root.

Remove the old Jekyll files and directories (such as `_config.yml`, `_pages`, `_layouts`, `_includes`, `_sass`, `_site`, `.sass-cache`, `Gemfile`, and `Gemfile.lock`). Keep repository administration files you still need. If you have a custom GitHub Actions workflow that explicitly builds Jekyll, disable it or replace it with a static Pages deployment. In the simplest setup, select “Deploy from a branch” under Settings → Pages and choose your branch and its root folder. `.nojekyll` tells Pages to serve these files directly.

This conversion has not changed or published anything to GitHub.

## Conversion and checks

The layout uses a shared stylesheet, a responsive sidebar, and plain HTML pages. No framework, remote font, or script is needed for normal page content or navigation. Small scripts on legacy redirect pages preserve query strings and URL fragments; those pages also have an HTML refresh and a clickable fallback link.

The text of every converted content page was compared with its source. All copied downloads and images were checked for byte-for-byte equality. All local HTML links and asset references resolve. Three archived PDF links were corrected to existing `.pdf` filenames, and one archived Zoom link was given its missing `https://` prefix. External resources (such as YouTube, Zoom, mailing lists, and linked third-party notes) still need internet access and were not exhaustively checked.

## All content files

| Page | Editable file |
| --- | --- |
| eCHT (/) | `index.html` |
| eCHT Course on homology and cohomology (/course-on-algebraic-topology-homology-and-cohomology-winter-23/) | `course-on-algebraic-topology-homology-and-cohomology-winter-23/index.html` |
| eCHT Course on stable homotopy theory (/course-on-algebraic-topology-homotopy-theory-winter-24/) | `course-on-algebraic-topology-homotopy-theory-winter-24/index.html` |
| eCHT Course on duality and spectra (/course-on-duality-and-spectra-fall-24/) | `course-on-duality-and-spectra-fall-24/index.html` |
| eCHT Course on stable homotopy theory (/course-on-stable-homotopy-theory-winter-24/) | `course-on-stable-homotopy-theory-winter-24/index.html` |
| eCHT Course on stable homotopy theory (/course-on-stable-homotopy-theory-winter-25/) | `course-on-stable-homotopy-theory-winter-25/index.html` |
| eCHT Course on stable homotopy theory (/course-on-stable-homotopy-theory-winter-26/) | `course-on-stable-homotopy-theory-winter-26/index.html` |
| eCHT Course on stable homotopy theory (/course-on-stable-homotopy-theory/) | `course-on-stable-homotopy-theory/index.html` |
| eCHT Course on stable homotopy theory (/course-on-topological-k-theory-winter-23/) | `course-on-topological-k-theory-winter-23/index.html` |
| Professional Development (/professional-development/) | `professional-development/index.html` |
| Research Experience for Undergraduates Summer 2023 (/reu-summer-23/) | `reu-summer-23/index.html` |
| Research Experience for Undergraduates Summer 2024 (/reu-summer-24/) | `reu-summer-24/index.html` |
| eCHT Research Seminar Reading Group (/research-seminar-reading-group/) | `research-seminar-reading-group/index.html` |
| Seminar on Machine Computation (/seminar-machine-computation/) | `seminar-machine-computation/index.html` |
| Employment Network Fall 2020 (/network-fall-20/) | `network-fall-20/index.html` |
| Employment Network Fall 2022 (/network-fall-22/) | `network-fall-22/index.html` |
| Code of Conduct (/code-of-conduct/) | `code-of-conduct/index.html` |
| eCHT Courses (/courses/) | `courses/index.html` |
| Dormant Activities (/dormant-activities/) | `dormant-activities/index.html` |
| eCHT Minicourses (/minicourses/) | `minicourses/index.html` |
| eCHT Reading Seminars (/reading-seminars/) | `reading-seminars/index.html` |
| Funding Reports (/reports/) | `reports/index.html` |
| eCHT Research Seminar (/research-seminar/) | `research-seminar/index.html` |
| Research Workshops (/research-workshops/) | `research-workshops/index.html` |
| eCHT Kan Seminar (/kan-seminar-fall-19/) | `kan-seminar-fall-19/index.html` |
| eCHT Kan Seminar (/kan-seminar-fall-20/) | `kan-seminar-fall-20/index.html` |
| eCHT Kan Seminar (/kan-seminar-fall-22/) | `kan-seminar-fall-22/index.html` |
| eCHT Kan Seminar (/kan-seminar-fall-23/) | `kan-seminar-fall-23/index.html` |
| eCHT Kan Seminar (/kan-seminar-fall-24/) | `kan-seminar-fall-24/index.html` |
| eCHT Kan Seminar (/kan-seminar-fall-25/) | `kan-seminar-fall-25/index.html` |
| eCHT Kan Seminar (/kan-seminar-winter-22/) | `kan-seminar-winter-22/index.html` |
| eCHT Kan Seminar (/kan-seminar-winter-25/) | `kan-seminar-winter-25/index.html` |
| eCHT Reading Seminar on the Adams Spectral Sequence for Topological Modular Forms (/reading-seminar-on-adams-spectral-sequence-for-topological-modular-forms-winter-23/) | `reading-seminar-on-adams-spectral-sequence-for-topological-modular-forms-winter-23/index.html` |
| eCHT Reading Seminar on Algebraic K-theory (/reading-seminar-on-algebraic-k-theory-fall-20/) | `reading-seminar-on-algebraic-k-theory-fall-20/index.html` |
| eCHT Reading Seminar on Algebraic Vector Bundles (/reading-seminar-on-algebraic-vector-bundles-fall-23/) | `reading-seminar-on-algebraic-vector-bundles-fall-23/index.html` |
| eCHT Reading Seminar on Commutative Ring Spectra (/reading-seminar-on-commutative-ring-spectra-winter-21/) | `reading-seminar-on-commutative-ring-spectra-winter-21/index.html` |
| eCHT Reading Seminar on Equivariant Algebra (/reading-seminar-on-equivariant-algebra-winter-21/) | `reading-seminar-on-equivariant-algebra-winter-21/index.html` |
| eCHT Reading Seminar on Equivariant Homotopy Theory (/reading-seminar-on-equivariant-homotopy-theory-fall-21/) | `reading-seminar-on-equivariant-homotopy-theory-fall-21/index.html` |
| eCHT Reading Seminar on the Adams Spectral Sequence for Topological Modular Forms (/reading-seminar-on-floer-homotopy-theory-winter-22/) | `reading-seminar-on-floer-homotopy-theory-winter-22/index.html` |
| eCHT Reading Seminar on Equivariant Homotopy Theory (/reading-seminar-on-foundations-of-hermitian-k-theory-fall-21/) | `reading-seminar-on-foundations-of-hermitian-k-theory-fall-21/index.html` |
| eCHT Reading Seminar on Group Actions on Exotic Spheres (/reading-seminar-on-group-actions-on-exotic-spheres-winter-26/) | `reading-seminar-on-group-actions-on-exotic-spheres-winter-26/index.html` |
| eCHT Reading Seminar on Homotopical Combinatorics (/reading-seminar-on-homotopical-combinatorics-winter-25/) | `reading-seminar-on-homotopical-combinatorics-winter-25/index.html` |
| eCHT Reading Seminar on Hopf Rings (/reading-seminar-on-hopf-rings-winter-24/) | `reading-seminar-on-hopf-rings-winter-24/index.html` |
| eCHT Reading Seminar on Kervaire Invariant One (/reading-seminar-on-kervaire-invariant-one-fall-20/) | `reading-seminar-on-kervaire-invariant-one-fall-20/index.html` |
| eCHT Reading Seminar on the Adams Spectral Sequence for Topological Modular Forms (/reading-seminar-on-mahowald-invariant-fall-22/) | `reading-seminar-on-mahowald-invariant-fall-22/index.html` |
| eCHT Reading Seminar on Motives (/reading-seminar-on-motives-spring-20/) | `reading-seminar-on-motives-spring-20/index.html` |
| eCHT Reading Seminar on Quadratic Curve Counting (/reading-seminar-on-quadratic-curve-counting-fall-24/) | `reading-seminar-on-quadratic-curve-counting-fall-24/index.html` |
| eCHT Reading Seminar on Group Actions on Exotic Spheres (/reading-seminar-on-secondary-steenrod-algebra-fall-25/) | `reading-seminar-on-secondary-steenrod-algebra-fall-25/index.html` |
| eCHT Reading Seminar on Synthetic Spectra (/reading-seminar-on-synthetic-spectra-winter-22/) | `reading-seminar-on-synthetic-spectra-winter-22/index.html` |
| eCHT Reading Seminar on Topological Hochschild Homology (/reading-seminar-on-topological-hochschild-homology-spring-20/) | `reading-seminar-on-topological-hochschild-homology-spring-20/index.html` |
| About eCHT (/who-we-are/) | `who-we-are/index.html` |
