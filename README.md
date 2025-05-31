# GitHub Action Webhook Sender

This repository is configured to automatically send webhook notifications to a specified endpoint when certain GitHub actions occur.

## Supported Events

- **PUSH**: Triggered when code is pushed to any branch
- **PULL_REQUEST**: Triggered when a pull request is opened
- **MERGE**: Triggered when a pull request is merged

## Setup Instructions

1. Fork or clone this repository
2. Go to your repository's Settings > Secrets and variables > Actions
3. Add a new repository secret:
   - Name: `WEBHOOK_URL`
   - Value: Your webhook endpoint URL (e.g., `http://your-domain/webhook/receiver`)

## Event Formats

### PUSH
```
{author} pushed to {to_branch} on {timestamp}
```
Example: "Travis" pushed to "staging" on 1st April 2021 - 9:30 PM UTC

### PULL_REQUEST
```
{author} submitted a pull request from {from_branch} to {to_branch} on {timestamp}
```
Example: "Travis" submitted a pull request from "staging" to "master" on 1st April 2021 - 9:00 AM UTC

### MERGE
```
{author} merged branch {from_branch} to {to_branch} on {timestamp}
```
Example: "Travis" merged branch "dev" to "master" on 2nd April 2021 - 12:00 PM UTC

## Testing

To test the webhook triggers:

1. Push some changes to any branch
2. Create a new pull request
3. Merge a pull request

The actions will automatically trigger and send webhooks to your configured endpoint.
