# CSE 4504 Team Project GitHub Workflow

During the development of this project, the following workflow will be used for each stage (feature). The diagram shows the workflow for feature_1. For each subsequent feature, the same workflow will be used (replacing feature_1 with a different feature number or name).
```mermaid
%%{init: {'flowchart': {'nodeSpacing': 20, 'rankSpacing': 25, 'htmlLabels': false}, 'themeVariables': {'fontSize': '12px'}}}%%
flowchart TD
 
    Start([Start Project]) --> Design[In class design in a feature branch]
    Design --> Implement[Implement your part in YOUR branch made from feature branch]
    style Design fill:#FFFEC4
    Implement --> Review[In class review of your work]
    style Implement fill:#96C9F2
    Review -- Approved --> Merge_Ind[Merge YOUR branch to feature branch]
    style Review fill:#FFFEC4
    Review -- Changes Needed --> Implement
    Merge_Ind --> IntegrationTest[Test feature branch]
    style Merge_Ind fill:#FFFEC4
    style IntegrationTest fill:#FFFEC4
    IntegrationTest -- Pass --> MergeMain
    IntegrationTest -- Fail --> Fix[Implement fixes in feature branch]
    Fix --> IntegrationTest
    style Fix fill:#96C9F2
    MergeMain --> Done([Feature Complete])
    style MergeMain fill:#FFFEC4
    style Done fill:#93DBB8
```
The diagram below shows a git branches that you would typically have to complete a feature:
```mermaid
%%{init: {'gitGraph': {'mainBranchName': 'main'}}}%%
gitGraph
    commit id: "Initial"
    branch feature
    checkout feature
    commit id: "Design in feature branch"

    branch person1
    checkout person1
    commit id: "P1: implement"
    commit id: "P1: revise after review"

    checkout feature
    branch person2
    checkout person2
    commit id: "P2: implement"
    commit id: "P2: revise after review"

    checkout feature
    branch person3
    checkout person3
    commit id: "P3: implement"
    commit id: "P3: revise after review"

    checkout feature
    merge person1 id: "Merge P1 branch"
    merge person2 id: "Merge P2 branch"
    merge person3 id: "Merge P3 branch"
    commit id: "Integration test - fail"
    commit id: "Fix issue"
    commit id: "Integration test - pass"

    checkout main
    merge feature id: "Feature complete"
```
