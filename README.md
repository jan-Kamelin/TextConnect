# TextConnect

TextConnect is a simple text-only social media website where users can submit posts using a Google Form. The submitted posts are displayed dynamically by fetching data from a Google Sheet published as a CSV.

## Features

- **Submit Posts**: Users can submit posts through an embedded Google Form.
- **View Posts**: Submitted posts are displayed dynamically on the website.
- **Simple Design**: Clean and minimalistic design with a gray and blue theme.

## Main Instance

The main instance of TextConnect is located at [jan-kamelin.github.io/TextConnect](https://jan-kamelin.github.io/TextConnect).

## Setup Instructions

Follow these steps to set up and deploy TextConnect on GitHub Pages:

### 1. Create Google Form

1. Create a Google Form with the following fields:
   - Username
   - Password
   - Post Content

2. Link the Google Form responses to a Google Sheet.

### 2. Publish Google Sheet as CSV

1. Open the Google Sheet linked to your form responses.
2. Click on `File` > `Publish to the web`.
3. Under the `Link` tab, select `Comma-separated values (.csv)` for the sheet containing the form responses.
4. Click `Publish` and copy the provided link.

### 3. Update HTML Code

1. Use the following HTML code for your website:

    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>TextConnect</title>
        <style>
            body {
                font-family: Arial, sans-serif;
                background-color: #f0f0f0;
                color: #333;
                margin: 0;
                padding: 0;
            }

            header {
                background-color: #007bff;
                color: white;
                padding: 1rem;
                text-align: center;
            }

            main {
                padding: 1rem;
            }

            #form-section, #posts-section {
                background-color: #ffffff;
                border: 1px solid #ccc;
                border-radius: 5px;
                margin-bottom: 1rem;
                padding: 1rem;
            }

            h2 {
                color: #007bff;
            }

            .post {
                border-bottom: 1px solid #ccc;
                padding: 1rem 0;
            }

            .post:last-child {
                border-bottom: none;
            }
        </style>
    </head>
    <body>
        <header>
            <h1>TextConnect</h1>
        </header>
        <main>
            <section id="form-section">
                <h2>Submit Your Post</h2>
                <iframe src="https://docs.google.com/forms/d/e/1FAIpQLSdyHWOoXPmm_SsSil5p-PU5m0loSVvAGCI2B6wl1zFrkJMJWQ/viewform?embedded=true" frameborder="0" style="width:100%; height:500px; border:none;"></iframe>
            </section>
            <section id="posts-section">
                <h2>Recent Posts</h2>
                <div id="posts-container"></div>
            </section>
        </main>

        <script>
            document.addEventListener("DOMContentLoaded", function() {
                const sheetUrl = 'https://docs.google.com/spreadsheets/d/e/2PACX-1vQMKhgL1rxtAvWQcUnh3ijRCWoq95ZX7B8CJybejegLLinZR-agPYQ0y0yeA4L7AMnRzu5EWrnye9UU/pub?gid=112872717&single=true&output=csv';

                fetch(sheetUrl)
                    .then(response => response.text())
                    .then(csvText => {
                        const rows = csvText.split('\n').slice(1); // Remove header
                        const postsContainer = document.getElementById('posts-container');
                        rows.forEach(row => {
                            const columns = row.split(','); // Split columns by comma
                            if (columns.length >= 3) {
                                const username = columns[0].trim(); // Get username
                                const postContent = columns[2].trim(); // Get post content
                                const postElement = document.createElement('div');
                                postElement.className = 'post';
                                postElement.innerHTML = `
                                    <p><strong>${username}</strong></p>
                                    <p>${postContent}</p>
                                `;
                                postsContainer.appendChild(postElement);
                            }
                        });
                    })
                    .catch(error => {
                        console.error('Error fetching or parsing data:', error);
                    });
            });
        </script>
    </body>
    </html>
    ```

2. Replace the `sheetUrl` in the script with your published CSV URL.

### 4. Deploy on GitHub Pages

1. Create a new repository on GitHub.
2. Name the repository (e.g., `TextConnect`).
3. Clone the repository to your local machine.
4. Add the updated HTML file to the repository.
5. Commit and push the changes to GitHub.
6. Go to the repository settings on GitHub.
7. Scroll down to the "GitHub Pages" section.
8. Select the branch you want to deploy from (e.g., `main` or `master`) and click "Save".
9. Your site should be live at `https://<your-username>.github.io/<repository-name>`.

## Usage

- **Submit Posts**: Users can submit posts by filling out the form embedded on the website.
- **View Posts**: Submitted posts will be displayed under the "Recent Posts" section.

## License

This project is licensed under the MIT License.
