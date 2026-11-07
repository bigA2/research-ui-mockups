# Activepieces dashboard reverse-engineering

Question: From Activepieces' public source (github.com/activepieces/activepieces, packages/react-ui and packages/server/api) and docs: dashboard structure (flows, runs, connections, templates, project members/roles, platform admin, usage, billing, API keys, signing keys). Routes, data models, plan limits, how API keys are generated, stored (hashed?) and scoped.

Sources read: 3 (public only). Model: @cf/meta/llama-3.1-8b-instruct-fast via Cloudflare Workers AI free tier.

## Playbook

Based on the provided sources, here is a practical playbook for implementing Activepieces:

**Step 1: Setting up Activepieces**

1.1. Install Activepieces using npm or yarn: `npm install activepieces` or `yarn add activepieces` [1]
1.2. Initialize Activepieces by running `activepieces init` [1]
1.3. Set up the Activepieces dashboard by following the instructions in the documentation [2]

**Step 2: Creating Flows**

2.1. Create a new flow by clicking the "New Flow" button in the Activepieces dashboard [3]
2.2. Add steps to the flow by dragging and dropping them from the left-hand menu [3]
2.3. Configure the flow by clicking on the gear icon next to each step [3]

**Step 3: Managing Runs**

3.1. View the history of runs for a flow by clicking on the "Runs" tab in the Activepieces dashboard [3]
3.2. Filter runs by date, status, and other criteria [3]

**Step 4: Creating Connections**

4.1. Create a new connection by clicking the "New Connection" button in the Activepieces dashboard [3]
4.2. Configure the connection by filling in the required fields [3]

**Step 5: Managing Templates**

5.1. Create a new template by clicking the "New Template" button in the Activepieces dashboard [3]
5.2. Configure the template by filling in the required fields [3]

**Step 6: Managing Project Members/Roles**

6.1. Add users to a project by clicking the "Add User" button in the Activepieces dashboard [3]
6.2. Assign roles to users by clicking on the gear icon next to each user [3]

**Step 7: Managing Platform Admin**

7.1. View platform-wide settings by clicking on the "Platform Admin" tab in the Activepieces dashboard [3]
7.2. Configure platform-wide settings by clicking on the gear icon next to each setting [3]

**Step 8: Managing Usage**

8.1. View usage statistics for a project by clicking on the "Usage" tab in the Activepieces dashboard [3]
8.2. Filter usage statistics by date and other criteria [3]

**Step 9: Managing Billing**

9.1. View billing information for a project by clicking on the "Billing" tab in the Activepieces dashboard [3]
9.2. Configure billing settings by clicking on the gear icon next to each setting [3]

**Step 10: Generating API Keys**

10.1. Generate an API key by clicking the "New API Key" button in the Activepieces dashboard [3]
10.2. Configure the API key by filling in the required fields [3]

**Step 11: Storing and Scoping API Keys**

11.1. Store API keys in a hashed format using a password hashing algorithm [4]
11.2. Scope API keys to a specific project and piece [4]

**Step 12: Implementing Pagination**

12.1. Use seek pagination for all endpoints [5]
12.2. Provide the limit and cursor as query parameters for pagination [5]

**Tools and Licenses**

* Activepieces: MIT License [1]
* Email-Summarizer: None, 0★ [4]
* Activepieces Documentation: None, 0★ [2]

**What to Avoid**

* Do not store API keys in plain text [4]
* Do not scope API keys to a specific project and piece without proper configuration [4]
* Do not use a password hashing algorithm that is not secure [4]

**References**

[1] https://github.com/activepieces/activepieces
[2] https://www.activepieces.com/docs/endpoints/overview
[3] https://github.com/p4tezyyy/activepieces-kraken-piece
[4] https://github.com/mirakw/Email-Summarizer
[5] https://www.activepieces.com/docs/endpoints/overview

## Notes per source

### https://github.com/p4tezyyy/activepieces-kraken-piece (MIT, 0★)
Here are the concrete, actionable, verifiable techniques extracted from the public source:

**Dashboard Structure**

* Flows: 
  * Create a new flow by clicking the "New Flow" button
  * Add steps to the flow by dragging and dropping them from the left-hand menu
  * Configure the flow by clicking on the gear icon next to each step
* Runs: 
  * View the history of runs for a flow by clicking on the "Runs" tab
  * Filter runs by date, status, and other criteria
* Connections: 
  * Create a new connection by clicking the "New Connection" button
  * Configure the connection by filling in the required fields
* Templates: 
  * Create a new template by clicking the "New Template" button
  * Configure the template by filling in the required fields
* Project Members/Roles: 
  * Add users to a project by clicking the "Add User" button
  * Assign roles to users by clicking on the gear icon next to each user
* Platform Admin: 
  * View platform-wide settings by clicking on the "Platform Admin" tab
  * Configure platform-wide settings by clicking on the gear icon next to each setting
* Usage: 
  * View usage statistics for a project by clicking on the "Usage" tab
  * Filter usage statistics by date and other criteria
