```markdown
# raycast-extensions Development Patterns

> Auto-generated skill from repository analysis

## Overview

This skill teaches you how to contribute to the `raycast-extensions` repository, which is a TypeScript-based monorepo for Raycast extensions. You'll learn the coding conventions, file structure, and the main workflows for adding, updating, and maintaining extensions, including asset management, changelog updates, and repository-level configuration.

## Coding Conventions

- **Language:** TypeScript
- **Framework:** None detected
- **File Naming:** Use `camelCase` for files and directories.
  - Example: `myExtension.ts`, `getUserData.ts`
- **Import Style:** Use alias imports.
  - Example:
    ```typescript
    import utils from "@/utils";
    ```
- **Export Style:** Use default exports.
  - Example:
    ```typescript
    export default function myFunction() { ... }
    ```
- **Commit Messages:** Freeform, usually concise (~41 characters), may use prefixes but not strictly enforced.

## Workflows

### Add New Extension
**Trigger:** When you want to contribute a brand new extension to Raycast.  
**Command:** `/add-extension`

1. Create a new directory under `extensions/{extension-name}/`.
2. Add configuration files: `.gitignore`, `.prettierrc`, `eslint.config.*`, and `tsconfig.json`.
3. Add `package.json` and `package-lock.json`.
4. Write `README.md` and `CHANGELOG.md`.
5. Add assets (icons, images) in `assets/` and screenshots in `metadata/`.
6. Implement main source files in `src/`.
7. Add utility files as needed.
8. Write initial tests if necessary.
9. Update `CHANGELOG.md` and optimize images.

**Example Directory Structure:**
```
extensions/
  myExtension/
    .gitignore
    .prettierrc
    eslint.config.js
    tsconfig.json
    package.json
    package-lock.json
    README.md
    CHANGELOG.md
    assets/
      icon.png
    metadata/
      screenshot.png
    src/
      index.ts
      utils.ts
```

---

### Feature Update Existing Extension
**Trigger:** When you want to add a new feature or major improvement to an existing extension.  
**Command:** `/feature-extension`

1. Modify or add source files in `extensions/{extension}/src/`.
2. Update or add assets/metadata if UI or icons change.
3. Update `package.json` or `package-lock.json` if dependencies or commands change.
4. Update `README.md` if user-facing behavior changes.
5. Update `CHANGELOG.md` to document the feature.

---

### Bugfix Extension
**Trigger:** When you want to fix a bug in an extension.  
**Command:** `/bugfix-extension`

1. Edit specific source files in `src/` to address the bug.
2. Update or add tests if needed.
3. Update `CHANGELOG.md` to document the fix.

---

### Update Extension Assets or Metadata
**Trigger:** When you want to refresh screenshots, icons, or metadata for an extension.  
**Command:** `/update-assets`

1. Add or update files in `assets/` and/or `metadata/`.
2. Update `package.json` if metadata fields change.
3. Update `CHANGELOG.md` to note asset/metadata changes.

---

### Update Changelog and Optimize Images
**Trigger:** When merging a PR or finalizing changes to an extension.  
**Command:** `/changelog-optimize-images`

1. Edit `CHANGELOG.md` to reflect the latest changes.
2. Optimize or compress images in `assets/` or `metadata/`.
3. Commit with a message mentioning changelog and image optimization.

---

### Update CODEOWNERS or GitHub Metadata
**Trigger:** When you want to change code ownership or update GitHub integration/configuration.  
**Command:** `/update-codeowners`

1. Edit `.github/CODEOWNERS`.
2. Optionally edit `.github/extensionName2Folder.json` or `.github/raycast2github.json`.
3. Commit with a message referencing CODEOWNERS.

---

## Testing Patterns

- **Testing Framework:** [vitest](https://vitest.dev/)
- **Test File Pattern:** Files end with `.test.ts` and are placed alongside or near the code under test.
- **Example Test File:**
  ```typescript
  // src/utils.test.ts
  import { describe, it, expect } from "vitest";
  import myFunction from "./utils";

  describe("myFunction", () => {
    it("should return true", () => {
      expect(myFunction()).toBe(true);
    });
  });
  ```

## Commands

| Command                      | Purpose                                                              |
|------------------------------|----------------------------------------------------------------------|
| /add-extension               | Add a new extension to the repository                                |
| /feature-extension           | Add a new feature or major improvement to an existing extension      |
| /bugfix-extension            | Fix a bug in an existing extension                                   |
| /update-assets               | Update screenshots, icons, or metadata for an extension              |
| /changelog-optimize-images   | Update the extension's changelog and optimize images                 |
| /update-codeowners           | Update repository-level CODEOWNERS or GitHub metadata/config files    |
```