## *Exploring ARM Templates: Creating And Deploying Azure Web App*

### *Introduction*
ARM templates is an infrastructure as code services, ARM stands for Azure Resource Manager, which is Microsoft’s deployment and management service for Azure. You use the ARM management layer for creating, updating, and deleting Azure resources. You no longer need to click around the portal creating resources or writing scripts to deploy a resource. Instead, the template defines the resources, and the Azure ARM management layer is responsible for creating the infrastructure.

A web application (web app) is an application program that is stored on a remote server and delivered over the internet through a browser interface. web app ares designed for a wide variety of uses and users, from an organization to an individual for numerous reasons. Commonly used web applications can include webmail, online calculators or e-commerce shops. While users can only access some web apps by a specific browser, most are available no matter the browser.

### *ARM Template Components:

These components make your work easier as a developer and enable you to write your scripts. Templates use a JavaScript Object Notation (JSON) syntax that also includes advanced capabilities. Here is a blank ARM template: 

![image](https://github.com/akpatiudo/Arm-template/assets/118566096/bbdf1b27-1e0b-4706-8e97-fc7b815932e9)

The template has the following sections:

Parameters - Provide values during deployment that allow the same template to be used with different environments.

Variables - Define values that are reused in your templates. They can be constructed from parameter values.

User-defined functions - Create customized functions that simplify your template.

Resources - Specify the resources to deploy.

Outputs - Return values from the deployed resources.

DependsOn:  ARM templates require that you manually create resource dependencies. Dependencies determine the order Azure should deploy the resources. For example, if an ARM template is deploying web app and a virtual machine, the app service plan exists first before creating the virtual machine.

in this work my focuse is on the parameter.

### *Steps I Took:*

first I deleted the function and variables ARM template component

Name: within the parameter,  I named the resources for the resource (web app and app service plan) This value can be set from a parameter, or set manually. And I substituted the name in the script as shown below. Anywhere I have ‘webapp1’, it was replaced with ‘webappname and’ anywhere I have ‘appserviceplan1’ it was replaced with ‘appseviceplanname’. 

![image](https://github.com/akpatiudo/Arm-template/assets/118566096/28e1abf3-3d86-4c79-9014-72ac18833d6d)

Type: The type of resource to deploy. The <resource provider> refers to the high-level family of resources to deploy, I used *string*

ApiVersion: The API version determines what properties are available to configure on the resource. I used 2020-12-01

the parameter file was created, this house the parameters that makes the script reuseable, the value houses the name of the web app and app service plan. this can be change and the cold redeployed

### *Deploy the ARM Template*
With the ARM template ready, you can now deploy the web app to your Azure environment. it will apear like this

![image](https://github.com/akpatiudo/Arm-template/assets/118566096/bbd3733d-4ace-49f8-9b03-7f17a1f6cc54)

when you lunch the Default domain in you browser you have this:

![image](https://github.com/akpatiudo/Arm-template/assets/118566096/68221aff-931f-4980-ba69-e8599ec0b951)




