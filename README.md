# Wix Scraper

:warning: **IMPORTANT NOTICE**: This tool should only be used by those who have paid for Wix. Your Wix website might not belong to you under [Wix Terms of Service](https://www.wix.com/about/terms-of-use) if you haven't paid for it. By using Wix Scraper, you agree to abide by Wix's Terms of Service.

---

## Overview

Wix Scraper is a Python script that allows you to convert a Wix-created website into an offline local copy, with downloaded images and fonts. It also removes all Wix-related JavaScript and replaces it with the nearest open-source alternative, such as slick.js and Leaflet.js.

## Speed

Due to getting rid of Wix JS, CSS, animations, and other Wix-like content, as well as adding more SEO, we get a better website. Here's the Google Lighthouse report:

Normal Wix:

![image](https://github.com/ryanhlewis/WixScraper/assets/76540311/8815a5ae-88ab-4d2f-92ae-73bcdbe5a56f)

Wix Scraper:

![image](https://github.com/ryanhlewis/WixScraper/assets/76540311/044b540b-5069-451d-abc9-32a8206b8d30)

## Configuration

To run Wix Scraper for any Wix website, you need to set up a configuration file (config.json) like the one below:

```json
{
    "site": "https://example.wixsite.com/example1",
    "blockPrimaryFolder": "example1",
    "wait": 3,
    "recursive": "True",
    "darkWebsite": "False",
    "forceDownloadAgain": "False",
    "metatags": {
        "/example1": {
            "title": "Example1 | The Best Wix Website",
            "description": "Example1 is the best Wix website of all time.",
            "keywords": "example keyword, example1 keyword",
            "canonical": "https://example1.com/",
            "image": "https://example1.com/banner.png",
            "author": "Example1 Author"
        },
        "/example1/about": {
            "title": "About | Example1 Website",
            "description": "About Example1 which is the best Wix website of all time.",
            "keywords": "example keyword, example1 keyword",
            "canonical": "https://example1.com/about",
            "image": "https://example1.com/banner.png",
            "author": "Example1 Author"
        }
    },
    "mapData": {
        "latitude": "32.0879315",
        "longitude": "34.797246",
        "zoom": "12",
        "mapMarker": {
            "latitude": "32.0879315",
            "longitude": "34.797246",
            "popup": "<p>Wix HQ, Tel Aviv, Israel</p>"
        }
    }
}
```

### Configuration Variables

- `site`: This is the URL of the Wix website you want to scrape.
- `blockPrimaryFolder`: This is the primary folder after "wixsite.com" if one exists.
- `wait`: This is the time (in seconds) the scraper waits before loading a new page.
- `recursive`: If set to "True", the scraper will scrape all pages linked from the initial page.
- `darkWebsite`: If set to "True", the scraper will apply a dark mode theme to the scraped website.
- `forceDownloadAgain`: If set to "True", the scraper will download all files again, even if they already exist in the target directory.
- `metatags`: This is a dictionary containing the metadata of each page on the website. This includes the title, description, keywords, canonical URL, image URL, and author of each page.
- `mapData`: This is the data required to display a map on the website. This includes the latitude and longitude of the location, the zoom level of the map, and the details of the map marker.

## Usage

To run Wix Scraper, first fill in the configuration file. Then, use the following command:

```bash
python wixscraper.py
```

That's it! You now have a fully offline and working copy.
