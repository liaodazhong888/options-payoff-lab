# Upload to GitHub and Publish the Page

Chinese version: [github-pages.zh-CN.md](github-pages.zh-CN.md).

This project is a static web page; `index.html` is the site entry point. Once published with GitHub Pages, readers can use the page directly in a browser.

## Step 1: Unzip and check

Unzip the release package, open the `options-payoff-lab` folder, and double-click `index.html` to confirm it opens and the slider works.

Upload the contents of this folder. **Do not upload only the ZIP file, and do not nest the whole project inside a subfolder of the repository.** The repository home page should show `index.html` and `README.md` directly.

## Step 2: Create a public repository

Sign in to GitHub and choose New repository.

- Repository name: `options-payoff-lab`.
- Description (example): `Interactive options payoff lab for beginners: drag the price, compare four strategies with and without holding the stock.`
- Choose Public so everyone can view the source and use the page.
- The package already contains a README and a LICENSE, so there is no need to auto-generate the same files.

After creating the repository, use the "upload an existing file" entry; for an existing repository, choose Add file → Upload files. Drag the project files and the `docs` folder into the upload area, keep the directory structure, and commit.

If the file picker does not show dotfiles such as `.nojekyll`, show hidden files first, or upload the full directory with GitHub Desktop. They are not secrets.

## Step 3: Turn on GitHub Pages

1. Open the repository's Settings.
2. In the sidebar, choose Pages.
3. Under Build and deployment, set Source to Deploy from a branch.
4. Set Branch to `main` and the directory to `/ (root)`, then save. If the default branch is not `main`, pick the branch that contains `index.html`.
5. Wait for deployment to finish, then go back to the Pages settings page and open the site with Visit site.

The project site address is usually `https://<your-username>.github.io/<repository-name>/`; the Pages settings page shows the actual address. This format is an example; the package contains no pre-filled account or repository address.

Public repositories can use GitHub Pages on GitHub Free. According to GitHub's official docs, page updates after a commit can take up to about 10 minutes.

## Step 4: Share and update

Put the published page link in the repository's About → Website field, so others can open it from the repository.

Later, edit `index.html` and commit to the publishing branch; GitHub Pages will redeploy. When you update the screenshot, replace `docs/preview.png` at the same time.

## If the page does not open

- 404: confirm that the publishing branch's root directory contains `index.html` directly, and that deployment has finished.
- You only see source code: open the published site address from Pages; GitHub's file browsing page is for viewing source.
- Still showing the old version: confirm the new commit has been deployed, then refresh the browser or reopen the page.
- On a phone the layout stacks vertically instead of side by side: that is the narrow-screen layout; a wider window shows the two-column layout.

## Official documentation

- [Adding a file to a repository](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository)
- [Creating a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
- [Configuring a publishing source for your GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
