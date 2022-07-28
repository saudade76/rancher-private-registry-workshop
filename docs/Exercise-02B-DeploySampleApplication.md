# Lab 2 B - Deploy sample applications from Harbor Registry onto RKE2 cluster

This exercise will continue from the previous Exercise 2B. We'll deploy a sample application rancher's hello-world from Harbor registry. It will require back and forth navation between Rancher and Harbor Portal. 

# // Public 설치된 Harbor 에서 Hello-World container 이미지를 가져와서 Rancher 를 통해서 Deployment 수행
![image](https://user-images.githubusercontent.com/74942851/181430262-dbfdae46-73a3-45c3-a6eb-1838c998aecb.png)



Private registry can be directly configured during cluster setup and user need not to know or enter the registry url along with the image name. For visibility purpose, exercise is designed in this way to manually enter complete path.  

###### Usecase: CLI has serveral benefits including flexibility. However, GUI provide more controlled options and guided navigation. It makes learning easier and interactive. Rancher provides user interface for Kubernetes management without additional learning curve. 

## Action 1: Prepare for deployment on Rancher 

This action will involve 2 steps from 2B.1 to 2B.2

**Step 2B.1)** Ensure that you are logged in to the Rancher (Refer to the Step 1 of section **Before We Begin**). Click on `Hamburger Menu icon (1)`. It will show list of clusters. Now click on downstream cluster `rke2-cluster1 (2)` from the clusters list.

![Screenshot-2022-07-24-at-4.23.26-PM](../images/Screenshot-2022-07-24-at-4.23.26-PM.png)

**Step 2B.2)** Click on `Workload (1)` menu option and then click on `Deployments (2)`. Navigate to the right of the screen and click on `Create (3)`. 

![Screenshot-2022-07-24-at-4.26.54-PM](../images/Screenshot-2022-07-24-at-4.26.54-PM.png)

**End of Action 1**



## Action 2: Copy pull command from Harbor 

This action will involve 4 steps from 2B.3 to 2B.6

**Step 2B.3)** Now you will need to specify container image location which needs to be copied from the Harbor portal. Ensure that you are logged in to the Harbor (Refer to the Step 1 of section Before We Begin). On Harbor Home page, click the `library` link on main screen under Project Name column. 

![Screenshot-2022-07-24-at-4.29.54-PM](../images/Screenshot-2022-07-24-at-4.29.54-PM.png)

**Step 2B.4)** Click on link `library/hello-world` under Name column (This may depend on how many nested repository is been create).

![Screenshot-2022-07-24-at-4.30.22-PM](../images/Screenshot-2022-07-24-at-4.30.22-PM.png)

**Step 2B.5)** Click on container image link `sha256:xxxxxxxx` under **Artifacts** column. 

![Screenshot-2022-07-24-at-4.31.08-PM](../images/Screenshot-2022-07-24-at-4.31.08-PM.png)

**Step 2B.6)** Click on copy icon `[[]` under the **Pull Command** column. This action will copy pull command to the clipboard. To avoid accedental delete, you may choose to copy on any of text editor of your choice. 

![Screenshot-2022-07-24-at-4.31.57-PM](../images/Screenshot-2022-07-24-at-4.31.57-PM.png)

**End of Action 2**



## Action 3: Continue to the deployment on Rancher 

This action will involve 5 steps from 2B.7 to 2B.11

**Step 2B.7)** Navigate back to the Rancher portal (Make sure that you are the Deployment screen). Fill in the following details and click on `Create` 

`Namespace : default`

`Name : user's choice e.g. rancher-hello-world-harbor`

`Container Image : paste the pull command copied from harbor without statement "docker pull" e.g. harbor.yy.yy.yy.yy.sslip.io/library/hello-world:v0.1.2`

`Pull Seceret : as specified in Step 2A.5 (From dropdown) e.g. harbor-registry `

`Service Type : Node Port (From the dropdown)`

`Private Container Port : 80`

Leave the Listning Port blank. System will assign a higher port of it's choice greater than 30000.  

![Screenshot-2022-07-24-at-4.33.37-PM](../images/Screenshot-2022-07-24-at-4.33.37-PM.png)

**Step 2B.8)** Verify that deployment is successfully created and click on the hyperlink of the deployment under **Name** column. 

![Screenshot-2022-07-24-at-4.39.50-PM](../images/Screenshot-2022-07-24-at-4.39.50-PM.png)

**Step 2B.9)** Verify that 1 Pod is in Running state. 

![Screenshot-2022-07-24-at-4.41.07-PM](../images/Screenshot-2022-07-24-at-4.41.07-PM.png)

**Step 2B.10)** Click on `Service Discovery (1)` option from the left hand static menu and then click on `Services (2)`  submenu under the Service Discovery. Now click on the link `3nnnn/TCP (3)` under **Target** column.

![Screenshot-2022-07-24-at-4.42.05-PM](../images/Screenshot-2022-07-24-at-4.42.05-PM.png)

**Step 2B.11)** Verify that Rancher's Hello world application is accessible on designated Node Port. 

![Screenshot-2022-07-24-at-4.44.19-PM](../images/Screenshot-2022-07-24-at-4.44.19-PM.png)

**End of Action 3**

**End of Exercise 2B**

Continue to: [Exercise 3A-Installing and setting OPA constraint on RKE2 cluster](https://github.com/dsohk/rancher-private-registry-workshop/blob/main/docs/Exercise-03A-InstallOPA.md)
