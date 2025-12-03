# Saturn Magnetic Field Explorer

Interactive 3D visualization of Saturn's magnetic field using the Cassini 11 model.

## Live Demo

Visit: https://YOUR_USERNAME.github.io/saturn-magnetic-field/

## Features

- **Interactive L-shell slider**: View magnetic field lines from L=1 to L=30
- **Adjustable range**: Show field lines within ±0.1 to ±5 of selected L-shell
- **3D orbit controls**: Drag to rotate, scroll to zoom
- **Saturn with texture and rings**
- **Auto-rotate option**

## L-shell Values

The visualization includes field lines at:
- L = 1.00 to 2.00 in steps of 0.01 (101 values)
- L = 2.1 to 10.0 in steps of 0.1 (80 values)  
- L = 10.5 to 30.0 in steps of 0.5 (40 values)

Total: 221 unique L-shell configurations

## Deployment to GitHub Pages

1. Create a new GitHub repository (e.g., `saturn-magnetic-field`)

2. Push this folder to the repository:
   ```bash
   cd saturn_web_viewer
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/saturn-magnetic-field.git
   git push -u origin main
   ```

3. Enable GitHub Pages:
   - Go to repository Settings → Pages
   - Source: Deploy from a branch
   - Branch: main, folder: / (root)
   - Click Save

4. Your site will be live at `https://YOUR_USERNAME.github.io/saturn-magnetic-field/`

## Local Development

Simply open `index.html` in a modern browser. No build step required.

For local testing with a server:
```bash
python3 -m http.server 8000
# Then visit http://localhost:8000
```

## Credits

- Magnetic field model: Cassini 11 (Dougherty et al.)
- Saturn texture: NASA/Hubble
- Built with Three.js
