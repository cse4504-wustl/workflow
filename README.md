# CSE 4504 Team Project GitHub Workflow

During the development of this project, the following workflow will be used for each stage (feature). The diagram shows the workflow for feature_1. For each subsequent feature, the same workflow will be used (replacing feature_1 with a different feature number or name).
```mermaid
%%{init: {'flowchart': {'nodeSpacing': 20, 'rankSpacing': 25, 'htmlLabels': false}, 'themeVariables': {'fontSize': '12px'}}}%%
flowchart TD
 
    Start([Start Project]) --> Design[In class design in a feature branch]
    style Start fill:#ED7A6D
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
 
    MergeMain --> Done([Feature Complete])
    style Done fill:#93DBB8
```

```mermaid
flowchart TD
    Start([Start Project]) --> InitFeature[Create 'feature_1' branch from main]
    subgraph Team_Start [Team Design Work]
    InitFeature --> Design[Design interfaces, commit and push to 'feature_1']
    Design --> DivideTasks[Divide implementation work among teammates. Update README.md file with Work Assignment section, specifying individual implementation responsibilities.]
    end

    subgraph Indiv_Work [Individual Development Work]
    DivideTasks --> BranchInd[Create individual task branch]
    BranchInd --> Implement[Implement assigned components]
    Implement --> PR_Ind[Open PR from individual task branch to 'feature_1']
    end
    style Indiv_Work fill:#96C9F2

    subgraph Team Integration Work
    Review_Ind -- Changes Needed --> Implement
    PR_Ind --> Review_Ind{Team Review}
    Review_Ind -- Approved --> Merge_Ind[Merge to 'feature_1']    
    Merge_Ind --> Pull[Pull updated 'feature_1']
    Pull --> Test[Run integration tests]
    Test --> Fix{Bugs Found?}
    Fix -- Yes --> FixCommit[Commit fixes to 'feature_1']
    FixCommit --> Test
    Fix -- No --> FinalPR[Open PR from feature_1 to 'main']
    FinalPR --> Review_Final{Final Review}
    Review_Final -- Approved --> MainMerge[Merge to 'main']
    end

    MainMerge --> Done([Feature Complete])
```
