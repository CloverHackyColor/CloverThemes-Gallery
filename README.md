[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://github.com/CloverHackyColor/CloverThemes-Gallery/blob/main/LICENSE) [![pages-build-deployment](https://github.com/CloverHackyColor/CloverThemes-Gallery/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/CloverHackyColor/CloverThemes-Gallery/actions/workflows/pages/pages-build-deployment)
# CloverThemes Gallery
## Start using ➢ [CloverThemes Gallery](https://cloverhackycolor.github.io/CloverThemes-Gallery/)

## How it work
1. Fetching the Data (The Smart API Call)
Instead of making dozens of separate requests for every folder (which causes GitHub to block you), the script makes one single call to the GitHub Git Tree API (/git/trees/master?recursive=1). This asks GitHub to hand over a complete map of every single file and folder in the repository in milliseconds.

2. Matching Folders to Images
Once the script has the "map" of the repository, the JavaScript filters through it to find all the root-level theme folders. At the same time, it looks inside those folders for image files (.png, .jpg, .svg, etc.). It prioritizes files named screenshot, preview, or theme, and saves the exact URL for that image.

3. Building the Cards
The script then dynamically generates an HTML "card" for every theme it found. It sorts them alphabetically and injects them into the grid layout.

4. Loading the Previews
For each card, it sets the image URL to start downloading.
	•	If the image loads successfully, it fades the image in and hides the "Loading preview..." text.
	•	If an image fails to load (or doesn't exist), it catches the error and displays a clean "No preview available" text, preventing broken image icons.

5. The Download Mechanism
When you click the green "Download" button, we have local ZIP downloads for theme folders in-browser ZIP generation using JSZip. The folder tree parsing now keeps each theme’s full file list (including nested files), stores it in a map, and uses delegated button clicks to fetch files, build a per-theme archive, and download it as `<theme>.zip`. The download button now shows a zipping state and is temporarily disabled, with clearer failure messaging if GitHub fetches fail or are rate-limited.

- In short: It grabs a master list of files from GitHub -> matches themes to their screenshots -> builds beautiful dark-mode cards -> and routes downloads through a dedicated ZIP service!

* Page build by: [chris1111](https://github.com/chris1111)

