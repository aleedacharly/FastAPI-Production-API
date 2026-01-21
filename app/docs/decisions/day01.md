# Day 01 – Project Initialization and Engineering Foundations

## Purpose of Day 01

Day 01 focuses on establishing engineering foundations before implementing any features.
The goal is to reduce future complexity, enforce consistency, and make the system safe to evolve.

No business logic is implemented on this day by design.

---

## Project Intent

This project is a production-style backend API service built with FastAPI.
It is intended to be a long-lived service that can grow in complexity without becoming fragile.

The API is the product. There is no frontend in this project.

---

## Repository Initialization

The repository was created with a clear README defining:
- Project goals
- Explicit non-goals
- High-level intent

Non-goals are intentionally documented to prevent scope creep and architectural drift.

---

## Python Version Selection

Python 3.11 is used explicitly.
This ensures access to modern language features, improved performance, and better error reporting.

Defining the Python version upfront avoids undefined behavior across environments.

---

## Dependency Management with Poetry

Poetry is used for dependency management and environment isolation.

Two files serve distinct purposes:
- `pyproject.toml` defines dependency intent
- `poetry.lock` guarantees reproducible installations

Reproducibility is prioritized over flexibility to ensure predictable builds and debugging.

---

## Project Structure

A layered directory structure is established under the `app/` module.

Each layer has a single responsibility:
- `api` handles HTTP request/response logic
- `services` contains business logic
- `models` defines database models
- `schemas` define external data contracts
- `db` manages persistence concerns
- `core` will hold configuration and cross-cutting concerns

This structure enforces clear dependency direction and prevents business logic from leaking into the API layer.

---

## Formatting and Linting Standards

Code formatting is enforced using Black.
Linting is enforced using Ruff.

These tools:
- Remove subjective style decisions
- Catch common bugs early
- Reduce cognitive load during development

Standards are enforced from Day 01 to avoid accumulating technical debt.

---

## FastAPI Application Stub

A minimal FastAPI application is created to verify:
- Environment correctness
- Framework wiring
- Dependency resolution

The application intentionally contains only a health check endpoint.

---

## Health Check Endpoint

A `/health` endpoint is implemented.

Health checks are not user-facing features.
They are required for infrastructure systems to determine service availability and stability.

---

## Running the Application

The application is run locally using Uvicorn to confirm:
- The environment is correctly configured
- The service starts successfully
- API documentation is accessible

A project that cannot run locally is not considered valid.

---

## Decision Documentation

Engineering decisions are documented to preserve context over time.

Code describes what was built.
Decision documentation explains why choices were made.

This prevents future refactors from breaking hidden assumptions.

---

## Outcome of Day 01

By the end of Day 01:
- The project structure is stable
- Tooling is standardized
- The application boots correctly
- Future work can proceed safely

Day 01 establishes constraints that enable faster and safer development in subsequent stages.
