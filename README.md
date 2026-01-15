# ITSM-technical-support-agent
This is about building a technical support AI agent in Azure AI Foundry that uses a custom Python function to generate support tickets
## Steps:
### Step 1:
Start by creating an Azure AI Foundry project at ai.azure.com, selecting supported regions like eastus or westus3, and deploying a gpt-4o model with a 50K TPM limit. Clone this repo, set up a Python environment in Azure Cloud Shell (PowerShell), and configure .env with the project connection string and model deployment name.
### Step 2:
Custom Function Implementation
Define submit_support_ticket() in user_functions.py, which generates a UUID-based ticket number, saves details (email, description) to a .txt file, and returns a JSON confirmation. Register it in a ToolSet using FunctionTool for agent access.
### Step 3:
Agent Development
In agent.py, use AIProjectClient with DefaultAzureCredential to connect, create a "support-agent" with instructions to collect user details and call the function, then run threaded conversations via create_and_process_run(). Display responses, logs, and generated tickets; clean up by deleting agent/thread.
### Step 4:
Running and Cleanup
Sign in with az login, run python agent.py, interact (e.g., report an issue), and verify ticket files. Delete the resource group in Azure portal to avoid costs.

​
