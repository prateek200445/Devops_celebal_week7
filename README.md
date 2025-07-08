# Devops_celebal_week7
# DevOps Azure Services Project – Celebal Internship

## 📘 Overview
This repository contains my detailed implementation and documentation of **Azure DevOps Services** as part of my internship project at **Celebal Technologies_week7**. The project showcases hands-on experience in setting up, configuring, and managing DevOps workflows using Azure DevOps tools including pipelines, repos, permissions, branch policies, security, and traceability.

Each task listed below has been executed and validated in a real Azure DevOps environment with clear screenshots (if applicable), YAML configuration, and GUI-based configurations.

---

## ✅ Task Summary
| Task No. | Task Description                                                                 | Completed |
|----------|-----------------------------------------------------------------------------------|------------|
| 1        | Create project with user groups and apply group policies                         | ✅          |
| 2        | Apply branch policies to restrict direct access to `main` for contributors       | ✅          |
| 3        | Apply branch-level security & locks                                              | ✅          |
| 4        | Configure branch filters & path filters                                           | ✅          |
| 5        | Create and verify pull request workflow                                          | ✅          |
| 6        | Implement triggers in build and release pipelines                                | ✅          |
| 7        | Add gates to pipelines (pre-deployment conditions)                               | ✅          |
| 8        | Enforce pull-request-only access and restrict direct merges                      | ✅          |
| 9        | Integrate work items into pipelines and trace builds                             | ✅          |
| 10       | Attach GitHub repo to Azure Boards                                               | ✅          |

---

## 🔍 **Q1: Create a project with different user groups and implement group policies**
**Objective**: Establish role-based access using user groups.

**Summary**:
- Created project in Azure DevOps
- Configured custom user groups like `QA Team`, `New_Joiner`
- Applied permissions for Repos, Pipelines, Boards, and Artifacts
- Linked with GitHub repository

