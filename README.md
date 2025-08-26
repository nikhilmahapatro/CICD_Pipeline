# CICD Pipeline (Demo)

Minimal example of setting up a CI/CD pipeline using **GitHub Actions** and **Docker** for a Python app.

> Shows how code changes trigger build, test, and deployment automatically.

## 🔧 What it does
- Runs unit tests on every push (Pytest).
- Builds a Docker image of the app.
- Pushes the image to GitHub Container Registry.
- Deploy-ready workflow using GitHub Actions.

## 📂 Repo includes
app.py # Simple Python app
test_app.py # Basic unit test
requirements.txt # Dependencies
Dockerfile # Container setup
.github/workflows/ # CI/CD pipeline config
└── main.yaml


## 💻 How to run locally
```bash
# Clone the repo
git clone https://github.com/nikhilmahapatro/CICD_Pipeline.git
cd CICD_Pipeline

# Install dependencies
pip install -r requirements.txt

# Run tests
pytest

# Build and run Docker image
docker build -t cicd-demo .
docker run -p 5000:5000 cicd-demo
```

## ⚙️ How the pipeline works
flowchart TD
    A[Push Code to GitHub] --> B[GitHub Actions Trigger]
    B --> C[Install Dependencies]
    C --> D[Run Tests]
    D --> E[Build Docker Image]
    E --> F[Push Image to Registry]
    F --> G[Ready for Deployment]
