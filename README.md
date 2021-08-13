# Firefox Vertical Tabs
Vertical tabs for Firefox, inspired by Edge.

Works with Light theme, Dark theme, and System theme (auto dark mode).
There are some minor glitches with Alpenglow, but they should be easy to fix.

It also plays nice with Container Tabs.

## Screenshots
![Linux Screenshot](./screenshots/linux.png)

![macOS Screenshot](./screenshots/macos.png)

## Compatibility
Compatible with Firefox 91.

I have only tested this for Linux and macOS. There might be some bugs on Windows 
because the window decorations look different. I can't test this because I don't 
have a Windows computer, but if you find any bugs and know how to fix it, feel 
free to submit a patch.

##  How to install
- Go to `about:config` in your URL bar, search for `toolkit.legacyUserProfileCustomizations.stylesheets` 
and set it to `true`.
- Go to `about:profiles` in your URL bar, click "Open Directory" next to your 
Root Directory under your default profile
  - If there is no `chrome` folder, create it.
  - Create a file called `userChrome.css` inside the `chrome` folder.
  - Copy & paste the contents of `userChrome.css` into your file (or symlink it).
- Install the [Tab Center Reborn](https://addons.mozilla.org/en-US/firefox/addon/tabcenter-reborn/) 
extension.
- Make sure to enable "Allow this extension to run in Private windows" so you're
  not left stranded while browsing.
- Go to `about:addons` in your URL bar, select *Tab Center Reborn*, go to *Preferences* 
and set:
  - *Animations*: on.
  - *Use current browser theme*: on, if you want to use dark mode.
  - *Compact Mode*: either "Dynamic" or "Enabled". It works with "Disabled" too 
    but looks nicer with only favicons.
  - *Favicon-only pinned tabs*: off.
  - Activate *Custom Stylesheet* and paste the contents of `tabCenterReborn.css` 
    into the text area below, and click "Save CSS" under the textbox.
- Restart Firefox.
