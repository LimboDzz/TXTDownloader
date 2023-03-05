## Description

This userscript can download books as txt from certain websites.

## For Tutorial

### Structure

```js
function main() {
	const downloadButton = new Button();
	downloadButton.addEventListener('click', download);
	downloadButton.attach();
}

async function download() {
	const pageLinks = getAllPageLinks();
	const dataArray = await fetchAllPages(pageLinks);
	saveFile(dataArray);
}
```

### What I've encountered

1. Insert custom styles

   ```js
   const style = document.createElement('style');
   style.textContent = `Your custom styles...`;
   document.head.append(style);
   ```

2. res.text() gets garbled text. To solve this, use **TextDecoder()** to specify the gbk encoding.

   ```js
   const gb2312Decoder = new TextDecoder('gbk');
   const html = gb2312Decoder.decode(buffer);
   ```

3. Use **DOMParser** to parse plain text to html for further manipulation on fetched contents.

   ```js
   const parser = new DOMParser();
   const doc = parser.parseFromString(html, 'text/html');
   ```

4. 3 steps for browse-side file downloading

   ```js
   const fileData = new Blob(arrayBuffer);
   const fileUrl = URL.createObjectUrl(fileData);
   triggerDownloadAnchor();
   ```

## Supported Websites

- [x] dmshuba.com
- [x] yqshuwang.com
- [ ] tbc...
