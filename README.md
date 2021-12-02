<img align="right" width="50"  src="./images/vyopath-logo.png">
<br />
<br />

# Flow Threat Detection

**Flow Threat Detection** is a Machine-Learning-based Network Intrusion Detection System (NIDS) meant to be used in NetFlow V5 traffic.

### Product Overview: 
This product is capable of detecting network attacks within a NetFlow network protocol using machine learning techniques. The ML multiclass trained model can detect 4 main network traffic categories: Benign, Brute Force, DoS & DDoS.

**Detection categories:**
- Benign: If the inference output is *Benign* that means that the input NetFlow record does not belongs to any attack class, in other words, is normal traffic.
- Brute Force: If the inference output from an input Netflow record is *Brute Force*, that record belongs to possible Brute Force attack.
- DoS: If the inference output from an input Netflow record is *DoS*, that record belongs to a possible Denial of Service attack.
- DDoS: If the inference output from an input Netflow record is *DDoS*, that record belongs to a possible Distributed Denial of Service attack.

**Model performance:**
   -  Overall accuracy (binary detection): 84%
   -  Overall recall (binary detection): 84%
   -  Multiclass accuracy (multiclass detection): 78%

Note: binary detection means for the ability of the model to detect a benign event vs all the attacks categories gather into only one ‘attack’ label.

**Inference throughput:**
Using the recommended instance type: ml.c5.large and a 25MB sample file
- Elapsed time: 10.4s
- Processing rate: 25960 rows/sec

Related links: 
- Vyopath website: https://www.vyopath.com/
- AWS Marketplace product link: 