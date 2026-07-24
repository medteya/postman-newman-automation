# API Testing & Automation Pipeline

## Summary of Repo

This repository contains an automated API testing project utilizing **Postman**, **Newman CLI**, and **GitHub Actions**. It showcases two core testing implementations:

- **Local Store API (`store.collection.json`)**: Functional and integration test suites covering local endpoints (`/products`, `/users`, `/orders`), CRUD operations, schema validations, query parameters, and edge cases.
- **Petstore API (`petstore.collection.json`)**: Automated test suite integrated into a CI/CD pipeline using GitHub Actions to execute collections and deploy interactive HTML reports to GitHub Pages.

---

## Requirements

To run and test this project locally, ensure you have the following installed on your machine:

- **Node.js** (v16 or higher recommended)
- **npm** (Node Package Manager, comes bundled with Node.js)
- **Git**

---

## Steps to Install

1. Clone the repository to your local machine.
2. Open your terminal in the project root directory.
3. Run the following command to install all dependencies:
   ```bash
   npm install
   ```

---

## Steps to Launch

Start the local API test server in your terminal:

```bash
npm run turn-on-api
```

(The mock server will start running locally at http://localhost:3000)

---

## Steps to Generate Reports

### Locally via Newman & HTML Extra:

1. Ensure your local server is running.
2. Execute the test collection and generate an HTML report using Newman:
   ```bash
   npx newman run store.collection.json -r htmlextra
   ```
3. Open the generated report folder (typically newman/) in your browser to view detailed test results.

### Automatically via CI/CD (GitHub Actions)

1. Push your code changes to the `main` branch.
2. The configured GitHub Action (`.github/workflows/petstore-tests.yml`) will automatically run `petstore.collection.json`, compile the HTML report, and deploy it live to your GitHub Pages URL.
