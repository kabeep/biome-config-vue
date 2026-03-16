# biome-config-vue

A streamlined, production-ready **Biome** configuration template tailored for **Vue 3** projects (TS/JS). This template provides a solid foundation for linting, formatting, and organizing imports with a focus on Vue Single-File Components (SFC).

---

## 🚀 Quick Start

### Option 1: Use as a GitHub Template
Click the green **"Use this template"** button at the top of this page to create a new repository with this configuration pre-installed.

### Option 2: Add to an Existing Project
If you already have a project, you can pull this configuration directly:

```bash
curl -O https://raw.githubusercontent.com/kabeep/biome-config-vue/main/biome.jsonc
```

## 🛠 Features

- **Vue SFC Support**: Pre-configured globals for Vue macros (`defineProps`, `defineEmits`, `defineModel`, etc.) to prevent linter "undefined" errors.
    
- **VCS Integration**: Automatically respects your `.gitignore` and is synced with the `dev` branch.
    
- **Optimized Formatting**:
    
    - Single quotes for JS/JSX.
    
    - 2-space indentation.
    
    - 120-character line width for better readability on modern monitors.
    
- **Strict Linting**:
    
    - Enables `nursery` rules for the latest Biome improvements.
    
    - Strict `noUnusedImports` enforcement (set to `error`).
    
    - Complexity monitoring: Warns when a function exceeds 120 lines.
    
- **Auto-Organize**: Import sorting is enabled by default on save (via `assist`).

---

## ⚠️ Known Limitations: Vue + Less

As of the current version of Biome, there is a known limitation regarding **Less** support within Vue Single-File Components (SFC):

> **The Issue:** Biome's parser currently has experimental/incomplete support for `less` blocks inside `.vue` files. While standard CSS works, using `<style lang="less">` may cause the Biome CLI or IDE extension to throw parsing errors or fail to format that specific block.

**Current Workarounds in this Template:**

1. **CSS Formatter Disabled**: In this config, `"css": { "formatter": { "enabled": false } }` is set to prevent Biome from breaking your Less styles or throwing intrusive errors during the build process.

2. **External Files**: If you have complex Less logic, consider moving it to an external `.less` file.

3. **Alternative Linters**: For robust Less linting, it is recommended to use **Stylelint** alongside Biome until native SFC Less support matures.

---

## ⚙️ Configuration Highlight

This template includes specific overrides for `.vue` files to ensure a smooth development experience:

```
"overrides": [
  {
    "includes": ["src/**/*.vue"],
    "javascript": {
      "globals": [
        "defineEmits",
        "defineProps",
        "defineExpose",
        "defineModel",
        "defineOptions",
        "defineSlots",
        "withDefaults"
      ]
    }
  }
]
```

## 📄 License

This project is licensed under the [MIT License](LICENSE).