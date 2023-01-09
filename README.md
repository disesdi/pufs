# Evaluating Robustness of Physical Unclonable Functions (PUFs) For Unmanned Aerial System Authentication With Random Forests & Gradient Boosting

This project explores machine learning attacks on Physical Unclonable Functions (PUFs), which have been proposed as an authentication method for resource-constrained and security-vulnerable applications such as Unmanned Aircraft Systems (UAS), and Internet of Things (IOT) devices.

code for this project is [available here](https://github.com/disesdi/pufs/blob/f9eb23984ba8e442f2734e86c05553f7fda5fea7/pufs_1.ipynb)

find the [full writeup & results here](https://anglesofattack.io/1/pufs.html)

## Background

###  UAS Prevalence & Security Vectors

Unmanned Aircraft Systems are becoming an increasingly mainstream–and vital–part of modern life. The US Cybersecurity & Infrastructure Security Agency (CISA) names UAS/drones as "[critical infrastructure](https://www.cisa.gov/unmanned-aircraft-systems)", citing use cases as diverse as firefighting, to the delivery of critical medical supplies.<sup>[1]</sup>

Drone use has skyrocketed, particularly among the general public. According to [the FAA  as of 2022](https://www.faa.gov/uas), of the over 867,000 drones currently registered, more than half a million (535,461) are registered as recreational.<sup>[2]</sup>

With widespread use, security concerns around malicious drone activity have risen to the fore.

According to CISA,<sup>[1]</sup> malicious UAS activity may include:

* *Weaponized or Smuggling Payloads – Depending on power and payload size, UAS may be capable of transporting contraband, chemical, or other explosive/weaponized payloads.*


* *Prohibited Surveillance and Reconnaissance – UAS are capable of silently monitoring a large area from the sky for nefarious purposes.*


* *Intellectual Property Theft – UAS can be used to perform cyber crimes involving theft of trade secrets, technologies, or sensitive information.*


* *Intentional Disruption or Harassment – UAS may be used to disrupt or invade the privacy of other individuals.*<sup>[1]</sup>

Given the potential for serious misuse of the technology, securely identifying and authenticating UAS is a critical challenge. However, UAS-specific security constraints, as well as the proliferation of industry-wide security challenges already existent in the underlying technologies, are complicating factors that must be weighed in any solution.

In addition to their potential for malicious misuse, UAS have a number of well documented cyber attack vectors, with various proposals for mitigation in the literature.<sup>[3]</sup>  Cybersecurity risks are prevalent in UAS to such an extent that CISA also published a [Cybersecurity Best Practices For Operating Commercial UAS](https://www.cisa.gov/sites/default/files/publications/CISA%20Cybersecurity%20Best%20Practices%20for%20Operating%20Commerical%20UAS%20%28508%29.pdf), with a number of recommendations for operators.<sup>[4]</sup>


### Resource Constraints & Security Needs

As both their use and susceptibility to attacks increase, IOT and UAS devices share a need for system-wide security improvements to reduce the attack surface. 

UAS and IOT devices also share a common characteristic of being resource-constrained;<sup>[5]</sup> that is, these devices often have physical size and, in aerospace applications in particular, weight considerations. 

These considerations co-exist and interact with the need for optimizing computational performance on what are often already small devices. 

Due to the combination of security needs and resource constraints, authentication of these systems is of particular interest.

Specifically, their constraints, combined with the ways in which these systems operate in the wild, make familiar methods of authentication increasingly less practical for application within UAS & IOT machines.

## Models

this project uses `GaussianNB`, `svm`, and `RandomForestClassifier` models from the `sklearn` library, as well as `XGBClassifier` from `xgboost`.

Results are summarized in the table below.

## Results Summarized

|          Model         | Parameter Optimization   | Score  |
|:----------------------:|--------------------------|--------|
| Gaussian Naive Bayes   | None                     | 53.90% |
| Support Vector Machine | None                     | 56.03% |
| XGBoost                | None                     | 56.00% |
| Random Forests         | None                     | 56.67% |
| Random Forests 2       | Number of Estimators: 99 | 57.07% |
| XGBoost 2              | Max Tree Depth: 11       | 57.40% |


These results are in line with current academic literature,<sup>[20]</sup> and were acheived using a Jupyter Notebook kernel running inside a Linux virtual machine hosted on a Chromebook laptop. Increasingly large datasets and computationally intensive methods have increasingly accurate results. 

*Code available [here >>](https://github.com/disesdi/pufs/blob/main/pufs_1.ipynb)*