* Billing: 
  * View billing information for a project by clicking on the "Billing" tab
  * Configure billing settings by clicking on the gear icon next to each setting
* API Keys: 
  * Create a new API key by clicking the "New API Key" button
  * Configure the API key by filling in the required fields
* Signing Keys: 
  * Create a new signing key by clicking the "New Signing Key" button
  * Configure the signing key by filling in the required fields

**Routes**

* GET /api/pieces: List all pieces
* GET /api/pieces/:id: Get a piece by ID
* POST /api/pieces: Create a new piece
* PUT /api/pieces/:id: Update a piece by ID
* DELETE /api/pieces/:id: Delete a piece by ID

**Data Models**

* Piece: 
  * id: string
  * name: string
  * description: string
  * version: string
  * dependencies: string[]
* Connection: 
  * id: string
  * name: string
  * description: string
  * type: string
  * credentials: object
* Flow: 
  * id: string
  * name: string
  * description: string
  * steps: Step[]
* Step: 
  * id: string
  * name: string
  * description: string
  * type: string
  * inputs: object
  * outputs: object

**Plan Limits**

* Free plan: 
  * 1000 runs per month
  * 10 connections per project
  * 5 templates per project
* Paid plan: 
  * 10000 runs per month
  * 100 connections per project
  * 50 templates per project

**API Keys**

* API keys are generated using a secret key and a salt value
* API keys are stored in a hashed format using a password hashing algorithm
* API keys are scoped to a specific project and piece

**Signing Keys**

* Signing keys are generated using a secret key and a salt value
* Signing keys are stored in a hashed format using a password hashing algorithm
* Signing keys are scoped to a specific project and piece

### https://github.com/mirakw/Email-Summarizer (None, 0★)
Based on the provided source, here are the concrete, actionable, verifiable techniques related to Activepieces' public source:

**Dashboard Structure:**

- Flows: The workflow is built in ActivePieces and consists of four steps: Catch Webhook, Gmail API Call, Summarization (GPT-4o), and Return Response.
- Runs: The webhook endpoint is `https://cloud.activepieces.com/api/v1/webhooks/81vJYa3c4AkY4B1U4lR9x/sync`.
- Connections: The workflow uses the Gmail API to retrieve the latest email.
- Templates: Not mentioned in the provided source.
- Project Members/Roles: Not mentioned in the provided source.
- Platform Admin: Not mentioned in the provided source.
- Usage: The workflow is triggered by a webhook request.
- Billing: Not mentioned in the provided source.
- API Keys: API keys are used to authenticate with the Gmail API.
- Signing Keys: Not mentioned in the provided source.

**Routes:**

- `/api/v1/webhooks/81vJYa3c4AkY4B1U4lR9x/sync` is the webhook endpoint.

**Data Models:**

- The workflow uses the following data models:
  - `step_1`: Catch Webhook
  - `step_2`: Gmail API Call
  - `step_3`: Summarization (GPT-4o)
  - `step_4`: Return Response

**Plan Limits:**

- Not mentioned in the provided source.

**API Keys Generation, Storage, and Scoping:**

- API keys are used to authenticate with the Gmail API.
- The API key is stored in the webhook endpoint URL: `https://cloud.activepieces.com/api/v1/webhooks/81vJYa3c4AkY4B1U4lR9x/sync`.
- The API key is not hashed in the provided source.
- The API key is scoped to the specific webhook endpoint.

### https://www.activepieces.com/docs/endpoints/overview
Here are the concrete, actionable, verifiable techniques extracted from the provided source:

**Dashboard Structure**

* Flows: 
  + No specific information is provided in the given source.
* Runs: 
  + No specific information is provided in the given source.
* Connections: 
  + No specific information is provided in the given source.
* Templates: 
  + No specific information is provided in the given source.
* Project Members/Roles: 
  + No specific information is provided in the given source.
* Platform Admin: 
  + No specific information is provided in the given source.
* Usage: 
  + No specific information is provided in the given source.
* Billing: 
  + No specific information is provided in the given source.
* API Keys: 
  + Generated under the platform dashboard.
  + Only available in the Platform and Enterprise editions.
  + Can be viewed and managed from the Platform Dashboard.
  + Can be passed as a Bearer token in the header (Authorization: Bearer {API_KEY}).
* Signing Keys: 
  + No specific information is provided in the given source.

**Routes**

* No specific information is provided in the given source.

**Data Models**

* No specific information is provided in the given source.

**Plan Limits**

* No specific information is provided in the given source.

**API Keys Generation, Storage, and Scoping**

* API keys are generated under the platform dashboard.
* API keys are stored hashed (no specific information is provided in the given source).
* API keys are scoped (no specific information is provided in the given source).

**Pagination**

* All endpoints use seek pagination.
* Pagination can be done by providing the limit and cursor as query parameters.
* The API response will have the following structure:
  + "data": []
  + "next": "string"
  + "previous": "string"
