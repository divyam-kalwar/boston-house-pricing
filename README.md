# Boston House Pricing Prediction

## Software and Tools Requirements

Before starting, make sure you have the following tools and software installed:

1. [Github Account](https://github.com/): To host and manage your project repositories.
2. [VS Code IDE](https://code.visualstudio.com/): An easy-to-use integrated development environment (IDE) for coding.
3. [Heroku Account](https://heroku.com): For deploying the application in the cloud (optional if you're deploying).
4. [Git CLI](https://git-scm.com/book/en/v2/Getting-Started-The-Command-Line): Command-line tool for version control.

## Steps to Set Up the Development Environment
### 1. Clone the Repository (if not already done):
```bash
git clone https://github.com/divyam-kalwar/boston-house-pricing.git
```
```bash
cd boston-house-pricing
```
### 2. Create a Virtual Environment

To avoid any potential conflicts with your existing Python setup, it's recommended to create a separate virtual environment.

Run the following commands to create and activate your environment:

```bash
conda create -n venv python==3.7 -y
```
```bash
conda activate venv
```

### 3. Install Dependencies from the requirements.txt File:

Once the `requirements.txt` file is ready, install the packages by running:

```bash
pip install -r requirements.txt
```

### 4. Prepare Your Application for Deployment (Optional)

If you're planning to deploy the application, you can follow these steps for setting up Heroku:

1. Log in to your Heroku account using your web browser.
2. Create new app.
3. Choose the Github deployment Method and connect to your repository.
4. Your application is deployed.

### 5. Deployment using Docker

I have added all the required docker files to the repository.

#### 1. Configure GitHub Secrets
After creating app in the Heroku. Add the Heroku credentials in your repository using GitHub action.
1. Go to Settings → Secrets and variables → Actions → New repository secret.
2. Add:
* HEROKU_EMAIL
* HEROKU_API_KEY
* HEROKU_APP_NAME
#### 2. Test Your Pipeline
1. Push changes to the main branch.
2. GitHub Actions will automatically build and push the Docker image to Heroku.

### Additional Steps

#### Run the Application Locally

After setting up your environment and installing dependencies, you can run the Flask app locally with:

```bash
python app.py
```

Make sure the app is running on your local server (usually http://127.0.0.1:5000).

#### Deploy to Heroku (if applicable)

After completing the local setup, if you wish to deploy, follow the Heroku deployment steps mentioned earlier.