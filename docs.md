---
title: X68000 Setup for MiSTer
--- 

## Installation

X68000 is a system that uses a lot of different resolutions across 15kHz, 24kHz and 31kHz, so we will need to use the VGA scaler. 

(The X68000 core also does not support Direct Video (yet?), so if you are using a RetroTink 4K scaler, auto-configuration of the scaler settings will not work — you will have to load a profile manually or just use the defaults.)

Add this configuration to your `MiSTer.ini`:

```
[X68000]
forced_scandoubler=0
vga_scaler=1
direct_video=0

[video=256x240]
vscale_mode=1
video_mode=256,240,60

[video=256x256]
vscale_mode=1
video_mode=256,256,60

[video=256x512]
vscale_mode=1
video_mode=256,512,60

[video=512x240]
vscale_mode=1
video_mode=512,240,60

[video=512x256]
vscale_mode=1
video_mode=512,256,60

[video=512x512]
vscale_mode=1
video_mode=512,512,60

[video=640x480]
vscale_mode=1
video_mode=640,480,60

[video=768x512]
vscale_mode=1
video_mode=768,512,60

[video=1024x1024]
vscale_mode=1
video_mode=1024,1024,60
```

### Unpacking the Games

**Windows:** For unpacking multiple files, on Windows, we recommend using 7zip, selecting all the zip files you want, and using the "Extract here" right click menu item. If asked to overwrite duplicate files, just say "Yes to All".

**macOS:** Most of the tools will unfortunately create a dedicated folder for every game when you unpack (even if they say they won't, like in the case of Keka), so the most efficient way is to use the Terminal:

```
cd DirectoryWithYourFiles
for f in *.zip; do unzip -o "$f" -d ./; done
````

(If you are uncomfortable using the Terminal, just unpack all the files and move the directories manually)

Once unpacked, copy all the folders to the root of your MiSTer. The directories look like this:

```
_Computer
config
docs
games
```

If asked, use the "Merge" option to merge the directories.

The games will launch directly from the MiSTer menu inside `Computer` using MGL files.


<script>
        document.addEventListener("DOMContentLoaded", function () {
            // Select h3 and below
            const headings = document.querySelectorAll("h3[id], h4[id], h5[id], h6[id]");

            headings.forEach((heading) => {
                // Make the heading clickable
                heading.classList.add("clickable-heading");

                // Add a click event listener that will navigate to the anchor link
                heading.addEventListener("click", function () {
                    const slug = heading.id;
                    window.location.hash = `#${slug}`;
                });

                // Add a visual indicator (e.g., a link icon that appears on hover)
                const linkIcon = document.createElement("span");
                linkIcon.innerHTML = " 🔗";
                linkIcon.style.opacity = "0";
                linkIcon.style.transition = "opacity 0.2s";
                linkIcon.style.fontSize = "80%";

                heading.appendChild(linkIcon);

                // Show the link icon when hovering over the heading
                heading.addEventListener("mouseover", () => {
                    linkIcon.style.opacity = "1";
                });
                heading.addEventListener("mouseout", () => {
                    linkIcon.style.opacity = "0";
                });
            });
        });
</script>
