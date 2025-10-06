# Configure Azure resources

## Deploying the Modern Enterprise Search (MES) agent template

Now that your Codespace/Dev Container and ENV files are configured, it is time to deploy the Azure resources. This is done using a `Makefile`.

To deploy everything run the following command from the Codespace/Dev Container prompt:

```bash
    make deploy
```

This will deploy the infrastructure and the application code.


### Additional Information

For a full set of Makefile rules, run `make help`.

``` bash
vscode ➜ /workspaces/<jumpstart> (main ✗) $ make help
help                         Show this help
deploy                       Deploy infrastructure and application code
build                        Build application code
infrastructure               Deploy infrastructure
extract-env                  Extract infrastructure.env file from Terraform output
deploy-webapp                Deploys the web app code to Azure App Service
deploy-functions             Deploys the function code to Azure Function Host
deploy-enrichments           Deploys the web app code to Azure App Service
deploy-search-indexes        Deploy search indexes
extract-env-debug-webapp     Extract infrastructure.debug.env file from Terraform output
extract-env-debug-functions  Extract local.settings.json to debug functions from Terraform output
functional-tests             Run functional tests to check the processing pipeline is working
merge-databases              Upgrade from bicep to terraform
import-state                 import state of current services to TF state
prep-upgrade                 Command to merge databases and import TF state in prep for an upgrade from 1.0 to 1.n
prep-env                     Apply role assignments as needed to upgrade
prep-migration-env           Prepare the environment for migration by assigning required roles
run-data-migration           Run the data migration moving data from one resource group to another
manual-inf-destroy           A command triggered by a user to destroy a resource group, associated resources, and related Entra items
```

## Configure authentication and authorization

If you have chosen to enable authentication and authorization for your deployment by setting the environment variable `REQUIRE_WEBSITE_SECURITY_MEMBERSHIP` to `true`, you will need to configure it at this point.

**NOTICE:** If you haven't enabled this, but your Tenant requires this, you may still need to configure as noted above.

