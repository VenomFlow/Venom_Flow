# VenomFlow instruction manual

You can use the [Galaxy Docker Image GitHub page](https://github.com/bgruening/docker-galaxy-stable) to review more information on how to install and maintain Galaxy Docker Images.

Programs used in developing VenomFlow:
1. [Trimmomatic](http://www.usadellab.org/cms/uploads/supplementary/Trimmomatic/TrimmomaticManual_V0.32.pdf)- To trim Illumina FASTQ data and to remove adapters. 
2. [FastQC](https://dnacore.missouri.edu/PDF/FastQC_Manual.pdf)- To determine the quality of the FASTQ reads
3. [Trinity](http://cbsu.tc.cornell.edu/lab/doc/trinity_workshop_part1.pdf)- To reconstruct FASTQs
4. [GetORF](http://embossgui.sourceforge.net/demo/manual/getorf.html)- To turn assembly (nucleotides) into open reading frames or peptides/proteins (amino acids)
5. [SignalP](http://resources.qiagenbioinformatics.com/manuals/signalP/current/SignalP_User_Manual.pdf)- To identify signal sequence for toxin characteristics
6. [BLAST](http://nebc.nerc.ac.uk/bioinformatics/documentation/blast+/user_manual.pdf)- To Validate our results 

## Understanding Docker 

[Docker](https://www.docker.com/get-started) is a platfrom that uses containers to develop, deploy and run applications. The use of the containers make the project lighter and flexible. In order to lunch each container, it runs an image which has everything that is needed for a container to run. In summary, a container is a runtime of an image, and each image becomes an individual memory of the container.

- Docker needs to be installed before accessing VenomFlow 

### Testing and Running Docker Image 

After installing Doocker, ensure that you have have the supported version of Docker by using:

```
docker --version
```

In order to see the list of running containers use:
```
docker ps
```

The next step is to create Docker file.Through Dockerfile you can define what goes into the container that builds Docker image. (Image has all the needed dependencies for the application). First, create project directory with file names Dockerfile and paste the following:

```
. /code RUN pip install -r requirements.txt CMD ["python", "app.py]
```

For more guidance in installing Docker file please click [here](https://docs.docker.com/engine/reference/builder/)

**Creating Docker Image**

We based our docker image following bgruening instructions that already contains [full-fledged Galaxy installation](https://github.com/bgruening/docker-galaxy-stable)

After creation of Docker image and the appropriate dockerfile, you can run the image by using:

```
docker run -v {your project location}:/export -itp {your IP+your choice of web tag number} {your repository ID}:Tag startup
```

When the image running, the web browser can run with the IP and the web tag number. For example:

```
146.95.252.87.8092
```

To access VenomFlow pipeline, simply run 8082 web tag with you IP adress and use 'admin' for Username and 'admin' for Password.

When logged in, please go to 'Workflow' and run 'Venomic_1a' pipeline. Every step can be altered to specific set of parameters or data sets. 

To save the changes you made to the image you would need to do two things: to commit to the changes (with a new tag) and to use ‘push’ the save. Therefore, firstly you would use:

```
#commitID user/repotag:tagname' and to push your work: 'Docker push
```

