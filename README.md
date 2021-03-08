# BLAST-DB
#Create database
makeblastdb -in uniprot_sprot.fasta -dbtype prot


#Run database
blastx -num_threads 64 \
-qurey alatum.transcripts.fasta \
-db /NABIC/HOME/senthil/002_DB/uniprot_sprot.fasta \
-out uniprot.xml -outfmt 5 &>log &