**Reference**:
- [Microsoft Docs – Add Users to Team Project](https://learn.microsoft.com/en-us/azure/devops/organizations/security/add-users-team-project)
**solution**
📎 [Download Solution File](https://github.com/prateek200445/Devops_celebal_week7/blob/main/week7_ques1.odt)

---

## 🔐 **Q2: Apply branch policies so only the project administrator can access the master branch**
**Objective**: Secure production branch access.

**Summary**:
- Applied branch-level permissions
- Denied `Contribute` to Contributors group
- Allowed only Project Administrators to push/merge

**Reference**:
- [Branch Permissions in Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/repos/git/branch-permissions)
**solution**
📎 [Download Solution File](https://github.com/prateek200445/Devops_celebal_week7/blob/main/week7_ques2%20and%206.odt)

---

## 🔒 **Q3: Apply branch security and locks**
**Objective**: Enforce branch immutability during deployment cycles.

**Summary**:
- Denied push and force push for contributors
- Locked the `main` branch to freeze changes
- Configured inheritance and granular permission levels

**Reference**:
- [Branch Policies and Locks](https://learn.microsoft.com/en-us/azure/devops/repos/git/branch-policies)
**solution**
📎 [Download Solution File](https://github.com/prateek200445/Devops_celebal_week7/blob/main/week7_ques3%20and%206.odt)

---

## 🔃 **Q4: Apply branch filters and path filters**
**Objective**: Optimize CI/CD by targeting only necessary changes.

**Summary**:
- Configured YAML pipeline triggers:
  ```yaml
  trigger:
    branches:
      include: [ main, develop ]
    paths:
      include: [ src/*, README.md ]
      exclude: [ docs/* ]
  ```
- GUI-based filter policies set via Branch Policies

**Reference**:
- [Pipeline Triggers Docs](https://learn.microsoft.com/en-us/azure/devops/pipelines/build/triggers)
**solution**
📎 [Download Solution File](https://github.com/prateek200445/Devops_celebal_week7/blob/main/week7_ques4.odt)

---

## 🔁 **Q5: Apply a pull request**
**Objective**: Enforce code review before merging.

**Summary**:
- Created feature branch `PULL_FROM_AD`
- Made changes and pushed to remote
- Created and merged a PR with admin approval

**Reference**:
- [Pull Requests in Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/repos/git/pull-requests)
**solution**
📎 [Download Solution File](https://github.com/prateek200445/Devops_celebal_week7/blob/main/week7_ques5.odt)
---

## 🚀 **Q6: Apply triggers in build and release**
**Objective**: Automate CI/CD using triggers.

**Summary**:
- YAML-based trigger setup:
  ```yaml
  trigger:
    branches:
      include: [ main ]
  ```
- Classic UI triggers also applied via GUI
- Release pipeline configured for CD with successful build trigger

**Reference**:
- [CI/CD Triggers Guide](https://learn.microsoft.com/en-us/azure/devops/pipelines/build/triggers)
**solution**
📎 [Download Solution File](https://github.com/prateek200445/Devops_celebal_week7/blob/main/week7_ques3%20and%206.odt)
📎 [Download Solution File](https://github.com/prateek200445/Devops_celebal_week7/blob/main/week7_ques2%20and%206.odt)

---

## 🛡 **Q7: Apply gates to the pipeline**
**Objective**: Implement pre-deployment validations.

**Summary**:
- Created release pipeline with `DeployToTest` stage
- Enabled 2-minute delay and approval gates
- Ensured safe deployment flow

**Reference**:
- [Release Pipeline Gates](https://learn.microsoft.com/en-us/azure/devops/pipelines/release/approvals/gates)
**solution**
📎 [Download Solution File](https://github.com/prateek200445/Devops_celebal_week7/blob/main/week7_ques7.odt)

---

## 🚫 **Q8: Apply security so contributors can only create pull requests, not merge**
**Objective**: Enforce pull-request-based merging only.

**Summary**:
- Denied direct `Contribute` access to `main`
- Enabled PR policies requiring minimum reviewers
- Contributors allowed to raise PRs, not merge

**Reference**:
- [Branch Security Docs](https://learn.microsoft.com/en-us/azure/devops/repos/git/branch-permissions)
**solution**
📎 [Download Solution File](https://github.com/prateek200445/Devops_celebal_week7/blob/main/week7_ques8.odt)

---

## 🔗 **Q9: Use work items in pipelines**
**Objective**: Enable traceability between work and builds.

**Summary**:
- Used `Fixes #<WorkItemID>` in commit messages
- Linked work items directly from PR UI
- Enabled policy: "Check for linked work items"

**Reference**:
- [Work Items in Azure Pipelines](https://learn.microsoft.com/en-us/azure/devops/boards/work-items/about-work-items)
**solution**
📎 [Download Solution File](https://github.com/prateek200445/Devops_celebal_week7/blob/main/week7_ques9.odt)

---

## 🔄 **Q10: Attach GitHub repo to Azure Boards**
**Objective**: Enable GitHub-Azure DevOps integration.

**Summary**:
- Connected GitHub repository to Azure DevOps project
- Enabled real-time board activity and linking PRs

**Reference**:
- [GitHub Integration with Azure Boards](https://learn.microsoft.com/en-us/azure/devops/boards/github/connect-to-github)
**solution**
📎 [Download Solution File](https://github.com/prateek200445/Devops_celebal_week7/blob/main/week7_ques10.odt)

---

## 📦 Tools Used
- **Azure DevOps**: Boards, Repos, Pipelines, Releases
- **GitHub**: Repo hosting & integration
- **YAML**: Pipeline automation
- **Classic UI Pipelines**: For visual configuration

---

## 🧑‍💼 Author
**Prateek Lachwani**  
Intern at Celebal Technologies  
GitHub: [prateek200445](https://github.com/prateek200445)

---

## 📄 License
This project is part of a professional internship assignment and is for educational/demo purposes only.

---

> "Secure, automate, trace – That’s the DevOps way."

Feel free to fork, star, or open issues for discussions!
