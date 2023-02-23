# external-service-oas
Open API specifications for 2 versions of an External Service in a managed package for testing an upgrade.

## Step 1
A second generation managed package was created an External Service (**SalesDocSearch**) created from [swagger_v1.json](/swagger_v1.json), as well as
an Apex class with a static method that invoked the External Service. This package was then promoted, and its version id was added as the `ancestorId` in the `sfdx-project.json`.

## Step 2
The External Service (**SalesDocSearch**) was updated to reference [swagger_v2.json](/swagger_v2.json#L574-L623). The difference in the APIs is an additional 10 fields being added to the response. This worked in the scratch org where development was being done, however it fails to create a second generation managed package with the following error:
```
"SalesDocSearch: Error encountered while saving External Registration. Please try again later."
```
