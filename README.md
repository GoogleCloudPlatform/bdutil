# David's bdutil fork
Hadoop/Yarn/Spark, etc. are stuck on Java 7/JRE1.7. If you project needs Java 1.8, you can use
this repo. 

## Instructions
1. Clone this repo
2. Start the cluster
   Start the cluster using extensions/spark/spark_env.sh, e.g.,

   `./bdutil --bucket your-bucket -n 1 -P your-project  --env_var_files extensions/spark/spark_env.sh --zone us-central1-a deploy`
3. (Optional) If you see repeated messages about being unable to ssh, you may need to add the `all-ssh` tag.
   If your project has a ssh-whitelist (which is pretty reasonable), you may need to tag your master and workers with `all-ssh`
   so the bdutil script can ssh in and install Spark, etc. The easiest way is to go to https://console.developers.google.com/,
   find your master and workers, and add `all-ssh` on each one. You'll know that you need this if the bdutil script saying
   it's waiting for the master and workers to start up.
4. Submit Spark jobs as you normally would (with spark-submit on the master).

## Original bdutil message
Tools for creating Hadoop and Spark clusters on Google Compute Engine. See http://cloud.google.com/hadoop for more information.
