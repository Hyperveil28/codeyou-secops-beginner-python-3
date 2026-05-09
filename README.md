# ============================================================
# Week 3 - Conditionals and Logic in Python
# Assignment: Building a Login Attempt Analyzer
#
# File: login_report.py
#
# Description:
# This script analyzes failed login attempts and classifies
# the login event based on the number of failed attempts and
# whether the account is privileged.
#
# Skills Practiced:
# - User input
# - Variables
# - if / elif / else conditionals
# - Logical operators
# - Formatted security reporting
# - Datetime timestamping
# ============================================================

from datetime import datetime


print("=" * 40)
print("   Cyber Defense - Login Attempt Report")
print("=" * 40)

# Collect analyst and account information
analyst_name = input("Enter analyst name: ")
username = input("Enter username being analyzed: ")

# Collect failed login count
failed_logins = int(input("Enter number of failed login attempts: "))

# Collect privileged account status
privileged_input = input("Is this a privileged account? (yes/no): ").strip().lower()

# Normalize privileged account response
is_privileged = privileged_input == "yes"

# Default values
risk_level = "INFORMATIONAL"
alert_message = "[+] No failed logins recorded."

# Analyze login activity using conditionals and logical operators
if failed_logins > 5 and is_privileged:
    risk_level = "HIGH"
    alert_message = "[*] Privileged account shows multiple failed logins!"

elif failed_logins > 5 and not is_privileged:
    risk_level = "MEDIUM"
    alert_message = "[!] Standard account shows multiple failed logins."

elif failed_logins >= 1 and failed_logins <= 5:
    risk_level = "LOW"
    alert_message = "[-] Some failed login attempts observed."

elif failed_logins == 0:
    risk_level = "INFORMATIONAL"
    alert_message = "[+] No failed logins recorded."

else:
    risk_level = "UNKNOWN"
    alert_message = "[!] Invalid login attempt count detected."

# Generate timestamp
report_time = datetime.now().strftime("%Y-%m-%d %H:%M")

# Format privileged account display
privileged_display = "Yes" if is_privileged else "No"

# Display final report
print("\n" + "=" * 40)
print("   Cyber Defense - Login Attempt Report")
print("=" * 40)
print(f"Analyst: {analyst_name}")
print(f"User: {username}")
print(f"Failed Attempts: {failed_logins}")
print(f"Privileged Account: {privileged_display}")
print(f"Risk Level: {risk_level}")
print(f"Alert: {alert_message}")
print(f"Report Generated: {report_time}")
print("=" * 40)
