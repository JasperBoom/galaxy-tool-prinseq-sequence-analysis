# galaxy-tool-prinseq-sequence-analysis

__!!Repo can be deleted, copy is also kept [here](https://github.com/JasperBoom/galaxy-tools-naturalis-internship)!!.__

Use PRINSEQ to do quality control checks on raw sequence data.  
The PRINSEQ tool will do quality control checks on raw sequence data. These checks include summary graphs and tables.

Files in fastQ format should always have a .fastq extension.  
Files in fastA format should always have a .fasta extension.

## Getting started

### Prerequisites
Download and install the following software according to the following steps.
* [PRINSEQ](https://sourceforge.net/projects/prinseq/files/)

The PRINSEQ folder should be moved to the following file and renamed to "Prinseq".
```
sudo mkdir -m 755 /home/Tools
/home/Tools <-- Move PRINSEQ to this directory
sudo chmod -R 755 /home/Tools/Prinseq
```
The following three files in the Prinseq folder should be made avaible from any location.
```
sudo ln -s /home/Tools/Prinseq/prinseq-lite.pl /usr/local/bin/prinseq-lite.pl
sudo ln -s /home/Tools/Prinseq/prinseq-graphs.pl /usr/local/bin/prinseq-graphs.pl
sudo ln -s /home/Tools/Prinseq/prinseq-graphs-noPCA.pl /usr/local/bin/prinseq-graphs-noPCA.pl
```
Make sure your system can handle JSON files.
```
sudo cpan JSON
```

### Installing
Download and install the tool according to the following steps.
```
cd /home/Tools
sudo git clone https://github.com/JasperBoom/galaxy-tool-prinseq-sequence-analysis
sudo chmod -R 755 galaxy-tool-prinseq-sequence-analysis
```
```
sudo mkdir -m 755 /home/galaxy/tools/directoryname
sudo cp /home/Tools/galaxy-tool-prinseq-sequence-analysis/getPrinseqAnalysis.sh /home/galaxy/tools/directoryname/getPrinseqAnalysis.sh
sudo cp /home/Tools/galaxy-tool-prinseq-sequence-analysis/getPrinseqAnalysis.xml /home/galaxy/tools/directoryname/getPrinseqAnalysis.xml
```
Edit the following file in order to make galaxy display the tool.
```
/home/galaxy/config/tool_conf.xml
```
```
<tool file="airdentification/getPrinseqAnalysis.xml"/>
```
Edit the following file in order to prevent galaxy from blocking html output.
```
/home/galaxy/config/galaxy.yml
```
```
sanitize_all_html: false
```

## Source(s)
* __Schmieder R, Edwards R__,  
  Quality control and preprocessing of metagenomic datasets.  
  Bioinformatics. 2011; 27(6): 863-864. __doi: 10.1093/bioinformatics/btr026__  
  [PRINSEQ](http://prinseq.sourceforge.net/)
* __Giardine B, Riemer C, Hardison RC, Burhans R, Elnitski L, Shah P__,  
  Galaxy: A platform for interactive large-scale genome analysis.  
  Genome Research. 2005; 15(10) 1451-1455. __doi: 10.1101/gr.4086505__  
  [Galaxy](https://www.galaxyproject.org/)

```
Copyright (C) 2018 Jasper Boom

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License version 3 as
published by the Free Software Foundation.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program. If not, see <https://www.gnu.org/licenses/>.
```
