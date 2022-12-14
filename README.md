# CTU-50-FEEL Dataset

Dataset used by the [FEEL project](https://github.com/stratosphereips/feel_project). 
It's a variant of the CTU-50-v1 dataset, which is not yet published.

This repository contains the pre-computed feature vectors, 
generated by [feature extraction](https://github.com/stratosphereips/feel_project/tree/main/preprocessing) 
of the project.

The dataset spans five days and is split into benign client data, which comes from the day-to-day traffic of real users,
and malicious data, which was generated from captured traffic of malware. 
The dataset does not include any identifiable information. The features were created from the raw Zeek captures 
by splitting them into one-hour widows and grouping all connections with the same 4-tuple.
This means every hour, a connection to one service will produce a single feature vector. 

The data is in the form of CSV, with the first 41 columns being numerical features. Each feature vector contains 
two columns with label information. 

Every vector is uniquely identifiable using these columns:
* id.orig_h - source IP address. The last octet of the address is obfuscated with a value consistent across the dataset.
* id.resp_h - target IP address
* id.resp_p - target port
* proto - used protocol
* day - the day of the capture (value from 1 to 5)
* hour - an hour of the day from which the feature vector was computed

This dataset is used in the thesis on Decentralized Federated Learning for
Network Security by Pavel Janata
