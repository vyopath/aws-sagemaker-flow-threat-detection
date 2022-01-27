<img align="right" width="50"  src="./images/vyopath-logo.png">
<br />
<br />

# Flow Threat Detection

**Flow Threat Detection** is a Machine-Learning-based Network Intrusion Detection System (NIDS) meant to be used in NetFlow V5 traffic.

---

## Product Overview: 
This product is capable of detecting network attacks within a NetFlow network protocol using machine learning techniques. The ML multiclass trained model can detect 4 main network traffic categories: Benign, Brute Force, DoS & DDoS.

### Detection categories:
- **Benign:** If the inference output is *Benign* that means that the input NetFlow record does not belongs to any attack class, in other words, is normal traffic.
- **Brute Force:** If the inference output from an input Netflow record is *Brute Force*, that record belongs to possible Brute Force attack.
- **DoS:** If the inference output from an input Netflow record is *DoS*, that record belongs to a possible Denial of Service attack.
- **DDoS:** If the inference output from an input Netflow record is *DDoS*, that record belongs to a possible Distributed Denial of Service attack.

### Released versions

- **V1.0.0**
  - First release of the product.
- **V1.1.0**
  - New Machine learning model.
  - Now trained using with events captured from Honeypots.
  - Improved detection accuracy for Brute Force and SSH DoS events. Now is over 90%
- **V1.1.1**
  - All the features from the v1.1.0
  - Added a post-processing stage that uses a conversational approach to enhance the model performance up to 5%

---

### Model performance:

- V1.0.0
  -  Multiclass accuracy (multiclass detection): 84%
- V1.1.0
  - Multiclass accuracy: 95%
- V1.1.1
  - Multiclass accuracy: 97%

**Inference throughput:**
- V1.0.0
   - Instance type: ml.c5.large
   - File type and size: CSV, 25MB
   - Elapsed time: 10.4s
   - Processing rate: 25000 rows/sec
- V1.1.0
   - Instance type: ml.c5.large
   - File type and size: CSV, 25MB
   - Elapsed time: 14s
   - Processing rate: 20000rows/sec
- V1.1.1
   - Instance type: ml.c5.xlarge
   - File type and size: CSV, 6MB
   - Elapsed time: 53s
   - Processing rate: 1200 rows/sec
---

### Post-processing:

This feature is only available on version *V1.1.1*

The post-processing stage is located after the output of the Machine Learning model. Using new engineered features and statistical analysis this stage is capable of enhance the overall accuracy up to 5%.

*How it works?*

After data is ingested, a unique identifier is created for every event that belongs to the same conversation. A conversation is defined by the identifiers from the source and destination parts such as IP's, ports, etc.

The conversation ID will be used later after the model inference, where the predicted values within the same conversation are analyzed using statistical analysis, creating weighted parameters to redefine the raw predictions from the model.



*Note:* The post-processing stage requires extra time compared with the version without it. Depending on the size and structure of the input data this stage may increase the processing time up to 15X. Therefore we don't recommend using this feature for near real-time applications.

--- 

### Related links: 
- Vyopath website: https://www.vyopath.com/
- AWS Marketplace product link: 