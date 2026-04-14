# Website URL Excel Task

This package contains a Python script for both tasks:

## Task 1: Broken links report
- Read website page URLs from Excel
- Open each page
- Extract all `<a href="">` links
- Check which links are broken/inaccessible
- Export results to a new Excel file

## Task 2: Download all images
- Read website page URLs from Excel
- Open each page
- Extract all `<img src="">` image links
- Download all images into one folder

---

## Input Excel format

Keep the first column header as:

`URL`

Example rows:
- https://lanoequip.com/
- https://lanoequip.com/new-equipment.html
- https://lanoequip.com/parts-toro.html

---

## Install requirements

Open terminal / command prompt:

```bash
pip install requests beautifulsoup4 openpyxl
```

## Run Task 1

```bash
python scraper_task.py --task broken_links --input input_urls.xlsx --output broken_links_report.xlsx
```

## Run Task 2

```bash
python scraper_task.py --task download_images --input input_urls.xlsx --output downloaded_images
```

---

## Notes
- Some websites block scraping or block `HEAD` requests. The script tries `GET` if needed.
- Relative links like `/about` are automatically converted to full URLs.
- `mailto:`, `tel:`, `javascript:`, and `#anchor` links are ignored.
- If a page itself does not open, the script adds that page as an error in the report.

## Output for Task 1
Excel columns:
- `pageURL`
- `Broken Links`
- `Status`
