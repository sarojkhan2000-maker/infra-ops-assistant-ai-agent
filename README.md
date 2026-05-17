# Infra Ops Assistant AI Agent

## Project Overview
This project demonstrates an AI-powered infrastructure operations assistant using Microsoft Foundry, Logic Apps, Azure Automation Runbooks, and SOP-based RAG.

## What This Project Does
- Uses Microsoft Foundry Agent for direct AI chat
- Starts Azure VM from AI chat
- Uses Logic App as API wrapper
- Calls Azure Automation Runbook using webhook
- Uses SOP knowledge for high C drive cleanup recommendation
- Triggers approved C:\Temp cleanup through Runbook
- Excludes Azure Monitor integration for this project

## Architecture

Foundry Agent Chat
        ↓
OpenAPI Tool
        ↓
Logic App
        ↓
Azure Automation Webhook
        ↓
Runbook
        ↓
Azure VM Action

## Completed Features
1. VM Power ON from Foundry chat
2. SOP-based RAG recommendation for high C drive
3. C:\Temp cleanup after user confirmation
4. Logic App wrapper for start VM action
5. Logic App wrapper for folder cleanup action

## Tools Used
- Microsoft Foundry Agent
- Foundry IQ / Knowledge Base
- Azure AI Search
- Azure Logic Apps
- Azure Automation Runbooks
- Azure VM Run Command
- Azure Blob Storage

## Runbooks Used
- rb-start-vm
- rb-clear-temp-folder

## SOP Behavior
If user reports high C drive usage:
1. First recommend clearing C:\Temp.
2. If issue continues, recommend clearing C:\Logs.
3. Ask confirmation before cleanup.
4. Do not recommend deleting system folders.

## Final Working Flows

### VM Start Flow
Foundry Chat → OpenAPI Tool → Logic App → Automation Webhook → rb-start-vm → VM started

### SOP Cleanup Flow
Foundry Chat → SOP RAG → User Approval → Logic App → Automation Webhook → rb-clear-temp-folder → C:\Temp cleaned

## Security Notes
- Webhook URLs and Logic App signatures are not committed to GitHub.
- Secrets are replaced with placeholders.
- Real URLs should be stored securely outside source code.