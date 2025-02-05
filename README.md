# Enterprise Scale AI Factory - Template repo

![Header](documentation/images/header.png)

Welcome to the Enterprise Scale AIFactory solution accelerator template. <br>
This is a template repository, bootstrapped with the Enterprise Scale AIFactory submodule (the most common way of leveraging the AIFactory template acceleration)

> [!IMPORTANT]
>This project provides a ready-to-run github repo, bootstrapped and connected to the *Enterprise Scale AI Factory Github submodule*. For full documentation visit the documentation section [`Enterprise Scale AI Factory submodule`](https://github.com/jostrm/azure-enterprise-scale-ml/blob/main/documentation/readme.md)
>

This repo will leverages resources/templates from the [`Enterprise Scale AI Factory submodule`](https://github.>com/jostrm/azure-enterprise-scale-ml/) including templats for `IaC AI landingzones, DataOps, MLOps, GenAIOps`. <br>This repo and act as your repo with options as: [Github private, internal, public repo](https://resources.github.com/learn/pathways/administration-governance/essentials/manage-your-repository-visibility-rules-and-settings/), or a [private or public Azure Devops repository](https://learn.microsoft.com/en-us/azure/devops/organizations/projects/make-project-public?view=azure-devops)

## The purpose of this repo
This repo, is purposed to bootstrap a repository, that automatically links to the centralized (readonly)submodule `azure-enterprise-scale-ml`, and provides you with templates for YOUR variables, to customize your AI Factory, besides the basic [.env.template](./.env.template) parameters that will end up as Variables in your Github/Azure Devops.

It also provides an automation script to copy templates IaC automation variables and other templates for (DataOps, MLOps, GenAIOps)[https://github.com/jostrm/azure-enterprise-scale-ml/]. (Read more)[which you can read more about here]<br>

## Simple mode VS Advanced mode
This repo is the *simple mode* to setup an AIFactory. This contains automation to:
- Automate the [full manual AIFactory setup process seen here](https://github.com/jostrm/azure-enterprise-scale-ml/blob/main/documentation/v2/10-19/13-setup-aifactory.md). Estimated time effort for manual setup is 2h, and is reduced to 10min with this repo.
- Set default vaules for all 30 [AIFactory based parameters seen here](https://github.com/jostrm/azure-enterprise-scale-ml/blob/main/documentation/v2/10-19/13-parameters-ado.md), saving you estimated time effort of 1h.

The ESML AIFactory with manual seup is said to accelerate setup from 500-1500h down to ~4h setup time.<br>
This repo accelerates even further, below 1h, since leaving only a hand-full of variables to setup in [.env.template](./.env.template)
-> Making it a good choice to quickly setup infrastructure securely for AI-hackathons, workshops, education - scenarios where you are OK if naming convention does not comply 100% with your organizations choices, and you don't need to peer it to your Hub - e.g. where `AIFAcotry standalone mode` is OK.

> [!NOTE]
> You can still go into *advanced mode*, and edit all parameters. You will find them here in the [parameters](aifactory\parameters)
>

## Setup options
As a mirror-repo (Github) or "Bring your own repo" (Github or Azure Devops) <br>

After you have copied the  [.env.template.template](./.env.template-.template) as your [.env](./.env) file, you have the options below.

- A) Bootstrap as a mirror-repo in Github, it becomes a private, internal or public Github repo
    - **When to choose**: If you are allowed to create own repos, and Gihub is your preffered choice.
    - **Automation scripts to run**: The scripts below, will bootstrap an empty repo.
        - [10-mirror-gh-repo-from-template-once.sh](./10-mirror-gh-repo-from-template-once)
        - [12-create-aifactory-pipeline-and-run-once.sh](./12-create-aifactory-pipeline-and-run-once.sh)
        - [13-add-project-pipeline-and-run-once.sh](./13-add-project-pipeline-and-run-once.sh)
- B) Bring your own "empty" repo 
    - **When to choose**: If your organization don't allow you to create repos, or if you preffer Azure Devops.
    - **Automation scripts to run**: The scripts below, will bootstrap an empty repo.
        - [11-init-template-files-once.sh](./11-init-template-files-once.sh)
        - [12-create-aifactory-pipeline-and-run-once.sh](./12-create-aifactory-pipeline-and-run-once.sh)
        - [13-add-project-pipeline-and-run-once.sh](./13-add-project-pipeline-and-run-once.sh)

> [!NOTE]
>   
> The steps A nd B above will create pipelines in Azure Devops or Github (as GHA workflowws), and the pipelines will setup the AIFactory and AI Factory projects. Before you start you will need configure your [.env](./.env) environment variables. Read more at [bootstrapping.md](./documentation/bootstrapping.md) section.
>

## How to create more projects of different types? 
As explained in previous section you will end up with automation pipelines, in either your own Azure Devops (as Release pipelines) or your own Github repositorys (as Actions/Workflows).

The pipelines, can be executed multiple times, to provision multiple AIFactory projects. 
You only need to change a few parameters, such as below
- project_number = "002"
- project_members = "objecetid1234dsf, objectId356546"
- project_type = esgenai

For full documentation, please visit [`Enterprise Scale AI Factory documentation`](https://github.com/jostrm/azure-enterprise-scale-ml/blob/main/documentation/readme.md)
## Feature Highlights

- Bootstrap your project in under an hour, including enterprise grade security
- Enteprise grade security and networking (private link).
- Provision resources with IaC (BICEP)
- Automate IaC with (Github Actions or Azure Devops)
- Easy-to-configure and extend templates: DataOps, MLOps, GenAIOps
- AI Factory project types
    - ESGenAI: GenAI: Azure AI Foundry with RAG using Azure AI Search
    - ESML: DataOps and MLOps with notebooks templates - both Databricks (Pyspark) and Jupyter notebooks(Python). Mix compute & tech, while using same MLOps pipeline

> [!NOTE]
>**Enterprise secrurity**: Both fully private mode (private link for also the Azure AI Studio) or private link with AI Studio accessible from certain IP. Role-based access control is used, meaning EntraID for all sercice-to-servcice and user-to-service connections. Not using any keys (since global keys have full permission to services, it is not recommended)
>

[Full documentation -  "Enterprise Scale AI Factory"](https://github.com/jostrm/azure-enterprise-scale-ml/blob/main/documentation/readme.md)

## How-to

1. [Bootstrapping a new AIFactory](documentation/bootstrapping.md)
2. [Bootstrapping a new AIFactory project (Type: ESGenAI or ESML)](documentation/bootstrapping.md)
3. [Delivering a new Feature: CI/CD with MLOps or GenAIOps](documentation/delivering_new_feature.md)

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
