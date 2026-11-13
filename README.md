# Katia Sommers | Author

This is the Hugo source for Katia Sommers' author website. It uses the Magnolia Hugo theme as a Git submodule and is intended to remain a lightweight, mostly static site.

## Prerequisites

- Hugo Extended **0.150.0** (see `.hugo-version`)
- Git, with submodule support
- Node.js only for the existing Magnolia asset dependency (`npm install`)

The project has been tested on Windows with `C:\Tools\Hugo\0.150.0\hugo.exe` and should also work on macOS with the same Hugo Extended version.

## Clone and run locally

Clone the repository and initialize Magnolia:

```text
git clone --recurse-submodules <repository-url>
cd author-site
npm install
hugo server
```

Open `http://localhost:1313/`. If the repository is already cloned, use `git submodule update --init --recursive`.

## Editing content

- Homepage: `content/en/_index.md`
- Books: `content/en/pages/books/index.md`
- Author bio: `content/en/pages/about/index.md`
- Contact page: `content/en/pages/contact/index.md`
- Blog listing: `content/en/posts/_index.md`
- Blog posts: create a page bundle under `content/en/posts/<post-slug>/index.md`
- Navigation and site-wide text: `config/_default/languages/.en.toml`

Create a post with:

```text
hugo new content/en/posts/my-post/index.md
```

Then set its front matter and change `draft: true` to `draft: false` when it is ready.

## Production build

Run the pinned Hugo Extended executable directly on Windows if it is not on `PATH`:

```text
C:\Tools\Hugo\0.150.0\hugo.exe --minify
```

On macOS or when Hugo is on `PATH`:

```text
hugo --minify
```

The generated site is written to `public/`, which is ignored by Git.

## Deployment intent

The intended workflow is to push this source repository to GitHub and connect it to Cloudflare Pages. Configure Hugo Extended `0.150.0` and the production build command there when deployment is ready. Deployment credentials and provider settings are intentionally not stored in this repository.

## Magnolia notes

Do not edit `themes/Magnolia`. Project-level layouts can override theme layouts when needed. The contact page currently shows a disabled placeholder until a form provider is selected. The homepage newsletter copy is also a placeholder and can later be replaced with a Buttondown, MailerLite, or Kit form.
