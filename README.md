## Inspiration

India’s gig economy delivery partners working with platforms like Swiggy, Zomato, and Zepto depend heavily on daily earnings. However, external disruptions such as heavy rainfall, extreme heat, pollution spikes, and sudden curfews can reduce their working hours significantly, leading to a loss of 20–30% of their weekly income.

These challenges inspired us to build a solution focused on **income protection instead of traditional insurance**, creating a smart and automated safety net for gig workers.



## What it does

GigShield AI is an **AI-powered parametric insurance platform** that protects gig workers from income loss caused by external disruptions.

The system monitors real-time environmental conditions like weather and air quality. When predefined thresholds are crossed, it automatically detects disruptions, estimates income loss, and triggers **instant payouts**, eliminating the need for manual claims.



## System Architecture

User → Frontend (React) → Backend (Spring Boot) → AI Engine (Python) → External APIs (Weather, AQI) → Decision Engine → Payout System



## How we built it

We built GigShield AI using a modern full-stack architecture:

* **Frontend:** React (Dark SaaS Dashboard UI)
* **Backend:** Spring Boot (Java)
* **Database:** MySQL
* **AI/ML:** Python (Scikit-learn, Pandas)
* **APIs:** OpenWeatherMap API, AQI API
* **Payments:** Razorpay (Test Mode)

We integrated AI-based risk scoring with parametric triggers to automate claim processing.



###  System Workflow

![Workflow](./images/workflow.png)

This workflow shows how user data flows through the system—from input collection to AI-based risk analysis and automated payout processing.



###  System Architecture

![Architecture](./images/architecture.png)

The architecture represents the interaction between frontend, backend, AI engine, and external APIs, ensuring a scalable and real-time processing system.

###   System Auto Claim Flow

![Claim Flow](./images/claim-flow.png)


This diagram illustrates how the system automatically detects disruptions, verifies conditions, calculates income loss, and triggers instant payouts without manual claims.


## AI/ML Strategy

We use machine learning models to predict disruption risk:

* **Models:** Logistic Regression, Random Forest
* **Input Features:**

  * Rainfall data
  * AQI levels
  * Historical order patterns
* **Output:**

  * Risk Score (0–100%)

This enables **data-driven and automated claim decisions**.


##  API Strategy

- **Weather API Endpoint:**  
  Used to fetch rainfall data and weather forecast

- **Polling Frequency:**  
  Data is fetched every 15 minutes for real-time monitoring

- **Fallback Mechanism:**  
  In case of API failure, a mock data generator is used to ensure system continuity



## Data Sources & Threshold Logic

We use:

* OpenWeatherMap API → Rainfall data
* AQI API → Air Quality Index

### Thresholds:

* Rainfall > 30mm → High disruption
* AQI > 300 → Unsafe working conditions

These thresholds are based on environmental safety benchmarks and observed drops in delivery activity.

##  Disruption Triggers

| Disruption | Trigger Condition |
|-----------|------------------|
| Heavy Rain | Rainfall > 30mm |
| Extreme Heat | Temperature > 45°C |
| Severe Pollution | AQI > 300 |
| Zone Closure | Curfew or access restriction |


## Income Loss Calculation

$$
\text{Income Loss} = \text{Average Hourly Earnings} \times \text{Hours Lost}
$$

$$
\text{Average Hourly Earnings} = \frac{\text{Daily Earnings}}{\text{Working Hours}}
$$

---

## Example Scenario

* Location: Delhi
* Rainfall: 75mm
* AQI: 320
* Risk Score: 85%

### System Action:

* Threshold exceeded
* Claim automatically triggered
* Estimated Income Loss: ₹800
* Instant payout processed



## Adversarial Defense & Anti-Spoofing Strategy

To prevent fraud and misuse:

* **GPS Validation:** Ensures user is present in affected area
* **Platform Activity Check:** Verifies reduced order activity
* **Multi-API Verification:** Cross-checks environmental data
* **AI-based Anomaly Detection:** Detects unusual claim behavior
* **Time Validation:** Matches disruption with working hours

To ensure system integrity and prevent fraudulent claims, GigShield AI implements a multi-layer fraud detection system:

- **Speed Validation:**  
  If user speed > 80 km/h → flagged as suspicious

- **GPS Jump Detection:**  
  Sudden location change > 5 km within a short time → possible spoofing

- **Activity Validation:**  
  If user was inactive before disruption → claim rejected

- **Duplicate Claim Detection:**  
  Multiple claims from the same zone/event → flagged as suspicious

This ensures a **secure and fraud-resistant system**.



## Financial Viability

GigShield AI follows a sustainable weekly premium model.

