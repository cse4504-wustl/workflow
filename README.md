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
