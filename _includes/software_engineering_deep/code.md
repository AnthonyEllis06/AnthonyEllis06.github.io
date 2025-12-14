
---
I spent a lot of time trying to define what approach was both the most simple to implement while also being robust enough to enable me to easily implement the design I wanted. I considered other full stack frameworks such as the mean stack but ultimately decided on the django framework due to its amount of public documentation and built in features such as model generation and admin page generation that would allow me the quickest path to developing a base for the application. By default django come built in with a lightweight sqlite3 database setup that essentially stores all of the data in a single file. The ability to start with a already setup database and then later convert to a more capable and deployable database such as postgresql made django an easy choice. I chose to use reacts static templating engine to make the web page more reactive and dynamic while being fairly easy to implement. If I had chose to go the full react route I would have to as a separate frontend application that would communicate with the backend and the backend with the database in a more complex model view controller architecture, however for simplicity I chose to use static react templates the django rendered directly in the browser. The use of static react pages also allowed me to easily implement my doubly linked list data structure into the frontend logic in a way that followed the data structure principle search and sort operations.

Old Artifact User Interface(left) Enhanced Artifact User Interface(right)
<div style="display: flex; gap: 2px; justify-content: center;">
<img src="/assets/images/NamelistAppUserInterface.png" alt="Namelist App User Interface" width="50%"/>
<img src="/assets/images/EnchantedBeautyInterface.png" alt="Enchanted Beauty Interface" width="50%"/>
</div>
---
The addition of running the the application inside of a docker container greatly simplified deployment. The process of learning docker was relatively simple due to a large amount of public documentation and tutorials however docker after the intital setup is fairly easy to work with, especially for a simple web application such as this. By using docker I can essentially define what packages the environement needs and package them all together into a single image that can be run on machines that have docker installed or deployed to services such as AWS or other cloud platforms that support containerized applications. The simplicity of docker comes from its three main files, the dockerfile, the docker compose files, and the requirements file all which outline the steps needed to create and run the environment. The use of a docker container also allowed me to very easily setup the postgresql database due to being able to run both the backend and frontend in the same container. This allowed me to use djangos built in database management tools to easily rebuilt the database schema for postgresql and connect to it with minimal changes to the original codebase.

Docker Container Running Application(left) Visual Studio Running Original Application(right)
<div style="display: flex; gap: 2px; justify-content: center;">
<img src="/assets/images/DockerRunInterface.png" alt="Namelist App User Interface" width="50%"/>
<img src="/assets/images/VisualStudioRunInterface.png" alt="Enchanted Beauty Interface" width="50%"/>
</div>

---
The biggest addition to the whole project that was easily available due to the use of django was security features. By using djangos built in administration page and authentication system I was able to easily and quickly setup a layer of security to protect sensitive client information such as phone numbers. Django's built in administration page automatically uses the built in database management system to define what data is in the database. This allows for the the owner or admin to easily access and manage the client information on the database side without needing to manually edit the information in the forms page which should be a rare occurance for updating client information.

Django Admin Page for Managing Client Information
<img src="/assets/images/DjangoAdminInterface.png" alt="Django Admin Page" width="100%"/>
---