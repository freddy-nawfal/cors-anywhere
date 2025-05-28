# CORS Anywhere for Vercel

This is a simple CORS Anywhere server designed for easy deployment on Vercel.

## Deployment

1.  **Clone this repository (or create your own based on these files).**
2.  **Install Vercel CLI (if you haven't already):**
    ```bash
    npm install -g vercel
    ```
3.  **Deploy from your project directory:**
    ```bash
    vercel
    ```
    Follow the on-screen prompts. Vercel will automatically detect the `vercel.json` and `package.json` files and deploy the serverless function.

## Usage

Once deployed, your Vercel instance will act as a CORS proxy.

To use it, prepend your Vercel deployment URL to the URL you want to access.

For example, if your Vercel app is deployed at `my-cors-proxy.vercel.app` and you want to access `http://example.com/api/data`, you would use the following URL:

`https://my-cors-proxy.vercel.app/http://example.com/api/data`

The server will fetch the content from `http://example.com/api/data` and add the necessary CORS headers to the response, allowing you to access it from any origin in your frontend application.

## Configuration

*   **`vercel.json`**: Configures Vercel to rewrite all incoming requests to the `api/cors-anywhere.js` serverless function.
*   **`api/cors-anywhere.js`**: Contains the server logic using the `cors-anywhere` package. It's configured to allow all origins by default (`originWhitelist: []`). You can modify this if needed, but for a general proxy, an empty whitelist is common.
*   **`package.json`**: Defines the project dependencies, primarily `cors-anywhere`.
