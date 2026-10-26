# ZeroClient Launcher (Windows starter project)

A Windows Electron desktop starter with a neon lime/pink/black original UI, a live Mojang Java version-manifest selector, Modrinth project search, featured server shortcuts, and Microsoft/offline account UI placeholders.

## Requirements
- Windows 10/11 64-bit
- Node.js LTS (includes npm)
- Internet connection for version manifest and Modrinth search

## Run the UI locally
1. Extract the ZIP.
2. Open the extracted `ZeroClient` folder in a terminal.
3. Run `npm install`
4. Run `npm start`

## Build a Windows installer
Run in the project folder:

```powershell
npm install
npm run dist:win
```
The installer should be created in `dist/` after the build succeeds. Building on Windows is recommended.

## Important status / next engineering steps
This is a runnable **launcher UI starter**, not yet a complete Minecraft launcher. The Launch button intentionally reports that the game backend is not integrated. Before distributing a real launcher, implement:
- Microsoft OAuth and Minecraft Services entitlement/profile checks using a secure, registered application and a maintained auth library.
- Minecraft asset/library downloads, Java runtime management, version JSON processing, mod-loader installation (Fabric/Forge/NeoForge), launch arguments, logs and crash handling.
- Actual multiplayer server-list editing in each Minecraft installation. The current Join buttons copy the server address; they do not edit `servers.dat` or launch Minecraft.
- Mod installation with version/loader compatibility checks and dependency handling. Modrinth search is connected; its Open links open the project page. CurseForge API use requires an API key and must be implemented behind a backend or otherwise handled without exposing secrets.
- Create and add an original `src/icon.ico` icon if you want a custom Windows executable icon; the starter currently builds without a custom ICO file.

Do not use this project to collect Microsoft passwords. Use the official Microsoft sign-in flow and never ask users to type their Microsoft password directly into the launcher.
