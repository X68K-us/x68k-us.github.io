---
title: X68000 Setup for MiSTer
--- 

### Coming Soon

Simple setup instructions coming soon.

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
