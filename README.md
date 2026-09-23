# DHZhang123.github.io

Source for my personal data science blog, built with [Quarto](https://quarto.org/). Includes two computational posts (one R, one Python) with pinned, reproducible environments.

## Install first

- [Quarto](https://quarto.org/docs/get-started/) 1.10.18+
- [uv](https://docs.astral.sh/uv/getting-started/installation/) 0.12.7+ (Python environment)
- [R](https://cran.r-project.org/) 4.6.1+ (`renv` bootstraps itself, no separate install needed)

## Build instructions

```bash
git clone git@github.com:DHZhang123/DHZhang123.github.io.git
cd DHZhang123.github.io

# Restore Python environment
uv sync

# Restore R environment — run inside R, from this folder
# renv::restore()

# Render the site
uv run quarto render
```

`uv run quarto render` also renders the R chunks correctly: starting it from the top level starts R there too, which reads `.Rprofile` and activates `renv` automatically.

## Viewing the site

Built site lands in `docs/`. Open `docs/index.html` locally, or view it live at **https://dhzhang123.github.io**.

## Data

Both posts use the **Palmer Penguins** dataset (Gorman, Williams, Fraser, 2014; Palmer Station Antarctica LTER; CC0), loaded via the `palmerpenguins` package in each language. Since the data ships with the package, no network access is needed at render time — only during initial `uv sync` / `renv::restore()`.