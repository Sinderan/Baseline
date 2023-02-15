## Baseline v0.5.1
### New Features
- Include the package `/usr/local/Baseline/Packages/SwiftDialog.pkg` to install a bundled copy of SwiftDialog instead of downloading.
- An additional class of Scripts can now be defined as `InitialScripts`. Scripts in this dictionary are:
    - Processed by the same function as `Scripts` and thus have the same requirements and features.
    - Initiated immediately upon a confirmed end user login, and prior to the main Dialog list.
    - There is no SwiftDialog window open while Initial Scripts are being processed. This means admins are welcome to create their own custom SwiftDialog experience with branding and messaging as you see fit.
    - It is recommended that Initial Scripts call a dialog window with the `--blurscreen` and `--ontop` options to match the defaults used in the main Baseline script.
- New `Restart` configuration key.
    - Boolean value which when set to `false` will not force a restart at the completion of Baseline
    - Default is `true` and this key does not need to be included if you want to leave the default behavior
- Added `InitialScripts` and `Restart` to the ProfileManifest 
### Bug Fixes
- Fixed a logic loop where Baseline would never exit if SwiftDialog wasn't installed successfully with Installomator.
- General code cleanup