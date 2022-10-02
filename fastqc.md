# Prepare the folders
folder="/home/cjmb3/MacroSpi1ChIPdataGEO/FASTQC"
mkdir $folder
fastq="/home/cjmb3/MacroSpi1ChIPdataGEO"          
cd $fastq
# Run fastqc:
for a in *.fastqsanger.gz; do echo $a; cat $a | fastqc $a -t 2 -o $folder; done
cd $folder
# only needed once to install multiqc: < pip install --user multiqc >
# then put it in my path and run it: < export PATH=/home/cjmb3/.local/bin:$PATH >
multiqc .
