# Credential exposure response

A nonempty PostgreSQL configuration was committed to this public repository.

## Required owner action

1. Immediately rotate the database password with the hosting provider.
2. Disable the old user if no longer needed; inspect login/query logs for unauthorized access.
3. Restrict network access and privileges; use dedicated credentials per environment.
4. Review Git history, forks, caches, other files and CI logs for exposed secrets.
5. Consider coordinated Git history cleanup after rotation, recognizing existing clones may retain the old values.

Deleting the tracked file **does not revoke the password or remove it from past commits**.

## Developer setup

Copy book-inventory-api/.env.example to book-inventory-api/.env and fill in fresh credentials locally. The .env path is ignored by Git. Never commit the actual values or put them in the README.

Database functionality and any deployed endpoint must be verified separately; this is a targeted security fix, not a production-readiness claim.
