# F1 Oracle: Race Performance Predictor
This is an end-to-end data science project designed to explore full-stack analytics, from database management to machine learning deployment. This project integrates PostgreSQL for data warehousing, Scikit-learn for predictive modeling, and Streamlit for the user interface. It also features a unique integration of Generative AI to provide "human-like" sports analysis.
In this project, the architecture is divided into three main components: The Data Layer, The Prediction Engine, and The AI Dashboard.

DATA PIPELINE & STORAGE

Built on a robust relational database structure using PostgreSQL.
Data Warehouse: The system ingests 14 distinct CSV datasets (including circuits, lap times, pit stops, and race results) into a normalized SQL schema (f1_db).
ETL Process: Custom Python scripts utilize SQLAlchemy and Pandas to clean data, handle foreign key dependencies, and safely transact data into the database.
Safety Protocols: Implements environment variable protection for database credentials and secure connection handling.

MACHINE LEARNING ENGINE 

Contains the logic for forecasting driver performance.
Feature Engineering: The model utilizes complex calculated fields such as 5-race rolling averages for driver points, constructor consistency, and qualifying performance vs. race results.
Prediction Model: A pre-trained Python model (.pkl) analyzes historical patterns to predict the exact finishing position of a driver based on their starting grid slot and team performance.

INTERACTIVE DASHBOARD & AI ANALYST

A user-friendly web application built with Streamlit that serves as the front end.
Dynamic Controls: Features dependent dropdown menus—selecting a driver (e.g., Lewis Hamilton) automatically filters the "Team" dropdown to only show constructors they have actually driven for (e.g., Mercedes, McLaren).
Real-time Inference: Users can manipulate the "Starting Position" slider to see how qualifying performance impacts the predicted race result instantly.
GenAI Integration: The dashboard connects to Google Gemini. Once a numerical prediction is made, the AI acts as a "Virtual Sports Analyst," interpreting the data to generate a text-based summary explaining the context of the prediction.
