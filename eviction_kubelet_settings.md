Eviction Kubelet Settings
=============

The following configuration is to override the default behivour when the DiskPressure condition prevents you from running a pod on the node:

**use at your own risk**


Open File
-----------

```
/var/lib/kubelet/config.yaml
```

Add/modify the contents
-----------

`
evictionSoft:
  nodefs.available: "10Gi"
  nodefs.inodesFree: "10%"
  imagefs.available: "10Gi"
  imagefs.inodesFree: "10%"
evictionSoftGracePeriod:
  nodefs.available: 5m
  nodefs.inodesFree: 5m
  imagefs.available: 5m
  imagefs.inodesFree: 5m
evictionHard:
  nodefs.available: "10Gi"
  nodefs.inodesFree: "10%"
  imagefs.available: "10Gi"
  imagefs.inodesFree: "10%"
`

Restart
-------------

`systemctl restart kubelet`
