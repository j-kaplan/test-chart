To replicate:

Create the custom resource:
`kubectl apply -f crd.yaml`

---

This Fails with error:
`helm install . --name fail`
>Error: unable to decode "": no kind "FooRestore" is registered for version "foo.my.domain.com/v1alpha1"

But the resource gets created:
`kubectl get foorestores fail-test-chart-restore-fail`

---

This works because no hook is declared:
`helm install . --set fail=false --name success`

Resource gets created as well:
`kubectl get foorestores success-test-chart-restore-success`
