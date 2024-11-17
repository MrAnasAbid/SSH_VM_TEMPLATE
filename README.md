# SSH VM Deployment Template

This repository provides a template for deploying Python projects to a VPS server using GitHub Actions.

## Steps to Set Up

### Prerequisites
1. A VPS server with SSH access.
2. Python 3.x and Git installed on the VPS.
3. Add the following secrets to your GitHub repository:
   - `SSH_IP`: VPS IP address.
   - `SSH_USER`: SSH username.
   - `SSH_PRIVATE_KEY`: Private key for SSH authentication.

   To add secrets:
   - Go to **Settings > Secrets and variables > Actions > New repository secret**.

### Workflow Overview
The provided GitHub Actions workflow:
1. Installs Python, PDM, and dependencies.
2. Connects to the VPS using SSH.
3. Pulls the latest code from the `main` branch.
4. Installs project dependencies using PDM.
5. Activates the virtual environment and runs `src/test_pipeline.py`.

### How to Use
1. Ensure your project is stored at `/root/dummy_projects/SSH_VM_TEMPLATE` on the VPS, or update the path in the workflow file.
2. Push changes to the `main` branch:
   ```bash
   git add .
   git commit -m "Deploy update"
   git push origin main

### Troubleshooting
- SSH Issues: Check your SSH_PRIVATE_KEY and SSH_IP.
- Dependency Issues: Ensure Python, PDM, and dependencies are properly installed on the VPS.
- Script Errors: Check the GitHub Actions logs for more details.