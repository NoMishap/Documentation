https://docs.openshift.com/container-platform/3.6/dev_guide/expose_service/expose_internal_ip_nodeport.html

apiVersion: v1
kind: Service
metadata:
  annotations:
​    openshift.io/generated-by: OpenShiftWebConsole
  creationTimestamp: '2018-09-19T16:17:59Z'
  labels:
​    app: openshiftproxy
  name: openshiftproxy
  namespace: nomishap
  resourceVersion: '33742544'
  selfLink: /api/v1/namespaces/nomishap/services/openshiftproxy
  uid: 93442f3c-bc27-11e8-80c6-fa611228ff41
spec:
  clusterIP: 172.30.243.164
  externalTrafficPolicy: Cluster
  ports:
​    - name: http
​      nodePort: 30036
​      port: 8080
​      protocol: TCP
​      targetPort: 8080
  selector:
​    deploymentconfig: openshiftproxy
  sessionAffinity: None
  type: NodePort
status:
  loadBalancer: {}