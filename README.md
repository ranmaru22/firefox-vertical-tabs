# Firefox Vertical Tabs

Vertical tabs for Firefox, inspired by Edge. Works with Light theme, Dark
theme, and System theme (auto dark mode). There are some minor glitches with
Alpenglow, but they should be easy to fix.

It also plays nice with Container Tabs.

## Screenshots

![](./screenshots/linux.png)

![](./screenshots/macos.png)

## Compatibility

**Tested compatibility with up to Firefox 124.**

There has recently been in change in Firefox that requires the use of
`-moz-platform` instead of `-moz-os-version` to use OS-specific CSS. This will
work from 99.0b1 upwards but might not on older versions, so be aware of that.
If you run an older version of Firefox and have an issue, change this back.

(Also, since the only OS-specific CSS in the file targets Windows, it should
not affect you on Mac or Linux either way.)

It should work on newer versions as well unless there\'s any breaking changes
in how `userChrome.css` works.

I have only tested this for Linux and macOS. There might be some bugs on
Windows because the window decorations look different. I can\'t test this
because I don\'t have a Windows computer, but if you find any bugs and know how
to fix it, feel free to submit a PR.

## Minified files

Starting with version 6.0, the releases include minified versions of both CSS
documents. This is because the CSS will exceed the storage quota for web
extensions otherwise as it has grown quite large (see issue #116).

**WARNING: You HAVE to use the minified version of `tabCenterReborn.css`
(`tabCenterReborn.min.css`) otherwise you will run into issues because of a
huge payload. This is because Firefox allows extensions only a certain amount
of data to pass around and this mod has grown so large that it is over that
limit.**

If you don't want to use the minified version, you need to remove some lines of
code from that file until it works. Unfortunately that's currently the only way.

You do not need to use a minified version of `userChrome.css`, so for now we
don't provide one.

## How to install

-   Go to `about:config` in your URL bar, search for
`toolkit.legacyUserProfileCustomizations.stylesheets` and set it to `true`.
-   Go to `about:profiles` in your URL bar, click *\"Open Directory\"* next to
your Root Directory under your default profile.
-   If there is no `chrome` folder, create it.
-   Create a file called `userChrome.css` inside the `chrome` folder.
-   Copy and paste the contents of `userChrome.css` into your file (or symlink
it).
-   OPTIONAL: Adjust `--delay` setting in the `userChrome.css` file.
-   OPTIONAL: Adjust `--fullscreen-sidebar-width` setting in the
`userChrome.css` file.
-   Install the [Tab Center
Reborn](https://addons.mozilla.org/en-US/firefox/addon/tabcenter-reborn/)
extension.
-   Make sure to enable *\"Allow this extension to run in Private windows\"* so
you\'re not left stranded while browsing.
-   Go to `about:addons` in your URL bar, select **Tab Center Reborn**, go to
**Preferences** and set:
    -   **Animations**: on.
    -   **Use current browser theme**: on, if you want to use dark mode.
    -   **Compact Mode**: \"Enabled\" is recommended. It works with \"Dynamic\"
    or \"Disabled\" too but looks nicer with only favicons.
    -   **Favicon-only pinned tabs**: Your choice. If set to \"on\", you will
    only have one icon on the top of the collapsed bar and a row of icons in
    the expanded state, with \"off\", they appear like normal tabs (one per
    row) with a pin icon on the right and a separator bar between pinned and
    normal tabs. The mod works well with both settings.
    -   Activate **Custom Stylesheet** and paste the contents of
    `tabCenterReborn.min.css` into the text area below, and click \"Save CSS\"
    under the text box. If you don\'t want to use the minified version, you
    need to remove some code manually, otherwise Firefox will complain about
    too large a payload and ignore the CSS completely (see issue #116).
-   Restart Firefox.

## Things to note

-   If the sidebar does not show up, you can press `Shift-F1` to show the Tab
Center Reborn sidebar directly, or `Cmd-B` / `Ctrl-B` to toggle the sidebar in
general.
-   In Fullscreen mode, the sidebar will collapse to a 1px wide border instead
to be as unintrusive as possible. You can expand it by pushing your cursor all
the way to the edge of the screen. This can be disabled by setting
`--fullscreen-sidebar-width` to `48px`.
-   If your window controls are not correctly aligned, disable compact mode at
`Customize toolbar...` menu.
