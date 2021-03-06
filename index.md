

Welcome to the website of the **JeDaSS** poster @[ESWC_2021](https://2021.eswc-conferences.org/)! 

# **Towards Scientific Data Synthesis Using Deep Learning and Semantic Web**
<br/>
  _We aim to develop a new approach combining semantic web and machine learning to_👇
  
 * categorize a given dataset into a domain topic and,
 * extract hidden links between its data attributes and data attributes from other datasets
 
  <br/>
  <img style="margin-left: auto; margin-right: auto; width: 80%" src="assets/summary.png">
 <br/>
 


##  Motivation

 * The Collaborative Research Center [(CRC) AquaDiva](http://www.aquadiva.uni-jena.de/) is a large collaborative project spanning a variety of domains including [biology](http://www.aquadiva.uni-jena.de/Projects.html), [geology](http://www.aquadiva.uni-jena.de/D03.html), [chemistry](http://www.aquadiva.uni-jena.de/C03.html), and [computer science](http://www.aquadiva.uni-jena.de/D01.html) with the common goal to better understand the Earth’s critical zone. 
 *  Datasets collected within [AquaDiva](https://addp.uni-jena.de/), like those of many other cross-institutional, cross-domain research projects, are complex and difficult to reuse since they are highly diverse and heterogeneous.
 *  This limits the dataset accessibility to the few people who were either involved in creating the datasets or have spent a significant amount of time aiming to understand them.
 *  Furthermore, more time is needed to figure out the major theme of unfamiliar datasets.
 
We believe that dataset analysis and summarization can be used as an elegant way to provide a concise overview of an entire dataset.

## Definitions
* A *dataset (DS)* is defined as a tuple _<PD, MD>_ of *primary data (PD)* and *metadata (MD)* organized for a specific purpose.
* _PM_ represents actual data organized according to a specific structure, called *data structure (DT)*
* *DT* consists of a set of *data attributes (i.e. DT={da1, da2,...,dtn})*
* Each data attribute has a _name_, _datatype_, _(optional) unit_, _description_, as well as **annotation** based on a domain ontology.
* Each tuple in the primary data is a collection of data cells containing data values (called _data points_).
* _MD_ contains information about,e.g., the data owner, data curators, the methodology used to produce primary data, etc.

In our implementation, almost all data attributes of available datasets are annotated using the [**AquaDiva ontology (ADOn)**](https://fusion.cs.uni-jena.de/fusion/activity/oapt) as the domain-specific ontology.

<b/>

## Methodology

* Developing new data analysis and summarization approach 
   * combining semantic web and machine learning approaches
   * Semantically classifies data attributes of scientific datasets (tabular data) 
   *  This classification contributes to summarizing individual datasets, but also to link them to others. 
  
  <img style="margin-left: auto; margin-right: auto; width: 80%" src="assets/JeDaSS.png">
 
 * The proposed approach has two main phases:
   * _off-line_: to train and build a classification model using supervised deep learning using convolution layers and
   * _on-line_: making use of the pre-trained model to classify datasets into the learned categories.
 
 <img style="margin-left: auto; margin-right: auto; width: 80%" src="assets/framework.png">

### Data preparation
 
 * Proposing a new structure capturing several features from the _dataset_ into a single container
 * As _data attributes_ are the most important parts of the _dataset_, gathering all information related to _data attributes_
 * Considering for each data attribute  the name, datatype, unit, data points attached to the data attribute as well as its semantic annotation. 

   <img style="margin-left: auto; margin-right: auto; width: 80%" src="assets/prep1.png">

 
 ### Image generation
 
 * Proposing a method to transform the constructed new structure into a number of images, where a set of images is generated for each data attribute
 *  As shown below in the Figure,  the *”Airtemperaturemean”* data attributes from the *” Weather and soil data monitoring”* along with its annotation, data type (decimal), unit(Celsius), and 30 data points
 <img style="margin-left: auto; margin-right: auto; width: 50%" src="assets/conv1.png">
 

### Classification
 
 * Currently using the [ResNet18 convolutional neural network](https://arxiv.org/pdf/1512.03385.pdf) to build the classification model
 * Building and testing the proposed approach using datasets of the [AquaDiva data portal](addp.uni-jena.de).
   * Using 114 datasets representing different domain topics, such as weather monitoring, groundwater hydrochemistry, gene abundance, or soil physical parameters
   * 70% of these were used for training and 30% for evaluation
   * the total number of _data attributes_ is 1300
   * the number of _data points_ within a dataset ranges from 300 (5 data attributes×60 tuples) to 12,000,000

<br/>
 
 ## Prelimanry results
  <img style="margin-left: auto; margin-right: auto; width: 80%" src="assets/result.png">
 
<br/>

## Availability
 The resources related to the development of the proposed approach can be found at the [GitHub](https://github.com/fusion-jena/JeDaSS)

<br/>

# People
* [Alsayed Algergawy](https://fusion.cs.uni-jena.de/fusion/members/alsayed-algergawy/), Heinz-Nixdorf  Chair for Distributed Information Systems, University of Jena
* [Hamdi Hamed](https://fusion.cs.uni-jena.de/fusion/members/hamdi-Hamed/), Heinz-Nixdorf  Chair for Distributed Information Systems, University of Jena
* [Birgitta König-Ries](https://fusion.cs.uni-jena.de/fusion/members/birgitta-konig-ries/), Heinz-Nixdorf  Chair for Distributed Information Systems, University of Jena

<img style="margin-left: auto; margin-right: auto; width: 60%" src="assets/people.png">
<br/>

# Acknolwedgement

* This work has been funded by the Deutsche Forschungsgemeinschaft([CRC AquaDiva](http://www.aquadiva.uni-jena.de/), Project 218627073)
<!--
<img style="margin-left: auto; margin-right: auto; width: 60%" src="assets/logo.png">
-->
