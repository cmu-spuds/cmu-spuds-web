# CMU SPUD Lab Website

This is the website for the Security, Privacy, Usability and Design (SPUD) Lab at Carnegie Mellon University.

Built with [al-folio](https://github.com/alshedivat/al-folio), a Jekyll theme for academics.

## Quick Links

- **Publications**: Automatically fetched from `https://sauvik.me/papers.json` (configured in `_config.yml` → `jekyll_get_json`)
- **News**: Automatically fetched from Google Sheets (configured in `_config.yml` → `google_sheets_news`)
- **Configuration**: See `_config.yml` for all site settings
- **Customization**: See [CUSTOMIZE.md](CUSTOMIZE.md) for detailed customization guide
- **Installation**: See [INSTALL.md](INSTALL.md) for setup instructions

## Updating Content

### Publications

Publications are automatically pulled from `https://sauvik.me/papers.json` during the build process. No local files need to be updated.

**Configuration**: See `_config.yml` → `jekyll_get_json` section.

### News

News items are managed via Google Sheets: [SPUD Lab News Sheet](https://docs.google.com/spreadsheets/d/1hjbkuxD2R-mZU4PkBJfvcV3QtldjzmIlqV8rP4M1CTY/edit?usp=sharing)

**To update news**: SPUD lab members can edit the Google Sheet after logging in through `spudlab@andrew.cmu.edu`. The sheet should have columns: `date`, `title`, `content`, `inline`, `url`.

**Manual News**: You can also create news items manually by adding `.md` files to the `_news` directory.

### Other Content

- **People**: Edit `_data/people.yml`
- **Projects**: Add files to `_projects/` directory
- **Pages**: Edit files in `_pages/` directory
- **Site Settings**: Edit `_config.yml`

## Development

### Local Setup

```bash
bundle install
bundle exec jekyll serve
```

### Building

```bash
bundle exec jekyll build
```

The site will be generated in the `_site` directory.

### Clear Cache and Rebuild

If you encounter build issues or need to force a fresh build with updated external data:

```bash
# Clear Jekyll cache
rm -rf .jekyll-cache

# Clear built site
rm -rf _site

# Rebuild
bundle exec jekyll build
```

Or to serve locally with a clean build:

```bash
rm -rf .jekyll-cache _site && bundle exec jekyll serve
```

## Deployment

The site is automatically built and deployed to GitHub Pages via GitHub Actions.

**Automatic builds happen when:**

- Code is pushed to `main` or `master` branch
- Every 6 hours (to pick up changes from Google Sheets and publications.json)
- Manually triggered from the Actions tab

**Deployment process:**

1. GitHub Actions builds the site (fetches external data from Google Sheets and `sauvik.me/papers.json`)
2. Deploys the built site to the `gh-pages` branch
3. GitHub Pages serves the site from `gh-pages` branch

**Configuration**: See `.github/workflows/deploy.yml` for the deployment workflow.

## Documentation

- [INSTALL.md](INSTALL.md) - Installation and setup instructions
- [CUSTOMIZE.md](CUSTOMIZE.md) - Customization guide
- [FAQ.md](FAQ.md) - Frequently asked questions
- [CONTRIBUTING.md](CONTRIBUTING.md) - Contribution guidelines

## License

The theme is available as open source under the terms of the [MIT License](LICENSE).

Originally based on [al-folio](https://github.com/alshedivat/al-folio) theme.
