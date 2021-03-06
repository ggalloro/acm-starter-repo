# acm-starter-repo
Basic Repo Structure to start implementing Anthos Config Management 

This is working progress used to start showing/implementing ACM

This repo contains:

- A simple starting namespace structure, containing one namespace named 'application1' that can be renamed to what works for you and replicated to create more namespaces.

- A resource quota applied to all namespaces that limits to 5 pods, 2 cpu and 4Gi of memory

- A 'user1' SA in the application1 namespace to be bound to the default admin ClusterRole (not needed if working with Google Accounts on GKE or using any other Identity provider)

- A 'user1' role binding in the namespace1 namespace to bind the SA (or user from identity provider) to the default admin ClusterRole

- A network policy, applied to all the managed namespaces, to show how to allow inbound traffic only from same namespace and outbound traffic only to specific address outside the cluster (to be replaced with what works for you)

- An Anthos Config Management Policy Controller Constraint to block priviledged containers in non system namespaces. This would require tho have Policy controller component installed with ACM as described in the documentation: https://cloud.google.com/anthos-config-management/docs/how-to/installing-policy-controller#installing

- It includes some cluster objects and cluster selectors in clusterregistry folder as starting assets in case you want to apply different policies to different clusters
