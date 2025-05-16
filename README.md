# Astro blog tutorial

## Created with Astro Starter Kit: Minimal

```sh
npm create astro@latest -- --template minimal
```
## GitHub Pages
*Project settings*
- Modify defineConfig in file astro.config.mjs 
- Change site: "https://yourgithubaccount.github.io"
- Add base: "yourrepositoryname"
- More info: [configuration-reference](https://docs.astro.build/en/reference/configuration-reference/)

*Updating links*
- Website is most likely beign deployed to subfolder (repository name) on github.io server
- Because of that links have to be prefixed with repository name set via config
```
// Navigation.astro
---
import { base } from "astro:config/client";
---
<a href=`${base}/about/`>About</a>

```

```
// MarkdownPostLayout.astro
---
import { base } from "astro:config/client";
---
<p class="tag"><a href={`${base}/tags/${tag}`}>{tag}</a></p>

```
```
// index.astro
---
import { base } from "astro:config/client";
<p class="tag"><a href={`${base}/tags/${tag}`}>{tag}</a></p>
```

*GitHub settings*
- Check that repository is public (so that GitHub Pages is enabled for free account)
- Check that build source is GitHub Actions
  - Reposotory settings -> Pages -> Build and deployment -> Source -> GitHub Actions
- Follow tutorial to create workflow [actions/astro-deploy](https://github.com/marketplace/actions/astro-deploy)
- Workflow will render website when Main branch changes

## Testing
*Unit and integration tests: Vitest*  
  - npm run test
  
*End-to-end tests: Playwright*  
  - npx playwright test
  - npx playwright show-report

## Project Structure
Inside of your Astro project, you'll see the following folders and files:

```text
/
├── public/
├── src/
│   └── pages/
│       └── index.astro
└── package.json
```

Astro looks for `.astro` or `.md` files in the `src/pages/` directory. Each page is exposed as a route based on its file name.

There's nothing special about `src/components/`, but that's where we like to put any Astro/React/Vue/Svelte/Preact components.

Any static assets, like images, can be placed in the `public/` directory.

## Commands

All commands are run from the root of the project, from a terminal:

| Command                   | Action                                           |
| :------------------------ | :----------------------------------------------- |
| `npm install`             | Installs dependencies                            |
| `npm run dev`             | Starts local dev server at `localhost:4321`      |
| `npm run build`           | Build your production site to `./dist/`          |
| `npm run preview`         | Preview your build locally, before deploying     |
| `npm run astro ...`       | Run CLI commands like `astro add`, `astro check` |
| `npm run astro -- --help` | Get help using the Astro CLI                     |

## Want to learn more?

Feel free to check [our documentation](https://docs.astro.build) or jump into our [Discord server](https://astro.build/chat).
