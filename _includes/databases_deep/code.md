
---
The first enhancement that I made can be seen in my API classes where one has four endpoints and the other only has two with modified parameters. By conjoining these endpoints into a single endpoint for collection editing and a single endpoint for individual item editing I am creating an extra layer of data integrity protection, this is of high importance because corrupt data could lead to lost appointments or even a lost client. This new design pattern is also done to more align with RESTful API principles. 

Old Artifact API endpoints(left) Enhanced Artifact API endpoints(right)
<div style="display: flex; gap: 2px; justify-content: center;">
<img src="/assets/images/artifactCRUDOperations.png" alt="Namelist App User Interface" width="50%"/>
<img src="/assets/images/EnchantedBeautyCrud.png" alt="Enchanted Beauty Interface" width="50%"/>
</div>
---
The second major enhancement I made was converting the database from MongoDB to PostgreSQL. The main reason I made this choice to change the database was due to amount of documentation and PostgreSQL being more widely used and accepted into deployable platforms. I tested the commonality of PostgreSQL by researching into the popular cloud platform AWS and found that I was seeing more and more services that supported PostgreSQL through the AWS platform. Due to how popular AWS is for deploying web applications I felt that PostgreSQL would be the most industry standard choice. The conversion process was fairly simple due to Django's built in database management tools that allows me to define a schema and then build the database from that schema. Those same Django tools were also used to switch from the default sqlite3 database to PostgreSQL fairly easily.
New Artifact Database Schema with PostgreSQL
<img src="/assets/images/databaseSchema.png" alt="Enchanted Beauty Interface" width="100%"/>