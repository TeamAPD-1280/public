# CTF Learning Hub Documentation

This repository contains the source files for the CTF Learning Hub documentation site.

The site is built with **MkDocs** and the **Material for MkDocs** theme. Content is written in Markdown and published as a static website using GitHub Pages.

## Purpose

The CTF Learning Hub provides learning resources for new and developing Capture the Flag participants. It includes guidance on getting started, safe competition practices, lab setup, cybersecurity fundamentals, and CTF challenge categories.

## Key Files and Folders

| Path | Purpose |
|---|---|
| `docs/` | Main documentation content |
| `docs/index.md` | Homepage for the site |
| `docs/assets/` | Images, logos, stylesheets, and other static assets |
| `mkdocs.yml` | MkDocs site configuration and navigation |
| `requirements.txt` | Python dependencies required to build the site |
| `README.md` | Contributor and setup instructions |

## Prerequisites

Before working on the documentation, install:

- Git
- Python 3
- Python virtual environment support
- A text editor such as VS Code

On Ubuntu or WSL:

```bash
sudo apt update
sudo apt install -y git python3 python3-venv python3-pip
```

## Clone the Repository

```bash
git clone https://github.com/TeamAPD-1280/public.git
cd public
```

## Set Up the Python Virtual Environment

Create a local virtual environment:

```bash
python3 -m venv .venv
```

Activate it:

```bash
source .venv/bin/activate
```

Your terminal prompt should show `(.venv)` when the environment is active.

Install the required dependencies:

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

## Run the Site Locally

From the repository root, run:

```bash
mkdocs serve
```

Open the local preview in your browser:

```text
http://127.0.0.1:8000
```

MkDocs will automatically reload the site when you save changes.

To stop the local server, press:

```text
Ctrl + C
```

To leave the virtual environment:

```bash
deactivate
```

## Validate the Site Before Committing

Before committing changes, run:

```bash
mkdocs build --strict
```

This checks that the site can build successfully. Strict mode treats warnings as errors, which helps catch broken navigation links, missing pages, and configuration issues before publishing.

Do not commit changes until the build completes successfully.

## How to Add or Edit Documentation

Most content lives inside the `docs/` folder.

To edit an existing page, open the relevant `.md` file and update the Markdown content.

To add a new page:

1. Create a new Markdown file under the appropriate folder.
2. Use lowercase filenames with hyphens.
3. Add the page to `mkdocs.yml` if it should appear in the navigation.
4. Run `mkdocs build --strict` to confirm the site builds.

Example filename:

```text
secure-design-principles.md
```

Avoid spaces in filenames:

```text
Secure Design Principles.md
```

## Linking Between Pages

Use relative links when linking to other documentation pages.

Example:

```markdown
[Ethics and Rules](../getting-started/ethics-and-rules.md)
```

For pages in the same folder:

```markdown
[Networking](networking.md)
```

## Updating Site Navigation

The site navigation is controlled by `mkdocs.yml`.

Example:

```yaml
nav:
  - Home: index.md

  - Getting Started:
      - What is a CTF?: getting-started/what-is-a-ctf.md
      - Ethics and Rules: getting-started/ethics-and-rules.md
      - Lab Setup: getting-started/lab-setup.md
```

If a page is not listed in `mkdocs.yml`, it may still build, but it may not appear in the left navigation menu.

After changing navigation, always run:

```bash
mkdocs build --strict
```

## Contribution Workflow

Use the following workflow when contributing changes.

### 1. Update your local copy

```bash
git pull
```

### 2. Create a new branch

```bash
git switch -c update-documentation
```

Use a short, descriptive branch name, such as:

```text
add-osint-resources
update-lab-setup
fix-navigation
```

### 3. Make your changes

Edit or add the required Markdown files.

### 4. Preview locally

```bash
source .venv/bin/activate
mkdocs serve
```

Review the site at:

```text
http://127.0.0.1:8000
```

### 5. Validate the build

```bash
mkdocs build --strict
```

Fix any warnings or errors before continuing.

### 6. Check changed files

```bash
git status
git diff --stat
```

### 7. Commit your changes

```bash
git add .
git commit -m "Update documentation"
```

Use a clear commit message. Examples:

```bash
git commit -m "Add OSINT learning resources"
git commit -m "Update lab setup instructions"
git commit -m "Fix MkDocs navigation"
```

### 8. Push your branch

```bash
git push -u origin update-documentation
```

### 9. Open a pull request

Open a pull request on GitHub and include:

- A summary of the changes
- Any pages added or removed
- Any navigation changes
- Any known issues or follow-up work

A maintainer should review the pull request before it is merged.


