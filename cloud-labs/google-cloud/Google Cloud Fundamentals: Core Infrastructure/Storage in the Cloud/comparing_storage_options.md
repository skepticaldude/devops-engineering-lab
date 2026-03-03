Now that we’ve covered Google Cloud’s core storage options, let’s do a comparison to help highlight the most suitable service for a specific application or workflow.

Consider using Cloud Storage if you need to store immutable blobs larger than 10 megabytes, such as large images or movies.

This storage service provides petabytes of capacity with a maximum unit size of 5 terabytes per object.

>[!NOTE]
>Consider using Cloud SQL or Spanner if you need full SQL support for an online transaction processing system.
>
>Cloud SQL provides up to 64 terabytes, depending on machine type, and Spanner provides petabytes.
>
>Cloud SQL is best for web frameworks and existing applications, like storing user credentials and customer orders.

If Cloud SQL doesn’t fit your requirements because you need horizontal scalability, not just through read replicas, consider using Spanner.

Consider Firestore if you need massive scaling and predictability together with real time query results and offline query support.

This storage service provides terabytes of capacity with a maximum unit size of 1 megabyte per entity.

Firestore is best for storing, syncing, and querying data for mobile and web apps.

Finally, consider using Bigtable if you need to store a large number of structured objects.

Bigtable doesn’t support SQL queries, nor does it support multi-row transactions.

This storage service provides petabytes of capacity with a maximum unit size of 10 megabytes per cell and 100 megabytes per row.

Bigtable is best for analytical data with heavy read and write events, like AdTech, financial, or IoT data.

Depending on your application, it’s possible that you might use one, or several, of these services to do the job.

You may have noticed that BigQuery hasn’t been mentioned in this section of the course.

This is because it sits on the edge between data storage and data processing, and is covered in more depth in other courses.

The usual reason to store data in BigQuery is so you can use its big data analysis and interactive querying capabilities, but it’s not purely a data storage product.
