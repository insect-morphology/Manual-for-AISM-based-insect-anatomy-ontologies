# How to create AISM-based insect anatomy ontologies using the Ontology Development Kit (ODK) and edit them in Protégé 

[![DOI](https://zenodo.org/badge/331670812.svg)](https://zenodo.org/badge/latestdoi/331670812)

A manual edited by [Jennifer C. Girón](https://github.com/JCGiron), [István Mikó](https://github.com/teleaslamellatus), and [Luis A. González Montaña](https://github.com/luis-gonzalez-m) 

**Suggested citation**: Girón, J. C., González Montaña, L. A., Mikó, I. 2021. How to create AISM-based insect anatomy ontologies using the Ontology Development Kit (ODK) and edit them in Protégé. GitHub repository. https://doi.org/10.5281/zenodo.4642556

January 2021

## Background

We created an ontology for the Anatomy of the Insect SkeletoMuscular system ([AISM](https://github.com/insect-morphology/aism)) using the Ontology Development Kit ([ODK](https://github.com/INCATools/ontology-development-kit)). The ODK provides a standardized system to create, manage, release and edit ontologies to maximize interoperability among them (i. e., ability to reuse terms from existing ontologies; more details at https://douroucouli.wordpress.com/2018/08/06/new-version-of-ontology-development-kit-now-with-docker-support/) and facilitate collaborative editing using [GitHub](https://github.com/). 

The AISM contains basic and generalized terms shared across insects, along with relationships and annotation options, with the idea that it serves as a base for order-specific insect anatomy ontologies that incorporate order-specific terms. So the idea with the AISM is to provide a backbone and headstart for order-specific ontologies.

Because of the way that ODK imports pre-existing terms, the full AISM can be overwhelming for first-time users, as it includes all the terms and relationships inherited from multiple hierarchies from other ontologies involved (i.e. [BFO](http://www.obofoundry.org/ontology/bfo.html), [BSPO](http://www.obofoundry.org/ontology/bspo.html), [PATO](http://www.obofoundry.org/ontology/pato.html), [RO](http://www.obofoundry.org/ontology/ro.html), [UBERON](http://www.obofoundry.org/ontology/uberon.html)). That is why a **_simplified version of the AISM_** is provided and should be the starting point for any future insect order-specific ontologies. This version includes essential relationships and annotation properties as well as basic insect-specific terms.

We provide here instructions for creating ontologies using this **_simplified version of the AISM_**.

## Initial thoughts for order-specific ontologies

Given that the AISM already contains basic terms and definitions for Insecta, the main goal of order-specific ontologies would be to gather order-specific terminology.

The way we are doing this for the Coleoptera Anatomy Ontology project [COLAO](https://github.com/insect-morphology/colao) is by getting all the most broadly accepted beetle terms and definitions from Lawrence and Ślipiński (2013; Adult morphology. In: [Australian beetles volume 1: morphology, classification and keys. CSIRO Publishing](https://www.publish.csiro.au/book/6466/), p. 30–63), and for now, adding them to a team-shared spreadsheet. Once we get those terms incorporated into the ontology file, we will be adding additional terms traditionally used, annotating whether those are synonyms of the more broadly accepted terms. We will also add terms from specialized morphological works on different skeletal systems in order to increase and refine the knowledge base.

### Defining a name and ID for order-specific ontologies
We invite you to read through the [Principles](http://www.obofoundry.org/principles/fp-000-summary.html) established by the [OBO Foundry](http://www.obofoundry.org/about-OBO-Foundry.html), the organization working to build tools and standards to maintain and increase interoperability across biological ontologies. Specifically dealing with ontology names is [Principle 3](http://www.obofoundry.org/principles/fp-003-uris.html) and the [recommendations](http://www.obofoundry.org/id-policy) therein. 

For now, once you define an ID, which will be the prefix for all your unique identifiers and the acronym for your order-specific ontology, just make sure that this ID is not listed on the [main OBO Foundry page](http://www.obofoundry.org/). Once you have a first release version of your ontology you will need to officially request the name space by issuing a [New Ontology Request](https://github.com/OBOFoundry/OBOFoundry.github.io/issues/new?assignees=&labels=new+ontology&template=new-ontology-request.md&title=) via Issue Tracking in GitHub (see also the available [instructions](http://obofoundry.org/docs/NewOntologyRegistrationInstructions.html) for this).


## Getting started

### Required software

Managing an ontology in the context of the [ODK](https://github.com/INCATools/ontology-development-kit) offers the advantage of collaborative work with version control. It requires ontology managers and editors to be familiar with the _command line_, the use of [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) and [GitHub](https://github.com/), and the use of [Protégé](https://protege.stanford.edu/).

**Every member of the team will need:**
- A **text editor program** installed in their computers to explore and edit files without interfering with file format. There are several options: 

The simplest editors:

**For Mac:** [BBEdit](https://www.barebones.com/products/bbedit/)

**For Windows:** [Notepad++](https://notepad-plus-plus.org/downloads/)

Other programs with text editor capabilities that are also used for programming, available for both Mac and Windows: [Atom](https://atom.io/) and [Visual Studio Code](https://code.visualstudio.com/).
- To have [**git**](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) installed on the computer
- A [GitHub](https://github.com/) account
- To be able to pull files from and push files to GitHub from their computers either using git commands in the command line (the route recommended by developers) or [GitHub Desktop](https://desktop.github.com/) (an app to manage your GitHub repositories from your computer).
- To install and use [Protégé](https://protege.stanford.edu/) (an ontology editing software) to edit the appropriate ontology file directly on their computers.

## Workflow overview

There are two kinds of roles in the development of the AISM and AISM-based ontologies: **managers** and **editors**. Here is a simplified overview of the tasks for each role:

![Overview](https://github.com/insect-morphology/Manual/blob/main/img/overview.png)


### Ontology manager tasks:

For each order-specific ontology there should be at least one **manager**. This person has several tasks. We will walk you through each of the steps in this manual.
1. [Set up the main repository](https://github.com/insect-morphology/Manual-for-AISM-based-insect-anatomy-ontologies/blob/main/Sections/Setting-up-main-repository.md) by requesting a "placeholder repository" to be hosted at [insect-morphology](https://github.com/insect-morphology) 
2. [Create an AISM-based ontology](https://github.com/insect-morphology/Manual/blob/main/Sections/Creating-AISM-based-insect-ontology.md) using the [Ontology Development Kit](https://github.com/INCATools/ontology-development-kit), including the first release of the ontology
3. [Upload this initial AISM-based ontology as a repository](https://github.com/insect-morphology/Manual/blob/main/Sections/Upload-initial-ontology-as-GitHub-repository.md) in [GitHub](https://github.com/)
4. [Submit a pull request](https://github.com/insect-morphology/Manual/blob/main/Sections/Submit-pull-request.md) to get the AISM-based ontology files to be hosted at [insect-morphology](https://github.com/insect-morphology) (at this stage the order-specific ontology main manager will become an admin within the [insect-morphology](https://github.com/insect-morphology) organization and will be able to review and accept pull requests from collaborators)
5. [Manage and maintain](https://github.com/insect-morphology/Manual/blob/main/Sections/Manage-idranges.md) the `idranges` file
6. Review and accept pull requests submitted by order-specific ontology **editors**
7. [Submit the new ontology for inclusion in the OBO Foundry](http://www.obofoundry.org/faq/how-do-i-register-my-ontology.html) - this will be done when there has been some order-specific development (when order-specific terms have been added)

### Ontology editor tasks:

Ontologies hosted at [insect-morphology](https://github.com/insect-morphology) can be edited by anyone who wishes to, but changes must be submitted for review and acceptance to the main repository.

1. Request an ID range by contacting the **ontology manager** (who should be identified in the initial `README.md` file in the ontology repository at [insect-morphology](https://github.com/insect-morphology)), or by creating a new issue within the appropriate ontology repository.
2. [Get the ontology files](https://github.com/insect-morphology/Manual/blob/main/Sections/Obtaining-main-ontology-files.md) available from [insect-morphology](https://github.com/insect-morphology)
3. [Edit the appropriate ontology file](https://github.com/insect-morphology/Manual/blob/main/Sections/Using-Protege.md) using [Protégé](https://protege.stanford.edu/)
4. [Submit a pull request](https://github.com/insect-morphology/Manual/blob/main/Sections/Submit-pull-request.md) so that the **ontology manager** can take a look at your proposed changes and accept them if appropriate. 

------------------

If you have comments about a particular term that needs revision, but do not want to get into ontology editing, you can use our [issue tracker](https://github.com/insect-morphology/aism/issues), providing as much information as you can, including references with DOI if possible to support your request.
