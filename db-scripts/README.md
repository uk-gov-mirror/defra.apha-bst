<h1>📂 DB Scripts</h1>

<p>
This repository contains structured database scripts for schema creation/maintenance, and direct execution. 
Scripts are organized in sequential order to simplify deployments via Jenkins Job.
</p>

<hr/>

<h2>📑 Folder Structure</h2>

<pre>
db-scripts/
│── 01-tables/        # Table creation scripts
│── 02-views/         # View definitions
│── 03-indexes/       # Index creation scripts
│── 04-procedures/    # Stored procedure definitions
│── 99-directscripts/ # One-off / ad-hoc scripts
│── Makefile          # Automation for executing scripts
│── README.md         # Documentation
</pre>

<p> The Makefile is triggered by a Jenkins job after the database restore, and executes the scripts automatically. </p>
<hr/>
