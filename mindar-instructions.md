# MindAR.js Implementation Instructions

## Generating the Target File

To use MindAR.js, you need to create a `.mind` target file from your business card image. Follow these steps:

### Option 1: Online Compiler (Easiest)

1. Go to the [MindAR Image Compiler](https://hiukim.github.io/mind-ar-js-doc/tools/compile/)
2. Upload your business card image
3. Click "Compile" and wait for the process to complete
4. Download the generated `.mind` file
5. Save it as `targets.mind` in the same directory as your HTML file

### Option 2: Using Node.js CLI

If you prefer using the command line:

1. Install the MindAR CLI tool:
   ```
   npm install -g @hiukim/mind-ar-js
   ```

2. Run the compiler:
   ```
   mindar-image-compiler <path-to-image-file> <output-directory>
   ```

3. Rename the output file to `targets.mind` and place it in your project directory

## Testing the AR Experience

1. You need to serve the files via HTTPS (required for camera access)
2. Use a local development server or deploy to GitHub Pages
3. Access the page on a mobile device
4. Point your camera at the business card
5. You should see the blue overlay and "Hello MindAR!" text appear

## Troubleshooting

- If the target isn't detected, try improving lighting conditions
- Make sure your business card has enough distinct features for tracking
- Check the browser console for any errors
- The debug panel will show the current status of the AR system
