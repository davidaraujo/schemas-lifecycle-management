# Schemas lifecycle management in Confluent Schema Registry

* Schemas stored as code on the `src/main/schemas` folder
* PR on code changes triggers a schema compatibility checking using the Schema Registry maven plugin:
    * `mvn schema-registry:test-compatibility`
    * The workflow defined on `.github/workflows/schema-ci-cd-pull-request.yml` 
* Merge a PR triggers a schema registration using the Schema Registry maven plugin:
    * `mvn schema-registry:register`
    * The workflow defined on `.github/workflows/schema-ci-cd-merge.yml` 

Next steps for the project: workflow to move schemas from dev to prod Schema Registries.

