# generic-admission-server
A library for writing admission webhooks based on k8s.io/apiserver


```go
import "github.com/openshift/generic-admission-server/pkg/cmd"

func main() {
	cmd.RunAdmission(&admissionHook{})
}

// where to host it
func (a *admissionHook) ValidatingResource() (plural schema.GroupVersionResource, singular string) {}

// your business logic
func (a *admissionHook) Validate(admissionSpec *admissionv1beta1.AdmissionRequest) *admissionv1beta1.AdmissionResponse {}
```
