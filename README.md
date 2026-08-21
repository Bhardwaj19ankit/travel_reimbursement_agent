# Travel Reimbursement Approval Agent --- Setup Guide

This README explains how to set up and run
`ankit_kumar_travel_reimbursement_agent_openai_final.ipynb` using
Python, Jupyter, and the OpenAI API.

## Prerequisites

Install Python 3.10 or later. You also need an OpenAI API key.

Check Python:

``` bash
python --version
```

Check pip:

``` bash
python -m pip --version
```

## 1. Open the Project Folder

Example with Git Bash on Windows:

``` bash
cd ~/Documents/projects/my_project
```

Place the notebook in this folder:

``` text
my_project/
└── ankit_kumar_travel_reimbursement_agent_openai_final.ipynb
```

## 2. Create a Virtual Environment

``` bash
python -m venv venv
```

### Activate on Git Bash / Windows

``` bash
source venv/Scripts/activate
```

### Activate on Command Prompt

``` bat
venv\Scripts\activate
```

### Activate on PowerShell

``` powershell
.\venv\Scripts\Activate.ps1
```

### Activate on macOS / Linux

``` bash
source venv/bin/activate
```

After activation you should normally see `(venv)` in the terminal.

## 3. Upgrade pip

``` bash
python -m pip install --upgrade pip
```

## 4. Install Required Packages

``` bash
python -m pip install openai jupyter pandas matplotlib
```

Verify:

``` bash
python -c "import openai, pandas, matplotlib; print('Required packages installed successfully')"
```

Check Jupyter:

``` bash
jupyter --version
```

## 5. Set the OpenAI API Key

Do not hard-code the API key in the notebook.

The OpenAI Python SDK supports loading the key from the `OPENAI_API_KEY`
environment variable.

### Git Bash on Windows

``` bash
export OPENAI_API_KEY="your-openai-api-key"
```

### Command Prompt

``` bat
set OPENAI_API_KEY=your-openai-api-key
```

### PowerShell

``` powershell
$env:OPENAI_API_KEY="your-openai-api-key"
```

### macOS / Linux

``` bash
export OPENAI_API_KEY="your-openai-api-key"
```

Verify without printing the secret:

``` bash
python -c "import os; print('OPENAI_API_KEY configured:', bool(os.getenv('OPENAI_API_KEY')))"
```

Expected:

``` text
OPENAI_API_KEY configured: True
```

The commands above normally configure the key for the current terminal
session. If you open another terminal, set it again unless you have
securely configured it persistently.

## 6. Optional: Set the Model

The notebook already has a default model. To override it:

### Git Bash / macOS / Linux

``` bash
export OPENAI_MODEL="gpt-4.1-mini"
```

### Command Prompt

``` bat
set OPENAI_MODEL=gpt-4.1-mini
```

### PowerShell

``` powershell
$env:OPENAI_MODEL="gpt-4.1-mini"
```

## 7. Start Jupyter

Make sure the virtual environment is active and the API key has been
configured.

Launch Jupyter:

``` bash
jupyter notebook
```

Or launch the notebook directly:

``` bash
jupyter notebook ankit_kumar_travel_reimbursement_agent_openai_final.ipynb
```

Jupyter normally opens in the browser on a local address such as:

``` text
http://localhost:8888/tree
```

## 8. Run the Notebook

Open the notebook and select:

``` text
Kernel → Restart Kernel and Run All Cells
```

The notebook runs the policy configuration, sample claims, deterministic
tools, OpenAI function schemas, OpenAI agent, claim evaluation,
dashboard, tests, and final structured JSON.

Expected sample decisions:

``` text
CLM-001 → APPROVE
CLM-002 → REJECT
CLM-003 → PARTIAL_APPROVE
CLM-004 → MANUAL_REVIEW
CLM-005 → MANUAL_REVIEW
```

## 9. Final Output

The final code cell outputs one structured JSON object per claim with:

-   `claim_id`
-   `decision`
-   `approved_amount`
-   `deducted_amount`
-   `missing_docs`
-   `policy_refs`
-   `confidence`
-   `explanation`
-   `tools_used`

## Common Issues

### OPENAI_API_KEY is required

Set the key in the same terminal from which you start Jupyter:

``` bash
export OPENAI_API_KEY="your-openai-api-key"
jupyter notebook
```

### ModuleNotFoundError

Activate the environment and reinstall packages:

``` bash
source venv/Scripts/activate
python -m pip install openai jupyter pandas matplotlib
```

### jupyter: command not found

``` bash
python -m pip install jupyter
python -m notebook
```

### Dashboard reports no results

An earlier claim-evaluation cell failed. Use:

``` text
Kernel → Restart Kernel and Run All Cells
```

Then fix the first error shown before rerunning the dashboard.

## Stop Jupyter

In the terminal running Jupyter, press:

``` text
Ctrl + C
```

## Deactivate the Environment

``` bash
deactivate
```

## Quick Start --- Windows with Git Bash

``` bash
cd ~/Documents/projects/my_project

python -m venv venv

source venv/Scripts/activate

python -m pip install --upgrade pip

python -m pip install openai jupyter pandas matplotlib

export OPENAI_API_KEY="your-openai-api-key"

python -c "import os; print('OPENAI_API_KEY configured:', bool(os.getenv('OPENAI_API_KEY')))"

jupyter notebook ankit_kumar_travel_reimbursement_agent_openai_final.ipynb
```

Then use:

``` text
Kernel → Restart Kernel and Run All Cells
```

## Security

-   Never hard-code the OpenAI API key in the notebook.
-   Never commit API keys to Git.
-   Never put a real key in this README.
-   Do not expose keys in screenshots or logs.
-   Rotate a key immediately if it is accidentally exposed.
