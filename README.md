# Mailspring Theme Updater Plugin

This plugin aims to be a quick fix for keeping a theme up to date with its remote counterpart.

If you like this plugin, check out my Mailspring theme inspired by Inbox, and Google Cloud Console: [Mailspring Agapanthus Theme](https://github.com/danieljimeneznz/mailspring-agapanthus-theme)

## Build Instructions

Due to the power of Intellisense, and difficulty compiling the plugin utilising `Babel`, typescript was chosen to build the
plugin (+ mailspring has moved to typescript, so if the plugin was to be included in the base application, adding it to
would be super easy).

1. Clone the main Mailspring repository into a directory i.e. `root/Mailspring` (Note, this does not need to compile
   correctly as this repository is only needed for typing).
2. Clone this repository into a directory with the same parent i.e. `root/mailspring-theme-updater-plugin`.
3. Run `npm run build` in the plugin directory which will output the compiled files in
   `root/mailspring-theme-updater-plugin/dist/mailspring-theme-updater-plugin/lib` (Note, errors may occur due to compilation errors with the
   Mailspring repository, check the output lib files were compiled correctly).
4. Run `npm run post-build` in the plugin directory which will copy the `package.json` into the `root/mailspring-theme-updater-plugin/dist/mailspring-theme-updater-plugin/lib` folder
   and install the corresponding dependencies.
5. Install the plugin!

## Notes

- Types are referenced by the `tsconfig.json` file including the `../Mailspring/app/src/global/*` files, which contain the
  declarations for the types that Mailspring exports.
- This plugin only supports updating themes that have a github remote.
