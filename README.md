# Cystic Fibrosis Microbiome Analysis Core website

Public site: https://wagnerbd.github.io/Microbiome-NRC/

This is a static **Jekyll / GitHub Pages** site. No database or local build is needed to add resources.

## First-time installation

1. Back up the existing GitHub repository (or work on a new branch).
2. Copy the files and folders from this package into the **root** of `wagnerbd/Microbiome-NRC`, replacing the old versions. Keep the `assets/` PDFs.
3. Delete the obsolete root-level `_default.html`, `navigation.yml`, `index.md`, and `resources.md` if still present. They are replaced by `_layouts/default.html`, `index.html`, and `resources.html`.
4. In GitHub, open **Settings → Pages** and confirm **Deploy from a branch**, branch **main**, folder **/(root)** (unless the repository already uses a different deployment workflow).
5. Wait for deployment, then check the homepage, resource filters, PDFs, mobile layout, and footer at https://wagnerbd.github.io/Microbiome-NRC/.

## Add a PDF (SOP, white paper, or publication)

1. Upload the PDF to `assets/docs/` using **Add file → Upload files** in GitHub. Prefer simple filenames without spaces, e.g. `sop-sputum-processing-v1.pdf`.
2. Edit `_data/resources.yml` in GitHub (pencil icon). Add an entry at the top or bottom:

```yaml
- title: "Sputum processing standard operating procedure"
  type: SOP
  year: 2026
  description: "Sample processing steps for microbiome analysis. Version 1.0."
  file: /assets/docs/sop-sputum-processing-v1.pdf
```

3. Commit your changes (prefer a new branch and pull request). The resource card appears automatically after GitHub Pages deploys. Use exactly one of `file` or `url` per resource.
4. For a white paper, use `type: White paper`; for a publication, `type: Publication`; for a code or dataset repository, use `type: Code & data` and `url: https://...`.
5. Do not list an SOP or white paper until its actual file is uploaded and approved for public release.

## Add a publication link instead of uploading a PDF

```yaml
- title: "Example publication title"
  type: Publication
  year: 2026
  description: "Optional one-sentence summary."
  url: https://doi.org/10.xxxx/example
```

Prefer a DOI/publisher link when publisher copyright terms do not permit hosting the PDF. Check rights for the PDFs already included in this repository.

## Add public code or data

Link to a dedicated GitHub repository, Zenodo, or an appropriate public data repository using `type: Code & data` and `url:`. Include a README, license, citation instructions, software requirements, data dictionary, and version/release information. Confirm all shared datasets are appropriately de-identified and approved for public distribution.

## Change site text, colors, and navigation

- Homepage: `index.html`
- About/contact: `about.html`
- Resource catalog: `_data/resources.yml`
- Shared header/footer: `_layouts/default.html` (**one footer only**)
- Colors, fonts, layout: `assets/css/style.css`
- Search/filter logic: `assets/js/library.js`
- Site title and GitHub Pages base path: `_config.yml`

## Invite a student to contribute

1. On GitHub, open the repository → **Settings → Collaborators and teams** (or **Collaborators**) → **Add people**.
2. Invite the student's GitHub username and have them accept the invitation. If available, give **Write** access; on personal repositories, collaborator permissions may be less granular.
3. Ask them to create a **branch** for each change and open a **pull request** rather than editing `main` directly.
4. Review changed files and test the deployed site before merging. You can optionally enable branch protection/rulesets for `main` under **Settings → Rules → Rulesets** to require pull request review; availability and enforcement depend on repository visibility and GitHub plan.
5. Never share your GitHub password or personal access token.

## Notes

- Search/filter runs in the visitor's browser and does not require a backend.
- The current catalog includes the 12 PDFs actually present in the supplied archive. Missing SOP and white-paper placeholder links have intentionally been omitted.
- `_config.yml` assumes repository name `Microbiome-NRC` and owner `wagnerbd`. Update `url` and `baseurl` if these change.
- Existing filenames are preserved to avoid disrupting uploaded files. New PDFs should use clean filenames.
