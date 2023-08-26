This repository contains builds of most versions of Proton released on Steam (excluding beta, rc and experimental). All builds were downloaded from Steam and provided here as is without any modifications.

## How to use these builds in Steam

1. Download a release from [**the releases page**](https://github.com/Kron4ek/proton-archive/releases)
2. Create a `~/.steam/root/compatibilitytools.d` directory
3. Extract the downloaded archive into `~/.steam/root/compatibilitytools.d`
4. Create a `~/.steam/root/compatibilitytools.d/BUILDNAME/compatibilitytool.vdf` file with such content (replace `BUILDNAME` with the name of the downloaded build):
```
   "compatibilitytools"
{
  "compat_tools"
  {
    "BUILDNAME" // Internal name of this tool
    {
      // Can register this tool with Steam in two ways:
      //
      // - The tool can be placed as a subdirectory in compatibilitytools.d, in which case this
      //   should be '.'
      //
      // - This manifest can be placed directly in compatibilitytools.d, in which case this should
      //   be the relative or absolute path to the tool's dist directory.
      "install_path" "."

      // For this template, we're going to substitute the display_name key in here, e.g.:
      "display_name" "BUILDNAME"

      "from_oslist"  "windows"
      "to_oslist"    "linux"
    }
  }
}
```
5. Restart Steam if it's already running
6. Now you can enable the downloaded Proton version in the `Compatibility` tab in the `Properties` of a game in Steam
