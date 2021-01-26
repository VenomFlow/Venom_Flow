# Venom_Flow

# In developing VenomFlow  we used :
1)  Trimmomatic- for trimming Illumina FASTQ data and removing adapters. 
(Manual: http://www.usadellab.org/cms/uploads/supplementary/Trimmomatic/TrimmomaticManual_V0.32.pdf)
2)  FastQC- To determine the quality of FASTQ reads
(Manual: https://dnacore.missouri.edu/PDF/FastQC_Manual.pdf)
3)  Trinity - To reconstruct FASTQs 
( Manual : http://cbsu.tc.cornell.edu/lab/doc/trinity_workshop_part1.pdf)
4)  GetORF- turn assembly (nucleotides) into open reading frames or peptides/proteins (amino acids)
(Manual: http://embossgui.sourceforge.net/demo/manual/getorf.html)
5)  SignalP-  to identify all of the open reading frames that have a signal sequence for toxin characteristics.
(Manual: http://resources.qiagenbioinformatics.com/manuals/signalP/current/SignalP_User_Manual.pdf) 
6)  BLAST - to compare signalP results to other protein and rule our (based on e values for probability) non toxin proteins. 
(Manual: http://nebc.nerc.ac.uk/bioinformatics/documentation/blast+/user_manual.pdf)


1.1 Prerequisites for Docker:
Docker needs to be installed for Mac, Linux or clusters. (https://www.docker.com/get-started)

2.0 Understanding Docker:
Docker is using containers to develop, deploy and run applications. The use of the containers make the project lighter and flexible. In order to lunch each container, an image has to run. Each image includes everything that is needed for a container to run. In summary, a container is a runtime of an image, and each image becomes an individual memory of the container.

2.1 Test Docker version:
Ensure that we have the supported version of Docker:
