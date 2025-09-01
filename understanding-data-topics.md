# Understanding Data Topics  

## Understanding Data Science  

### Data Science  

#### Key Processes  
- **Collecting data**  
- **Analyzing data**  
- **Transforming data into insights**  

---

### What is Data Science?  
Data Science is a field that makes sense of the vast amount of information we generate.  

- Uses data to understand needs, preferences, and behaviors.  
- Involves taking raw data, cleaning it, and extracting patterns to generate insights.  

---

### Applications of Data Science  
- Personalized recommendations (e.g., shopping platforms, streaming services).  

---

### Roles in Data Science and Their Tools  

**Data Engineers**  
- Build custom pipelines and storage systems to ensure data is accessible and reliable.  

**Data Analysts**  
- Interpret and visualize data, turning it into stories that anyone can understand.  

**Data Scientists**  
- Apply statistics and machine learning techniques to uncover patterns and trends.  

**Machine Learning Scientists**  
- Focus on building advanced models.  
- Use sophisticated algorithms.  
- Push beyond traditional approaches in predictive modeling.  

**AI Engineers**  
- Specialize in integrating AI models into real-world applications such as autonomous vehicles, smart homes, and intelligent assistants.  

---

### 📖 Chapter 1 (Summary)  
This chapter introduces the world of Data Science, its uses, and its real-world applications.  

In essence, Data Science powers many of the applications and platforms we use daily. For example, in an e-commerce app like **Shopee**, the recommendations you see are not random—they are generated through Data Science techniques.  

Data Science involves collecting, analyzing, and using data to make predictions with algorithms and machine learning models.  

This chapter also explains the distinctions among the various roles in the data field:  
- **Data Engineers** create pipelines and systems to make data accessible.  
- **Data Analysts** transform data into understandable stories.  
- **Data Scientists** generate predictions and insights that benefit organizations.  
- **Machine Learning Scientists** design and improve machine learning models.  
- **AI Engineers** apply these models to real-world scenarios, such as self-driving cars and smart technologies.  

---

## Data Sources & Data Science Workflow

### Sources of Data

#### Company Data
- Collected by companies for business purposes  
- Supports data-driven decisions  
- Examples: **Web events, survey data, customer data**

#### Open Data
- **Data APIs** – request data from 3rd parties over the internet  
- **Public Records** – shared by organizations  
- **Statistical Offices & Government Agencies** – publish data on weather, environment, and population  

---

### Data Types

- **Quantitative Data** – numerical, measurable  
- **Qualitative Data** – descriptive, not measured with numbers  

#### Other Data Types
- **Image Data**  
- **Text Data**  
- **Geospatial Data** – with location info  
- **Network Data** – shows relationships (e.g., social connections)  

---

### Data Storage and Retrieval

#### Workflow Steps
1. **Data Collection and Storage**  
2. **Data Processing and Transformation**  
3. **Data Analysis and Visualization**  

#### Considerations
- **Location** – where to store (local/cloud)  
- **Data Type** – structured vs. unstructured  
- **Retrieval** – efficiency in accessing data  

#### Types of Data Storage
- **Document Database** – stores unstructured data (emails, video, web pages); uses **NoSQL**  
- **Relational Database** – stores structured tables; uses **SQL**  

---

### Data Pipelines
- Automates data movement and storage  
- Can be **scheduled** or **event-triggered**  
- Monitored with alerts  
- Critical for **big data**  
- Maintained by **Data Engineers**  

---

### ETL Process
1. **Extract** – collect data from sources (APIs, IoT, databases)  
2. **Transform** – clean, organize, and prepare data  
   - Join datasets  
   - Restructure  
   - Remove irrelevant info  
3. **Load** – save data into storage for analysis/visualization  

---

### 📖 Chapter 2 (Summary) 
- Data comes from **company sources** (surveys, customer data) and **open data** (APIs, government records).  
- Two main data types: **Quantitative (numbers)** and **Qualitative (descriptions)**, plus other forms like **text, image, geospatial, and network data**.  
- Data must be stored and retrieved efficiently, considering **location, type, and retrieval method**.  
- Storage systems include **relational databases (SQL)** and **document databases (NoSQL)**.  
- **Data pipelines** automate movement and processing to handle large-scale or continuous data.  
- **ETL (Extract, Transform, Load)** ensures data is collected, cleaned, and prepared for analysis.  

---

## Data Science Workflow

### The Three-Phase Workflow

The data science workflow consists of three critical phases that transform raw, messy data into actionable insights:

1. **Data Preparation**  
2. **Exploratory Data Analysis (EDA)**  
3. **Data Visualization/Dashboards**  

---

### Phase 1: Data Preparation

> "You would not use vegetables without cleaning, peeling and dicing them, as your soup would taste weird and no one would eat it. Well, if you don't clean, peel and dice your data, your results will look weird, and no one will use them!"

#### Why Data Preparation is Essential
- Real-world data is messy and dirty  
- Skipping cleaning leads to errors, incorrect results, and algorithm failures  
- **Mandatory step** before any analysis  

#### The 6 Essential Data Cleaning Steps

1. **Tidy Data Structure**
   - **Goal:** Matrix format with observations in rows, variables in columns  
   - **Problem:** Features in rows, observations in columns  
   - **Solution:** Transpose/restructure using Python/R functions  

2. **Remove Duplicates**
   - Identify exact matches across all columns  
   - Remove duplicates, retain only unique observations  
   - Tools: Python and R  

3. **Unique Identification**
   - **Problem:** Multiple people with same name  
   - **Solutions:**  
     - Combine features (e.g., Name + Last Name + Birth Year)  
     - Assign **unique IDs** (recommended, sequential IDs)  

