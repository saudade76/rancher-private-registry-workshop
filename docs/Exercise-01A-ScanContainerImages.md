# Lab 1 A - Scanning container image for vulnerabilities through Trivy on Harbor

In this exercise, we are login to the harbor portal and using native scanning tool Trivy for vulnarabilities. It has 2 main steps loging the harbor portal and scanning pre-loaded container image for vulnarabilities. 

# SUSE Public Repository 에서 Image 가져오고, Scan 해보는 실습

###### Usecase: With the growing awareness about supply chain security, it is important to gain visibility into the software components used in the application. Scanning container images gives insight about the known vulnarabilities and and related fixes.   

## Action 1: Scan pre-loaded container image rancher's hello-world:latest

This action will involve 5 steps from 1A.1 to 1A.5 

**Step 1A.1)** Ensure that you are logged in to the Harbor (Refer to the Step 1 of section Before We Begin). On Harbor Home page, click the `library` link on main screen under **Project Name** column. 

![](../images/Screenshot-2022-07-22-at-4.30.08-PM.png)



**Step 1A.2)** Click on link `library/rancher/hello-world` under **Name** column (This may depend on how many nested repository is been create it may be shown to you as  `library/hello-world` due to the lab setup).![Screenshot-2022-07-22-at-4.50.02-PM](../images/Screenshot-2022-07-22-at-4.50.02-PM.png)



**Step 1A.3)** Click on container image link `sha256:xxxxxxxx` under **Artifacts** column. Verify that `latest` is shown under the **Tags** column and **Vulnarabilities** column shows **`Not Scanned`** 

![](../images/Screenshot-2022-07-22-at-4.57.33-PM.png)



**1A.4)** Scroll down to the bottom at **Additions** section and click on `SCAN` under **Vulnarabilities** sub-section.

![](../images/Screenshot-2022-07-22-at-5.08.13-PM.png)



Immediately after clicking SCAN, you'll notice **Queued** indicator

![](../images/Screenshot-2022-07-22-at-6.14.49-PM.png)



And it will start Scanning. 

![](../images/Screenshot-2022-07-22-at-6.17.00-PM.png)



**1A.4)** After successful scan, a result will be shown with following details 

`Vulnerability` i.e. CVE Number, `Severity` i.e. Critical, High, Medium etc., `CVSS3` i.e. Common Vulnarability Score as per CVSS Version 3.0, `package`, `Current version`, `Fixed in version` and `Listed in CVE Allowlist` . Clicking on arrow (>) sign will provide detailed description. 

![](../images/Screenshot-2022-07-22-at-6.27.18-PM.png)

**End of Action 1**

**End of Exercise 1A**

Continue to: [Exercise 1B-Setting up Harbor as a proxy to SUSE Registry and replicating images to Harbor](https://github.com/dsohk/rancher-private-registry-workshop/blob/main/docs/Exercise-01B-SetupHarborProxySUSERegistryReplicate.md)
