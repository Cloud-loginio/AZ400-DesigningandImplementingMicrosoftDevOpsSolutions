---
lab:
    title: 'Validate lab environment'
    module: 'Module 0: Welcome'
---

# Validate lab environment

## Student lab manual

## Instructions to create an Azure DevOps Organization (you only have to do this once)
### Start here if you have an Azure subscription

1. Open a browser and navigate to [https://portal.azure.com](https://portal.azure.com), then search at the top of the Azure portal screen for **Azure DevOps**. In the resulting page, click **Azure DevOps organizations**.
1. Next, click on the link labelled **My Azure DevOps Organizations** or navigate directly to [https://aex.dev.azure.com](https://aex.dev.azure.com).
1. On the **We need a few more details** page, select **Continue**.
1. In the drop-down box on the left, choose **Default Directory**, instead of “Microsoft Account”.
1. If prompted (*"We need a few more details"*), provide your name, e-mail address, and location and click **Continue**.
1. Back at [https://aex.dev.azure.com](https://aex.dev.azure.com) with **Default Directory** selected click the blue button **Create new organization**.
1. Accept the *Terms of Service* by clicking **Continue**.
1. If prompted (*"Almost done"*), leave the name for the Azure DevOps organization at default (it needs to be a globally unique name) and pick a hosting location close to you from the list.
1. Once the newly created organization opens in **Azure DevOps**, click **Organization settings** in the bottom left corner.
1. At the **Organization settings** screen click **Billing** (opening this screen takes a few seconds).
1. Click **Setup billing** and on the right-hand side of the screen select the **Azure Pass - Sponsorship** subscription and click **Save** to link the subscription with the organization.
1. Once the screen shows the linked Azure Subscription ID at the top, change the number of **Paid parallel jobs** for **MS Hosted CI/CD** from 0 to **1**. Then click the **SAVE** button at the bottom.
1. In **Organization Settings**, go to section **Pipelines** and click **Settings**.
1. Toggle the switch to **Off** for **Disable creation of classic build pipelines** and **Disable creation of classic release pipelines**

    > Note: The **Disable creation of classic release pipelines** switch sets to **On** hides classic release pipeline creation options such as the **Release** menu in the **Pipeline** section of DevOps projects.

1. In **Organization Settings**, go to section **Security** and click **Policies**.
1. Toggle the switch to **On** for **Allow public projects**

    > Note: Extensions used in some labs might require a public project to allow using the free version.

1. **Wait at least 3 hours before using the CI/CD capabilities** so that the new settings are reflected in the backend. Otherwise, you will still see the message *"No hosted parallelism has been purchased or granted"*.

## Instructions to create the sample Azure DevOps Project (you only have to do this once)

### Exercise 0: Configure the lab prerequisites

> **Note**: make sure you completed the steps to create your Azure DevOps Organization before continuing with these steps.

In this exercise, you will set up the prerequisites for the lab, which consist of a new Azure DevOps project with a repository based on the [eShopOnWeb](https://github.com/MicrosoftLearning/eShopOnWeb).

#### Task 1:  Create and configure the team project

In this task, you will create an **eShopOnWeb** Azure DevOps project to be used by several labs.

1. On your lab computer, in a browser window open your Azure DevOps organization. Click on **New Project**. Give your project the following settings:
    - name: **eShopOnWeb**
    - visibility: **Private**
    - Advanced: Version Control: **Git**
    - Advanced: Work Item Process: **Scrum**

1. Click **Create**.

    ![Create Project](images/create-project.png)

#### Task 2:  Import eShopOnWeb Git Repository

In this task you will import the eShopOnWeb Git repository that will be used by several labs.

1. On your lab computer, in a browser window open your Azure DevOps organization and the previously created **eShopOnWeb** project. Click on **Repos>Files** , **Import a Repository**. Select **Import**. On the **Import a Git Repository** window, paste the following URL <https://github.com/MicrosoftLearning/eShopOnWeb.git>  and click **Import**:

    ![Import Repository](images/import-repo.png)

1. The repository is organized the following way:
    - **.ado** folder contains Azure DevOps YAML pipelines.
    - **.devcontainer** folder container setup to develop using containers (either locally in VS Code or GitHub Codespaces).
    - **infra** folder contains Bicep&ARM infrastructure as code templates used in some lab scenarios.
    - **.github** folder container YAML GitHub workflow definitions.
    - **src** folder contains the .NET 8 website used on the lab scenarios.

#### Task 3: Set main branch as default branch

1. Go to **Repos>Branches**.
1. Hover on the **main** branch then click the ellipsis on the right of the column.
1. Click on **Set as default branch**.

You have now completed the necessary prerequisite steps to continue with the different individual labs for this AZ-400 course.
