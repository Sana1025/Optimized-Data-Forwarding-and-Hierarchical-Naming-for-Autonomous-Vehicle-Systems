

# **Optimized Data Forwarding and Hierarchical Naming for Autonomous Vehicle Systems**

This project implements an optimized **Forwarder Selection Mechanism** for **Vehicular Ad-hoc Networks (VANETs)** integrated with **Named Data Networking (NDN)** and evaluated using machine learning.
It focuses on improving **safety event dissemination**, **bandwidth efficiency** and **forwarder reliability** in dense vehicular environments.

---

##  **Key Features**

* 5×5 zone grid + 2×2 subzones per zone (100 total blocks)
* Priority-based forwarder selection (SCAF Model)
* NDN hierarchical name generation
* VANET ↔ NDN Interest/Data exchange simulation
* ML-based forwarder prediction (Random Forest)
* Visualizations for:

  * Zone mapping
  * Forwarder distribution
  * Data dissemination
  * ML performance

---

##  **Forwarder Selection Logic (SCAF)**

Forwarders are scored using weighted metrics:

| Factor         | Weight |
| -------------- | ------ |
| Event Severity | 50%    |
| Vehicle Type   | 30%    |
| Speed          | 20%    |

Priority:
Emergency events → highest,  Bus > Car,Higher speed → stable forwarder

---

##  **NDN Naming Structure**

Each vehicle is mapped to a hierarchical NDN name:

```
/Zone<Main>/<Sub>/<VehicleType>/<Event>
```

Example:

```
/ZoneA/A1_3/car/EmergencyBrake
```

Supports:

* Event filtering
* Interest/Data exchange
* Role identification

---

##  **Data Dissemination Model**

Supports the following communication paths:

* Forwarder → Non-Forwarder
* Forwarder → Forwarder
* Non-Forwarder → Forwarder (Interest)
* Forwarder → NFWD (Data Response)

NDN caching prevents redundant broadcasts.

---

##  **Machine Learning Evaluation**

ML used to predict optimized forwarders from enriched features.

Models tested:

* Random Forest (Best)
* Decision Tree
* Logistic Regression
* SVM
* KNN

Best performance (Random Forest):

```
Accuracy > 95%
Precision > 94%
Recall > 93%
F1 Score > 94%
```

---

##  **Output Files (Pipeline)**

| File                            | Description               |
| ------------------------------- | ------------------------- |
| Zone block output.csv           | Vehicles + Zone labels    |
| Fowaders_OUTPUT.csv             | Initial forwarders        |
| optimized_forwarders.csv        | Filtered final forwarders |
| dataset_generation_NDN.csv      | Forwarders + NDN names    |
| NDN_Final_Sharing_Realistic.csv | Enriched data for ML      |

---

##  **Tech Stack**

* **Python**
* Pandas, NumPy
* Altair (Visualization)
* Scikit-Learn (ML)
* Seaborn + Matplotlib
* NDN concepts
* VANET safety communication logic

---

##  **Applications**

* Intelligent Transportation Systems
* VANET & Road Safety Networks
* NDN-based ITS architectures
* 6G Connected Mobility
* Smart City Communication Models

---

##  **Future Extensions**

* RSU integration
* Blockchain trust validation
* Real-time GPS streams
* Federated learning for vehicles
* Multi-event collision resolution
* MQTT/Kafka for traffic ingestion


