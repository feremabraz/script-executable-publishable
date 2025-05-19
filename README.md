# script-executable-publishable

Template that you can use to create an executable script, ready to be published in NPM. It does not use any bundler.

If you are wondering whether or not you need a bundler for your purposes, you can read [this answer](https://stackoverflow.com/questions/67245509/why-do-we-still-need-module-bundlers-when-we-have-native-esm-support-in-browsers) on stackoverflow and maybe [this blog article](https://cmdcolin.github.io/posts/2022-05-27-youmaynotneedabundler).

![script-executable-publishable](assets/script-executable-publishable.png)

## <u>How to use</u>

The procedure is straightforward:

1. [Use this project as a template](https://github.com/gamekaiju/script-executable-publishable/generate).
2. Replace all occurrences of 'script-executable-publishable' in `package.json` with your project name. Update the description, author, and license fields as needed.
3. **Authentication & Registry:**
   - If you intend to publish to the **public npm registry** (npmjs.com), simply run:
     ```sh
     pnpm login
     ```
     You do **not** need a `.npmrc` file or a GitHub token for public npm.
   - If you intend to publish to **GitHub Packages** (npm.pkg.github.com), you need a `.npmrc` file with an auth token. You can use the provided `.npmrc.example`:
     ```sh
     cp .npmrc.example .npmrc
     # Then edit .npmrc and add your GitHub Personal Access Token (with write:packages scope)
     ```
4. Install dependencies:
   ```sh
   pnpm install
   ```
   If you don’t have pnpm, [follow this guide](https://pnpm.io/installation).
5. Lint and format your code (recommended):
   ```sh
   pnpm lint
   pnpm format
   ```
   > This project uses [Biome](https://biomejs.dev/) for linting and formatting.
6. (Recommended) Test your script locally before publishing. You can use [`pnpm link --global`](https://pnpm.io/cli/link) or [these npm tips](https://hirok.io/posts/avoid-npm-link#tl-dr).
7. When you're ready to publish to npm, run:
   ```sh
   pnpm publish --access public
   ```

## <u>Public vs Private Packages</u>

- For **public packages on npmjs.com**, use:
  ```sh
  pnpm publish --access public
  ```
- For **private packages on npmjs.com**, use a **scoped package name** (e.g., `@yourname/package`) and publish with:
  ```sh
  pnpm publish --access restricted
  ```
- For **private packages on GitHub Packages**, packages are private by default. Just publish as usual after configuring `.npmrc`.
