# T3.1 reference libraries

State of the reference library landscape as assessed in the WP4 use cases. I'm trying to cover the markers, standards used, taxonomic backbown, and data flows. 
For now this only maps the reference libraries reported in the WP4 use cases. Next, I will add those covered by WP2 D2.1.
I also included some of the WP4 recommendations (e.g. using automated pipelines).

```mermaid
flowchart TB;
    subgraph Nucleotide databases;
        ENA["`EMBL ENA
            *all sequence data (fasta)*
            *GSC::MIxS + ENA checklists*
            *... taxonomy*`"]
        NCBI["`**NCBI Genbank/SRA**
            *all sequence data (fasta)*
            *GSC::MIxS + NCBI checklists*
            *NCBI taxonomy*`"] 

        ENA <== INSDC ==> NCBI

        end
        SILVA{{"`**SILVA**`"}}

        OWN1{{"`**own refseq 
                 from Genbank**`"}}
        NCBI--- |automated download|OWN1

        OWN2{{"`**own refseq**`"}}
        NCBI--- |manual download|OWN2
        IN---OWN2

    subgraph Quality-controlled databases;
        
        BOLD{{"`**BOLD**
                *COI*`"}}
        %%ENA & NCBI -.- BOLD

        MIDORI{{"`**MIDORI**`"}}

        IN{{"`**in-house db**`"}}

        GEANS{{"`**GEANS**`"}}

        end 

    subgraph Curated databases;

        diat{{"`**diat.barcode**
            *marker ...*
            *checklist/standard used?*
            *taxonomic backbone?*`"}}

     end



style IN stroke:#red
style OWN1 stroke:green
style OWN2 stroke:red

```

