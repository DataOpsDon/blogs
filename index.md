# JD's Blog Site Deployment

This YAML file is part of the deployment process for JD's blog site. It's used in Azure DevOps pipelines to automate the deployment of the site's resources.

## Deployment Process

1. **Agent Pool Selection**: The deployment runs on the agent pool specified in the `parameters.agentPool` parameter.

2. **Variable Groups**: Several variable groups are used to manage the deployment and environment variables.

3. **Environment**: The `parameters.environment` parameter specifies the target environment for the deployment.

4. **Deployment Steps**: The deployment process includes several steps:

   - **Download Deployment Artifacts**: This step downloads the deployment artifacts needed for the deployment.

   - **Download Deployment Templates**: This step downloads the Bicep templates used for the deployment.

   - **Install Powershell Modules**: This step runs a PowerShell script that retrieves the IP address of the agent machine.

   - **Deploy Bicep Template**: This step deploys the Bicep template `main.bicep` with the specified parameters.

   - **Configure Virtual Machines**: This step runs a PowerShell script `configureVirtualMachines.ps1` that configures the deployed virtual machines.

   - **Get Virtual Machine IP Addresses**: This step retrieves the IP addresses of the deployed virtual machines and stores them in a pipeline variable.

This YAML file is a key part of the CI/CD process for JD's blog site, ensuring that the site can be reliably and consistently deployed to any environment.
