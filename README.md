# hvanz.github.io

Personal website of Hernán Vanzetto: https://hvanz.github.io/

The site uses Jekyll. GitHub Pages builds and publishes it each time you push to the default branch.

## Files

- `_config.yml`: site title and headline.
- `_layouts/default.html`: the page layout and CSS (including dark mode).
- `_data/projects.yml`: the project list, newest first.
- `index.md`: the home page. It uses the default layout.

## Add a project

Add an entry to `_data/projects.yml`:

```yaml
- title: Project name
  description: |
    - First point. Markdown is allowed.
  links:
    - name: GitHub
      url: https://github.com/...
```

## Build and see the site locally

### One-time setup (macOS)

The system Ruby is too old for Jekyll. Install a newer Ruby with Homebrew, then install Jekyll:

```bash
brew install ruby
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.bash_profile
source ~/.bash_profile
gem install --user-install jekyll
echo 'export PATH="$(gem env user_gemhome)/bin:$PATH"' >> ~/.bash_profile
source ~/.bash_profile
```

### Start the local server

```bash
jekyll serve
```

Open http://localhost:4000. When you change a file, Jekyll builds the site again; reload the page to see the change. To see changes to `_config.yml`, stop the server and start it again.

If `jekyll serve` stops with an error about `webrick`, run `gem install --user-install webrick` and try again.

Jekyll writes the built site to `_site/`. Git ignores this folder.
