how to set up Cymbal Superstore’s cloud environment.

Let’s start with how to set up Cymbal Superstore’s cloud environment.

Cymbal Superstore is ready to start implementing basic cloud infrastructure for their organization.

As an Associate Cloud Engineer, you have been assigned to the team to help with this phase of the project.

The team begins with a planning meeting to decide how Cymbal Superstore’s cloud structure will be organized.

The outcomes of this phase of the migration journey include establishing a resource hierarchy, implementing organizational policies, managing projects and quotas, managing users and groups, and applying access management.

Setting up billing and monitoring the use of your cloud resources are also things to consider.

Let’s take a closer look.

How to set up a resource hierarchy on Google Cloud depends on the needs and structure of the organization.

Cymbal Superstore plans to migrate three applications to the cloud: its supply chain application, which will run on VMs; its containerized

ecommerce application, which will use GKE; and its transportation management application, which will use Cloud Run functions to track truck location.

These applications correspond to three different departments.

Operations manages the B2B supply chain, Logistics oversees transportation, and Sales & Marketing manages the eCommerce application.

The graphic shows a possible organizational hierarchy for Cymbal Superstore.

The Cymbal Superstore organization is at the top, followed by optional folders underneath, one for each division and one for each application.

There are multiple projects under the B2B supply chain app folder, one for each environment related to continuous integration/continuous delivery: a development, staging, and production environment.

Other apps in the chart would have a similar project structure.

As you set up the hierarchy, you will also need to grant organizational policies.

For example, Marketing might need to access the data in the supply chain system to see if inventory levels affected recent marketing campaigns.

Giving Marketing viewer permissions on the supply chain production environment might be a good choice to give them the access they need.

An Associate Cloud Engineer could also be tasked with enabling Application Programming Interfaces (API’s) within projects during setup.

Cymbal Superstore’s ecommerce project requires access to Google Kubernetes Engine and Cloud SQL as a database backend and you’ll need to enable the APIs for those services.

Setting up the cloud environment also involves granting members IAM roles to ensure that they have

the right access to projects depending on their needs of their job and role at Cymbal Superstore.

For example, data analysts in the Marketing department will need to have access to historic sales data in the ecommerce system.

This could be a great use case for BigQuery, Google Cloud’s data warehouse solution.

How would we go about giving proper access?

New data analysts would need to be added to the data_analyst group.

Managing permissions and rules at a group level is easier than keeping track of permissions for individual users.

> [!NOTE]
> Data analysts need to access the data in the dataset or table, so they require the bigquery.dataViewer role at the proper level.
> 
> Queries in BigQuery are executed as an executable job.
> 
> So to submit a query, a data analyst would also need the bigquery.jobs.create permission.
> 
> This permission is included in the predefined bigquery.user role.

You would give the data_analyst group access to this role in the Production project.

As a cloud engineer, you’ll need to know how to manage Cymbal Superstore’s users and groups in

Cloud Identity, a service for managing users and groups if you are not doing so via Google Workspace.

Google Cloud Observability, which used to be called Google Cloud’s operations suite and Stackdriver before that,

provides metrics and logging services for all of your services, resources, and projects in your cloud architecture.

To monitor metrics from multiple projects, you set up project scoping.

If Cymbal Superstore’s Operations department decides to monitor metrics across all three supply chain projects in the staging

environment project, you will set staging as a scoping project and then add dev and production as monitored projects.

While migrating to Google Cloud, Cymbal Superstore will be moving some of its IT expenditure to

operational expenses, and different departments associated with each application will be responsible for compute and storage costs.

You’ll need to create a different billing account for each group and link each project to the appropriate account.

The department lead in Sales and Marketing expresses particular concern about the cost of housing its data warehouse in BigQuery and how to optimize queries and storage.

You’ll need to set up custom billing budgets and alerts for this department.

Each department will also need you to set up billing exports that can be used to track charges.
