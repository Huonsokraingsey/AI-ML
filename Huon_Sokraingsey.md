# Week 1 Day 1 - Homework Assignment

## Mapping the ML Universe

---

## Part 1: Conceptual Exercises

Complete these three exercises before moving on to the coding section. They do not require any code — write your answers as comments or in a separate markdown/text file called `w1d1-concepts.md`.

---

### Exercise A: Classify Real-World ML Problems

For each scenario below, determine:
- Problem type (`classification`, `regression`, `clustering`, or `generative`)
- At least 2 likely input features
- What the model output would be

| Scenario | Problem Type | Input Features | Output |
|----------|-------------|----------------|--------|
| Predict whether a loan applicant will default | Classification | Loan Amount, Credit, Loan Purposes | Default or Non-Default |
| Forecast next month's energy consumption for a city | Regression | GDP, Population, Energy consumption per month, Weather | Numerical |
| Group customers by purchasing behavior | Clustering | Age, Gender, Salary, Budget | Target's purchase |
| Detect fraudulent credit card transactions | Classification | Avergage Spending, Money Transcation, Shop | Fraud or Normal |
| Generate product descriptions from an image | Generative | Image, Keyword, Language | Text Generation |
| Predict the severity (1–5) of a patient's condition | Classification | Age, Dieses's history, heartrate | Class 1-5 |

**How to think about it**:

- Start by asking: *"What does the model output?"* — is it a category, a number, a group, or new content?
- For input features, ask: *"What information would a human expert look at to make this decision?"*
- Watch out for tricky cases: an output that looks like a number (e.g., a severity score 1–5) might still be treated as classification — think about whether the *distance* between values matters.
- If no labeled examples exist in the scenario, clustering is likely the right framing.
- If the model is asked to *produce* something new rather than predict a pre-existing value, lean toward generative.

---

### Exercise B: Map the ML Lifecycle

**Scenario**: A hospital wants to predict which patients admitted to the ER are at high risk of readmission within 30 days.

For each lifecycle step, write 2–3 sentences describing what would happen in this specific scenario.

```
1. Problem Definition:   The objective is to develop a machine learning model capable of predicting which patients are at risk of returning to the emergency room within 30 days after being discharged, enabling doctors to proactively follow up on their symptoms.
2. Data Collection:      We will take data from electronic health records over the last 2–3 years. This data will include patient details like age and gender, how often they have visited the ER before, their main medical conditions, and lab results. We need a real-world dataset with 10,000 to 50,000 patients so that the model sees enough cases of patients coming back to the ER and learns to predict it well.
3. EDA & Preprocessing:  We need to make sure our data is balanced, has no missing values or odd entries, and we will use "one-hot encoding" for any category data if needed.
4. Model Training:       The model will give a simple yes/no answer (1 = high risk of coming back, 0 = low risk). We will start with easy-to-explain models like Logistic Regression or Random Forest so doctors can understand why a patient was flagged for example, "High risk because of age and diabetes." We will split the data into a training set and a validation set, making sure that the same patient's data doesn't appear in both, which could make the model unfair.
5. Evaluation:           Just looking at accuracy can be misleading because the data may be unbalanced. Instead, we will focus on Recall (catching as many true high-risk patients as possible) and the F1-Score. We will also use a Confusion Matrix to see how many healthy patients are wrongly labeled as "High Risk," since that wastes hospital resources.
6. Deployment:           The model will be added to the hospital's electronic health record system. When a patient is discharged, a "Risk Alert" will appear on their digital dashboard if needed.
7. Monitoring:          We need to watch for changes in data patterns for example, if the hospital changes how it records information or if flu season causes a short-term rise in patients returning. If the model's accuracy drops over several months, it means the model has become outdated and needs to be retrained using the most recent 6 months of patient data.
```

**How to think about each step**:

- **Problem Definition**: Pin down *what exactly* is being predicted, who will act on the prediction, and what "good enough" looks like in business terms.
- **Data Collection**: What records does the hospital already store? How far back should you go? What's a realistic minimum dataset size?
- **EDA & Preprocessing**: What could be messy or missing in medical records? Are there obvious class imbalances? How do you turn diagnosis codes into model-friendly features?
- **Model Training**: Should you start simple or complex? Why might interpretability matter here more than in other industries?
- **Evaluation**: Why might raw accuracy be misleading? What metric would better capture real usefulness?
- **Deployment**: Who sees the output? What context would a nurse or case manager need alongside a risk score?
- **Monitoring**: What real-world changes could make the model go stale? How would you detect this before users notice?

---

### Exercise C: AI vs ML vs Deep Learning Sorting

Label each system as **Rule-based AI**, **Classical ML**, or **Deep Learning**. Write one sentence justifying your choice.

1. A chess engine that evaluates positions using a hand-crafted evaluation function
Rule-based AI – It relies on a hand-crafted evaluation function written by humans rather than learning patterns from data.
2. A spam filter trained on 10 million labeled emails using random forest
Classical ML – Random forest is a traditional machine learning algorithm that learns patterns from labeled email data without using deep neural networks.
3. GPT-4 generating text responses
Deep Learning – GPT-4 uses a deep neural network with many layers (transformer architecture) to generate human-like text.
4. Netflix's collaborative filtering recommendation engine
Classical ML – Collaborative filtering is a classical machine learning technique that learns patterns from user-item interaction data without deep architectures.
5. A thermostat that adjusts temperature based on time-of-day rules
Rule-based AI – It operates solely on predefined time-based rules programmed by humans, with no learning from data.
6. A CNN that detects tumors in medical images
Deep Learning – CNNs (Convolutional Neural Networks) are deep learning models that automatically learn hierarchical features from image data.
7. A decision tree that approves/rejects credit card applications based on features
Classical ML – A decision tree is a traditional machine learning model that learns simple if-then rules from structured features.

**How to think about it**:

- Ask: *"Does this system learn from data, or does a human write all the rules?"* — if a human encodes the logic explicitly, it's rule-based AI.
- Ask: *"Is this working with raw unstructured data (images, text, audio) at scale?"* — if yes, Deep Learning is likely involved.
- A decision tree *algorithm* trained on data is Classical ML even though the output looks like a set of rules.
- For ambiguous cases (e.g., collaborative filtering): think about whether the underlying method is a neural network or a mathematical decomposition.

---

## 📤 Submission

1. Save your answers in a file named `w1d1-concepts.md`
2. Add it to your repository at `modules/1-foundations/codes/w1d1/w1d1-concepts.md`
3. Submit the GitHub link via the class submission form

---
