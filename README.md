# AbbVie (or Dynamic CIK) Shares Outstanding Viewer

This single-file web application fetches and displays the maximum and minimum shares outstanding for a given company (defaulting to AbbVie) from the SEC EDGAR API.

## Features

*   **Dynamic CIK Fetching**: Fetches data for AbbVie (CIK 0001551152) by default, or for any specified 10-digit CIK via a URL query parameter.
*   **Data Filtering**: Filters SEC data for `EntityCommonStockSharesOutstanding` entries with fiscal years (FY) greater than 2020 and valid numeric values.
*   **Max/Min Calculation**: Identifies and displays the highest and lowest shares outstanding values along with their respective fiscal years.
*   **Responsive UI**: Fully responsive and modern design using Tailwind CSS CDN.
*   **Single-file HTML**: All code (HTML, CSS via Tailwind CDN, JavaScript) is contained within a single `index.html` file, making it easy to deploy.
*   **Inline JavaScript**: No external JS files, simplifying local execution.
*   **No Page Reloads**: When a CIK is changed via the URL, the data updates dynamically without a full page reload.

## Usage

1.  **Save the file**: Save the provided `index.html` file to your local machine.
2.  **Open in Browser**: Open the `index.html` file using any modern web browser.

    *   By default, it will display data for **AbbVie (CIK: 0001551152)**.

3.  **Specify a Different CIK**: To view data for another company, append a `?CIK=` query parameter to the URL in your browser's address bar. For example:

    ```
    file:///path/to/your/index.html?CIK=0001018724
    ```

    (Replace `0001018724` with the 10-digit CIK of the company you wish to view. E.g., Apple Inc. CIK is 0000320193).

    The page content will update dynamically without a full reload.

## Data Source

Data is sourced from the [SEC EDGAR API](https://www.sec.gov/edgar/sec-api-documentation).

## Important Notes on SEC API Usage

*   **User-Agent**: The SEC API guidance requests a descriptive User-Agent. However, direct `fetch` requests from client-side JavaScript in a web browser cannot set custom `User-Agent` headers for cross-origin requests due to browser security policies. The browser's default User-Agent is used instead.
*   **Rate Limits**: The SEC imposes rate limits on API requests (typically 10 requests per second, with bursts permitted). Excessive requests may lead to temporary blocking. For robust production applications or heavy usage, it is strongly recommended to implement a server-side proxy to manage requests, set appropriate headers (including `User-Agent`), and handle caching.

## `uid.txt`

The `uid.txt` file is included as requested. Its specific purpose or content was not provided in the prompt, so it contains a placeholder value.

## Development

This application is built with:

*   **HTML5**
*   **Tailwind CSS CDN**: For responsive and modern styling.
*   **Vanilla JavaScript**: For data fetching, processing, and DOM manipulation.

Feel free to inspect the `index.html` file to understand the inline JavaScript logic and styling.
