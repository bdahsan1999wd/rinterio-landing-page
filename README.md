## ✅ Tailwind CLI + DaisyUI Setup: Full Checklist

This checklist will guide you through setting up Tailwind CSS and DaisyUI in your project.

1.  ✅ **Initialize Node.js project:**

    This command creates a `package.json` file, which is essential for managing your project's dependencies.

    ```bash
    npm init -y
    ```

2.  ✅ **Install Tailwind CLI & DaisyUI:**

    This command installs Tailwind CSS, Tailwind CLI (which processes your CSS), and DaisyUI (a component library for Tailwind).

    ```bash
    npm install tailwindcss@latest @tailwindcss/cli@latest daisyui@latest
    ```

3.  ✅ **Create `app.css` file:**

    Create a file named `app.css` in your project's root directory. This file will contain your main CSS, where you'll import Tailwind and DaisyUI styles.

    ```css
    /* ----------Google Fonts Added---------- */

    @import "tailwindcss";
    @source "./public/*.{html,js}"; /*----- Directs Tailwind to scan your HTML and JS files for Tailwind classes -----*/
    @plugin "daisyui" {
      themes: all; /*----- Imports all DaisyUI themes -----*/
    }

    /* ----------CSS Custom Styles Added---------- */
    @theme {
    }
    ```

4.  ✅ **Add `build:css` script to `package.json`:**

    This script defines a command (`npm run build:css`) that uses the Tailwind CLI to process your `app.css` and generate the final CSS output (`public/output.css`). The `--watch` flag tells Tailwind to watch for changes in your CSS and HTML files and automatically rebuild the CSS.

    ```json
    "scripts": {
      "build": "npx @tailwindcss/cli -i app.css -o public/output.css --watch"
    },
    ```

5.  ✅ **Build CSS:**

    Run this command in your terminal to generate the `output.css` file. If you have the `--watch` flag in your script, Tailwind will continue to watch for changes.

    ```bash
    npm run build
    ```

6.  ✅ **Create an HTML file and link the compiled CSS:**

    Create an HTML file (e.g., `public/index.html`). Link the generated `output.css` file in the `<head>` section of your HTML. The `data-theme="light"` attribute sets the default theme.

    ```html
    <!DOCTYPE html>
    <html lang="en" data-theme="light">
      <!-- Sets the language to English and default theme to 'light' using daisyUI -->
      <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />

        <!-- Title Added -->
        <title>Tailwind and daisyUI</title>

        <!-- Link to the compiled Tailwind CSS (with daisyUI if installed) -->
        <link rel="stylesheet" href="./output.css" />
      </head>
      <body></body>
    </html>
    ```

7.  ✅ **.gitignore Tips:**

    A `.gitignore` file specifies which files and directories should _not_ be included in your Git repository. This keeps your repository clean and avoids committing unnecessary files.

    Add the following to your `.gitignore` file:

    ```
    node_modules
    ```

    `node_modules`: This directory contains the Node.js packages you've installed. It can be huge and should not be committed.

    After cloning the project, use these commands:

    ```bash
    npm install      # Reinstalls the packages listed in package.json
    npm run build    # Regenerates the output.css file
    ```

✅ **Final Step:** Open `public/index.html` in your browser. DaisyUI and Tailwind CSS should be working perfectly!
