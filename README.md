The Tokyo Olympics dataset that I am working with could contain a wide range of data related to the athletes, events, medals, countries, and other relevant aspects of the 2020 Tokyo Olympics. Here's a detailed description of the type of data typically included in such a dataset and how it aligns with my Azure data engineering project:

Athletes Data

Columns: Athlete ID, Athlete Name, Age, Gender, Nationality, Sport, Discipline.
Description: Information about the athletes participating in the Tokyo Olympics, such as their demographics, the country they represent, and the sports they compete in.
Events Data

Columns: Event ID, Event Name, Sport, Discipline, Date, Venue.
Description: Data on the various events held, including event name, discipline (e.g., Track & Field, Swimming), sport, date, and the venue where the event took place.
Medals Data

Columns: Medal ID, Athlete ID, Event ID, Medal Type (Gold, Silver, Bronze), Country, Date.
Description: Details about medals awarded, linked to athletes and events. It records which athletes won medals, which country they represented, and what type of medal they earned.
Countries Data

Columns: Country Code, Country Name, Number of Athletes, Total Medals.
Description: Data about the countries participating in the Olympics, including the total number of athletes and medals won by each country.
Sports Data

Columns: Sport ID, Sport Name, Discipline, Number of Events.
Description: Data about each sport featured in the Tokyo Olympics, including the specific disciplines within each sport and the number of events held.
Data Flow in the Project
Data Ingestion (GitHub to ADLS Gen2):

Source: I used HTTP requests from an Azure Data Factory (ADF) pipeline to pull the raw dataset from GitHub.
Storage: The raw data was loaded into a Data Lake (ADLS Gen2), making it accessible for further processing.
Data Cleaning and Transformation (Databricks):

Mounting: I mounted the raw data stored in ADLS Gen2 to Databricks.
Cleaning: I used PySpark in Databricks to clean the data (e.g., removing duplicates, handling missing values, standardizing formats).
Transformation: I applied business logic or aggregation to the data, processing it into a refined version, and saved the cleaned data in another container called "transformed" within the same ADLS Gen2.
Data Analysis and Reporting (Synapse Workspace):

Lake Database: I created a Synapse workspace, set up a lake database, and connected to the cleaned and transformed data stored in ADLS Gen2.
Table Creation: I created tables in Synapse, linked to the cleaned datasets.
Analysis: I ran SQL queries to analyze the data for stakeholder questions, such as:
Which country won the most medals?
Who was the youngest gold medalist?
Which sport had the highest number of participating athletes?
Stakeholder Reporting:
I justified my analysis by presenting insights based on the SQL queries I ran in Synapse, providing meaningful answers to stakeholder questions about the performance and statistics of the Tokyo Olympics.
