# script-executable-publishable

Template that you can use to create an executable script, ready to be published in NPM. It does not use any bundler.

If you are wondering whether or not you need a bundler for your purposes, you can read [this answer](https://stackoverflow.com/questions/67245509/why-do-we-still-need-module-bundlers-when-we-have-native-esm-support-in-browsers) on stackoverflow and maybe [this blog article](https://cmdcolin.github.io/posts/2022-05-27-youmaynotneedabundler).

![script-executable-publishable](assets/script-executable-publishable.png)

## <u>How to use</u>

The procedure is fairly simple.

1.  [Use this project as a template](https://github.com/gamekaiju/script-executable-publishable/generate).
2.  Refill every occurrence of 'script-executable-publishable' inside package.json with your own project name. Replace 'description', 'keys' and 'author' with your own values and clear the readme: `cat /dev/null > README.md`. Update the license.
3.  Copy the example npmrc file as '.npmrc': `cp .npmrc.example .npmrc` and replace the placeholder with a [Personal Access Token](https://github.com/settings/tokens) created with 'write:packages' as scope.
4.  Do `pnpm install`. If you don't have pnpm yet, [follow this guide](https://pnpm.io/installation).
5.  To test if your script works as intended before publishing, use [npm as explained here](https://hirok.io/posts/avoid-npm-link#tl-dr) to avoid headaches.
6.  When you're ready to publish, do `pnpm publish`.
