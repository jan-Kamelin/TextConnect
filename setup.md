# TextConnect Setup Documentation

This documentation provides step-by-step instructions to set up a new instance of TextConnect, a simple text-only social media platform. Follow these steps to get your instance up and running on GitHub Pages.

## Prerequisites

Before you begin, ensure you have the following:
- A GitHub account
- Basic knowledge of HTML and GitHub Pages

## Step 1: Create a New Repository on GitHub

1. Log in to your GitHub account.
2. Click on the `+` icon in the top-right corner and select `New repository`.
3. Name your repository (e.g., `TextConnect`).
4. Add a description if you like.
5. Set the repository to `Public`.
6. Initialize the repository with a README file.
7. Click `Create repository`.

## Step 2: Clone the Repository to Your Local Machine

1. Open a terminal or command prompt.
2. Clone the repository using the following command:

    ```bash
    git clone https://github.com/your-username/TextConnect.git
    ```

3. Navigate to the repository directory:

    ```bash
    cd TextConnect
    ```

## Step 3: Create HTML Files

1. Create the following HTML files in the repository directory:
    - `index.html`
    - `privacy-policy.html`
    - `terms.html`
    - `about.html`

2. Copy and paste the corresponding HTML code into each file from the documentation provided.

## Step 4: Update the HTML Files

1. Open each HTML file and update the placeholder values such as:
    - [your contact email]
    - [Your Name]
    - [Your Country/State]
    - Effective Date

2. Save the changes to each file.

## Step 5: Commit and Push Changes to GitHub

1. Add the new files to the repository:

    ```bash
    git add .
    ```

2. Commit the changes with a message:

    ```bash
    git commit -m "Add initial HTML files for TextConnect"
    ```

3. Push the changes to GitHub:

    ```bash
    git push origin main
    ```

## Step 6: Enable GitHub Pages

1. Go to your repository on GitHub.
2. Click on `Settings`.
3. Scroll down to the `Pages` section.
4. Under `Source`, select the branch you want to deploy from (e.g., `main` or `master`).
5. Click `Save`.
6. Your site should be live at `https://<your-username>.github.io/<repository-name>`.

## Step 7: Set Up Google Form and Sheet

1. Create a Google Form with the following fields:
    - Username
    - Password
    - Post Content

2. Link the Google Form responses to a Google Sheet.

3. Publish the Google Sheet as a CSV:
    - Open the Google Sheet linked to your form responses.
    - Click on `File` > `Publish to the web`.
    - Under the `Link` tab, select `Comma-separated values (.csv)` for the sheet containing the form responses.
    - Click `Publish` and copy the provided link.

4. Update the `sheetUrl` in the `index.html` file with the published CSV URL.

## Step 8: Customize Your Instance

1. Update the content of the `about.html` file to provide information about your specific instance of TextConnect.
2. Make any additional customizations to the HTML and CSS to fit your needs.

## Step 9: Test Your Site

1. Open your GitHub Pages URL in a web browser.
2. Verify that the form submissions and posts are displayed correctly.
3. Make sure all links (Privacy Policy, Terms of Service, About) work correctly.

## Contact

If you have any questions or need assistance, feel free to contact us at [jankamelin@movim.eu](xmpp:jankamelin@movim.eu).

---

Congratulations! You have successfully set up a new instance of TextConnect.
