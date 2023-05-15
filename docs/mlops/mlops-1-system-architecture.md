# ML Systems Architecture Design

## **👀 Overview**

The creation and architecture of ML systems play a crucial role in the successful implementation of machine learning solutions. ML systems consist of various components, including data storage, preprocessing, model training, and prediction serving. Properly designing the architecture ensures that the system meets its intended objectives and functions effectively.

ML systems are subject to technical debt, which refers to accumulated problems in code and architecture caused by neglecting software quality during development. ML-specific technical debt includes issues like unstable data dependencies, feedback loops, pipeline complexities, and entanglement. Addressing these challenges is essential for maintaining the system's performance and facilitating future modifications.

Understanding ML system architecture is vital for several reasons. It provides a clear vision of the end product and guides decision-making throughout the development process. A well-designed architecture ensures system reliability, ease of maintenance, and scalability. Additionally, it promotes effective collaboration within the development team by establishing a shared understanding of the system's structure and functionality.

## **🎯 Goals**

The primary goals of considering ML system architecture are:

1. Define a clear and comprehensive architecture that aligns with the system's objectives and requirements.
2. Identify and address potential technical debt specific to ML systems to ensure long-term maintainability.
3. Balance development speed and reliability by making informed trade-offs during the architectural design phase.
4. Enable seamless integration with existing infrastructure and tools, leveraging established practices and frameworks.
5. Facilitate efficient data preprocessing, model training, and prediction serving processes within the system.
6. Ensure scalability, allowing the system to handle increasing data volumes and user demands.
7. Incorporate proper monitoring and error handling mechanisms to detect and resolve issues promptly.
8. Promote collaboration and shared understanding among team members by documenting and communicating the system architecture effectively.

By achieving these goals, ML system architects can build robust and efficient systems that deliver reliable predictions and support continuous improvement and evolution of machine learning solutions.

## **🏗️ Creating and Architecture of ML Systems**

### **ML Solution Architecture**

ML Solution Architecture refers to the design and organization of components and processes within a machine learning system to create an effective and scalable solution. It involves determining the structure and interaction between various elements such as data ingestion, preprocessing, model training, evaluation, deployment, and prediction serving.

