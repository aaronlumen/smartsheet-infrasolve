<<<<<<< HEAD
# smartsheet-infrasolve
Infrastructure Solutions smartsheet tooling
=======
# Goals:
# Implementing these ideas using the Smartsheet GitHook and providing the organization with my customized Python code can revolutionize how we manage our infrastructure deployments. The integration ensures real-time updates, enhances collaboration, reduces liability, and aligns with corporate healthcare initiatives. By leveraging these tools, we streamline processes, improve accuracy, and foster a more cohesive and efficient project management environment.

# This approach not only supports our immediate project needs but also sets a strong foundation for future scalability and innovation. Embracing these technological advancements will undoubtedly contribute to our mission of delivering exceptional patient care through reliable and advanced IT infrastructure.

# Sincerely,

# Author:
# Aaron Surina
# LV Solutions Architect III
# Enterprise Infrastructure Architecture
# Planning, Design & Construction | National Real Estate Services
# 
# e: aaron.surina@gmail.com | c: 707.200.4372
# python code below:
``` python

import json
import os

def get_user_input(prompt, default=None):
    """Helper function to get user input with a default value."""
    if default:
        prompt = f"{prompt} [{default}]: "
    else:
        prompt = f"{prompt}: "
    return input(prompt) or default

def main():
    print("Welcome to the Smartsheet-GitHub Integration Setup")

    # Get user inputs
    smart_token = get_user_input("Enter your Smartsheet API token")
    sheet_id = get_user_input("Enter your Smartsheet sheet ID")
    column_id = get_user_input("Enter your Smartsheet column ID")
    github_webhook_url = get_user_input("Enter your GitHub webhook URL")
    github_repo_url = get_user_input("Enter your GitHub repository URL")

    # Save to config.json
    config = {
        "SMARTSHEET_API_TOKEN": smart_token,
        "sheet_id": sheet_id,
        "column_id": column_id,
        "github_webhook_url": github_webhook_url,
        "github_repo_url": github_repo_url
    }

    with open('config.json', 'w') as config_file:
        json.dump(config, config_file, indent=4)

    print("\nConfiguration saved to config.json")

    # Instructions for setting up the GitHub webhook
    print("\nTo complete the setup, configure the GitHub webhook with the following details:")
    print(f"Payload URL: {github_webhook_url}")
    print("Content type: application/json")
    print("Select events: Just the push event (and optionally the pull request event)")

if __name__ == "__main__":
    main()

