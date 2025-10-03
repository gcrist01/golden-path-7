## Step 1: Getting Access


Use the following steps to authenticate and configure access to AWS resources necessary for your local environment to work. Essentially:
- CodeArtifact
- ECR


### 📖 Theory: Onboarding Prerequisites

Check the .NET Golden Path for full detailed [Onboarding Prerequisites](https://kiwibank.atlassian.net/wiki/spaces/SF/pages/5304156174/1.+Onboarding+Prerequisites)  


### ⌨️ Activity: Getting Started with ECR and CodeArtifact

1. Configure AWS SSO
1. Getting Started with ECR and CodeArtifact
1. Creating a GitHub repository

### ⌨️ Check Results: AWS and CodeArtifact access

Once you've finished the step above run the following commands and I'll check the result

#### Find your aws identity
Run `aws sts get-caller-identity --profile kb-aws-cicd-default-prod.KBCICD_Team_SrvFoundation`

Should produce a json object similar to
```
{
    "UserId": "AROXYZXYZXYZJ3MW:Gerard.CristofolRoig@kiwibank.co.nz",
    "Account": "853444444080",
    "Arn": "arn:aws:sts::853444444080:assumed-role/AWSReservedSSO_KBCICD_Team_SrvFoundation_9043076585c58ae0/Gerard.CristofolRoig@kiwibank.co.nz"
}
```
#### Find your CodeArtifact repositories
Run `aws codeartifact list-repositories --profile kb-aws-cicd-default-prod.KBCICD_Team_SrvFoundation`

It produces a json with the repositories available to you
capture it on a file and check it into the repo

```
aws codeartifact list-repositories --profile kb-aws-cicd-default-prod.KBCICD_Team_SrvFoundation > my-codeartifact-repos.json
git add my-codeartifact-repos.json
git commit -m "Add the aws codeartifact list-repositories json output"
git push
```



<details>
<summary>Having trouble? 🤷</summary><br/>

- [Troubleshooting tip or hint](https://kiwibank.atlassian.net/wiki/spaces/SF/pages/5208277781/Troubleshooting+Pipeline+Issues)

</details>