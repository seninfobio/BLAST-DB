# BLAST-DB
>wget ftp://ftp.ncbi.nlm.nih.gov/blast/db/FASTA/nr.gz && gunzip nr.gz &>log.nrdb &

>wget ftp://ftp.ncbi.nlm.nih.gov/blast/db/FASTA/swissprot.gz && gunzip swissprot.gz &> log.swissprotdb &

>wget ftp://ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/uniprot_sprot.fasta.gz &>log.uniprotdb &

>wget ftp.uniprot.org/pub/databases/uniprot/current_release/knowledgebase/complete/uniprot_trembl.fasta.gz &>log.trembldb &

[Biostar reference](https://www.biostars.org/p/148448/)
>curl -o plant.#1.protein.faa.gz ftp://ftp.ncbi.nlm.nih.gov/refseq/release/plant/plant.\[1-198\].protein.faa.gz
            
  [uniprot_plant proteins](http://www.uniprot.org/uniprot/?query=taxonomy%3A%22Viridiplantae+[33090]%22+keyword%3A%22Complete+proteome+[KW-0181]%22)
  



#Create uniprot_database
makeblastdb -in uniprot_sprot.fasta -dbtype prot &>log &


#Run database

blastx -num_threads 64 \
-query alatum.transcripts.fasta \
-db /NABIC/HOME/senthil/002_DB/uniprot_sprot.fasta \
-out uniprot.xml -outfmt 5 &>log &


#Create nr_database

makeblastdb -in nr -dbtype prot &>log &


#Run database

blastx -num_threads 64 \
-query alatum.transcripts.fasta \
-db /NABIC/HOME/senthil/002_DB/nr \
-out nr.xml -outfmt 5 &>log &


[Comprehensive Analysis of Non Redundant Protein Database](https://assets.researchsquare.com/files/rs-54568/v1_stamped.pdf)

[TAIR Protein sequences](https://www.arabidopsis.org/download_files/Genes/TAIR10_genome_release/TAIR10_blastsets/TAIR10_pep_20110103_representative_gene_model_updated)

[NCBI nr Database](https://ftp.ncbi.nlm.nih.gov/blast/db/FASTA/)

