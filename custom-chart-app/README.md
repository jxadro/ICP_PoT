# Custom Char App
This is a custom chart to demo Helm and Charts in IBM Cloud Private.


## Common Parameters

| Qualifier | Parameter  | Definition | Allowed Value |
|---|---|---|---|
| image     | pullPolicy | Image Pull Policy | Always, Never, or IfNotPresent. Defaults to IfNotPresent  |
|           | repository         | Name of image, including repository prefix (if required). | See Extended description of Docker tags |
|           | tag          | Docker image tag. | See Docker tag description |
| service   | name         | The name of the port service.  | |
|           | type          | Specify type of service. | Valid options are ClusterIP and NodePort. |
|           | port          | The port that this container exposes.  |   |
|           | targetPort  | Port that will be exposed externally by the pod. | |
| resources | limits.cpu    | Describes the maximum amount of CPU allowed. | Default is 100m. |
|           | limits.memory | Describes the maximum amount of memory allowed. | Default is 128Mi |
|           | requests.cpu  | Describes the minimum amount of CPU required - if not specified will default to limit (if specified) or otherwise implementation-defined value. |  |
|           | requests.memory | Describes the minimum amount of memory required. If not specified, the memory amount will default to the limit (if specified) or the implementation-defined value. | |
| replicaCount |     |  Describes the number of desired replica pods running at the same time. | Default is 1.  See [Replica Sets](https://kubernetes.io/docs/concepts/workloads/controllers/replicaset) |
| autoscaling | enabled | Specifies whether or not a horizontal pod autoscaler (HPA) is deployed.  Note that enabling this field disables the `replicaCount` field. | false (default) or true |
|     |  minReplicas  | Lower limit for the number of pods that can be set by the autoscaler.   |  Positive integer (default to 1)  |
|     |  maxReplicas  | Upper limit for the number of pods that can be set by the autoscaler.  Cannot be lower than `minReplicas`.   |  Positive integer (default to 10)  |
|     |  targetCPUUtilizationPercentage  | Target average CPU utilization (represented as a percentage of requested CPU) over all the pods.  |  Integer between 1 and 100 (default to 50)  |
