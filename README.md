# Login Attempt Tracker

## Overview

The Login Attempt Tracker is a beginner Python cybersecurity exercise that uses conditional logic to analyze failed login attempts and assign a risk level.

This script simulates how a SOC analyst or SIEM platform might evaluate suspicious authentication activity. It checks the number of failed login attempts and whether the account is privileged, then produces a structured risk report.

## Skills Practiced

- Python variables
- User input handling
- Boolean values
- `if`, `elif`, and `else` statements
- Logical operators: `and`, `or`, `not`
- Basic cybersecurity risk classification
- Analyst-style reporting

## How It Works

The script asks the user for:

1. Username  
2. Number of failed login attempts  
3. Whether the account is privileged  

It then assigns a risk level:

| Condition | Risk Level |
|---|---|
| 10 or more failed attempts on a privileged account | Critical |
| 10 or more failed attempts on a normal account | High |
| 5 or more failed attempts on a privileged account | High |
| 5 or more failed attempts on a normal account | Medium |
| 1 or more failed attempts on a privileged account | Medium |
| 0 failed attempts | Low |

## Example

```text
Username: admin
Failed Login Attempts: 12
Privileged Account: True
Risk Level: Critical
Recommended Action: Immediately lock the account, investigate activity, and notify security leadership.
