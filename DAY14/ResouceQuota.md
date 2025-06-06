# Resource Quotas

Resource Quotas in Kubernetes are a mechanism for limiting the resource usage of a namespace. They help ensure fair resource distribution among different teams or applications running in a cluster by enforcing limits on the consumption of resources like CPU, memory, and the number of objects (pods, services, etc.).

## Key Concepts of Resource Quotas

### 1. Purpose
Resource quotas are primarily used to prevent any single namespace from consuming too many resources and to promote fair resource sharing in multi-tenant environments.

### 2. Quota Types
You can set quotas for various resources, including:

- **CPU**: The total CPU resources (in cores) that can be requested by containers in the namespace.
- **Memory**: The total memory (in bytes) that can be requested by containers.
- **Persistent Volumes**: The total number of persistent volume claims (PVCs) allowed.
- **Pods**: The maximum number of pods that can be created in the namespace.
- **Services**: The maximum number of services that can be created.

### 3. Limits
Resource quotas can specify both **hard limits** (maximum resource usage) and **soft limits** (recommended usage).

## Example

```yaml
apiVersion: v1
kind: ResourceQuota
metadata:
  name: example-quota
  namespace: test-ns
spec:
  hard:
    pods: "3"
