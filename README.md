## Browser Extension – Local Setup Guide

This is a simple website scraper browser extension. It is not published on any extension store yet, so it needs to be loaded manually in your browser.

### How to Load the Extension Locally

#### Step 1: Download or Clone the Repository

* Download the ZIP from this repo and extract it
  **or**
* Clone the repo:

```
git clone <your-repo-url>
```

#### Step 2: Open Your Browser’s Extension Page

For Chrome:

* Open Chrome
* Go to `chrome://extensions/`

For Edge:

* Open Edge
* Go to `edge://extensions/`

#### Step 3: Enable Developer Mode

* Toggle **Developer mode** (top right corner)

#### Step 4: Load the Extension

* Click **Load unpacked**
* Select the folder that contains the extension files (the same folder where `manifest.json` is located)

#### Step 5: Done

* The extension should now appear in your browser
* Pin it from the extensions menu if needed

### Notes

* Make sure the folder structure stays intact
* If you make changes to the code, click **Reload** on the extension in the extensions page

### Troubleshooting

* If it doesn’t load, check the console for errors
* Ensure `manifest.json` is valid and in the root of the folder
