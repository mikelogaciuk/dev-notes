# Themes

## List

List of good themes for VSCode (mainly Rainglow variants):

### Dark

- defdo
- Rose Pine
- Violaceus
- Brave
- Crackpot
- Heroku
- Mosaic
- Omni
- Prime
- Catppucin
- Hack The Box

### Light

- Crackpot
- Iceberg Light
- Peacocks in Space

## Tweaks

Additional tweaks for VSCode:

```json
{
  "terminal.integrated.defaultProfile.linux": "zsh",
  "terminal.external.linuxExec": "/bin/bash",
  "window.menuBarVisibility": "toggle",
  "@azure.argTenant": "",
  "workbench.colorTheme": "Rosé Pine Moon",
  "workbench.activityBar.location": "bottom",
  "workbench.editor.showTabs": "single",
  "workbench.statusBar.visible": false,
  "workbench.startupEditor": "none",
  "workbench.tips.enabled": false,
  "editor.minimap.enabled": false,
  "breadcrumbs.enabled": false,
  "workbench.sideBar.location": "right",
  "workbench.iconTheme": "material-icon-theme",
  "material-icon-theme.hidesExplorerArrows": true,
  "workbench.tree.enableStickyScroll": false,
  "workbench.tree.renderIndentGuides": "none",
  "workbench.tree.indent": 16,
  "explorer.compactFolders": false,
  "explorer.confirmDragAndDrop": false,
  "explorer.confirmDelete": false,
  "editor.gotoLocation.multipleDefinitions": "goto",
  "window.customTitleBarVisibility": "auto",
  "editor.cursorBlinking": "smooth",
  "editor.cursorStyle": "block",
  "terminal.integrated.fontFamily": "'CaskaydiaCove Nerd Font', Consolas, Monaco, 'Courier New', monospace",
  "terminal.integrated.fontSize": 13,
  "editor.wordWrap": "on",
  "editor.fontFamily": "'VictorMono Nerd Font', 'CaskaydiaCove Nerd Font', 'JetBrainsMono', 'CaskaydiaCove Nerd Font Mono SemiBold', monospace",
  "editor.fontSize": 14,
  "editor.fontLigatures": true,
  "editor.fontWeight": 650,
  "editor.lineHeight": 1.5,
  "editor.scrollbar.horizontal": "hidden",
  "editor.scrollbar.vertical": "hidden",
  "editor.tokenColorCustomizations": {
    "textMateRules": [
      {
        "scope": [
          // Keywords to be in italic
          "comment", // As it is
          //"entity.name.type.class", // class names
          //"constant", // String, Number, Boolean..., this, super
          "support.function", // console.log, etc
          "keyword", // import, export, return...
          "keyword.control", // if, else, switch, case, break...
          "keyword.control.flow", // for, while, do, continue
          "storage.type", // var, let, const, function, class...
          "storage.modifier", // static keyword
          "storage.type.class.js", // class keyword
          "variable.parameter", // function parameters
          "variable.other", // Elixir function parameters
          "entity.name.function.decorator.python", // Python decorators
          "entity.name.function.member" // Ruby DSL's methods
        ],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "scope": [
          // Keywords to exclude from italics (VSCode has some defaults for italics)
          "entity.name.function", // function names
          "invalid",
          "keyword.operator",
          "constant.numeric.css",
          "keyword.other.unit.px.css",
          "constant.numeric.decimal.js",
          "constant.numeric.json"
        ],
        "settings": {
          "fontStyle": ""
        }
      }
    ]
  },
  "files.associations": {
    "*.css": "tailwindcss"
  },
  "editor.quickSuggestions": {
    "strings": "on"
  },
  "tailwindCSS.includeLanguages": {
    "plaintext": "html"
  },
  "github.copilot.editor.enableAutoCompletions": false,
  // "github.copilot.enable": { "*": true }, // Enable for all languages
  "github.copilot.enable": {}
}
```
