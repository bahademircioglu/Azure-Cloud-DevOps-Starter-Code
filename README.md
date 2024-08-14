This repo contains the starter materials for projects from the Udacity Azure Cloud DevOps Nanodegree Program.

Run tagging policy:
az policy definition create --name tagging-policy --rules 'tagging-policy.json' --display-name "Require tags on all resources" --description "This policy denies the creation of resources without tags." --mode Indexed

Apply tagging policy (use your own <subsID>):
az policy assignment create --policy tagging-policy --name tagging-policy --scope /subscriptions/<SubscriptionID>

Listing the policy created:
az policy assignment list --query "[?name=='tagging-policy']"

To create server image I modified "C1 - Azure Infrastructure Operations/project/starter_files/server.json" according my needs and used the following packer command to execute:
packer build -var 'client_id=<your-client-id>' \
             -var 'client_secret=<your-client-secret>' \
             -var 'tenant_id=<your-tennant-id>' \
             -var 'subscription_id=<your-sub-id>' \
             -var 'resource_group_name=<your-resource-group-name>' \
             -var 'location=<location you want to the vm deployed>' \
             server.json
             
