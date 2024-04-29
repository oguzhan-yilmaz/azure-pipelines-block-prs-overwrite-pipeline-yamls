# azure-pipelines-block-prs-overwrite-pipeline-yamls

This repository contains a Branch Protection Azure Pipeline that:

- Only runs for Pull Requests
- Checks any `azure-pipeline*.[yaml|yml]` file in the repo
- Compares the source and target branch file contents
- Errors out when target file doesn't match to the source file.

## Why do this?

- Developers might override the `azure-pipeline.yaml` files whenever it's changed after the Pull Request created.

## How to implement it for yourself

- Create an Azure Pipeline using [branch-protection.azure-pipelines.yaml](branch-protection.azure-pipelines.yaml)
- Go to your Azure Devops > Repos > Branches
- Select the options for the branch you want to protect
- Go to `Branch Policies`
- Under `Build Validation`, click on `Add build policy`
- and select the pipeline you've created