![Source: ["Hidden Technical Debt in Machine Learning Systems" paper](https://papers.nips.cc/paper/2015/file/86df7dcfd896fcaf2674f757a2463eba-Paper.pdf)](https://i.imgur.com/LzgGXiX.png)

Source: ["Hidden Technical Debt in Machine Learning Systems" paper](https://papers.nips.cc/paper/2015/file/86df7dcfd896fcaf2674f757a2463eba-Paper.pdf)

Key components and processes:

- **Data ingestion:** Collecting and acquiring relevant data for training and evaluation.
- **Data preprocessing**: Cleaning, transforming, and preparing data for modeling.
- **Feature engineering**: Extracting and selecting meaningful features from the data.
- **Model training**: Building and training machine learning models using the prepared data.
- **Model evaluation**: Assessing the performance and accuracy of trained models.
- **Model deployment**: Integrating the models into a production environment for real-time use.
- **Prediction serving**: Providing predictions or recommendations based on deployed models.
- **Monitoring**: Continuously monitoring the system's performance and data quality.
- **Scalability and efficiency**: Ensuring the system can handle large-scale data and user demand.
- **Security and privacy**: Implementing measures to protect sensitive data and ensure compliance.

A well-designed ML solution architecture enables the development of robust, scalable, and accurate machine learning systems. It ensures effective utilization of data, efficient model training and deployment, and reliable prediction serving.

**Why should we care about this?**

1. Architecture describes the end product we need to build.
2. Choosing an architecture dictates the strengths, weaknesses, and future modifications of the solution.
3. Poor architecture leads to technical debt and problems in its operation, maintenance, and development.
4. Effective teamwork requires a shared understanding of how your system is structured.

**Technical Debt** refers to the accumulated issues in software code or architecture that arise from neglecting software quality during development, resulting in additional future work and costs.

<aside>
💡 **ML Systems** have additional "capabilities" for accumulating technical debt. ML Engineers encounter this **first and foremost**.

</aside>

Examples include unstable data dependencies, feedback loops, glue code, pipeline jungles, dead experimental code paths, fixed thresholds in dynamic systems, entanglement (CACE principle), and more.

Initially, MLEs inherit all the problems and best practices from Software Engineering.

![Source: [https://www.freecodecamp.org/news/a-quick-introduction-to-clean-architecture-990c014448d2/](https://www.freecodecamp.org/news/a-quick-introduction-to-clean-architecture-990c014448d2/)](https://i.imgur.com/KSDVAZZ.png)

Source: [https://www.freecodecamp.org/news/a-quick-introduction-to-clean-architecture-990c014448d2/](https://www.freecodecamp.org/news/a-quick-introduction-to-clean-architecture-990c014448d2/)

### **Creating ML Systems**

<aside>
💡 To make great products: **do machine learning like the great engineer you are, not like the great machine learning expert you aren't**. 😄

Source: [https://developers.google.com/machine-learning/guides/rules-of-ml](https://developers.google.com/machine-learning/guides/rules-of-ml)

</aside>

[Best Practices](https://developers.google.com/machine-learning/guides/rules-of-ml) for ML Engineering by Martin Zinkevich:

- Make sure your pipeline is solid end to end.
- Start with a reasonable objective.
- Add common-sense features in a simple way.
- Make sure that your pipeline stays solid.

Here are some [rules for the ML system design developmen](https://developers.google.com/machine-learning/guides/rules-of-ml)t divided into the following phases:

1. Before Machine Learning
2. ML Phase I: Your First Pipeline
3. ML Phase II: Feature Engineering
4. ML Phase III: Slowed Growth, Optimization Refinement, and Complex Models

### **Requirements for Architecture**

- Requirements for feature computation
    - On-the-fly or precomputed?
    - Which software tools will be used?
- Requirements for training
    - How often?
    - On which resources?
- Requirements for prediction serving
    - How will predictions be served?
    - How quickly?
    - Minimum acceptable quality?
- Trade-off between development speed and reliability

Here's the information organized into a table format:

| Requirements  | Important information |
| --- | --- |
| Requirements for feature computation | On-the-fly or precomputed features?
Tools/frameworks for feature computation?
Scalability/performance requirements? |
| Requirements for training | Frequency of training?
Available training resources?
Constraints/requirements for data handling? |
| Requirements for prediction serving | Method of serving predictions?
Response time requirements?
Minimum acceptable prediction quality? |
| Trade-off between development speed and reliability | Development speed vs. reliability priorities?
Criticality of system reliability? |
| Requirements for autonomy | Autonomous operation or human intervention?
Desired level of decision-making autonomy?
Regulatory/compliance considerations? |
| Requirements for customizable processing | Need for data processing/model training customization?
Incorporating custom algorithms or pipelines?
Modular and configurable components? |
| Requirements for handling private data | Privacy regulations/concerns?
Security measures for private data?
Data handling/encryption requirements? |

In this table, the requirements for architecture are listed in the left column, and specific details or questions related to each requirement are provided in the right column.

### Feature Preprocessing

There are usually two approaches:

- Compute features in real-time
- Some features need to be precomputed

Using existing data sources introduces integration challenges and imposes constraints, such as response time.

A **Feature Store** is used to store features, which are utilized during both training and prediction serving.

![https://uploads-ssl.webflow.com/5f6353590bb01cacbcecfbac/6022bb585ddf720fe20f3566_graph_mainpage.png](https://uploads-ssl.webflow.com/5f6353590bb01cacbcecfbac/6022bb585ddf720fe20f3566_graph_mainpage.png)

For example, [Hopsworks](https://docs.hopsworks.ai/latest/).

### Training

- The most common approach is scheduled retraining - running code with cron jobs or task schedulers. *(This is practiced in our course)*
- Another approach is online learning ([e.g., using Kafka and TensorFlow](https://www.tensorflow.org/io/tutorials/kafka#online_learning)).

![Source: [https://towardsdatascience.com/machine-learning-in-production-using-apache-airflow-91d25a4d8152](https://towardsdatascience.com/machine-learning-in-production-using-apache-airflow-91d25a4d8152) ](https://miro.medium.com/max/700/1*QsFWK-skaXHCpmBoE_qKdA.png)

Source: [https://towardsdatascience.com/machine-learning-in-production-using-apache-airflow-91d25a4d8152](https://towardsdatascience.com/machine-learning-in-production-using-apache-airflow-91d25a4d8152) 

For example, [Machine Learning in Production using Apache Airflow](https://towardsdatascience.com/machine-learning-in-production-using-apache-airflow-91d25a4d8152).

### Prediction Serving

![Source: [https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines](https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines) ](https://ml-ops.org/img/model-as-service.jpg)

Source: [https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines](https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines) 

- Simple: Write a Python-based REST API wrapper *(This is practiced in our course)*
- Fast: Rewrite code in Go/C++ and use gRPC

![Source: [https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines](https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines) ](https://ml-ops.org/img/model-as-dependency.jpg)

Source: [https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines](https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines) 

- In monolithic architecture applications
- In mobile applications

![Source: [https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines](https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines) ](https://ml-ops.org/img/precompute-serving-pattern.jpg)

Source: [https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines](https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines) 

![Source: [https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines](https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines) ](https://ml-ops.org/img/model-on-demand.jpg)

Source: [https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines](https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines) 

### ML as a part of Existing Services

ML systems often arise on top of existing infrastructure:

1. There is already a data warehouse.
2. There is already a backend and established development approaches.

In such cases, it is typical to use existing tools and approaches. For example, using Airflow for running model training pipelines when it is already used in the company for ETL processes. Or deploying models on AWS SageMaker/OpenShift/Heroku when developers are already familiar with these platforms.

This can have both advantages (no need to build everything from scratch) and disadvantages (using inconvenient tools).

## Examples

### **Example 1: Practice in our course**

- Task: Daily user LTV forecast to prevent churn
- Architecture:
    1. Data is updated daily and available for download from Object Storage.
    2. Training occurs on a schedule.
    3. Real-time prediction using REST API queries.

### **Example 2**

- Requirement: Fixed frequency of response to forecasts
- Example tasks:
    - Daily user LTV forecast to prevent churn
    - Hourly weather forecast
    - Hourly energy consumption forecast
- Architecture:
    1. Data is collected from various sources and stored in a data warehouse (DWH), constantly updated.
    2. Scheduled training: Download fresh data (SQL), prepare the dataset, train the model.
    3. Scheduled prediction: Load the result into the database.

### **Example 3**

- Requirements: Big data, high-load services requiring a high-speed response
- Example tasks:
    - Maps: travel time from point A to point B
    - Ad rotation
    - Email spam classification
- Architecture:
    1. Data is collected from various sources (e.g., HDFS), features are computed (e.g., Spark), and stored in a Feature Store.
    2. Scheduled training: Download fresh data, prepare the dataset, train the model.
    3. Real-time prediction using gRPC queries, with code potentially rewritten in compiled languages.

## **🏁 Conclusion**

1. Architecture refers to the description and structure of software systems.
2. Technical debt is the accumulated issues in software code or architecture that arise from neglecting software quality during development, resulting in additional future work and costs.
3. ML systems have their own specific technical debt, which requires special attention and effort to address, in addition to regular development technical debt.
4. Discussing architecture is best started by defining the system requirements. Key ML-specific requirements include feature computation, model training, and prediction serving.

ML systems encompass a wide range of components and considerations, from feature preprocessing to training and prediction serving. It's important to carefully design the architecture, taking into account the specific requirements of the system and considering the trade-offs between development speed, reliability, scalability, and other factors.

## **🎓 Additional Resources**

- ["Hidden Technical Debt in Machine Learning Systems" paper](https://papers.nips.cc/paper/2015/file/86df7dcfd896fcaf2674f757a2463eba-Paper.pdf)
- [Rules of Machine Learning: Best Practices for ML Engineering by *Martin Zinkevich*](https://developers.google.com/machine-learning/guides/rules-of-ml)
- [Machine Learning Systems by Jeff Smith](https://www.manning.com/books/machine-learning-systems)
- [Three Levels of ML Software](https://ml-ops.org/content/three-levels-of-ml-software#code-deployment-pipelines)
- Clean Architecture: A Craftsman's Guide to Software Structure and Design, Robert C. Martin; [Short video about it](https://www.youtube.com/watch?v=DJtef410XaM)
- A Philosophy of Software Design (2018), John Ousterhout
- [Machine Learning in Production using Apache Airflow](https://towardsdatascience.com/machine-learning-in-production-using-apache-airflow-91d25a4d8152)
