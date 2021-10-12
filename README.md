# schemas-management

Workflow management for schemas

Change a schema and create a Pull Request
- create a new branch `git checkout -b [Branch Name]`
- change schema (add or delete fields)
- check changes ``git status``
- add changes to the new branch ``git add .``
- commit the changes ``git commit -m "New field on schemas xpto"``
- check the remote ``git remote``
- push changes to remote ``git push origin [Branch Name]``
- go to git, e.g. ``https://github.com/davidaraujo/schemas-lifecycle-management/pulls``
- click "Compare & pull request" to merge to master
![img.png](img.png)
- check the status of the PR and if sucessfully completed all the tasks on ``schema-ci-cd-on-pull-request.yml``, in particular if new schema passed the maven compatibility checking ``mvn schema-registry:test-compatibility --file pom.xml``
- if previous step is sucessful merge the PR and check if sucessfully completed all the tasks on ``schema-ci-cd-on-merge.yml`` , in particular if new schema passed the maven compatibility checking ``mvn schema-registry:register --file pom.xml``
  
ref: https://www.freecodecamp.org/news/how-to-make-your-first-pull-request-on-github-3/

