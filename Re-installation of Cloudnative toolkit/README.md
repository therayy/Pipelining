#### If you ran into installation issues with Cloudnative toolkit when installing via your local terminal follow these steps for reinstallation:
- STEP 1: 
           ```
           oc project default
- STEP 2: 
           ```
           oc delete job/ibm-toolkit -n default
- STEP 3: 
           ```
           oc delete project tools
           
- Refresh Terminal until deletes clears

- Run AND REPEAT: 
                  ```
                  oc projects
- STEP 4:  Go to:   https://cloud.ibm.com/shell

- STEP 5:  oc login < > --server= < >

- STEP 6:  
           ```
           curl -sfL get.cloudnativetoolkit.dev | sh -

- Wait until installation completes.

- STEP 7: 
          ```
          curl -sfL workshop.cloudnativetoolkit.dev | sh -
