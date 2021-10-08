### Pipelining or Running the application to the cloud.
[<img align="left" alt=" IBM | IBM" width="150px" src="https://iconape.com/wp-content/files/yk/70038/png/ibm.png" />] [IBM]
##### Cluster Setup:
- [IBM Cloud Native toolkit Setup ](https://cloudnativetoolkit.dev/resources/workshop/setup/)
- [IBM Tier app setup](https://cloudnativetoolkit.dev/resources/workshop/inventory/)
- [Hands-ON-TechZone](https://ec.yourlearning.ibm.com/w3/playback/10208199)
- [Artifactory setup](https://cloudnativetoolkit.dev/reference/tools/artifactory/)

- TOOLKIT 
   -  ```
      curl -sfL get.cloudnativetoolkit.dev | sh -
- Workshop
  - ```
    curl -sfL workshop.cloudnativetoolkit.dev | sh -

* Get application assign to IBM to be able to see the github (Enterprice Github) Curl for Github to connect to the cluster.
  - ```
    RELEASE=$(curl -s https://api.github.com/repos/IBM/ibm-garage-tekton-tasks/releases/latest | jq -r '.tag_name')

* Holding the toolkit
  - ```
    export NAMESPACE="tools"

* Giving access for K8's to run the pipeline.
  - ```
    kubectl apply -n ${NAMESPACE} -f "https://github.com/IBM/ibm-garage-tekton-tasks/releases/download/${RELEASE}/release.yaml"
   
* Giving admin policies.
  - ```
    oc adm policy add-scc-to-user anyuid system:serviceaccount:tekton-pipelines:tekton-pipelines-controller
      
  - ```
    oc adm policy add-scc-to-user anyuid system:serviceaccount:tekton-pipelines:tekton-pipelines-webhook
  - ```
    oc adm policy add-scc-to-user privileged -z pipeline
  - ```
    oc adm policy add-role-to-user edit -z pipeline

* Optional
  - ```
    oc policy add-role-to-user edit system:serviceaccount:<YOUR-PROJECT-NAME>:pipeline
   
* Run Pipeline
  - ```
    oc pipeline
___________________________________________________________________________________

#### Get Credentials:
- ```
  igc credentials

#### Notes
* 1 tier app single tier application.
* 3 tier app Front-End application with Back-End Application, Service & Database.
