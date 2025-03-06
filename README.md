# Thermos Studio Homepage

Homepage for Thermos Studio, which links to our applications.

## First-Time Firebase Setup

1. Start a new project at console.firebase.google.com.
2. In terminal at project repo:
    ```bash
    npm install -g firebase-tools
    firebase login
    firebase init hosting --no-overwrite # see step 3 for more options
    ```
3. Select Init options:
    - Choose existing project
    - Use as public directory? `public`
    - Configure as a spa? `No`
    - Set up automatic builds and deploy with GitHub? `No`
        - Setting up GitHub Actions afterwards avoids common service account issues with the firebase init command.
4. `firebase deploy`

## Local Development

A VSCode Dev Container is used for development. Upon launching, an http server is started and can be accessed at: `http://localhost:8080`

## GitHub Actions Deployment Setup

This project is configured to automatically deploy to Firebase when pushed to the `main` branch. To set up:

1. Generate a Firebase CI token:
   ```
   firebase login:ci
   ```
   This will provide you with a token to use in GitHub Actions.

2. Add the token to your GitHub repository as a Secret:
   - In your GitHub repository: Settings > Secrets and variables > Actions > "New repository secret"
     - Name: `FIREBASE_TOKEN`
     - Value: [The token you received from the login:ci command]

Upon pushes to `main`, the GitHub Actions workflow will automatically deploy the site to Firebase. This site is live at https://thermos.studio after deployment.

## Custom Domain Setup

Once deployed, you'll need to set up custom domain in the Firebase console:

1. Go to the Firebase console
2. Navigate to Hosting
3. Click "Add custom domain"
4. Follow the instructions to verify and configure your domain