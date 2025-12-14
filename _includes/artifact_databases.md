
---
## Databases Enhancement
My original artifact comes from my Client/Server development class where we built a database first web application using mongodb for our database and jupyter dash components for our frontend. The original artifact can only be run via the jupyter notebook interface and therefore limits the applications accessibility. The main resource from this artifact that I enhanced was using the same architecture of creating my own API but converting it over to django with postgresql as the database backend. This same structure of using an API to communicate between the frontend and backend became instrumental for defining how the Django templates with embedded javascript frontend would communicate the changes to the database. I also enhanced the original design by restructuring the backend to a RESTful API pattern where I separate my API calls into two different endpoints, one for collection editing and one for individual detail or item editing. This enhancement also allowed for a leaner, more data integrity focused design that also aligned with the RESTful API principles.


The original artifact can be found here: <a href="https://github.com/AnthonyEllis06/CS340">Original Databases Artifact</a>


<a href="/2025/12/13/databases.html">Databases Enhancement Deep Dive</a>