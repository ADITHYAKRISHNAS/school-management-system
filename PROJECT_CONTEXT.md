# Project Context

## Project
School Management System (SMS). A learning and portfolio project built
step by step.

## Stack
Django 5.2 LTS, HTML, CSS, vanilla JavaScript, SQLite (PostgreSQL later).
Git and GitHub, one branch per feature, pull requests.

## Roles
Management, Principal, Teacher, Non-Teaching Staff, Student, Parent.

## Features (v1.0)
Login and RBAC, users, classes and subjects, attendance with substitute
teachers, exams and marks, assignments, announcements, leave management,
answer-sheet requests (private PDF downloads), dashboards, CSV reports.

## Decisions so far
- Project folder is "config"; apps live in an apps/ folder.
- Custom User model with a "role" field, set before the first migration.
- Leave routing: parent -> class teacher, teacher -> Principal,
  non-teaching staff -> Management.
- Answer sheets are stored outside public URLs and served only by a
  permission-checked download view.
- A student's class is stored in an Enrollment table, one row per year.
- Sessions expire after 30 minutes of inactivity. Time zone: Asia/Kolkata.
- Models are not written until the ER diagram is reviewed against the SRS.

## Current status
Phase 0: setup in progress.