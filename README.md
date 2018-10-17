# Link Prediction on a MeSH Term Network

## Introduction:
PubMed is the largest index of biomedical literature boasting "more than 28 million citations". With 2-4 million papers being submitted every year this knowledge base grows substantially larger every year. The way this database is indexed is using an indexing language known as MeSH where every publication is indexed with a list of terms representing the subject of overarching subjects of the publications.

  ### Example:
  Electrophysiology of the frog gastric mucosa with sufficient CO2.
  Kidder GW 3rd.

  Is represented by: 

  MeSH terms

  Animals
  Carbon Dioxide*
  Electrophysiology*
  Gastric Juice/secretion
  Gastric Mucosa/physiology*
  Gastric Mucosa/secretion
  Hydrogen-Ion Concentration
  Hypoxia
  In Vitro Techniques
  Models, Biological
  Rana catesbeiana
  Secretory Rate
  Time Factors

## Motivation:
With so much literature at our disposal it's easy to get lost and feel overwhelmed when deciding what to focus research on. When even within specialized fields there are countless subfields.

Even then, once decided one has to wonder if all that focus and effort will lead to fruitful results, and whether or not within the vast wealth of knowledge that already exists there's hidden information that could help hold the key to a new discovery.

This is the goal of literature-based discovery which attempts to generate new hypothesis based on existing academic literature. Literature based discovery is the theory that if 2 previously unrelated entities are both related to the third entity then there is a higher likelihood that the 2 unrelated entities might have some unknown/undiscovered relationship. This is sound in theory but when it comes to verifying all the possible relationships the number of links this can include are in the millions if not billions.

So how do we verify if a link is viable research material? For that we can use supervised learning.

## Methods:
Using carefully chosen link prediction coefficients and word vector similarities from a network of intersections of MeSH terms:

Every node represents a MeSH term and every edge represents whether or not those MeSH terms have been used as indexes on the same paper. I created similarity vectors composed of these measurements to classify what links could lead to new discoveries while also doing it's best to identify 'unfruitful' research given that the possible 'unfruitful' research far outnumbers the possibilities of good research. 

###### Disclaimer: When I say unfruitful research I mean that which doesn't lead to new discovery, while testing hypothesis and failing to reject them is a normal part of the research process my aim isn't to undermine these attempts, it is to bolster confidence in their hypothesis prior to experimentation. 

Originally I was going to scrape the MEDLINE API to get data necessary for this project, but due to time constraints and the fact that running a full speed scraper on the whole of MEDLINE would take weeks to compile the information even at full speed, which consequently would probably get me banned, so I decided otherwise. Luckily the scraping work had already been done by a Kaggle user who uploaded multiple zip files containing the information I required.

### Bibliography

###### My project uses a very similar methodology to the one used in this first article but I conceived my idea prior to discovering this article and uses different metrics: 
1. Rindflesch, T., Hristovski, D., & Kastrin, A. (2016). Link Prediction on a Network of Co-occurring MeSH Terms: Towards Literature-based Discovery. Methods of Information in Medicine, 55(04), 340-346. doi:10.3414/me15-01-0108 



2. S., J., A. M., W., & J., B. (2015, August 10). Measuring Word Significance using Distributed Representations of Words. Retrieved from https://arxiv.org/abs/1508.02297

3. B., A., A., W., J., Y., & O. (1970, January 01). Translating Embeddings for Modeling Multi-relational Data. Retrieved from https://core.ac.uk/display/49700402



