## Infotact_Project_01
#### Design and develop an intelligent task management system that leverages NLP and ML techniques to automatically classify, prioritize, and assign tasks to users based on their behavior, deadlines, and workloads.

### Week 1: Data Collection & Preprocessing
<br>

### **--Objective--**
<br>
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
<br>

### 1. Data Loading
<br>
:) Shape of dataset → (20122, 8)
<br>


### 2. Data Cleaning & Renaming
<br>
:) Removed duplicates.
<br>
:) Dropped rows with missing values in Task Description and Skill.
<br>


###  3. Dataset Exploration
<br>
:) Total unique task descriptions: 265
<br>
:) Total unique categories: 13
<br>
:) Total unique skills: 232
<br>


### 4. Skill Assignment to Users
<br>
:) A dictionary was created mapping 40 users to 3–4 random skills each
<br>


###  5. Deadline, Workload & Priority Assignment
<br>
:) **Deadline:** Random date within 60 days from today.
<br>
:) **Workload:** Random integer from 1 to 10.
<br>
:) **Priority Logic:** if days_left <= 7 or workload >= 8 → High  
elif days_left <= 20 → Medium  
else → Low
<br>


### 6. Task Assignment Based on Skills
<br>
:) Each task was assigned to a user who has the required skill. If no perfect match, a random user was assigned.
<br>


### 7. Text Preprocessing using NLP
<br>
:) Preprocessing on Task Description involved:
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
<br>
:) Cleaned Dataset Saved As: cleaned_dataset.csv
<br>
:) Download Triggered via: files.download('cleaned_dataset.csv')
<br>

