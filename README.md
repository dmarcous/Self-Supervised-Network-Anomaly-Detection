# Self Supervised Network Anomaly Detection

1st Place solution for the [Armis DataHack2019 Challenge](https://github.com/armis-security/DataHack2019).

# Team

*Haitzikim*

[Alon Palombo](https://github.com/alonpal)

[Amit Shor](https://github.com/Amit688)

[Daniel Marcous](https://github.com/dmarcous)

[Daniel Surename](https://nothingtosehere.com)


# Solution Overview

## Solution [presentation](https://docs.google.com/presentation/d/1oi1FL_iTyaUUEXBjPzvNZMyNWe66y7kiYRGFyaoUWGE/edit#slide=id.gcb9a0b074_1_0)

## Solution TL;DR 
1. Data Cleaning
2. Feature Engineering
   1. Hand crafted features by our domain (& meme) expert
      * Is this a device you can bring to work?
      * Is this PC a router? 
      * etc.
   2. Multi Level Aggregated Features
      * Device Level
      * Netowrk, Device Type, Day of week, Hour Level (creating an hour normalized session dataset)
   3. Network Graph Features
      * Degree (in / out / total)
      * Pagerank
3. Preprocessing
4. Ensembling
   1. Multiple algorithms
   	  * Isolation forests
   	  * GMM
   	  * Elliptic envelope
   2. Multiple datasets
      * Device level
      * Netowrk & type & dow & hour normalized dataset
5. Self Supervised Learning
   * Anomaly detection confidence as label
   * Random forest regression on label
   * Permutation importance feature selection (per network !)
   * SHAP values explainability
6. Memes. Lots of memes!

# Devices Gone Rogue Challenge
Ever wondered what would happen if you just plug in that seemingly innocent USB you found laying around? You’re about to find out! In this devices-gone-rogue challenge - should you choose to accept it - you will gain access to traffic data of ~100K devices, and will be tasked with finding the devices that, well, misbehave. 
This challenge is fully unsupervised - so put your anomaly belt on and get to it!

## Data
[Devices](https://armis-datahack.s3.amazonaws.com/all_devices.csv) <br>
[Sessions](https://armis-datahack.s3.amazonaws.com/all_sessions.csv )

## Evaluation
Model results will be matched against a prelabeled dataset, and AUC (Area Under the Curve) will be calculated on the test set.
Also Meme mastery :)

## Leaderboard
<a name="Submissions"></a>
Leader Board can be accessed here https://leaderboard.datahack.org.il/armis
