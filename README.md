# Boston House Pricing Prediction

## Software and Tools Requirements

Before starting, ensure you have the following tools and software installed:

1. [GitHub Account](https://github.com/): To host and manage your project repositories.
2. [VS Code IDE](https://code.visualstudio.com/): An easy-to-use integrated development environment (IDE) for coding.
3. [Heroku Account](https://heroku.com): For deploying the application to the cloud (optional).
4. [Git CLI](https://git-scm.com/book/en/v2/Getting-Started-The-Command-Line): Command-line tool for version control.
5. [Docker](https://www.docker.com/): To containerize your application for deployment.
6. [Conda](https://docs.conda.io/en/latest/): For managing Python environments.

---

## Steps to Set Up the Development Environment

### 1. Clone the Repository
If not already done, clone the repository and navigate into the project directory:

```bash
git clone https://github.com/divyam-kalwar/boston-house-pricing.git
```
```bash
cd boston-house-pricing
```

---

### 2. Create a Virtual Environment
To avoid conflicts with your existing Python setup, create a separate virtual environment:

```bash
conda create -n venv python==3.7 -y
```
```bash
conda activate venv
```

---

### 3. Install Dependencies
Install the required packages from the `requirements.txt` file:

```bash
pip install -r requirements.txt
```

---

### 4. Run the Application Locally
After setting up the environment and installing dependencies, run the Flask app locally:

```bash
python app.py
```

Check that the app is running at [http://127.0.0.1:5000](http://127.0.0.1:5000).

---

## Deployment Options

### 1. Deployment Using Heroku (Optional)
If you plan to deploy the application on Heroku, follow these steps:

#### Step 1: Log in to Heroku
Log in to your Heroku account using your web browser.

#### Step 2: Create a New App
- Create a new application on Heroku.
- Choose the GitHub deployment method and connect to your repository.

#### Step 3: Deploy the Application
Your application will be deployed once the setup is complete.

---

### 2. Deployment Using Docker
The repository contains the required Docker files for containerization.

#### Step 1: Build and Run the Docker Image Locally
Build the Docker image and run the container locally:

```bash
docker build -t boston-house-pricing .
```
```bash
docker run -p 8501:8501 boston-house-pricing
```

#### Step 2: Configure GitHub Secrets for Heroku Deployment
If deploying to Heroku via Docker, configure GitHub Actions:

1. Navigate to Settings → Secrets and variables → Actions → New repository secret.
2. Add the following secrets:
   - **HEROKU_EMAIL**
   - **HEROKU_API_KEY**
   - **HEROKU_APP_NAME**

#### Step 3: Test the Pipeline
1. Push changes to the `main` branch.
2. GitHub Actions will automatically build and push the Docker image to Heroku.

---

## Additional Notes

### Running Tests
If your project includes unit tests, ensure they pass before deploying:

```bash
pytest
```

### Debugging
Check the logs for debugging if the application fails locally or during deployment:

- Local Logs: View the logs in the terminal where the application is running.
- Heroku Logs: Use the Heroku CLI to view logs:
  ```bash
  heroku logs --tail
  ```

### Recommended Tools for Future Enhancements
- [Streamlit](https://streamlit.io/): For creating interactive visualizations and dashboards.
- [Jenkins](https://www.jenkins.io/): For building a CI/CD pipeline for automated testing and deployment.

---

Enjoy predicting Boston house prices with your new application!

