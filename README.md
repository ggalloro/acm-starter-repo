# acm-starter-repo
Basic Repo Structure to start implementing Anthos Config Management 

This is working progress used to start showing/implementing ACM

This repo contains:

- A simple starting namespace structure, containing one namespace named 'namespace1' (to be renamed to what works for you)



- A resource quota applied to all namespaces that limits to 5 pods, 2 cpu and 4Gi of memory

- A role named 'deployer', applied to all namespaces, to be bound to an user or service account able to deploy applications only on assigned namespace

- A 'user1' SA in the namespace1 namespace to be bound to the deployer role (not needed if working with Google Accounts on GKE or using any other Identity provider)

- A 'user1' role binding in the namespace1 namespace to bound the SA and the deployer role

- A network policy, applied to all the managed namespaces, to show how to allow inbound traffic only from same namespace (and istio ingress gateway running in gke-system namespace in case of Anthos GKE On-Prem in order to allow traffic) and outbound traffic only to specific address outside the cluster (to be replaced with what works for you)

- An Anthos Config Management Policy Controller Constraint to block priviledged containers in non system namespaces. This would require tho have Policy controller component installed with ACM as described in the documentation: https://cloud.google.com/anthos-config-management/docs/how-to/installing-policy-controller#installing

- It includes some cluster objects and cluster selectors in clusterregistry folder as starting assets in case you want to apply different policies to different clusters
