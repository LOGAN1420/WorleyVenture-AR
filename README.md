# Business Card AR Experience

This project creates an interactive AR experience that triggers when pointing a camera at your business card.

## Features

- **3D Business Information**: Floating name and title with rotation animation
- **Interactive Contact Cards**: Email and phone information with hover effects
- **Social Media Links**: Twitter, LinkedIn, and GitHub buttons
- **Animated Elements**: Rotating logo and floating particles
- **Responsive Design**: Works on mobile and desktop browsers

## Setup Instructions

### 1. Generate NFT Marker Files

You need to create NFT (Natural Feature Tracking) marker files from your business card image:

#### Option A: Using AR.js NFT Marker Creator (Recommended)
1. Visit: https://carnaux.github.io/NFT-Marker-Creator/
2. Upload a high-quality image of your business card (JPG/PNG)
3. Wait for processing (can take several minutes)
4. Download the generated files (.fset, .fset3, .iset)
5. Create a `markers/` folder in your project
6. Place the files in `markers/` and name them `business-card` (without extensions)

#### Option B: Using AR.js NFT Marker Creator CLI
```bash
npm install -g @ar-js-org/nft-marker-creator
nft-marker-creator path/to/your-business-card.jpg
```

### 2. File Structure
```
project/
├── business-card-ar.html
├── markers/
│   ├── business-card.fset
│   ├── business-card.fset3
│   └── business-card.iset
└── README.md
```

### 3. Customize Content

Edit the HTML file to personalize:

- **Name and Title**: Update the `a-text` value in line ~85
- **Contact Information**: Modify email and phone in the contact cards
- **Social Media**: Update platform names and add click handlers
- **Colors**: Change the color scheme by modifying color attributes
- **3D Models**: Replace the simple box with your logo (GLTF format)

### 4. Running the Experience

1. Serve the files using a local web server (required for camera access):
   ```bash
   # Using Python
   python -m http.server 8000
   
   # Using Node.js
   npx serve .
   
   # Using PHP
   php -S localhost:8000
   ```

2. Open `http://localhost:8000/business-card-ar.html` in your browser
3. Allow camera permissions
4. Point camera at your business card

## Tips for Best Results

### Business Card Image Quality
- **High Resolution**: Use at least 1200x800px image
- **Good Contrast**: Ensure text and graphics are clearly visible
- **Avoid Reflective Materials**: Matte finish works better than glossy
- **Rich Visual Features**: Cards with logos, patterns, or unique designs track better
- **Avoid Plain Text**: Cards with only text may not track well

### Lighting and Environment
- **Good Lighting**: Ensure the card is well-lit without harsh shadows
- **Steady Hands**: Keep the card and camera as stable as possible
- **Appropriate Distance**: Hold card 20-40cm from camera
- **Avoid Glare**: Position to minimize reflections

## Customization Examples

### Adding Click Actions
```javascript
// Add to the script section
document.querySelector('.email-card').addEventListener('click', function() {
    window.open('mailto:john@example.com');
});

document.querySelector('.phone-card').addEventListener('click', function() {
    window.open('tel:+15550123');
});
```

### Loading Custom 3D Models
```html
<!-- In a-assets -->
<a-asset-item id="logo" src="./assets/logo.gltf"></a-asset-item>

<!-- Replace the a-box with -->
<a-entity gltf-model="#logo" scale="0.1 0.1 0.1" position="0 1 0"></a-entity>
```

### Adding Sound Effects
```html
<!-- In a-assets -->
<audio id="click-sound" src="./assets/click.mp3" preload="auto"></audio>

<!-- Add to click handlers -->
<script>
document.querySelector('.clickable').addEventListener('click', function() {
    document.querySelector('#click-sound').play();
});
</script>
```

## Troubleshooting

### Camera Not Working
- Ensure HTTPS or localhost (required for camera access)
- Check browser permissions
- Try different browsers (Chrome/Firefox recommended)

### Marker Not Detected
- Verify marker files are correctly named and placed
- Check business card image quality
- Ensure good lighting conditions
- Try different angles and distances

### Performance Issues
- Reduce 3D model complexity
- Lower animation frame rates
- Test on different devices

## Browser Compatibility

- ✅ Chrome (Android/Desktop)
- ✅ Firefox (Android/Desktop)
- ✅ Safari (iOS/macOS)
- ❌ Internet Explorer (not supported)

## Next Steps

1. Replace placeholder content with your actual information
2. Generate NFT markers from your business card
3. Test the experience thoroughly
4. Consider hosting on a web server for sharing
5. Add analytics to track usage

## Resources

- [AR.js Documentation](https://ar-js-org.github.io/AR.js-Docs/)
- [A-Frame Documentation](https://aframe.io/docs/)
- [NFT Marker Creator](https://carnaux.github.io/NFT-Marker-Creator/)
