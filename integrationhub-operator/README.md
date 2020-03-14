Test Script
=========
```
operator-sdk build quay.io/jaysonzhao/integrationhub-operator:v0.1.1
docker push quay.io/jaysonzhao/integrationhub-operator:v0.1.1
oc delete -f deploy/crds/integrationhub.hzopen.info_v1alpha1_integrationhub_cr.yaml
PODTODEL="$(oc get pod |grep inte|while read c1 c2; do echo $c1; done)"
oc delete pod $PODTODEL
oc apply -f deploy/crds/integrationhub.hzopen.info_v1alpha1_integrationhub_cr.yaml
```

