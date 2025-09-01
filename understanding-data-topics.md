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

---

## Experimentation and Prediction

### A/B Testing and Experimentation

#### What are Experiments in Data Science?

**Purpose:**
- Drive decisions and draw conclusions
- Test hypotheses with data-driven approach
- Provide statistical evidence for business decisions

**Experimental Process:**
1. Start with a question and hypothesis
2. Collect data systematically
3. Perform statistical test on collected data
4. Interpret results and make decisions

#### A/B Testing Definition

**Core Concept:**
- Also called Champion/Challenger testing
- Purpose: Make a choice between two options
- Method: Compare performance of two variants (A and B)
- Split testing: Divide audience into two groups for controlled comparison

#### Four Essential Steps of A/B Testing

**Step 1: Pick a Metric to Track**
- Example: Click-Through Rate
- Definition: Percent of people who click on a link after viewing
- Formula: (Number of clicks / Number of views) × 100
- Must be relevant, measurable, and actionable

**Step 2: Calculate Sample Size**
- Ensure results aren't due to random chance
- Provide statistical validity without being unnecessarily large
- **Baseline Metric Dependency:** 50% rate needs smallest sample size; rates much higher/lower need larger samples
- **Sensitivity:** How small a change you can detect
- **Trade-off:** Larger samples detect smaller changes but require more resources

**Step 3: Run Your Experiment**
- Continue until calculated sample size is reached
- Don't stop early or run too long
- Maintain consistent experimental conditions
- Avoid peeking at results before completion

**Step 4: Check for Significance**
- Some difference between variants will always exist
- Determine if difference is meaningful or due to chance
- Perform statistical significance testing
- Use results to make informed decisions

#### Handling Non-Significant Results
- Differences exist but are smaller than chosen threshold
- Below detection sensitivity
- Not actionable for business decisions
- Running longer won't help - focus resources on more impactful experiments

#### A/B Testing Best Practices

**Planning Phase:**
- Clear question formulation
- Hypothesis establishment
- Appropriate metric selection
- Pre-calculate sample size

**Execution Phase:**
- Random assignment for unbiased groups
- Consistent experimental conditions
- Complete duration adherence
- Monitor data integrity

**Analysis Phase:**
- Apply appropriate statistical tests
- Consider both statistical and practical significance
- Base decisions on statistical evidence
- Document insights for future experiments

---

### Time Series Forecasting

#### Introduction to Time Series Data

**Definition:**
- Series of data points sequenced by time
- Each data point has a specific timestamp
- Time dependency is crucial

**Common Examples:**
- **Financial:** Stock prices, gas prices
- **Economic:** Unemployment rates, GDP
- **Environmental:** CO2 levels, tide heights
- **Medical:** Heart rate monitoring

#### Key Components of Time Series

**Pattern Elements:**
1. **Trend:** Long-term increase or decrease
2. **Seasonality:** Regular, predictable patterns (monthly, yearly cycles)
3. **Noise:** Random variations
4. **Cyclical:** Longer-term patterns different from seasonality

#### Seasonality Examples

**Temperature Patterns:**
- Annual cycles with summer peaks and winter troughs
- Predictable and repeatable

**Business Seasonality:**
- **Ice cream sales:** Peak in summer, low in winter
- **Paycheck spending:** Spikes at month-end when people receive paychecks

#### Forecasting Process

**Definition:**
- Using historical time series data to predict future values
- Combines statistical and machine learning methods

**Applications:**
- **Short-term:** Weather, traffic, stock market conditions
- **Long-term:** Population projections, economic trends, strategic planning

#### Case Study: Pea Prices in Rwanda (2011-2016)

**Data Source:** UN open data on global food prices

**Pattern Analysis:**
- **Seasonal patterns:** Clear yearly repetition
- **Price cycles:** Low around December/January, peak around August
- **Long-term trend:** General upward price trajectory

**Forecasting Results:**
- Model preserves seasonal patterns
- Anticipates continued price increases
- Includes confidence intervals (80% and 95%)

**Confidence Intervals:**
- **80% confidence:** Model is 80% sure true value falls within narrower band
- **95% confidence:** Model is 95% sure true value falls within wider band
- **Business value:** Help assess risk and plan for uncertainty

---

### Supervised Machine Learning

#### Introduction and Position

**Context:**
- Final step in data science workflow
- Methods for making predictions based on existing data
- Built upon prepared, explored, and cleaned data

#### What is Supervised Machine Learning?

**Definition:**
- Specific subset of machine learning
- Requires data with both labels and features
- Algorithm learns from labeled examples

**Key Applications:**
- Recommendation systems
- Medical diagnosis
- Pattern recognition
- Customer behavior prediction

#### Case Study: Customer Churn Prediction

**Business Problem:**
- Predict whether customers will stay subscribed or cancel
- Enable proactive customer retention strategies

**Data Requirements:**
- **Historical data:** Past customer records with known outcomes
- **Features:** Customer information that might affect churn (age, last purchase, income, usage patterns)
- **Labels:** Known outcomes (churned or stayed)

**Process:**
1. **Training phase:** Algorithm learns relationships between features and outcomes
2. **Prediction phase:** Model predicts churn probability for new customers
3. **Business action:** Targeted retention efforts for high-risk customers

