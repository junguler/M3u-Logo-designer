# M3U-Logo-designer
wrestle with claude to create a m3u logo designer, instead of searching the web for station logos this page draws a logo for every station using its title, it has 3 ways to load a playlist

* load local file: upload a m3u playlist and click this button to load its stations
* load online link: input the link of a m3u playlist (the raw file from github for example) and click the button to load its stations
* load pasted streams: copy and paste the streams title and links from wherever and click the button to load its stations

after loading, design the look you want with the live preview and the settings panels, then click **Generate ZIP** to get everything in one download

* the playlist, with a `tvg-logo` attribute added to every station
* a `logos` folder with one jpg per station

unzip it and keep the playlist next to the `logos` folder, the logo paths are relative so players that support `tvg-logo` can load them as long as the two stay side by side, the folder name can be changed in the settings

most iptv apps want full urls instead of relative paths, so there is an option (off by default) to write a full logo url prefix into `tvg-logo`, upload the `logos` folder to that location (a github repo works with the raw link) and the logos load anywhere, mpv and vlc ignore `tvg-logo` completely, kodi can use it through the iptv simple client

## design options

* background: solid, linear, radial, conic and mesh gradients with up to 3 colors, angle and hard stops
* pattern overlay: stripes, dots, grid, checker, rings, rays, waves, zigzag, crosses
* text: use the full title, a cleaned title, initials, first word and more, 12 fonts, case, weight, italic, spacing, alignment, rotation, offset, solid, gradient, auto contrast and rainbow fills
* stroke, shadow and depth: double stroke, hard or soft shadow, glow, 3D extrude
* frame: outer border and inner line
* effects: vignette, grain, scanlines, RGB split, glitch, brightness, contrast, saturation, hue, invert, pixelate
* dither: Bayer, Floyd-Steinberg, Atkinson and random with adjustable levels, cell size and grayscale or two-tone colors
* geometric shapes: square, circle, triangle, diamond, pentagon, hexagon, star, ring, cross, semicircle, parallelogram, insert them by hand with position, size, rotation, opacity, filled or outline, behind or over the text, or let the page add a random number of them
* text contrast %: the higher it is the more readable the text gets, it pushes the text color away from the background, adds a halo stroke and a soft backing glow
* shape and size: corner radius up to a full circle, image sizes from 128 to 1024 px, jpg quality

## random options

* randomize all, random colors and random style buttons, keep clicking until you like what you see
* randomize amount %: how much of the design the random buttons change, 100 changes everything, a low value gives a light remix of what you already have
* keep text readable: when on (it is by default) the random buttons never go below a minimum text contrast, so random designs stay legible
* randomize each entry: every station gets its own random remix of your design, how far each one drifts from it is set by the randomize amount %, change the seed to reshuffle them all
* vary per station: give every station its own hue, its own colors or its own style, it is based on the station title so the same title always gets the same logo

## save and load looks

* save look: downloads your current design as a small json file, send it to a friend or keep one per playlist
* load look: pick a saved look file to bring the design back, the output folder and logo url prefix stay as you set them
* the page also remembers the last design you used in your browser, reset clears it back to the defaults

## notes

* streams that already have a logo are left alone, there is an option to replace them (not active by default)
* streams with the same title share one image
* image names are the title plus a short hash, so they stay the same when you add or reorder stations, there is an option for plain names without the hash
* grain and random dither are seeded by the title too, so regenerating a playlist gives the same files and git only sees real changes
* fonts are the ones installed on your system, so the same design can look slightly different on another device
* everything is drawn with a canvas in your browser, nothing is uploaded anywhere

github pages are static, meaning this code runs on your device, you can just make a local copy of this page if you don't want to always open this page

this repo is made primarily as an auxiliary resource for my [m3u-radio-music-playlists](https://github.com/junguler/m3u-radio-music-playlists) repo and it's going to be linked there as well, it is a sister page of [M3U-Logo-embedder](https://github.com/junguler/M3U-Logo-embedder), use that one to find real logos and this one to design logos for the stations it couldn't find
