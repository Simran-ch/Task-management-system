## Infotact_Project_01
#### Design and develop an intelligent task management system that leverages NLP and ML techniques to automatically classify, prioritize, and assign tasks to users based on their behavior, deadlines, and workloads.

### Week 1: Data Collection & Preprocessing
### **--Objective--**
The goal for Week 1 was to load the raw task dataset, clean it, enrich it with synthetic values (like deadlines and workloads), and prepare it for downstream machine learning tasks. This included:
<br>

:) Loading the dataset from Google Drive.
<br>

:) Removing duplicates and handling missing values.
<br>

:) Assigning synthetic deadlines and workloads.
<br>

:) Generating task priorities based on deadlines and workloads.
<br>

:) Automatically assigning users based on skill matching.
<br>

:) Preprocessing task descriptions using NLP techniques.
<br>

:) Saving the final cleaned dataset for future use.
<br>

### **--Key Steps--**
### 1. Data Loading
df = pd.read_csv('/content/drive/My Drive/Infotact Internship/Project 1/Task Assignment.csv')
<br>

:) Shape of dataset → (20122, 8)
<br>

### 2. Data Cleaning & Renaming
:) Removed duplicates.
<br>
:) Dropped rows with missing values in Task Description and Skill.
<br>

###  3. Dataset Exploration
:) Total unique task descriptions: 265
<br>
:) Total unique categories: 13
<br>
:) Total unique skills: 232
<br>

### 4. Skill Assignment to Users
:) A dictionary was created mapping 40 users to 3–4 random skills each
<br>

###  5. Deadline, Workload & Priority Assignment
:) **Deadline:** Random date within 60 days from today.
<br>

:) **Workload:** Random integer from 1 to 10.
<br>

:) **Priority Logic:**      
if days_left <= 7 or workload >= 8 → High  
elif days_left <= 20 → Medium  
else → Low
<br>

### 6. Task Assignment Based on Skills
:) Each task was assigned to a user who has the required skill. If no perfect match, a random user was assigned.
<br>

### 7. Text Preprocessing using NLP
Preprocessing on Task Description involved:
<br>
:) Lowercasing
<br>
:) Tokenizing
<br>
:) Removing stopwords & punctuation
<br>
:) Stemming
<br>

### Final Output
:) Cleaned Dataset Saved As: cleaned_dataset.csv
<br>
:) Download Triggered via: files.download('cleaned_dataset.csv')
<br>

### Week 2: Task Classification using NLP and ML
### **--Objective--**
To classify tasks into relevant categories using the task descriptions. Applied NLP preprocessing and trained two machine learning models – Naive Bayes and Support Vector Machine (SVM) – for multi-class classification.
<br>

### **--Key Steps--**
### Model Used :
:) Multinomial Naive Bayes
<br>
:) Linear Support Vector Classifier (SVM)
<br>

###  Dataset:
Used the cleaned dataset generated in Week 1 which includes:
<br>
:) Processed_Description (preprocessed task text)
<br>
:) Category (target class)
<br>
:) Skill, Deadline, Priority, User Skills, and Assigned User columns
<br>

###  Results & Evaluation
**Naive Bayes:**
<br>
:) **Accuracy:** 94.30%
<br>
:) **Precision:** 94.20%
<br>
:) **Recall:** 94.30%
<br>

**Notable high scores in:**
<br>
:) Frontend, Documentation, Testing, Project Management – All achieved 95–100% accuracy
<br>
:) Slight drop in performance for rare categories like ui/ux design due to low support
<br>

**SVM:**
<br>
:) **Accuracy:** 95.57%
<br>
:) **Precision:** 95.90%
<br>
:) **Recall:** 95.57%
<br>

**Improved overall performance compared to Naive Bayes**
<br>
:) Consistently high performance across most classes
<br>
:) Handles imbalanced data better
<br>
:) Perfect scores in multiple categories including DevOps, Documentation, Project Management
<br>

##### Conclusion:
Both models performed exceptionally well, but SVM slightly outperformed Naive Bayes in terms of accuracy and precision. It is more suitable for production-level task classification due to its better handling of class imbalance.
