# Sparta Test App - Automated CI/CD Pipeline

This repository hosts the Sparta Node.js test app configured with an automated Continuous Integration & Continuous Delivery (CI/CD) pipeline using Jenkins, GitHub Webhooks, and SSH authentication.

---

## Table of Contents
1. [Overview & Pipeline Summary](#overview--pipeline-summary)
2. [Documentation Guide](#documentation-guide)
3. [Developer Workflow](#developer-workflow)
4. [Repository Structure](#repository-structure)

---

## Overview & Pipeline Summary

- **Branch Strategy:** Feature development takes place strictly on the `dev` branch. Direct pushes to `main` are restricted.
- **Automated Quality Gate:** Pushes to `dev` trigger Jenkins **Job 1 (`oanzia-job1-ci-test`)** via GitHub Webhooks.
- **Automated Merge:** Passing test runs trigger Jenkins **Job 2 (`oanzia-job2-ci-merge`)**, which merges `dev` into `main` and pushes back to GitHub via SSH.

---

## Documentation Guide

For the full architectural diagrams, step-by-step setup instructions for SSH keys, GitHub webhooks, Jenkins Freestyle job configurations, console output verification logs, and security advisory management:

👉 **[Read the Full CI/CD Pipeline Documentation (CI_CD_DOCUMENTATION.md)](CI_CD_DOCUMENTATION.md)**

---

## Developer Workflow

```bash
# 1. Switch to the development branch
git checkout dev

# 2. Make code adjustments and run tests locally
cd app
npm install
npm test

# 3. Commit and push to trigger Jenkins CI
git add .
git commit -m "feat: your descriptive commit message"
git push origin dev
```

---

## Repository Structure

```text
.
├── CI_CD_DOCUMENTATION.md    # Comprehensive CI/CD architecture, job configs, and execution logs
├── README.md                 # Project overview and navigation
└── app/                      # Sparta Node.js test application
    ├── app.js                # Express application entrypoint
    ├── package.json          # Dependencies & npm test scripts
    ├── models/               # Application data models
    ├── seeds/                # Seed scripts
    ├── test/                 # Mocha & Chai test suites
    └── views/                # EJS server-rendered templates
```


