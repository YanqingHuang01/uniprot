#### Download Uniprot Protein Sequences

You can download protein sequences for the proteome from the following link:  
[Uniprot Proteome UP000005640](https://www.uniprot.org/proteomes/UP000005640)

1. **uniprotkb_proteome_UP000005640_reviewed_canonical.fasta**  
   20,406 protein sequences

2. **uniprotkb_proteome_UP000005640_reviewed_canonical_and_isoform.fasta**  
   42,502 protein sequences

3. **uniprotkb_proteome_UP000005640_reviewed_and_unreviewed.fasta**  
   83,401 protein sequences

4. **uniprotkb_proteome_UP000005640_reviewed_and_unreviewed_and_isoform.fasta**  
   105,497 protein sequences


#### Concatenate All Sequences in the Fasta File for Each Line with Header '>'

To concatenate all protein sequences in a fasta file into a single line per sequence (with headers starting with '>'), use the following `awk` command:

```bash
awk '/^>/ {if (seq) print seq; print $0; seq=""; next} {seq = seq $0} END {if (seq) print seq}' uniprotkb_proteome_UP000005640_reviewed_and_unreviewed_and_isoform.fasta > oneline_uniprotkb_proteome_UP000005640_reviewed_and_unreviewed_and_isoform.fasta
