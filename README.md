# MyAgent

my-awesome-agent
A agent implementing a base ReAct agent using LangGraph Agent generated with googleCloudPlatform/agent-starter-pack version 0.2.3

Project Structure
This project is organized as follows:

my-awesome-agent/
├── app/                 # Core application code
│   ├── agent.py         # Main agent logic
│   ├── agent_engine_app.py # Agent Engine application logic
│   └── utils/           # Utility functions and helpers
├── deployment/          # Infrastructure and deployment scripts
├── notebooks/           # Jupyter notebooks for prototyping and evaluation
├── tests/               # Unit, integration, and load tests
├── Makefile             # Makefile for common commands
└── pyproject.toml       # Project dependencies and configuration
Requirements
Before you begin, ensure you have:

uv: Python package manager - Install
Google Cloud SDK: For GCP services - Install
Terraform: For infrastructure deployment - Install
make: Build automation tool - Install (pre-installed on most Unix-based systems)
Quick Start (Local Testing)
Install required packages and launch the local development environment:

make install && make playground
Commands
Command	Description
make install	Install all required dependencies using uv
make playground	Launch Streamlit interface for testing agent locally and remotely
make backend	Deploy agent to Agent Engine service
make test	Run unit and integration tests
make lint	Run code quality checks (codespell, ruff, mypy)
make setup-dev-env	Set up development environment resources using Terraform
uv run jupyter lab	Launch Jupyter notebook
For full command options and usage, refer to the Makefile.

Usage
This template follows a "bring your own agent" approach - you focus on your business logic, and the template handles everything else (UI, infrastructure, deployment, monitoring).

Prototype: Build your Generative AI Agent using the intro notebooks in notebooks/ for guidance. Use Vertex AI Evaluation to assess performance.
Integrate: Import your agent into the app by editing app/agent.py.
Test: Explore your agent functionality using the Streamlit playground with make playground. The playground offers features like chat history, user feedback, and various input types, and automatically reloads your agent on code changes.
Deploy: Set up and initiate the CI/CD pipelines, customizing tests as necessary. Refer to the deployment section for comprehensive instructions. For streamlined infrastructure deployment, simply run agent-starter-pack setup-cicd. Check out the agent-starter-pack setup-cicd CLI command. Currently only supporting Github.
Monitor: Track performance and gather insights using Cloud Logging, Tracing, and the Looker Studio dashboard to iterate on your application.
Deployment
Note: For a streamlined one-command deployment of the entire CI/CD pipeline and infrastructure using Terraform, you can use the agent-starter-pack setup-cicd CLI command. Currently only supporting Github.

Dev Environment
You can test deployment towards a Dev Environment using the following command:

gcloud config set project <your-dev-project-id>
make backend
The repository includes a Terraform configuration for the setup of the Dev Google Cloud project. See deployment/README.md for instructions.

Production Deployment
The repository includes a Terraform configuration for the setup of a production Google Cloud project. Refer to deployment/README.md for detailed instructions on how to deploy the infrastructure and application.

Monitoring and Observability
You can use this Looker Studio dashboard template for visualizing events being logged in BigQuery. See the "Setup Instructions" tab to getting started.

The application uses OpenTelemetry for comprehensive observability with all events being sent to Google Cloud Trace and Logging for monitoring and to BigQuery for long term storage.
