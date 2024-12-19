# API-Scrapper
This is learning repo for Web scrapping using Puppeteer

# Web Scraping and API Scraping with Puppeteer

Web scraping involves extracting data directly from web pages, while API scraping taps into structured data provided by an API. Puppeteer, a powerful Node.js library, allows you to control Chrome or Chromium, making it ideal for automating and scraping web data. This README outlines key Puppeteer commands to simplify web scraping tasks.

## Puppeteer Basics

### Initializing Browser and Page
- `puppeteer.launch()` → Instantiate a browser instance.  
- `browser.newPage()` → Open a new page instance.

### Navigating to a Website
- `page.goto(url)` → Open the specified website.

### Scraping and Interacting with Elements
- **Extract Data**:  
  - `page.evaluate()` → Execute JavaScript in the browser context.  
  - `document.querySelector()` → Select an HTML element by CSS selector.  
- **Iterate Over Data**:  
  - Use loops to process the retrieved elements.  

### Common Interactions
- Click buttons: `await page.click(".pager > .next > a")`.  
- Type in fields: `await page.type("#inputField", "Some text")`.  
- Wait for elements: `await page.waitForSelector(".target-class")`.  
- Take screenshots: `await page.screenshot({ path: "screenshot.png" })`.  

### Retrieve Attributes
```javascript
const links = await page.evaluate(() =>
  Array.from(document.querySelectorAll("a")).map((a) => a.href)
);
