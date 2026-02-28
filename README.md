# SMFM

This project contains a full definition and example of the SMFM standard commonly used in Sine mods as the optimal file management system.
(SMFM stands for the standard mod file management system)

## What is the SMFM standard?

SMFM stores files like such:

```text
assets/
scripts/
|- assets/
|- *
styles/
|- assets/
|- *
userChrome.css
userContent.css
script.js
```

This standard may seem a little confusing at first, but all of it is explained below.
Universal assets (assets used for both styles and scripts) are stored in their own folder at the root of your repository.

**If your project uses scripts:** Your entry point script should be stored at the root of the repository, labeled as `script.js` (or .mjs for modules). This file should only be stored there either if it is the only script in your project, or if it plays a critical role as the main script of your project. In any other scenario, your scripts should all be placed under the scripts folder. On top of this, if you only have one script in your project, it should be stored at the root and the assets for that script should be placed under the universal assets folder instead. If the standard declares that you should have a scripts folder, you may arrange all the scripts inside of that folder in any way you wish, with subfolders based on the topic of certain scripts.

**If your project uses styles:** There are two main files that you need to load in styles, `userChrome.css` and `userContent.css`. The chrome file allows you to style your browser interface, while content styles allow you to style websites like your new tab page, settings page, and even just standard websites like firefox.com. We recommend creating each file only as needed, rather than creating them even if your mod doesn't currently require them. For the SMFM standard, place both of these files at the root of the repository, and any imports that the mod requires should be placed under the styles folder. If you have assets used in only styles, place them under an assets folder in the styles folder. SMFM does not allow styles to be named after the mod or to be named `chrome.css` and `content.css` as it makes it more confusing for mod managers and contributors.

## Why use SMFM?

Organizing CSS and JS into folders makes your repository not only clean, but easy to understand for people attempting to contribute. This setup is also verified to work with Sine easily, allowing your mod metadata to be as small as possible and work with defaults.

## Where can I find an example of SMFM? (todo)

We store an up-to-date implementation of the SMFM standard on this repository under the example folder.

## What's the difference between SMFM vs uCL?

SMFM is designed to work easily with Sine mods and all of the defaults in it, optimizing your setup and making it easy for contributors to understand. uCL, on the other hand, is designed to work easily with custom user styles, which must be handled by the user manually. We recommend SMFM over uCL if you're developing for Sine, although it can also work for user styles.
