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

## References


1. “UAS - Critical Infrastructure.” n.d. CISA. Accessed October 18, 2022. https://www.cisa.gov/unmanned-aircraft-systems.


2. “Unmanned Aircraft Systems (UAS).” n.d. Federal Aviation Administration. Accessed October 18, 2022. https://www.faa.gov/uas.


3. Bora Ly & Romny Ly (2021) Cybersecurity in unmanned aerial vehicles (UAVs), Journal of Cyber Security Technology, 5:2, 120-137, DOI: 10.1080/23742917.2020.1846307


4. “Cybersecurity Best Practices for Operating Commercial Unmanned Aircraft Systems (UASs).” n.d. CISA. Accessed October 18, 2022. https://www.cisa.gov/sites/default/files/publications/
CISA%20Cybersecurity%20Best%20Practices%20for%20
Operating%20Commerical%20UAS%20%28508%29.pdf


5. Majid, Mamoona, Shaista Habib, Abdul Rehman Javed, Muhammad Rizwan, Gautam Srivastava, Thippa Reddy Gadekallu and Chun-Wei Lin. “Applications of Wireless Sensor Networks and Internet of Things Frameworks in the Industry Revolution 4.0: A Systematic Literature Review.” Sensors (Basel, Switzerland) 22 (2022): n. pag.


6. S. -Y. Chou, Y. -S. Chen, J. -H. Chang, Y. -D. Chih and T. -Y. J. Chang, "11.3 A 10nm 32Kb low-voltage logic-compatible anti-fuse one-time-programmable memory with anti-tampering sensing scheme," 2017 IEEE International Solid-State Circuits Conference (ISSCC), 2017, pp. 200-201, doi: 10.1109/ISSCC.2017.7870330.


7. Alkatheiri, Mohammed Saeed, Sajid Saleem, Mohammed A. Alqarni, Ahmad O. Aseeri, Sajjad Hussain Chauhdary and Yu Zhuang. “A Lightweight Authentication Scheme for a Network of Unmanned Aerial Vehicles (UAVs) by Using Physical Unclonable Functions.” Electronics (2022): n. pag.


8. Tsao, Kai-Yun, Thomas Girdler and Vassilios G. Vassilakis. “A survey of cyber security threats and solutions for UAV communications and flying ad-hoc networks.” Ad Hoc Networks 133 (2022): 102894.


9. Alladi, Tejasvi, Vishnu Venkatesh, Vinay Chamola and Nitin Chaturvedi. “Drone-MAP: A Novel Authentication Scheme for Drone-Assisted 5G Networks.” IEEE INFOCOM 2021 - IEEE Conference on Computer Communications Workshops (INFOCOM WKSHPS) (2021): 1-6.


10. Shamsoshoara, Alireza, Ashwija Reddy Korenda, Fatemeh Afghah and Sherali Zeadally. “A survey on physical unclonable function (PUF)-based security solutions for Internet of Things.” Comput. Networks 183 (2020): 107593.


11. Laguduva, V.R., Katkoori, S. & Karam, R. Machine Learning Attacks and Countermeasures for PUF-Based IoT Edge Node Security. SN COMPUT. SCI. 1, 282 (2020). https://doi.org/10.1007/s42979-020-00303-y


12. Patil, Akash Suresh, Rafik Hamza, Hongyang Yan, Alzubair Hassan and Jin Li. “Blockchain-PUF-Based Secure Authentication Protocol for Internet of Things.” ICA3PP (2019).


13. Patil, Akash Suresh, Rafik Hamza, Alzubair Hassan, Nan Jiang, Hongyang Yan and Jin Li. “Efficient privacy-preserving authentication protocol using PUFs with blockchain smart contracts.” Comput. Secur. 97 (2020): 101958.


14. Wang, Weizheng, Qiu Chen, Zhimeng Yin, Gautam Srivastava, Thippa Reddy Gadekallu, Fawaz Jaber Alsolami and Chunhua Su. “Blockchain and PUF-Based Lightweight Authentication Protocol for Wireless Medical Sensor Networks.” IEEE Internet of Things Journal 9 (2022): 8883-8891.


15. E. Dubrova, O. Näslund, B. Degen, A. Gawell and Y. Yu, "CRC-PUF: A Machine Learning Attack Resistant Lightweight PUF Construction," 2019 IEEE European Symposium on Security and Privacy Workshops (EuroS&PW), 2019, pp. 264-271, doi: 10.1109/EuroSPW.2019.00036.


16. Pundir, Nitin, Noor Ahmad Hazari, Fathi H. Amsaad and Mohammed Y. Niamat. “A novel hybrid delay based physical unclonable function immune to machine learning attacks.” 2017 IEEE National Aerospace and Electronics Conference (NAECON) (2017): 84-87.


17. Pramudita, Resa, Surya Ramadhan, Farkhad Ihsan Hariadi and Adang Suwandi Ahmad. “Implementation Ring Oscillator Physical Unclonable Function (PUF) in FPGA.” 2018 International Symposium on Electronics and Smart Devices (ISESD) (2018): 1-5.


18. Cambou, Bertrand Francis, Christopher Philabaum, Duane Booher and Donald Telesca. “Response-Based Cryptographic Methods with Ternary Physical Unclonable Functions.” Lecture Notes in Networks and Systems (2019): n. pag.


19. Babaei, Armin and Gregor Schiele. “Physical Unclonable Functions in the Internet of Things: State of the Art and Open Challenges.” Sensors (Basel, Switzerland) 19 (2019): n. pag.


20. Ebrahimabadi, Mohammad Haghir, Mohamed F. Younis and Naghmeh Karimi. “A PUF-Based Modeling-Attack Resilient Authentication Protocol for IoT Devices.” IEEE Internet of Things Journal 9 (2022): 3684-3703.

