# annotate-view-convert

This repository contains a set of tools to create, convert, and view interactive image-based projects.  
It is fully general-purpose and can be used with any kind of image (maps, diagrams, artworks, technical drawings, etc.).


##  Features

- Draw polygon shapes on any image interactively.
- Attach files (images, diagrams, etc.) to each shape.
- Export your shapes and data as JSON.
- Convert JSON into a JavaScript file easily.
- View shapes interactively, with optional filtering from Google Sheets.

###  interactive-drawing.html

**Purpose:**  
Draw polygons on an image, attach a file to each shape, and export all data as a JSON file.

**How to use:**

1. Open `interactive-drawing.html` in your browser.
2. Upload your base image (map, diagram, etc.).
3. Click points on the image to create a polygon.
4. When done, click "Save Unit", enter an ID, and upload a file for that shape.
5. Repeat for each shape.
6. Click "Save Project" to download `viewer-data.json`.


### convert-json-to-js.html

**Purpose:**  
Convert your JSON file into a JavaScript file that defines a global variable, so it can be loaded in the viewer.

**How to use:**

1. Open `convert-json-to-js.html` in your browser.
2. Select your `viewer-data.json` file.
3. Enter a variable name (e.g., `myData`).
4. Click "Download JS File" to download a file like `layer1.js`.


### interactive-viewer.html

**Purpose:**  
Display your image with interactive shape markers. You can also filter shapes using data from Google Sheets.

**How to use:**

1. Add your generated `.js` file (e.g., `layer1.js`) in the same folder as `interactive-viewer.html`.
2. Update `interactive-viewer.html` with your:
   - Google Sheets API key.
   - Google Sheet ID.
   - Base image filename if different.
3. Open `interactive-viewer.html` in your browser.
4. Click a floor or layer button to load shapes.
5. Use the filter sidebar to filter shapes by type or group (from your Google Sheet).
6. Click a shape marker to view the attached file.



## Google Sheet Setup for Filters

If you want to filter shapes, set up a Google Sheet with columns like below:

ID Status — Type Group
A001 active Type1 Group1
A002 active Type2 Group2
A003 inactive Type1 Group1


- **ID**: Must match the shape ID you used when drawing.
- **Status**: Use `active` for shapes you want to show.
- **Type** and **Group**: You can define them however you want (for filtering).

---

##  Workflow Summary

Step 1: Use `interactive-drawing.html` to draw and export JSON.  
Step 2: Use `convert-json-to-js.html` to convert JSON to JS.  
Step 3: Add JS file to `interactive-viewer.html` and open it to view and filter.



##  Notes

- Runs fully in the browser — no backend or server required.
- Works with any image type: maps, diagrams, floor plans, art, etc.
- You can have multiple layers (e.g., `layer1.js`, `layer2.js`) and load them via buttons.



## 🗂 Example File Structure

/your-project
├── interactive-drawing.html
├── convert-json-to-js.html
├── interactive-viewer.html
├── layer1.js
├── viewer-data.json
├── your-image.jpg
└── README.md



