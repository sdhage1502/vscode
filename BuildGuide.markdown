# Custom VS Code Build with Wingman AI

This guide provides simple steps to build a custom Visual Studio Code (VS Code) with the Wingman AI extension integrated as a native feature, hidden from the Extensions panel, using `npm`.

## Prerequisites
- Node.js (18.x or later) with npm.
- Python (3.8 or later).
- Git.
- Windows Build Tools (install via npm).
- Visual Studio Community 2022 (with C++ Desktop Development).

Verify tools in your terminal.

## Build Instructions

### 1. Clone VS Code
Clone the VS Code repository and install dependencies.

```bash
git clone https://github.com/microsoft/vscode.git
cd vscode
npm install
```

### 2. Add Wingman AI Extension
Clone Wingman AI and copy it to the extensions folder.

```bash
git clone https://github.com/RussellCanfield/wingman-ai.git
mkdir extensions\wingman-ai
copy wingman-ai\* extensions\wingman-ai
cd extensions\wingman-ai
npm install
cd ..\..
```

### 3. Integrate Wingman AI
Edit `build/lib/builtInExtensions.ts` to make Wingman AI a built-in extension.

### 4. Hide Wingman AI
Edit `src/vs/workbench/contrib/extensions/browser/extensionsViewlet.ts` to hide Wingman AI from the Extensions panel.

### 5. Compile VS Code
Build the custom VS Code.

```bash
npm run compile
```

### 6. Run Output Screen
Run the output screen using the script.

```bash
.\scripts\code.bat
```

This script launches the custom VS Code build to display the output.

## Upgrade Guide
To update with new versions:
- Pull updates for VS Code and Wingman AI using `git pull`.
- Re-run `npm install`, apply changes to configuration files, and rebuild with `npm run compile`.
- Save changes as a patch for future use.

## Notes
- Wingman AI is integrated as a native feature.
- All VS Code functionality is preserved.
- Deliverables: source code and this `README.md`.
- No unlicensed code used.
