# T3.3.2 Biodiversity data publishers

Links and data flows between biodiversity data publishers under T3.3 subtask T3.3.2 investigated [here](https://docs.google.com/spreadsheets/d/19YDmwBHyQ-77WHH79rsKAJrEMVifIENL7HfiiGRdBQ8/edit?gid=0#gid=0)

```mermaid
flowchart LR;
    subgraph Global;
        OBIS["`**OBIS**
            *DwC*`"]
        GBIF["`**GBIF**
            *DwC*`"]
        PANGEA{{PANGEA}}

        OBIS <==> GBIF
        PANGEA --> OBIS
        PANGEA --> GBIF
        iNaturalist --> GBIF
        Observation --> GBIF
        VertNet -.-> GBIF

        Dryad{{Dryad}}
        GigaDB{{GigaDB}}
        Zenodo{{Zenodo}}
        OpenBioDiv{{OpenBioDiv}}

        style Dryad stroke:#f66
        style GigaDB stroke:#f66
        style Zenodo stroke:#f66
        style OpenBioDiv stroke:#f66

        end
        subgraph Regional
        SCAR["`SCAR Antarctic Biodiversity Portal
            *DwC*`"]
        EurOBIS["`**EurOBIS**
            *DwC*`"] 
        EMODnet[EMODnet biology]
        SCAR <--> GBIF
        SCAR --> OBIS
        EurOBIS --> OBIS
        EurOBIS --> EMODnet
        HELCOM[HELCOM]
        end 

        subgraph National
        FinBIF --> GBIF
        PNDB -.-> GBIF
        NBN[NBN Atlas] --> GBIF
        EnviDat{{EnviDat}}
        GFBio --> GBIF
        end

        subgraph Institutional
        DASSH
        DASSH --> EurOBIS
        DASSH --> EMODnet
        DASSH --> NBN
        DASSH --> GBIF
        end
```

