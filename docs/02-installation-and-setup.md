# Installation and Setup

This guide explains how to install Kilo Code, authenticate with an AI provider, configure the development environment, and verify that everything works correctly.

Kilo Code supports multiple development environments. This guide focuses on the VS Code extension and the command-line interface (CLI).

Important: The VS Code extension and standalone CLI have separate installation procedures. The current VS Code extension includes its own embedded runtime. Installing the CLI is not a requirement for using the extension.

## Prerequisites

- Node.js 16+ or Python 3.8+
- Compatible code editor (VS Code, Vim, Emacs, etc.)
- Internet connection for AI services
- Terminal application.

```bash
node --version
npm --version
```

If either command is unavailable, install Node.js and npm before proceeding.

Official Node.js website:

https://nodejs.org/

## Installation Steps

### 1. Install Kilo Code CLI

```bash
# Using npm
npm install -g @kilocode/cli # -g make it available globally

# Using yarn
yarn global add kilocode

# Using pip (for Python users)
pip install kilocode
```

### 2. Verify Installation

```bash
kilo --version
```

### 3. Display available commands

```bash
kilo --help
```

### 4. Authentication

```bash
kilo auth login
```

Follow the prompts to authenticate with your AI provider account.

## Initial Configuration

### Create Configuration File

```bash
kilo init
```

This creates a `kilo.json` file in your project directory.

### Basic Configuration

```json
{
  "project": "my-app",
  "aiProvider": "openai",
  "model": "gpt-4",
  "temperature": 0.7,
  "maxTokens": 2000
}
```

## Editor Integration

### VS Code

1. Install the Kilo Code extension from the marketplace
2. Sign in with your account
3. Start using the AI assistant

### Vim/Emacs

Use the CLI interface or install the respective plugin from the package manager.

## Environment Setup

### Environment Variables

Create a `.env` file:

```bash
# AI Provider Settings
OPENAI_API_KEY=your_api_key_here
AI_MODEL=gpt-4

# Project Settings
PROJECT_NAME=my-app
DEBUG=true
```

## Verification

Run the following to ensure everything is working:

```bash
kilo health check
kilo test connection
```

## Troubleshooting

### Common Issues

**Installation fails**
- Check Node.js/Python version
- Verify internet connection
- Try installing with sudo/admin privileges

**Authentication errors**
- Verify API keys are correct
- Check account status with provider
- Try re-authenticating

**Extension not loading**
- Restart your editor
- Check for conflicting extensions
- Update to the latest version
