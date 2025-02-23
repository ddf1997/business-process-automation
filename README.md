# Business Process Automation Accelerator

## Overview

This accelerator provides a no code Studio for users to quickly build complex, multi-stage AI pipelines across multiple Azure AI and ML Services.  Users can select, and stack, AI/ML Services from across Azure Cognitive Services (OpenAI, Speech, Language, Form Recognizer, ReadAPI), Azure Machine Learning into a **single**, fully integrated **pipeline**. Integration between services is automated by BPA, and once deployed, a web app is created. This customizable UI&ast; provides and drag-n-drop interface for end users to build multi service pipelines. Finally, the user-created pipeline is triggered as soon as the first input file(s) are uploaded, storing the results in a Azure Blob Storage.

## Instructional Videos
- [Deployment in Azure](https://bpasource.blob.core.windows.net/source/VideoSeries/Deploy.mp4?sv=2020-04-08&st=2023-03-10T15%3A54%3A39Z&se=2026-06-12T14%3A54%3A00Z&sr=b&sp=r&sig=chMcBfD%2Foc2E05Od8xNkbWprWxHIIc7ApDbVazk2%2BO8%3D)
- [Create Your First Pipeline](https://bpasource.blob.core.windows.net/source/VideoSeries/first%20pipeline-20230310_122701-Meeting%20Recording.mp4?sv=2020-04-08&st=2023-03-10T17%3A51%3A01Z&se=2025-01-16T17%3A51%3A00Z&sr=b&sp=r&sig=Jz8PdJAWkLXnN3QqxEnXogRHtN55FC8emHZoic9TGEE%3D)
- [OpenAI Enterprise Search Using Cognitive Search and Semantic Search](https://bpasource.blob.core.windows.net/source/VideoSeries/enterpriseSearch.mp4?sv=2021-10-04&st=2023-05-15T13%3A35%3A46Z&se=2024-06-21T13%3A35%3A00Z&sr=b&sp=r&sig=ChoYuRwynC%2F2e2I6mDTpMWJm3h6OcBKlcmfc1PhHCmw%3D)
- [OpenAI Enterprise Search Using Vector Search and Redis Enterprise](https://bpasource.blob.core.windows.net/source/VideoSeries/vectorSearch.mp4?sv=2021-10-04&st=2023-05-15T13%3A38%3A16Z&se=2024-10-18T13%3A38%3A00Z&sr=b&sp=r&sig=504UNV7DmTUvUrHAUiaiwggmzET3iM9buc2LOw0N%2F0U%3D)

## Deploy to Azure Instructions

### Prerequisities
1. Github account (Admin)
2. Azure Resource Group (Owner)
3. Ensure your subscription has **Microsoft.DocumentDB enabled**  
To confirm/enable:  
      - Navigate to your subscription within portal.azure.com  
      - Select Resource Providers at bottom of left navigation pane  
      - Within the Filter by name menu, search for Microsoft.DocumentDB  
      - Once Microsoft.DocumentDB is found, check if the status is marked as "Registered". If marked as "NotRegistered", Select "Register"  
      **Note**: *This process may take several seconds/minutes, be sure to refresh the entire browser periodically*
4. Ensure that you have **accepted terms and conditions for Responsible AI**:  
You must initiate the creation of a "Cognitive services multi-service account" from the Azure portal to review and acknowledge the terms and conditions. You can do so here: [Quickstart: Create a Cognitive Services resource using the Azure portal](https://docs.microsoft.com/en-us/azure/cognitive-services/cognitive-services-apis-create-account?tabs=multiservice%2Cwindows).  
Once accepted, you can create subsequent resources using any deployment tool (SDK, CLI, or ARM template, etc) under the same Azure subscription.

1. [Get a Workflow Level Token (Classic)](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
2. Fork the repository to a git account of which you are the Admin.
3. Click on the "Deploy to Azure" Button that corresponds to your environment and which patterns you wish to create.  Redis pattern is only required for Vector Search.
4. Only the Resource Group, Repo Token (from #2), and Forked Git Repo Url are needed.  The remaining parameters are filled in for you.
5. For a demonstration, please view the first Instructional Video at the top of this Readme.

### Without OpenAI
[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fbusiness-process-automation%2Fmain%2Ftemplates%2Foneclick.json)

### With OpenAI
[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fbusiness-process-automation%2Fmain%2Ftemplates%2Foneclickoai.json)

### With OpenAI and Redis Enterprise (check pricing) for Vector Search
[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fbusiness-process-automation%2Fmain%2Ftemplates%2Foneclickoairedis.json)

## Document Ingestion Architecture
Once you've created a high-level Resource Group, you'll fork this repository and importing helper libraries, taking advantage of Github Actions to deploy the set of Azure Cognitive Services and manage all of the new Azure module credentials, in the background, within your newly created pipeline. After pipeline deployment, a static webapp will be created with your newly customizable POC UI for building and triggering pipelines.

![](images/architecture_white.png)  
*Document Ingestion High-level technical architecture*  


  
 
