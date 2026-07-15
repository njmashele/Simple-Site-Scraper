<p align="center">
  <img src="logo.jpg" width="280" alt="Simple">
</p>

# Simple Site Scraper

A Chrome extension that lets you point at a table (or any repeating block of elements) on a webpage and pull the data out as CSV or Excel. No coding required.

It automatically detects the most likely "table" on the page you're looking at, lets you cycle through other candidates if it picked wrong, and can crawl through multiple pages by clicking a "Next" button or scrolling an infinite-scroll list. When it's done, you get a spreadsheet preview right in the popup that you can rename columns on, delete columns from, and export.

## Features

- **Automatic table detection**: scans the page and scores elements by size and repetition to guess which block of content is the "table" you want.
- **Manual override**: hit "Try another table" to cycle through other candidates it found on the page.
- **Pagination support**: click to mark a "Next" button and the extension will crawl through pages automatically, with configurable min/max delay between requests.
- **Infinite scroll support**: for pages that load more content as you scroll instead of paginating.
- **Live preview**: scraped data shows up in an editable spreadsheet grid (powered by Handsontable) before you export anything.
- **Column editing**: rename or delete columns on the fly, with your changes remembered per-site.
- **Export options**: download as CSV, download as XLSX, or copy everything straight to your clipboard.

## Installation (unpacked / developer mode)

This extension isn't published on the Chrome Web Store, so you'll need to load it manually:

1. Download or clone this repository.
2. Open Chrome and go to `chrome://extensions`.
3. Turn on **Developer mode** (top right corner).
4. Click **Load unpacked**.
5. Select the folder you downloaded/cloned (the one containing `manifest.json`).
6. The Simple icon should now show up in your toolbar. Pin it if you want it visible at all times.

## Usage

1. Navigate to a page that has a table or list of data you want to extract.
2. Click the Simple icon in your toolbar. A popup window will open and it'll automatically try to find the best matching table on the page.
3. If it picked the wrong element, click **Try another table** to cycle through the other candidates.
4. (Optional) Click **Locate "Next" button** and then click the actual "Next"/pagination link on the page to teach Simple how to move to the following page. Skip this step if you only need the current page, or check **Infinite scroll** if the page loads more content on scroll instead.
5. Click **Start crawling** to begin collecting multiple pages. You can adjust the min/max delay between page loads in the form fields to avoid hammering the site.
6. Click **Stop crawling** any time to pause and download what's been collected so far.
7. Rename or delete columns directly in the preview grid. These preferences are saved per-domain so you won't have to redo them next time.
8. Export using the **CSV**, **XLSX**, or **COPY ALL** buttons.

## Third-party libraries

This extension bundles a few open-source libraries to handle parsing, spreadsheet display, and file exports:

- [jQuery](https://jquery.com/) 3.1.1
- [js-sha256](https://github.com/emn178/js-sha256)
- [PapaParse](https://github.com/mholt/PapaParse) 4.1.2
- [FileSaver.js](https://github.com/eligrey/FileSaver.js)
- [Bootstrap](https://getbootstrap.com/)
- [Handsontable](https://handsontable.com/)
- [SheetJS (xlsx)](https://sheetjs.com/)

Each of these carries its own license (mostly MIT), so it's worth double-checking before you redistribute this publicly.

## A note on analytics

`js/google-analytics.js` sends usage events (page views, downloads, errors) to a Google Analytics 4 property using a hardcoded measurement ID and API secret. If you're pushing this to a public repo, you'll probably want to either strip this file out, swap in your own GA property, or gate it behind a feature flag before sharing the code. Right now anyone who reads the source can see (and post events to) your analytics property.

## Known limitations

- LinkedIn is explicitly blocked from scraping.
- The popup preview is capped at 1,000 rows; everything past that is still collected but not rendered live.
- Table detection is heuristic-based (size + repeated class names), so oddly structured pages may need a manual "Try another table" nudge.

## License

Add a license of your choice here (MIT is a common pick for personal projects like this). Until you do, this repo defaults to "all rights reserved."
