# T3.2 pre- and processed eDNA data repositories

Links and data flows between repositories and databases where pre-processed ("raw" reads) and processed (species- and ASV/OTU tables) eDNA data are published.

```mermaid
flowchart TB;
    subgraph Processed eDNA data;
        OBIS["`**OBIS**
            *Occurrence data*
            *DwC DNA-derived extension*`"]
        GBIF["`**GBIF**
            *Occurrence data*
            *DwC DNA-derived extension*`"]


        OBIS <==> GBIF

        Dryad-processed{{"`Dryad
                ASV/OTU + species tables
                no standards`"}}
        Zenodo-processed{{"`Zenodo
                ASV/OTU + species tables
                no standards`"}}

        end
    subgraph Pre-processed eDNA data;
        ENA["`EMBL ENA
            *fasta*
            *GSC::MIxS + ENA checklists*`"]
        NCBI["`**NCBI Genbank/SRA**
            *fasta*
            *GSC::MIxS + NCBI checklists*`"] 

        ENA <==> NCBI

        Dryad-pre{{"`Dryad
                fasta
                no standards`"}}
        Zenodo-pre{{"`Zenodo
                fasta
                no standards`"}}
        end 

    ENA & NCBI  -.- OBIS & GBIF



style Dryad-processed stroke:#f66
style Zenodo-processed stroke:#f66

style Dryad-pre stroke:#f66
style Zenodo-pre stroke:#f66
```

