# KIMOX visual customization quick reference

1. Open `css/style.css`. Change `--orange`, `--surface` and `--bg` at the top for the main colors.
2. The glass style lives in `.glass`; reduce the transparency if text contrast decreases.
3. The project slider content lives in `js/data.js` and is built by `js/main.js`. Bootstrap provides touch/keyboard-friendly carousel controls.
4. Swap `assets/images/portrait.svg` with a photo and edit the `portrait` property in `js/data.js`.
5. Swap project SVGs with screenshots using each project's `image` property in `js/data.js`.
6. Brand icon source: `assets/icons/kimox-mark.svg`. Modify the SVG path and colors as needed.
7. Adjust `.hero`, `.section`, and responsive `@media` rules in `css/style.css` to change composition.
8. All animations have a reduced-motion fallback. Keep this preference enabled for accessibility.