### Example:

* Weekly Income: ₹6000
* Risk Probability: 20%
* Expected Loss: ₹1200

$$
\text{Premium} = \text{Expected Loss} + \text{Platform Fee}
$$

$$
= 1200 + 0.20% = ₹240
$$

This ensures:

* Sustainable revenue
* Risk coverage
* Scalability

## Subscription Plans & Coverage

| Plan | Weekly Premium | Coverage |
|------|---------------|---------|
| Basic | ₹20 | Up to ₹2000 income loss |
| Standard | ₹40 | Up to ₹4000 income loss |
| Pro | ₹60 | Up to ₹6000 income loss |

The following plans are designed to provide flexible and affordable coverage for gig workers.



## Coverage & Exclusions

### Covered:

* Heavy rainfall
* Extreme heat
* High AQI levels
* Government restrictions

### Excluded:

* Personal illness
* Voluntary absence
* Device/network issues
* War and pandemic events



## Regulatory Considerations

GigShield AI aligns with IRDAI guidelines for parametric insurance:

* Transparent payout triggers
* Predefined conditions
* No claim assessment delay


Future scope includes partnerships with licensed insurers.



## PROTOTYPE

<img width="237" height="519" alt="signup phone" src="https://github.com/user-attachments/assets/ada34183-8174-4e7a-944b-e46fcd693f77" />


<img width="392" height="520" alt="signup tab" src="https://github.com/user-attachments/assets/4c1ecef4-b295-4934-ad8b-1256434e03df" />


<img width="646" height="517" alt="signup web" src="https://github.com/user-attachments/assets/cee6bd13-6853-4fed-9156-eaa1fd43ff89" />

<img width="236" height="517" alt="dash phone" src="https://github.com/user-attachments/assets/2f636b29-3a88-4c55-8c1c-3716371a5d49" />


<img width="394" height="518" alt="dash tab" src="https://github.com/user-attachments/assets/bd1f4be5-edd5-4514-a28b-d47230919d80" />

<img width="645" height="521" alt="dash web" src="https://github.com/user-attachments/assets/a72ca2a1-6a70-40b8-86f3-55096488ae3d" />

<img width="241" height="518" alt="profile phone" src="https://github.com/user-attachments/assets/fb97ceeb-1453-4e0d-a28f-6326e425082f" />

<img width="248" height="522" alt="Settings" src="https://github.com/user-attachments/assets/75ed85a0-0236-4740-8783-ffeb131d45fd" />

<img width="238" height="520" alt="smart notification" src="https://github.com/user-attachments/assets/4414109c-5dac-47a2-843b-89cac39f26a0" />

<img width="245" height="524" alt="Subscription Plans" src="https://github.com/user-attachments/assets/da61d838-e06f-4b45-8673-f88627527001" />

<img width="241" height="520" alt="Payment Section" src="https://github.com/user-attachments/assets/ca77f449-d7c3-43f3-810d-4c4ef485e707" />

<img width="244" height="521" alt="Payment Success   Receipt" src="https://github.com/user-attachments/assets/a0942439-a6f3-451c-83c8-d03c39382613" />

<img width="244" height="524" alt="Risk   Claim History" src="https://github.com/user-attachments/assets/10686d56-e1da-4101-b0d7-fe7e3b5352d8" />

<img width="238" height="522" alt="Theme Preview" src="https://github.com/user-attachments/assets/5d54f2b3-2eff-4002-ab77-be10cdd57249" />


## Why GigShield AI Stands Out

* Fully automated claim system (zero manual effort)
* AI-driven risk prediction
* Faster than traditional insurance models
* Focused on gig workers (underserved segment)
* Real-time environmental data integration



## Challenges we ran into

* Designing a fair pricing model
* Simulating real-time data
* Building a zero-touch system
* Fraud prevention
* Balancing UI simplicity and functionality



## Accomplishments that we're proud of

* Built a parametric insurance prototype
* Implemented AI-based risk scoring
* Developed automated claim system
* Designed modern SaaS UI
* Created real-world impact solution



## What we learned

* Parametric insurance fundamentals
* AI in risk prediction
* Full-stack system design
* API integration
* User-centric design



## What's next for GigShield AI

* Hyperlocal AI risk prediction
* Integration with gig platforms
* GPS-based fraud detection
* Predictive disruption alerts
* Expansion across India



## Vision

GigShield AI aims to protect millions of gig workers by creating a real-time, AI-powered financial safety net.



## Built With

* React
* Spring Boot
* MySQL
* Python
* Scikit-learn
* Pandas
* OpenWeatherMap API
* AQI API
* Razorpay
