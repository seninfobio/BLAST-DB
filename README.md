# BLAST-DB
#Create uniprot_database
makeblastdb -in uniprot_sprot.fasta -dbtype prot &>log &


#Run database
blastx -num_threads 64 \
-qurey alatum.transcripts.fasta \
-db /NABIC/HOME/senthil/002_DB/uniprot_sprot.fasta \
-out uniprot.xml -outfmt 5 &>log &


#Create nr_database
makeblastdb -in nr -dbtype prot &>log &


#Run database
blastx -num_threads 64 \
-qurey alatum.transcripts.fasta \
-db /NABIC/HOME/senthil/002_DB/nr \
-out nr.xml -outfmt 5 &>log &


[Comprehensive Analysis of Non Redundant Protein Database](https://assets.researchsquare.com/files/rs-54568/v1_stamped.pdf)

[TAIR Protein sequences](https://www.arabidopsis.org/download_files/Genes/TAIR10_genome_release/TAIR10_blastsets/TAIR10_pep_20110103_representative_gene_model_updated)

[NCBI nr Database](https://ftp.ncbi.nlm.nih.gov/blast/db/FASTA/)

