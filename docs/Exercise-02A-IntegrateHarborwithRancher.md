# Lab 2 A - Integrate Harbor 

This exercise is independent from Exercise 1. We'll create a new secerets for Registries in Rancher. 

# // Harbor 정보 Secret 으로 저장 실습

###### Usecase: Ease of access without doubting the authenticity of container images makes oprtaions smooth and effortless. Rancher supports integration of public, private, containerd mirroring and registry authentication.  

## Action 1: Integrate Harbor

This action will involve 6 steps from 2A.1 to 2A.6

**Step 2A.1)** Ensure that you are logged in to the Rancher (Refer to the Step 1 of section **Before We Begin**). Click on downstream cluster `rke2-cluster1` from the clusters list on Rancher home page.

![Screenshot-2022-07-24-at-2.01.42-PM](../images/Screenshot-2022-07-24-at-2.01.42-PM.png)



**Step 2A.2)** Click on `Storage` from left-hand static menu. 

![Screenshot-2022-07-24-at-2.02.55-PM](../images/Screenshot-2022-07-24-at-2.02.55-PM.png)



**Step 2A.3)** Click on `Secrets` under **Storage** and then click on `Create` on the main screen.

![Screenshot-2022-07-24-at-2.05.04-PM](../images/Screenshot-2022-07-24-at-2.05.04-PM.png)



**Step 2A.4)** Click on `Registry` option. 

![Screenshot-2022-07-24-at-2.06.54-PM](../images/Screenshot-2022-07-24-at-2.06.54-PM.png)



**Step 2A.5)** Fill in following details and click on `Create`. 

`Namespace : default`

`Name : User's choice e.g. harbor-registry`

`Data : Custom (Default choice)`

`Registry Domain Name : Harbor URL i.e. https://harbor.yy.yy.yy.yy.sslip.io`

`Username : admin`

`Password : system generated strong password`

![Screenshot-2022-07-24-at-2.08.02-PM](../images/Screenshot-2022-07-24-at-2.08.02-PM.png)



**Step 2A.6)** Verify that harbor registry seceret  is successfully registered. 

![Screenshot-2022-07-24-at-2.11.17-PM](../images/Screenshot-2022-07-24-at-2.11.17-PM.png)

**End of Action 1**



**Tip:**

You may integrate private registry as default registry instead of public registry e.g. docker hub. This integration is out of scope of this workshop.  ![Screenshot-2022-07-26-at-1.27.40-PM](../images/Screenshot-2022-07-26-at-1.27.40-PM.png)

**End of Exercise 2 A**

Continue to: [Exercise 2B-Deploy sample applications from Harbor Registry onto RKE2 cluster ](https://github.com/dsohk/rancher-private-registry-workshop/blob/main/docs/Exercise-02B-DeploySampleApplication.md)
