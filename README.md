## Usage
### Please copy paste below code

```
module demo {
 source = "laurammberk/gke/gcp"
 gke_config = {
   cluster_name     = "project-cluster"
   location         = "us-central1"
   node_count       = 1
   min_node_count   = 1
   max_node_count   = 2
   machine_type     = "e2-medium"
   disk_size_gb     = "100"
   disk_type        = "pd-balanced"
   cluster_location = "us-central1"
   }
}
```

### To get the output add below code
```
output cluster_location {
  description = "GKE cluster location"
  value       = google_container_cluster.primary.location
}

output "cluster_name" {
  description = "GKE cluster name"
  value       = google_container_cluster.primary.name
}
```

### Run
```
terraform init
terraform apply
```