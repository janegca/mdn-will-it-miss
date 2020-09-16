# MDN will-it-miss NASA Feed Project

A case study to deploy a mini-site that reads NASA's API to display information on potentially hazardous space objects. The study is based on how to use the core _tools_ around web development (see dev-dependencies in package.json for a list) rather than the code itself.

The project uses some new features that are not fully standardized, for example, [CSS Nesting](https://drafts.csswg.org/css-nesting/) rather than SASS. After copying the inital application files to the <code>src</code> and creating the dot-config files <code>.eslintrc.json, .prettierrc.json, .postcssrc</code> files, had to build the application using the command:

```
		npx parcel src/index.html
```

which creates a <code>dist</code> directory publishes the code to it.

## Deployment

The code will be deployed to _Netlify_ via Github which is done by setting up atool chain that will eventually cause every <code>push</code> to the git repository to trigger a re-deployment to Netlify. This accomplished with the use of an `npm build src/index.html` script. Adding <code>build</code> to the command handles minification, (browser) cache-busting, and tree-shaking code to produce clean production files.

Example was deployed [_here_](https://condescending-wozniak-eeeef6.netlify.app/)

## Testing

Includes a simple test using <code>axios</code>. Couldn't get it to work as given:

<code>
"test": "node tests\*.js" --> "node test\nasa-feed.test.js"
</code>

References:

- [_MDN Case Study_](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Introducing_complete_toolchain)
  - [_Study Source Code_](https://github.com/remy/mdn-will-it-miss)
- [_Prettier Configuration Rules_](https://prettier.io/docs/en/configuration.html)
- [_ESLint Configuration Rules_](https://eslint.org/docs/rules/)