#### Model Evaluation

**Test Set Methodology:**
- Reserve portion of data for testing (don't use in training)
- Evaluate model performance on unseen data
- Provides unbiased assessment

**Evaluation Example:**
- Test set: 1000 customers (30 actually churned, 970 stayed)
- Model prediction: All customers will stay
- Overall accuracy: 97% (misleading!)
- Churn prediction accuracy: 0% (missed all 30 churners)

**Key Insight:** Overall accuracy can be misleading, especially with imbalanced data. Must examine class-specific performance.

#### Supervised Learning Framework

**Core Components:**
1. **Labels:** What we want to predict
2. **Features:** Data that might help predict the label
3. **Model Training:** Algorithm finds patterns in historical data
4. **Prediction:** Apply trained model to new, unlabeled data

---

### Unsupervised Machine Learning (Clustering)

#### Introduction to Clustering

**Definition:**
- Set of algorithms that divide data into categories (clusters)
- Part of unsupervised machine learning
- Helps identify patterns in unlabeled datasets

**Applications:**
- Customer segmentation
- Image categorization
- Anomaly detection
- Pattern discovery

#### Supervised vs. Unsupervised Learning

**Key Differences:**

| Aspect | Supervised | Unsupervised |
|--------|------------|--------------|
| Data Structure | Features + Labels | Features only |
| Known Outcomes | Yes | No |
| Purpose | Predict known categories | Discover hidden patterns |
| Examples | Churn prediction | Customer segmentation |

#### Case Study: Discovering New Flower Species

**Scientific Context:**
- Botanist exploring unexplored island
- Over 100 unknown flowers measured
- Unknown number of species
- Need to categorize discoveries

**Problem Characteristics:**
- Features available: Flower measurements (petal width, sepal length, number of petals)
- Labels unavailable: Unknown species classifications
- Perfect unsupervised learning scenario

#### Clustering Process

**Step 1: Define Features**
- Collect comprehensive measurements
- Use physical characteristics as model features
- Ensure systematic and quality data collection

**Step 2: Define Number of Clusters**
- Some algorithms require specifying cluster count
- Critical decision affecting data segmentation
- Use data visualization to inform choice

**Step 3: Compare Different Cluster Numbers**
- **Two clusters:** Suggests two new species
- **Three clusters:** Evidence for three species
- **Four clusters:** More granular division
- **Eight clusters:** Appears excessive for the data

**Visual Assessment:** 3D plot helps determine appropriate cluster count

**Step 4: Integrate Domain Knowledge**
- Botanical expertise enhances algorithm performance
- Example: Petal width has high natural variance within species
- Adjust feature weighting based on expert knowledge

#### Clustering Applications

**Scientific Research:**
- Species classification
- Pattern discovery in natural phenomena

**Business:**
- Customer segmentation for marketing
- Market analysis and behavior understanding

**Entertainment:**
- Content classification (movie genres)
- Recommendation systems

#### Best Practices

**Data Preparation:**
- Select relevant, meaningful features
- Ensure clean, accurate measurements
- Consider feature scaling when needed

**Algorithm Application:**
- Incorporate domain knowledge
- Use visualizations to inform decisions
- Test different cluster counts iteratively

**Result Validation:**
- Visual inspection for intuitive sense
- Expert review of clustering results
- Practical testing for intended application

#### Limitations

**Algorithm Constraints:**
- Many require pre-specifying cluster count
- Require human judgment for optimal results
- Cannot definitively validate without labeled data

**Data Dependencies:**
- Need sufficient sample sizes
- Success depends on appropriate feature selection
- Poor data quality leads to poor results

---

### 📖 Chapter 4 (Summary)

This chapter covers four essential methodologies for experimentation and prediction in data science:

**A/B Testing** provides a statistical framework for making data-driven decisions between alternatives through controlled experimentation. The four-step process (pick metric, calculate sample size, run experiment, check significance) ensures rigorous testing while avoiding common pitfalls like early stopping or misinterpreting non-significant results.

**Time Series Forecasting** uses historical temporal data to predict future values by identifying patterns like trends, seasonality, and cycles. The Rwanda pea prices case study demonstrates how forecasting models preserve seasonal patterns while providing confidence intervals to quantify uncertainty for business planning.

**Supervised Machine Learning** learns from labeled historical data to make predictions on new cases. The customer churn prediction example shows how algorithms find relationships between features and outcomes, but emphasizes the importance of examining class-specific performance rather than relying solely on overall accuracy.

**Unsupervised Learning (Clustering)** discovers hidden patterns in data without known labels. The flower species discovery case study illustrates the clustering process: defining features, determining cluster numbers through visualization, and integrating domain expertise to enhance algorithm performance.

**Universal Best Practices** across all methodologies include maintaining data quality, applying statistical rigor with uncertainty measures, embracing iterative improvement, and integrating business context. **Methodology Selection** depends on the specific problem: A/B testing for comparing alternatives, time series for temporal predictions, supervised learning for labeled prediction tasks, and clustering for pattern discovery in unlabeled data.

These methodologies provide a comprehensive toolkit for data-driven experimentation and prediction across diverse applications.
