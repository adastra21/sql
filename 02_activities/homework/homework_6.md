# Homework 6: Reflecton

- Due on Saturday, September 21 at 11:59pm
- Weight: 8% of total grade

<br>

**Write**: Reflect on your previous work and how you would adjust to include ethics and inequity components. Total length should be a few paragraphs, no more than one page.

We should incorporate ethics and equity in every stage of the data science process: data collection, storage, querying and modelling. To stay relevant to this course, I will restrict my response to the first two.

# Data Collection
When collecting data, we should ask ourselves: Is there anyone who could be potentially excluded? Data collection, especially through digital or online methods, can seem innocuous but often creates biased datasets. For instance, when the city of Boston created an app to report potholes, those reported were disproprotionately in affluent neighborhoods since the app required users to have a smartphone and a car ([Street Bump app](https://crowdgov.wordpress.com/new-updated-case-studies/boston-streetbump/)). Similarly, data collection on any group of people shaped by social inequities, such as those in the criminal justice system, will lead to a biased dataset: one that is likely to be overrepresentative of people of color (e.g. Blacks and Latinos). With a biased dataset, machine learning algorithms will learn the bias and replicate it in its predictions. A cautionary tale is the COMPAS model that predicted risk of future crime ([Machine Bias](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing)).

# Data storage
Within data storage, there are many ways to tackle ethics and inequities. I will cover schema design, privacy, and security.

## Schema design
We should view a database not as an abstract collection of tables, but as a socio-technical system that encodes societal assumptions and biases. For example, in Pakistan, the identity system that gives citizens access to basic services is the National Database and Registration Authority (NADRA) identity card system. Its database designers assumed that all citizens have two biological parents, one of two genders, and a paper trail of their family roots which led to unnecessary difficulties for citizens who did not fit into these sweeping assumptions ([When Databases Get to Define Family](https://www.wired.com/story/pakistan-digital-database-family-design/)).

When designing a database, we should create a flexible schmea by applying concepts from design thinking to find out all the ways that a column could be defined, and the data it could contain. We can then select column names, data types and relationships accordingly. For example, we may end up deciding that `Gender` should not be stored as a boolean, but rather as a flexible enum.

## Privacy
Privacy is another important consideration for storing information in databases. Today, most analytics systems use tags, custom scripts and cookies to automatically collect a tonne of data when someone visits a website or opens an app. This can include everything from clicks, pageviews and searches to filters used, search terms, and location. We should ask ourselves: Do we really need this information on every visitor? If not, how can we give customers the opportunity to opt-out without addiing significant friction? If we do, how can we get informed consent in an ethical way?

## Security
Many databases store personally-identifiable (PII) information which can include everything from demographic information such as name, phone number and home address to sensitive information such as medical history, voting history and credit card information. Databses that contain PII and sensitive information should encrypt it using a high level of encryption, restrict access for a narrow set of legally valid usecases, regularly check against data leaks, and develop security protocols to prevent hacks.