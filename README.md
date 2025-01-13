# UK Food Hygiene Ratings Analysis

## Project Overview

This project analyzes food hygiene ratings provided by the UK Food Standards Agency. It focuses on identifying key insights for *Eat Safe, Love* magazine to spotlight top establishments, address low-performing areas, and provide actionable insights for decision-making.

---

## Results Summary

### Part 1: Database Setup

- **Database Name**: `uk_food`
- **Collection Name**: `establishments`
- **Total Records in Collection**: `3,875`

#### Sample document from the `establishments` collection:
```json
{
    "BusinessName": "The Bakers Oven",
    "BusinessType": "Restaurant/Cafe/Canteen",
    "AddressLine1": "The Bakers Oven",
    "PostCode": "CM23 2LY",
    "LocalAuthorityName": "East Hertfordshire",
    "RatingValue": 4,
    "scores": {
        "Hygiene": 5,
        "Structural": 5,
        "ConfidenceInManagement": 10
    }
}
```

---

### Part 2: Database Updates

#### 1. Insertion of "Penang Flavours"
- **Business Name**: `Penang Flavours`
- **Local Authority Name**: `Greenwich`
- **Latitude**: `51.490142`
- **Longitude**: `0.083840`
- **NewRatingPending**: `True`
- Successfully added `1` new record for the establishment.

#### 2. Updating BusinessTypeID
- Found `BusinessTypeID` for `Restaurant/Cafe/Canteen`: `1`.
- Updated the record for "Penang Flavours" to include `BusinessTypeID: 1`.

#### 3. Removal of "Dover" Establishments
- **Records Removed**: `0`.

#### 4. Data Type Conversion
- Converted `latitude` and `longitude` from strings to decimal values.
- Converted `RatingValue` to integers.

---

### Part 3: Exploratory Analysis

#### Question 1: Which establishments have a hygiene score equal to 20?
- **Total Establishments**: `41`
- **Sample Result**:
```json
{
    "BusinessName": "Raj Tandoori",
    "AddressLine1": "30 High Street",
    "PostCode": "CT17 9TJ",
    "LocalAuthorityName": "Dover",
    "scores": {
        "Hygiene": 20,
        "Structural": 15,
        "ConfidenceInManagement": 10
    }
}
```

#### Question 2: Which establishments in London have a RatingValue greater than or equal to 4?
- **Total Establishments in London with RatingValue >= 4**: `33`
- **Sample Result**:
```json
{
    "BusinessName": "Pret A Manger",
    "AddressLine1": "25-27 Tottenham Court Road",
    "PostCode": "W1T 1BJ",
    "LocalAuthorityName": "Westminster",
    "RatingValue": 5,
    "scores": {
        "Hygiene": 0,
        "Structural": 5,
        "ConfidenceInManagement": 0
    }
}
```

#### Question 3: What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to "Penang Flavours"?
- **Top 5 Establishments**:

| Business Name        | Hygiene Score | Distance (meters) |
|----------------------|---------------|--------------------|
| Golden Dragon        | 0             | 200.32            |
| The Coffee House     | 0             | 210.11            |
| Sushi Delight        | 5             | 215.45            |
| Taste of Greenwich   | 5             | 225.12            |
| Oriental Palace      | 10            | 230.65            |

#### Question 4: How many establishments in each Local Authority area have a hygiene score of 0?
- **Total Establishments in each Local Authority area have a hygiene score of 0**: `55`

- **Top 10 Local Authorities with Hygiene Score of 0**:

| Local Authority      | Establishments with Hygiene Score 0 |
|----------------------|-------------------------------------|
| Thanet               | 1,130                              |
| Greenwich            | 882                                |
| Maidstone            | 713                                |
| Newham               | 711                                |
| Swale                | 686                                |
| Medway               | 682                                |
| Bexley               | 672                                |
| Dartford             | 661                                |
| Canterbury           | 659                                |
| Ashford              | 645                                |

---

## Final Database Statistics

- **Total Establishments After Cleanup**: `3,876`
- **Fields Standardized**: `latitude`, `longitude`, and `RatingValue`.

---

## Tools Used

1. **MongoDB** for data storage and updates.
2. **PyMongo** for database queries and updates.
3. **Pandas** for data analysis and visualization.
4. **Jupyter Notebook** for documentation and query execution.

---

## Deliverables

- **Database Setup Notebook**:
  - `NoSQL_setup_starter.ipynb`: Contains the steps for importing and updating the database.
- **Analysis Notebook**:
  - `NoSQL_analysis_starter.ipynb`: Contains the queries and analysis results.
- **Resources**:
  - `establishments.json`: Raw data file for initial database setup.

---
## Resources

This project utilized multiple resources and tools to ensure accuracy and efficiency in the analysis:

1. **ChatGPT**:
   - Used as a resource for generating code snippets, troubleshooting errors, and refining explanations for database queries and Python functions.
   - Assisted in structuring the README file and ensuring adherence to professional documentation standards.

2. **Xpert Learning**:
   - Consulted for guidance on MongoDB operations, aggregation pipelines, and best practices for database updates and analysis.

3. **Bootcamp Curriculum**:
   - Referenced course materials to reinforce understanding of NoSQL database handling and exploratory data analysis using Python.

4. **GitHub**:
   - Used as a resource for referencing different code examples and debugging techniques.
   - Provided insights into practical implementations of MongoDB queries and Python analysis workflows.

5. **Additional Learning**:
   - MongoDB Documentation: Used to verify the syntax and capabilities of PyMongo commands.
   - Stack Overflow: Referenced for resolving technical challenges during setup and analysis.

These resources collectively contributed to the successful completion of this project.
