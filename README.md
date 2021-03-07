# transposon_annotation_resonaTE
Transposon annotation tool "resonaTE" (part of TransposonUltimate)

## Installation
Installation as [CondaPackage](https://anaconda.org/DerKevinRiehl/transposon_annotator_reasonate):
```
 conda install -c derkevinriehl transposon_annotator_reasonate 
```
*Note: Otherwise you can find all source codes in this Github repository.*

## How to use ''reasonaTE''
**1) Create a project**
```
mkdir workspace
resonaTE -mode createProject -projectFolder workspace -projectName testProject -inputFasta sequence.fasta
```

**2) Annotate genome with annotation tools**
To annotate the genome with different annotation tools, three possible ways exist. 

*Option 1:* annotate with all tools automatically (this does not include ltrPred).
```
reasonate -mode annotate -projectFolder workspace -projectName testProject -tool all
```

*Option 2:* annotate with one specific tool (good for parallelization or rerunning, recommended).
```
reasonate -mode annotate -projectFolder workspace -projectName testProject -tool helitronScanner
reasonate -mode annotate -projectFolder workspace -projectName testProject -tool ltrHarvest
reasonate -mode annotate -projectFolder workspace -projectName testProject -tool mitefind
reasonate -mode annotate -projectFolder workspace -projectName testProject -tool mitetracker
reasonate -mode annotate -projectFolder workspace -projectName testProject -tool must
reasonate -mode annotate -projectFolder workspace -projectName testProject -tool repeatmodel
reasonate -mode annotate -projectFolder workspace -projectName testProject -tool repMasker
reasonate -mode annotate -projectFolder workspace -projectName testProject -tool sinefind
reasonate -mode annotate -projectFolder workspace -projectName testProject -tool sinescan
reasonate -mode annotate -projectFolder workspace -projectName testProject -tool tirvish
reasonate -mode annotate -projectFolder workspace -projectName testProject -tool transposonPSI
reasonate -mode annotate -projectFolder workspace -projectName testProject -tool NCBICDD1000
```

*Option 3:* run annotation tools with specified parameters (for advanced users)
For this purpose, we provide conda packages of all [transposon_annotation_tools](https://github.com/DerKevinRiehl/transposon_annotation_tools) except for ltrPred.
Please use the fasta file with renamed sequence names of the workspace project folder. (e.g. *workspace/testProject/sequence.fasta*)
Please note, as some tools (HelitronScanner, MiteFinderII, MITE-Tracker, SINE-Finder, TIRvish) do not annotate on both strands, we recommend to run these on the reverse complementary as well (e.g. *workspace/testProejct/sequence_rc.fasta*). Once you annotated the genomes with your own specified parameter settings, please copy the result files into the workspace's project Folder as shown in the example project (e.g. results of HelitronScanner to copy into *workspace/testProject/helitronScanner*) and rename the files accordingly.

*Running ltrPred:* If you want to include ltrPred annotations into the pipeline as well, install and run [ltrPred](https://github.com/HajkD/LTRpred). Later on, copy the result files into the project folder (*workspace/testProject/ltrPred*) and rename the files accordingly.

**3) Run the pipeline on the genome annotations**


## Documentation of output files


## Citations
Please cite our paper if you find transposition event detector "deTEct" useful:
(in progress)
