# MyAgent

**my-awesome-agent**

A powerful agent implementing a base ReAct agent using LangGraph, generated with the [googleCloudPlatform/agent-starter-pack](https://github.com/googleCloudPlatform/agent-starter-pack) version 0.2.3.

## Project Structure

my-awesome-agent/
├── app/
│   ├── agent.py
│   ├── agent_engine_app.py
│   └── utils/
├── deployment/
├── notebooks/
├── tests/
├── Makefile
└── pyproject.toml


## Requirements

Before you begin, ensure you have the following installed:

* **uv**: Python package manager - [Installation Instructions](<INSERT_UV_INSTALLATION_LINK>)
* **Google Cloud SDK**: For interacting with GCP services - [Installation Instructions](https://cloud.google.com/sdk/docs/install)
* **Terraform**: For infrastructure deployment - [Installation Instructions](https://www.terraform.io/downloads)
* **make**: Build automation tool - Generally pre-installed on most Unix-based systems.

## Quick Start (Local Testing)

Install required packages and launch the local development environment:

```bash
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

Export to Sheets
For full command options and usage, refer to the Makefile.

Usage
This template follows a "bring your own agent" approach, allowing you to focus on your core business logic while the template handles the surrounding infrastructure, UI, deployment, and monitoring.

Prototype: Start building your Generative AI Agent using the introductory notebooks located in the notebooks/ directory for guidance. Leverage Vertex AI Evaluation to assess your agent's performance.
Integrate: Incorporate your developed agent into the application by modifying the app/agent.py file.
Test: Thoroughly explore your agent's functionality using the Streamlit playground, accessible via the make playground command. This interface provides features like chat history, user feedback mechanisms, and support for various input types. It also automatically reloads your agent upon code changes for a streamlined development experience.
Deploy: Set up and initiate the CI/CD pipelines, customizing tests as needed. Refer to the Deployment section below for comprehensive instructions. For a streamlined infrastructure deployment, you can use the agent-starter-pack setup-cicd CLI command (currently supports GitHub only).
Monitor: Track your application's performance and gather valuable insights using Cloud Logging, Cloud Trace, and the provided Looker Studio dashboard to iterate and improve your agent.
Deployment
Note: For a streamlined one-command deployment of the entire CI/CD pipeline and infrastructure using Terraform, you can use the agent-starter-pack setup-cicd CLI command. Currently, this feature only supports GitHub repositories.

Dev Environment
You can test deployment to a development environment using the following commands:

Bash

gcloud config set project <your-dev-project-id>
make backend
The repository includes a Terraform configuration for setting up your development Google Cloud project. See deployment/README.md for detailed instructions.

Production Deployment
The repository also includes a Terraform configuration for setting up a production Google Cloud project. Refer to deployment/README.md for detailed instructions on how to deploy the infrastructure and application to your production environment.

Monitoring and Observability
You can utilize this Looker Studio dashboard template for visualizing events logged in BigQuery. Refer to the "Setup Instructions" tab within the dashboard to get started.

This application leverages OpenTelemetry for comprehensive observability. All events are automatically sent to:

Google Cloud Trace: For request tracing and performance analysis.
Google Cloud Logging: For application logs and debugging.
BigQuery: For long-term storage and analysis of observability data.
