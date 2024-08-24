# Customizing VS Code Theme with Custom CSS

This guide will walk you through customizing your Visual Studio Code (VS Code) theme using a custom CSS file. By following these steps, you'll be able to apply custom styles to your VS Code interface.

https://github.com/user-attachments/assets/cc83db9a-ca1c-46b3-baf4-f26d51229a22


## Prerequisites

1. **Visual Studio Code** installed on your machine.
2. Download and install the following VS Code extensions:
   - [Dracula Official](https://marketplace.visualstudio.com/items?itemName=dracula-theme.theme-dracula) - A dark theme for VS Code.
   - [Custom CSS and JS Loader](https://marketplace.visualstudio.com/items?itemName=be5invis.vscode-custom-css) - Allows you to inject custom CSS and JS into VS Code.

## Steps to Apply Custom CSS

### 1. Create and Configure `custom.css`

- Create a CSS file named `custom.css`.
- Copy and paste the following code into the `custom.css` file:

  ```css
  .mtk10 {
      color: yellow;
      background-image: linear-gradient(45deg, #ff61d2, #fe908f);
      -webkit-text-fill-color: transparent;
      background-clip: text;
      font-weight: 700;
  }

  .mtk5 {
      color: #50fa7b;
      background-image: linear-gradient(45deg, #11998f, #38ef7d);
      -webkit-text-fill-color: transparent;
      background-clip: text;
      font-weight: 700;
  }

  .monaco-editor .detected-link, .monaco-editor .detected-link-active {
      text-decoration: none;
      text-underline-position: under;
      border-bottom: 4px dashed #efdf62;
  }

  .codicon-accounts-view-bar-icon:before {
      content: '';
      background-color: darkslateblue;
      width: 40px;
      height: 40px;
      border-radius: 50%;
      /* Edit the Image Path in the url() below */
      background-image: url(/your/avatar/icon/path.png);
      background-size: 100%;
  }

  .monaco-workbench .part.editor>.content .editor-group-container>.title .tabs-container>.tab.active.tab-border-top>.tab-border-top-container, 
  .monaco-workbench .part.editor>.content .editor-group-container>.title .tabs-container>.tab.selected.tab-border-top>.tab-border-top-container {
      z-index: 6;
      top: 0;
      height: 5px;
      background-color: var(--tab-border-top-color);
      background-image: linear-gradient(45deg, #11998f, #d13abd, #efbd8a, #11998f);
      background-size: 200% auto;
      animation: borderTopActive 4s linear infinite;
  }

  @keyframes borderTopActive {
      to {
          background-position: 200%;
      }
  }

## 2. Update `settings.json`

1. Open the Command Palette by going to `View > Command Palette...` or pressing `Ctrl + Shift + P`.
2. Search for and select `Preferences: Open Settings (JSON)`.
3. Add the following code to the `settings.json` file, replacing `***your file path***` with the full file path to your `custom.css` file, starting with `file:///`:

    ```json
    "vscode_custom_css.imports": [
      "file:///***your custom.css file path***"
    ]
    ```

## 3. Add Background Image (Optional)

If you want to add a background image for the `.codicon-accounts-view-bar-icon`, follow these steps:

1. Copy the path of your image file.
2. Replace the path in the `background-image` URL of the `.codicon-accounts-view-bar-icon:before` rule in `custom.css` with your file path, starting with `/`.

## 4. Apply the Custom CSS

1. After configuring `settings.json`, open the Command Palette again.
2. Type and select `Enable Custom CSS and JS`.
3. Restart VS Code for the changes to take effect.

## Notes

- Ensure that the path to your `custom.css` file and any background images are correct.
- If VS Code updates or the custom CSS doesn't apply, try running `Enable Custom CSS and JS` from the Command Palette again.

Enjoy your newly customized VS Code interface!
