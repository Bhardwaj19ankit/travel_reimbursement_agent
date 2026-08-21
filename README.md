# Travel Reimbursement Approval Agent --- Setup Guide

This README explains how to set up and run
`ankit_travel_reimbursement_agent_openai.ipynb` using
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
cd ~/home/assignments
```

Place the notebook in this folder:

``` text
assignments/
└── ankit_travel_reimbursement_agent_openai.ipynb
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

Check Jupyter:

``` bash
jupyter --version
```

## 5. Set the OpenAI API Key

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


## 6. Start Jupyter

Make sure the virtual environment is active and the API key has been
configured.

Launch Jupyter:

``` bash
jupyter notebook
```

Or launch the notebook directly:

``` bash
jupyter notebook ankit_travel_reimbursement_agent_openai.ipynb
```

Jupyter normally opens in the browser on a local address.
