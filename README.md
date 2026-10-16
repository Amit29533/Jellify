# Jellify

A cinematic, Netflix-inspired theme for **Jellyfin Web 12+**. It brings a restrained black-and-red palette, editorial poster rails, full-bleed detail pages, refined navigation, and a coordinated playback overlay—while keeping Jellyfin's own artwork, labels, controls, and workflows.

The supplied mobile Netflix UI Kit inspired the mobile-first direction: immersive artwork, clear title/action priority, compact metadata, and touch-friendly controls. Jellify styles Jellyfin's existing UI and your server's media artwork; it does not bundle Netflix artwork, logos, fonts, or Figma assets.

## Install

### Server-wide

1. Open **Dashboard → Branding → Custom CSS**.
2. Paste the full contents of [`theme.css`](theme.css) into the CSS field.
3. Save, then reload Jellyfin Web. If an older theme is already installed, remove its imports first to avoid conflicting rules.

### One user or device

Open **Settings → Display → Custom CSS code** and paste the same stylesheet. Use this when you only want to change one user's web client or the official mobile app's web interface.

Jellify is a single, self-contained stylesheet: no plugins, JavaScript injection, remote fonts, or external image hosts are required. If you host the file yourself, you can also add it with an `@import` URL in Jellyfin's Custom CSS field.

## What it themes

- Jellyfin Web's **v12 Modern layout** (MUI navigation, drawer, library shelves and cards), with legacy header fallbacks.
- Item details: immersive backdrops, title/metadata hierarchy, play and secondary actions, synopsis, cast and recommendation shelves.
- The **web player OSD**: progress rail, transport controls, chapter preview, skip buttons and safe-area spacing.
- Touch-friendly poster rails, reduced-motion preferences, keyboard focus rings, and iPhone/iPad safe areas.

Jellify is CSS-only, so it doesn't invent or fetch a Netflix-style featured title. The home screen uses the sections, artwork and backdrops already provided by Jellyfin and your configured home layout.

## iOS and playback notes

Jellyfin's official iOS app wraps the Jellyfin web interface, so server CSS applies to its web-rendered screens. The stylesheet includes compact touch layouts and iOS safe-area handling. If playback switches to a native iOS player, its system controls are outside the web page and cannot be restyled with CSS; the Jellyfin Web HTML player OSD is themed. **Swiftfin** is a separate native client and does not load Jellyfin Web custom CSS.

Custom CSS is a web-client feature; native TV clients and other clients with their own UI are not affected. Jellyfin 12 may also leave the administration dashboard unthemed unless CSS is injected into the web client by a reverse proxy.

## Compatibility and customization

- Built against the Jellyfin Web **v12.0 Modern layout** and its existing detail/player markup. Jellyfin updates can change selectors; if a view looks off after an update, check the browser console and report the affected screen.
- Designed for desktop browsers, iPhone/iPad WebViews, and touch input. It does not change playback behavior, metadata, accessibility labels, or server settings.
- Adjust the color and motion tokens near the top of `theme.css` (`--jellify-red`, `--jellify-bg`, `--jellify-motion`) to personalize the palette.
- Motion automatically respects `prefers-reduced-motion`.

## References

- [Jellyfin CSS customization guide](https://jellyfin.org/docs/general/clients/css-customization/)
- [Jellyfin Web v12.0 source](https://github.com/jellyfin/jellyfin-web/tree/v12.0), used to target the Modern layout, item-detail markup and web-player OSD.
- [Jellyfin for iOS](https://github.com/jellyfin/jellyfin-ios) and the [mobile Netflix UI Kit prototype](https://www.figma.com/proto/ImaefqCNKxjArmNclncp9O/Netflix-UI-Kit--Mobile-iOS---Community-?node-id=180-22262&p=f&viewport=376%2C472%2C0.05&t=FJ0zFjWXXdqncE6k-1&scaling=scale-down&content-scaling=fixed&page-id=27%3A51).

## License

MIT. Jellyfin and Netflix are trademarks of their respective owners. Jellify is an independent community theme and is not affiliated with either project.