4. **Homogeneity (Standardization)**
   - **Units of Measurement:**  
     - Identify outliers programmatically  
     - Convert units (e.g., feet → meters by dividing by 3.281)  
   - **Text Formatting:**  
     - Ensure consistency (e.g., "United States" vs "US")  

5. **Data Types**
   - **Issue:** Tools misclassify data (e.g., Age as text instead of numeric)  
   - **Solution:** Manually verify + convert  
   - **Test:** Ensure mathematical operations work correctly  

6. **Missing Values**
   - **Causes:** Data entry errors, survey issues, intentional gaps, system issues  
   - **Handling Strategies:**  
     - Substitute exact values (best)  
     - Aggregate substitution (mean/median/min/max)  
     - Drop observations (less data but clean)  
     - Keep as-is (if algorithm handles missing values)  

---

### Phase 2: Exploratory Data Analysis (EDA)

> Introduced by statistician John Tukey — exploring data, forming hypotheses, with heavy emphasis on visualization.

#### Role in the Workflow
- **Occurs after** data preparation  
- Can **reveal new cleaning needs**  
- **Iterative process** → may return to cleaning  

#### The Power of Visualization: Anscombe's Quartet
- Four datasets with identical statistics but different visual stories:  
  1. Clear linear relationship  
  2. Non-linear relationship (linear regression inappropriate)  
  3. Linear with one extreme outlier  
  4. No correlation except one misleading extreme point  

👉 **Key Lesson:** Visualization reveals truth; statistics alone can mislead.  

#### The 6-Step EDA Process
1. **Know Your Data Features** → Understand meaning, verify types, dataset structure  
2. **Preview Your Data** → Inspect values, spot quality issues, scan for anomalies  
3. **Calculate Descriptive Statistics** → Counts, missing values, means, distributions  
4. **Visualize for Insights** → Patterns, relationships, distributions → generate hypotheses  
5. **Ask More Questions** → Explore findings (e.g., mission outcomes, locations, time trends)  
6. **Identify Outliers** → Check for unusual values, errors, or valid extremes  

#### EDA Best Practices
- **Visualization first** before conclusions  
- **Question everything**  
- **Iterative process** → revisit earlier steps  
- **Context matters** → domain knowledge helps interpretation  
- **Don't ignore outliers** → critical for analysis  

---

### Phase 3: Data Visualization & Interactive Dashboards

> "One picture is worth a thousand words" — but attention to detail is crucial.  

#### Visualization Best Practices

1. **Use Color Purposefully**  
   - Colors should have meaning → one variable = one color  

2. **Consider Colorblindness**  
   - Red-green colorblindness common  
   - Use colorblind-friendly palettes, accessibility tools, or patterns  

3. **Choose Readable Fonts**  
   - Sans-serif, consistent, readable over decorative  

4. **Label Everything**  
   - Titles, axis labels, legends → clarity first  

5. **Handle Axes Carefully**  
   - **Zero Baseline Rule:** Start at zero when possible  
   - Warning: Non-zero axes may mislead (e.g., Obamacare enrollment graphs)  

#### Interactive Dashboards

> "If a picture is worth a thousand words, then what is worth a thousand pictures? A dashboard!"

**Benefits**
- **Centralized information** in one place  
- **Holistic view** from multiple visualizations  
- **Contextual understanding** from combined insights  

**Car Dashboard Analogy**  
- Individual metrics (speed, RPM, gas) matter — but together, they give full context  

**Features**
- **Hover Effects:** Tooltips add info without clutter  
- **Filtering Capabilities:** User-driven exploration (time, category, region)  

#### Implementation Tools

- **Business Intelligence (BI) Tools:** Tableau, Looker, Power BI (no programming, fast setup)  
- **Programming Alternatives:**  
  - Python → Plotly, Streamlit  
  - R → Shiny  
  - JavaScript → D3.js  

---

### Complete Workflow Integration

#### Sequential Process
1. **Data Preparation** → Clean, structure, prepare  
2. **EDA** → Explore, visualize, understand  
3. **Visualization/Dashboards** → Present insights interactively  

#### Iterative Nature
- EDA reveals new cleaning needs  
- Visualization requires further analysis  
- Continuous refinement → better insights  

#### Key Success Factors
- **Quality Foundation:** Strong data preparation  
- **Visual Exploration:** Heavy reliance on visualization  
- **User-Centered Design:** Clarity & accessibility first  
- **Interactivity:** Users explore + customize  

---

### 📖 Chapter 3 (Summary)
The data science workflow is a step-by-step process that transforms messy raw data into meaningful insights. It consists of three main phases: **Data Preparation**, **Exploratory Data Analysis (EDA)**, and **Data Visualization/Dashboards**.

**Data Preparation** is essential for ensuring accuracy since real-world data is often messy. Six key steps: restructure data into tidy format, remove duplicates, assign unique identifiers, standardize units and text formats, verify data types, and handle missing values.

**Exploratory Data Analysis (EDA)** was introduced by statistician John Tukey, emphasizing visual exploration to form hypotheses. Visualization reveals insights that statistics alone may hide (*Anscombe's Quartet*). The six-step process includes understanding features, previewing data, calculating statistics, visualizing patterns, asking deeper questions, and identifying outliers.

**Data Visualization & Dashboards** communicate insights clearly through strong visualizations and interactive dashboards that combine multiple visualizations for context. Best practices include using colors purposefully, choosing clear fonts, labeling all elements, and starting axes at zero when possible.

The **overall workflow** is sequential but iterative: Preparation → EDA → Visualization. Each phase may lead back to earlier steps for refinement. Success depends on clean data, insightful exploration, clear visuals, and user-focused design.
