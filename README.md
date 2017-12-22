CloudFormationTemplate!
===================


 <i class="icon-cog"></i> **Deploys a Self-Signed Web Server.**

----------

 **The two part Stack uses CFT exports.**

> **<i class="icon-hdd"></i> How to use:**

> - Clone the repo.
> - Log in to AWS Console.
> - Load in S3.yaml, wait for it to complete, once done, click on **Resources** and navigate to the bucket, upload the four provided .zip files.
> - Load in ENV.yaml, wait for it to complete, once done, click on **Outputs** and navigate to the test page. 
> > - Click on <i class="icon-refresh"></i> Refresh, to view the stack events.

----------

> **<i class="icon-file"></i>Template Information:**

> - Creates a Self-Signed Web Server.
> - Does HTTP to HTTPS redirection
> - Allows for the selection of **KeyPair**, for SSH.
> - Allows for the selection of environment type, e.g. Dev, Test, Prod and Presales. 
> - Allows for the input of VPC CIDR. 
> - Allows for the input of Subnet CIDR. 
> - Allows for the selection of Application version to deploy, use the format as see in the [**App***.zip] and [**Test***.zip] files. * Specifies an integer version number.
> - Can be deployed in any region, does auto AMI selection.
> - For logs, navigate to **/var/log** and check the **cfn-init** logs.  
> - Monitoring with CloudWatch.
> - Ports open **HTTP 80**, **HTTPS 443** and **SSH 22**.
> - Creates a self sustained environment, within its own VPC.
> - Provides scale out option, via environmet selection.
> - Auto scaling group and launch configuration along with load balancing can be added to provide scale up, make sure to get a certificate from **Certificate Manager** for this to work. End to end HTTPS can be used or 443(ELB) to 80(Server) and 80(Server) to 443(ELB), can be used by configuring listeners for both HTTP 80 and HTTP 443 on ELB.
> - Provides basic testing, if it fails, the stack will be rolled back. Uses default stack deletion policies.
> - To test rollback provide 2 as the input for **APPVERSION** parameter during **ENV.yaml** stack creation.
