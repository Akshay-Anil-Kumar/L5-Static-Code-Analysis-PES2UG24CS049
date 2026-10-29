# Lab 5: Static Code Analysis — Ticket Booking System

## Overview

This project improves the code quality, security, and maintainability of the assigned Python ticket booking system using Pylint, Bandit, and Flake8.

## Requirements

- Python 3
- Pylint
- Bandit
- Flake8

## Setup

Create and activate a virtual environment:

```bash
python3 -m venv venv
source venv/bin/activate
python -m pip install pylint bandit flake8
python ticket_booking_system.py
pylint ticket_booking_system.py
bandit -r ticket_booking_system.py
flake8 ticket_booking_system.py

## Step 15 — Add a requirements file

```bash
cat > requirements.txt <<'EOF'
pylint
bandit
flake8
