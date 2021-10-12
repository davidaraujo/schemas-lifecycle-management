# Schema as code 
## A CI/CD pipeline for managing schemas on the Confluent Schema Registry using GitHub Actions workflow

For this project we are going to use GitHub workflows to run actions triggered by events in our schemas lifecycle, in particular:
* Run action **check schema compatibility** when a Pull Request is created to merge a new schema to master.
* Run action **register schema** when a Pull Request is approved and merged to master.

Steps to manage schemas from development to depoyment on the Confluent Schema Registry:
1. Create a new branch for your work: `git checkout -b [Branch Name]`.
2. Make changes by updating an existing schema or creating a new one under the `src/main/schemas` folder. 
3. Add the changes to your branch: ``git add .``.
4. Commit the changes: ``git commit -m "New field on schemas xpto..."``.
5. Push the new branch to your remote: ``git push origin [Branch Name]``.
6. Login to your GibHub remote, e.g. ``https://github.com/davidaraujo/schemas-lifecycle-management/pulls``, and check your new branch available for Pull Request:



- click "Compare & pull request" to merge to master
![img.png](img.png)
- check the status of the PR and if sucessfully completed all the tasks on ``schema-ci-cd-on-pull-request.yml``, in particular if new schema passed the maven compatibility checking ``mvn schema-registry:test-compatibility --file pom.xml``
- if previous step is sucessful merge the PR and check if sucessfully completed all the tasks on ``schema-ci-cd-on-merge.yml`` , in particular if new schema passed the maven compatibility checking ``mvn schema-registry:register --file pom.xml``
  
ref: https://www.freecodecamp.org/news/how-to-make-your-first-pull-request-on-github-3/

