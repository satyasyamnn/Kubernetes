# Store Core Concepts

## How to store application state/data and exchange data between pods in k8s

### Volumes (other options of data storage exists as well ex: database)

It is used by pods and containers to hold data and state.

A Pod can have multiple volumes attached to it.

Containers rely on mount path to access volume.

![Storage](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Storage/StorageWhereItfits.JPG)

## Storage types

### Volumnes

A volume refers to a storage location and must have a unique name

It is attached to a Pod and may or may not be tied to a Pod life time

A volume mount refences a volume by name and defines a mount path

![Volume Types](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Storage/Volumetypes.JPG)

![Volume Types Examples](https://github.com/satyasyamnn/Kubernetes/blob/master/Images/Storage/VolumetypesExamples.JPG)

### Persistent Volumes

### Persistent Volume Claims

### Storage classes