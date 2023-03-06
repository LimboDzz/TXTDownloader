## Contents

- [x] [txt-downloader](txt-downloader\)

## What I've learnt

### 2 ways to write userscripts in vscode

1. Webhook

   1. Sign in Greasy Fork

   2. User control panel - setup webhook

      ![setup-github-webhook](assets\setup-github-webhook.png)

   3. Publish script - Go to Admin - Source Syncing - Provide github raw url of your js file

      ![setup-source-syncing](assets\setup-source-syncing.png)

2. Require local js file

   1. Tampermonkey settings - Allow access to file URLs

      ![assets\allow-access-to-file-URLs.png](assets\allow-access-to-file-URLs.png)

   2. Save your script file wherever you want in your filesystem.

   3. Add @require inside `==UserScript==` header

      - Possible gotcha: Using the file:// URI scheme at the beginning of your @require path is now required.

      On Windows systems would be:

      `// @require      file://C:\path\to\userscript.user.js`

      For macOS and \*nix, you need three slashes in a row:

      `// @require      file:///path/to/userscript.user.js`

      ![assets\require-local-js-file.png](assets\require-local-js-file.png)

## Acknowledgments

Inspiration, code snippets, stackoverflow answers, etc.

- [How can I develop my userscript in my favourite IDE and avoid copy-pasting it to the Tampermonkey's editor every time?](https://stackoverflow.com/a/55568568/19419913)
- [油猴脚本开发从入门到精通 P0 开发环境配置与脚本分发](https://www.bilibili.com/video/BV1Da411Z7s7)
