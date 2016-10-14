---
autotoc: true
title: July 20, ,,  2012 Galaxy Development News Brief
---
<div class='right'></div>



<br />
# Get Galaxy

<div class='left'><a href='http://getgalaxy.org/'><img src='http://galaxy.psu.edu/static/getgalaxy.png' alt='getgalaxy' width="50px" /></a></div>

 **[getgalaxy.org](http://getgalaxy.org)** 

**new**: `% hg clone http://www.bx.psu.edu/hg/galaxy galaxy-dist`

**upgrade**: `% hg pull -u -r ec29ce8e27a1`

<br />
# GCC2012
<div class='center'><a href='/Events/GCC2012'><img src='/Events/GCC2012/GCC2012LogoWide400.png' alt='2012 Galaxy Community Conference' height="100" /></a> &nbsp; <a href='/Events/GCC2012/TrainingDay'><img src='/Events/GCC2012/GCC2012TrainingDayLogo.png' alt='Training Day' height="100" /></a></div>

The [2012 Galaxy Community Conference (GCC2012)](/Events/GCC2012) is a few short days away. Late registration is still open.

<br />
# FreeBayes Migration
The tool **Human Genome Variation -> [Freebayes](http://bioinformatics.bc.edu/marthlab/FreeBayes)** has moved from the Galaxy distribution to the Galaxy Main **[/Tool Shed](/Tool Shed)**.

```FreeBayes```
 is a high-performance, flexible, and open-source Bayesian genetic variant detector. It operates on [BAM](/Datatypes#bam) alignment files, which are produced by most contemporary short-read aligners.

<br />
# EMBOSS Update
The `emboss_5` repository in the Galaxy Main Tool Shed has been updated to include information for automatically installing the **EMBOSS Version 5.0.0** tool dependencies.  If you've installed the `emboss_5` repository into your local Galaxy instance, get this update from the tool shed, and you'll have the option of installing the tool dependencies.  

<br />
# Admin Genome Indexing
If `enable_beta_job_managers = True`, Galaxy will now show a *new option* in the admin interface, titled **Manage Local Data**. With this tool, a Galaxy admin will be able to select and download any genome already contained with the local `$GALAXYROOT/tool-data/shared/ucsc/builds.txt` file sourced from UCSC, NCBI, or Ensembl, optionally indexing the FASTA data with one or more of BWA, Bowtie, Bowtie 2, PerM, Picard, and SAM. After these processes finish, the indexed build will then be available for other tools in the analysis section. This does not replace setting up a build.txt file ([read more ...](/Admin/Data Integration)). This would replace many of the manual indexing processes for commonly used tools ([read more...](/Admin/NGS Local Setup)). Please this tool is still **beta**, feedback and bug reports welcome at galaxy-dev@bx.psu.edu for discussion. We will also touch on it during a breakout session at GCC (Day 2, Section 8, [Automation Strategies](/Events/GCC2012/Program/Breakouts/AutomationStrategies)).

Example of selecting a source, the indexes to create, and the target genome:
![](/Images/NewsGraphics/2012_07_20_select.png)

The status of the indexing for a single genome:
![](/Images/NewsGraphics/2012_07_20_status.png)

And a global status of all indexes for all genomes in progress:
![](/Images/NewsGraphics/2012_07_20_main-page.png)

<br />
# Simplified install of 3rd-party Dependencies
Automatic third-party tool dependency installation and compilation with installed repositories

Tool shed repository owners can define information in their repositories that enable third party tool dependencies to be automatically installed along with the repository for those repositories that contain tools that require the dependencies.  The process for enabling this is the inclusion of a simple xml file named tool_dependencies.xml in the repository. [Read more…](/Tool Shed#automatic_third-party_tool_dependency_installation_and_compilation_with_installed_repositories)

<br />
# Improved Error Handling
Several changes made in in determining errors from tool exit codes and output.  In the past, Galaxy has determined if a tool has an error by checking if anything was written to standard error (`stderr`}). Now each tool's XML can be customized to check the tool's exit code, standard output (`stdout`), and standard error (`stderr`). The exit code can be checked against a supplied range of values, and regular expressions can be checked against `stdout` and `stderr`. Users can specify if the error should result in a warning or a fatal error. If this feature is not specified, then the previous behavior of just checking `stderr` will be used.

<br />
# Tools
[/Admin/Config/Tool Dependencies](/Admin/Config/Tool Dependencies)
* **[Tophat2](http://tophat.cbcb.umd.edu/tutorial.html)** wrapper enhancements: 
  * use **Bowtie2** build
  * add option to report discordant pairs
  * update tests
  * add **Bowtie2** preset options

<br />
# User Interface (UI)
* *Enhancements*
  * Full integration with **[myExperiment](http://www.myexperiment.org)** website. Galaxy workflows can be 
    * exported from Galaxy to **myExperiment** and 
    * searched and imported from myExperiment website
  * Support for genomes as first-class objects

<br />
# Galaxy Track Browser (GTB)
[Trackster](/Learn/Visualization)
* New parameter space visualization for Trackster
* Make bookmarks available in shared Trackster visualizations

<br />
# Tool Shed
[/Tool Shed](/Tool Shed)
* *Enhancements*
  * The tool shed's category grid is now displayed when searching and browsing tool sheds from a local Galaxy instance. 
  * This category grid's search feature searches valid repository names and descriptions when browsing a tool shed from Galaxy.
* Going forward from this Galaxy release, the main Galaxy tool shed will track the Galaxy releases and the galaxy-dist repository on bitbucket.

<br />
# Bug Fixes
<div class='right'><a href='/Support'><img src='/Images/Icons/bug.png' alt='bugs' width="20" /></a></div> 
* Support Unvalidated values when exporting histories

<br />
# Announcements
[/News](/News), *[July 2012 Galaxy Update](/GalaxyUpdates/2012_07)*
## Collaboration
The new RGalaxy package in Bioconductor. [Read more …](/News/RGalaxyWrapRFunctionsAsTools)
<br />
## GalaxyCzars
<div class='right'><a href='/Community/GalaxyCzars'><img src='/Images/Logos/GalaxyCzars.png' alt='GalaxyCzars' width="150" /></a></div>
The [GalaxyCzars group](/Community/GalaxyCzars) was launched and had its [first meetup on July 9](/Community/GalaxyCzars/Meetups/2012_07_09).  !GalaxyCzars is a group of people that manage large local Galaxy installations.  See the [meeting writeup](/Community/GalaxyCzars/Meetups/2012_07_09) for links to slides and a screencast. The !GalaxyCzars will have a breakout at [GCC2012](/Events/GCC2012), and the next conference call will follow in September.
<br />
## Galaxy is Hiring!
<div class='left'>![Galaxy wants YOU](/Images/Icons/PointingFinger.png)<div class='center'></div></div>
**The [Galaxy Team](/GalaxyTeam) Wants You!**
<br />
Want to work on one of the fastest growing open source bioinformatics projects around?  The [Galaxy Project](http://galaxyproject.org/), a highly successful high throughput data analysis platform for Life Sciences with over 15,000 users worldwide, is hiring. [Read more...](/GalaxyIsHiring)
<br />
<br />
---
<br />
<br />
# About Galaxy
**[GalaxyProject.org](http://galaxyproject.org)**

The **[GalaxyTeam](http://bitbucket.org/galaxy/galaxy-central/wiki/GalaxyTeam/)** is a part of **[BX](http://www.bx.psu.edu/)** at [Penn State](http://www.psu.edu/), and the **[Biology](http://www.biology.emory.edu/)** and **[Mathematics and Computer Science](http://www.mathcs.emory.edu/)** departments at [Emory University](http://www.emory.edu/home/index.html/). 

**[Galaxy](http://usegalaxy.org )** is supported in part by [NSF](http://www.nsf.gov/), [NHGRI](http://www.genome.gov/), the [Huck Institutes of the Life Sciences](http://www.huck.psu.edu/), and [The Institute for CyberScience at Penn State](http://www.ics.psu.edu/), and [Emory University](http://www.emory.edu/home/index.html).

Join us at **Twitter [@galaxyproject](http://twitter.com/#galaxyproject)** or just read our tweets **[/Galaxy on Twitter](/Galaxy on Twitter)**