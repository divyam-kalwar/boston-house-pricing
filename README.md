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

Log in to your Heroku account using the CLI:

```bash
heroku login
```

Create a new Heroku app:

```bash
heroku create your-app-name
```

Add a `Procfile` to the root of your project. The `Procfile` should contain:

```txt
web: gunicorn app:app
```

This tells Heroku how to run your Flask application using gunicorn (a production WSGI server).

Commit the changes and push to Heroku:

```bash
git add .
git commit -m "Initial commit"
git push heroku master
```

Open the app in your browser:

```bash
heroku open
```

### Additional Steps

#### Run the Application Locally

After setting up your environment and installing dependencies, you can run the Flask app locally with:

```bash
python app.py
```

Make sure the app is running on your local server (usually http://127.0.0.1:5000).

#### Deploy to Heroku (if applicable)

After completing the local setup, if you wish to deploy, follow the Heroku deployment steps mentioned earlier.

