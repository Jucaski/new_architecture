```mermeid
---
config:
  theme: redux
  layout: dagre
---
flowchart LR
 subgraph ui["UI"]
        BA(("UI Components"))
  end
 subgraph logic["Logic"]
        LA(("interface datasource(inegi)"))
        BB(("Business Logic"))
  end
 subgraph manual["Manual"]
        CC(("Verified Data"))
        CB(("Standarice Data"))
        CA(("Cleaning Data"))
  end
 subgraph clean["Conmesurabilidad programada"]
        BF(("Verified Data"))
        BD(("Standarice Data"))
        BC(("Cleaning Data"))
  end
    DA(("data source 1(inegi)")) --> manual
    DB(("data source 2(const)")) --> manual
    clean --> db
    LA --> BB
    n1["inegi"] --> n2["año"]
    n2 --> n3["cvegeo"]
    n4["get /datasource2/...<br>get /all/...<br>get /datasource2/...<br>get /datasource1/data"] --> logic
    ui --> n4
    n5(("data source 3()")) --> manual
    manual --> clean
    logic --> db[("db")]

    n4@{ shape: rect}
```
