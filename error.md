
## List of Errors Encountered and their fixes

* Docker Desktop k8s stuck in `starting` mode
```
go to ~/Library/Group\ Containers/group.com.docker/settings.json and edit with k8sEnabled: false
```
* Pod creation error
```
Error from server (BadRequest): error when creating "nginx_pod.yaml": pod in version "v1" cannot be handled as a Pod: no kind "pod" is registered for version "v1" in scheme "k8s.io/kubernetes/pkg/api/legacyscheme/scheme.go:30"
```
Fix - `pod` -> `Pod`
