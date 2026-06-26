CS-340 Client/Server Development | Grazioso Salvare Dashboard
================================================================================

ABOUT THE PROJECT
================================================================================
This project involved building a full-stack animal shelter dashboard for a
fictional client, Grazioso Salvare. The backend is a MongoDB database populated
with Austin Animal Center data. A custom Python CRUD module handles all database
operations, and a Plotly Dash web application connects to that module to render
an interactive data table, pie chart, and geolocation map, all filterable by
rescue type.


REFLECTION
================================================================================

How do you write programs that are maintainable, readable, and adaptable?

The CRUD module from Project One is a good example of how I try to approach
this. Rather than writing raw PyMongo queries scattered throughout the dashboard
code, I encapsulated all database operations (create, read, update, delete)
into a single class with clean method signatures. That separation meant the
dashboard code never had to care about how the database connection worked or how
queries were formed. It just called shelter.read(query) and got data back. The
advantage of working that way is that if the database changes, say the
collection gets renamed or the authentication method changes, there is exactly
one place to fix it. Going forward, that same CRUD module could be reused for
any project that needs to interface with this MongoDB instance, whether that is a
different dashboard, a REST API, or an automated reporting script. The module
does not care what is consuming it.

================================================================================

How do you approach a problem as a computer scientist?

With this project I started from the client requirements and worked backward.
Grazioso Salvare needed to filter dogs by rescue type (water, wilderness,
disaster) based on specific breed, sex, and age criteria. So before writing
any dashboard code, I made sure the queries were right at the database level,
testing them directly in the mongo shell first. That bottom-up validation step
is something I leaned on more heavily here than in previous courses, where
assignments were more self-contained and the requirements were more prescribed.
When a real client's filtering logic is wrong, the whole dashboard is wrong, so
getting the data layer right before building on top of it mattered. For future
database projects I would follow the same pattern: understand what the client
actually needs to see, validate the queries against real data early, and build
the interface last.

================================================================================

What do computer scientists do, and why does it matter?

Computer scientists turn messy, manual processes into something structured and
automated. Without this dashboard, someone at Grazioso Salvare would have to
manually scan through thousands of animal records every time they needed to
identify rescue candidates. With it, a staff member can filter by rescue type in
one click and immediately see a ranked list of matching animals, a breakdown of
breeds, and a map of locations. That is not a technically impressive feature in
isolation, but it saves real time and reduces the chance of human error in a
process where picking the wrong animal for a rescue role has real consequences.
That is the part of this work that matters: not the tech stack, but what it
actually enables the people using it to do.

================================================================================
