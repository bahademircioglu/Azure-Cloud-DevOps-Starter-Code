This repo contains the starter materials for projects from the Udacity Azure Cloud DevOps Nanodegree Program.

Run tagging policy:
az policy definition create --name tagging-policy --rules 'tagging-policy.json' --display-name "Require tags on all resources" --description "This policy denies the creation of resources without tags." --mode Indexed

Apply tagging policy (use your own <subsID>):
az policy assignment create --policy tagging-policy --name tagging-policy --scope /subscriptions/<SubscriptionID>

Listing the policy created:
az policy assignment list --query "[?name=='tagging-policy']"
