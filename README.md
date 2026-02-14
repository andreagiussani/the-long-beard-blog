# The Long Beard Blog

## Access to the Blog
Visit the following [link](https://andreagiussani.github.io/the-long-beard-blog/)

## How to Locally Set up GitHub Pages
This repo is a GitHub Pages site built with **Jekyll** (via the `github-pages` gem).  
To run it locally on macOS, you need a Ruby version compatible with the GitHub Pages/Jekyll stack.

> ✅ **Important:** Ruby **4.x** currently breaks this stack (Liquid/Jekyll `tainted?` error).  
> Use **Ruby 3.3.x** locally.

---

## Prerequisites

### 1) Xcode Command Line Tools
```bash
xcode-select --install
````

### 2) Homebrew (if not installed)

Install from [https://brew.sh](https://brew.sh)

---

## Install Ruby 3.3 with rbenv

### 1) Install rbenv + ruby-build

```bash
brew install rbenv ruby-build
```

### 2) Enable rbenv in your shell (zsh)

```bash
echo 'eval "$(rbenv init - zsh)"' >> ~/.zshrc
source ~/.zshrc
```

> If you use bash, put this in `~/.bash_profile` instead:
> `eval "$(rbenv init - bash)"`

### 3) Install Ruby 3.3.6 (once)

```bash
rbenv install 3.3.6
```

---

## Configure this repo to use Ruby 3.3.6

From the repo root:

```bash
cd /path/to/the-long-beard-blog
rbenv local 3.3.6
```

This creates/updates `.ruby-version` in the repo.

Verify:

```bash
rbenv version
which ruby
ruby -v
```

Expected:

* `rbenv version` → `3.3.6 (set by .../.ruby-version)`
* `which ruby` → `~/.rbenv/shims/ruby`
* `ruby -v` → `ruby 3.3.6 ...`

---

## Install dependencies

From the repo root:

```bash
rm -rf Gemfile.lock .bundle vendor/bundle
gem install bundler
bundle install
```

---

## Run the site locally

```bash
bundle exec jekyll serve
```

Open:

* [http://127.0.0.1:4000](http://127.0.0.1:4000)

Common useful flags:

```bash
bundle exec jekyll serve --livereload --drafts --future
```

---

## Troubleshooting

### `ruby -v` still shows Ruby 4.x in this repo

Your PATH is still prioritizing Homebrew Ruby. Fix for the current terminal session:

```bash
hash -r
export PATH="$HOME/.rbenv/shims:$HOME/.rbenv/bin:$PATH"
rbenv rehash
ruby -v
```

If this happens often, ensure your shell loads rbenv correctly (see the “Enable rbenv in your shell” step).

### Native gem build fails (e.g., `ffi`)

Install libffi and point Bundler at it:

```bash
brew install libffi
bundle config set --local build.ffi "--with-opt-dir=$(brew --prefix libffi)"
bundle install
```

---

## Notes

* This repo uses `github-pages` to match GitHub Pages behavior.
* Keep Ruby pinned via `.ruby-version` to avoid ecosystem incompatibilities.

```

If you want, I can also add a tiny “Quick start” section at the top (3 commands) and a “Reset everything” section for when gems get messed up.
```

