# VESTA

A polished static landing-page prototype for VESTA — an intelligent virtual fitting mirror.

## Run locally

No build system is required.

1. Download/clone the repository.
2. Open `index.html` in a browser.

For the best local development experience, use VS Code + Live Server.

## Deploy with GitHub Pages

1. Create a new GitHub repository.
2. Upload `index.html` and the `assets` folder.
3. Go to **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select the `main` branch and `/ (root)`.
6. Save. GitHub will provide the published URL.

## Assets

The `assets` folder contains the photorealistic fashion imagery/crops used by the prototype.

The current garment selector is a UI prototype. Selecting a garment changes the selected state and demonstrates the interaction; it does not yet perform real AI garment transfer.

## Next technical step

For a production virtual try-on experience, connect the mirror interface to a real virtual try-on model/API. The front-end can then send a user's image/body pose plus the selected garment and display the generated result.
