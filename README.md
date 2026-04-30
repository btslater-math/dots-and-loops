# Dots & Loops

A minimal Jekyll blog with full LaTeX support via MathJax.

## How to deploy

1. **Create a GitHub repository** named `dots-and-loops`.

2. **Upload all the files and folders** from this directory to the repository,
   preserving the folder structure:
   ```
   dots-and-loops/
   ├── _config.yml
   ├── _layouts/
   │   ├── default.html
   │   └── post.html
   ├── _posts/
   │   └── 2026-04-29-welcome.md
   ├── index.html
   └── README.md
   ```

3. **Enable GitHub Pages:**
   - Go to Settings → Pages.
   - Under "Source", select "Deploy from a branch".
   - Choose the `main` branch and `/ (root)` folder.
   - Click Save.

4. Your blog will be live at `https://yourusername.github.io/dots-and-loops/`.

5. **Update `_config.yml`**: replace `yourusername` with your actual GitHub
   username in the `url` and `professional_site` fields.

## How to write a new post

1. Create a new file in `_posts/` with the naming format:
   ```
   YYYY-MM-DD-title-of-your-post.md
   ```

2. Add the front matter at the top:
   ```yaml
   ---
   layout: post
   title: "Your Post Title"
   date: 2026-05-15
   ---
   ```

3. Write your post in Markdown below the front matter.

## Using LaTeX

- **Inline math**: use single dollar signs — `$\pi_1(S^1) \cong \mathbb{Z}$`
- **Display math**: use double dollar signs:
  ```
  $$
  H_n(X, A) \longrightarrow H_{n-1}(A) \longrightarrow H_{n-1}(X)
  $$
  ```
- All standard LaTeX and AMS packages are available through MathJax.

## Editing the design

- **Colors and fonts**: edit the CSS variables in `_layouts/default.html`
  at the top of the `<style>` block.
- **Site title and description**: edit `_config.yml`.
- **Layout structure**: edit the HTML in `_layouts/default.html` and
  `_layouts/post.html`.
