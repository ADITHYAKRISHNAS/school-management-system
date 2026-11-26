# ADR-001: Use a custom User model with a role field

## Decision
Use a custom User model that extends Django's AbstractUser and adds a
"role" field.

## Why
Django cannot cleanly switch user models after the first migration.
Every feature in this system depends on knowing the user's role.

## Alternatives rejected
Using Django's default User plus a separate table for roles. It needs
an extra query on every request and is harder to keep consistent.

## Consequence
AUTH_USER_MODEL must be set in settings.py before the first migrate.