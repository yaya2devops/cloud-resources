---
title: Resources To HashiCorp Terraform
date: "2022-05-21T22:40:32.169Z"
description: Learn Infrastructure As Code and pass your certification exam
---




---

# Infrastructure As Code (IaC)

<img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1653311067910/kOfSuTBEs.png" width=500 >

As the name implies, IaC refers to **the management and provisioning of infrastructure using code rather than dealing with a graphical user interface and tapping here and there**. Although it does seem simple, a significant problem had to be resolved. <br>
For instance, setting up such a complex architecture the traditional approach can take days of configuration while using an IaC tool can save you a considerable amount of time and assist you in achieving the levels of agility required to construct a successful route.


---
## Cloud Providers IaC


<img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1653311294174/G97dVfo2r.png" width=500 >



It's important to note that each cloud provider have their own IaC tool.  <br>
These tools are useful when working with a specific cloud.<br> When a new service release is available here, for example, it may take some time before it is  accessible in an external product like Terraform.  <br>However, **Cloud Providers IaC tools can only be used within their own services.**



# Terraform
Terraform by HashiCorp is an infrastructure as code tool that allows you to provision cloud and on-premises resources in configuration files written with a coherent language called HashiCorp Configuration Language (HCL).

### Overview


<img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1653221233055/V_BUpB8lX.png" width=500 >


Say i'm working at a company "A" and my job is to carry out an Azure storage, an Amazon DynamoDB and Google Compute Enginer VM etc..<br>
Bouncing from a portal and its terminal to another is fine until Terraform comes to play.
HashiCorp's product can handle infrastructure across multiple cloud platforms.

### HashiCorp Configuration Language (HCL)
The language was designed in human-readable format and empowers declarative logic's use in more complex applications. It is JSON compatible, which means it can communicate with systems other than those in the HashiCorp products line. <br> HCL was created to have a more clearly visible and defined structure when compared with other well known configuration languages, like YAML.

```auth.tf
# Example for Authenticating with AWS
provider "aws" {
  region     = "us-west-2"
  access_key = "my-access-key"
  secret_key = "my-secret-key"
}
```

---
# Getting Started

### Install Terraform CLI
Terraform must be installed in order for your terminal to understand it. <br> 
Follow the steps outlined [here](https://learn.hashicorp.com/tutorials/terraform/install-cli).

### Lifecycle
The basic Terraform workflow consists of :
1. Write - Create infrastructure in the form of code <br>
2. Init - Initialize a working directory: ` terraform init `<br>
3. Plan - Before applying changes, preview them:` terraform plan `<br>
4. Apply - Create a replicable infrastructure: ` terraform apply  `<br>
5. Destroy - Destroy infrastructure when no longer needed: `terraform destroy` <br>

**What is a State file?** <br>
Terraform saves information about the infrastructure it creates in a terraform.tfstate file every time you run it.


### About Modules
The module is one of Terraform's Core concepts.
It is a collection of Terraform configuration files in a directory. A module can be as simple as a  single directory containing one or more .tf files.

``` .TF
.terraform/modules
├── ProdModules
│   ├── LICENSE
│   ├── main.tf
│   ├── output.tf
│   ├── variables.tf
│   ├── terraform.tfstate
│   ├── README.md
├── DevModule
│   ├── yaya.tf
│   ├── output.tf
│   ├── terraform.tfstate


```
You can find a ready-to-use modules in the [Terraform Registry](https://registry.terraform.io)


# Lab
To get started with Terraform, follow these steps:

1- Download and install Terraform: Go to the Terraform website (https://www.terraform.io/) and click on the "Download" button. Select the appropriate package for your operating system, and follow the prompts to install Terraform.

2- Set up an account with a cloud provider: In order to use Terraform, you'll need to have an account with a cloud provider such as AWS, Azure, or Google Cloud. Create an account with one of these providers and make note of your access keys, which you will use to authenticate Terraform.

3- Create a configuration file: Terraform uses configuration files written in the HashiCorp Configuration Language (HCL) to define the infrastructure you want to create. Create a new file with a `.tf` extension and use the HCL syntax to define the resources you want to create. For example, to create an EC2 instance in AWS, you might use the following configuration:


```
resource "aws_instance" "example" {
  ami           = "ami-027c0a66"
  instance_type = "t2.micro"
}
```

4- Initialize Terraform: Before you can use Terraform to create resources, you'll need to initialize it. Open a terminal, navigate to the directory where your configuration file is located, and run the following command:


```
terraform init
```

This will download and install any required plugins or modules.

5- Preview your changes: Before you create your resources, it's a good idea to preview the changes that Terraform will make. Run the following command to see a summary of the resources that will be created:


```
terraform plan
```

6- Create your resources: If the preview looks good, you can create your resources by running the following command:
```
terraform apply
```

This will create the resources defined in your configuration file.

That's it! You should now have a basic understanding of how to use Terraform to create infrastructure as code. For more information, be sure to check out the Terraform documentation.


---

# Proceed Further

### Hands-On
The best way to learn about terraform is to do it yourself.
With a hands-on approach, you'll quickly grasp the material and improve with each keystroke. <br>
[Terraform Best practices](https://www.terraform-best-practices.com) is a good option to consider along the way.

### Terraform Certification



<img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1653221441459/e2GB5lxQ6.png" width=500 >


Another way to get started is to study and take the exam. I've found this method useful since deadlines push to your limits. <br>

My first essay with PSI did not go well, but I learned a lot! Failures always teach you things that you would never learn if you only won.

[HashiCorp Certified: Terraform associate](https://www.hashicorp.com/certification/terraform-associate) is multiple choice exam that relies on a practical experience. <br>
In this case, Terraform open source [documentation](https://www.terraform.io/docs) is for everyone to learn and experiment this product with.

#### Certification Resources

- [HashiCorp Documentation](https://www.terraform.io/docs)
- [250 Practice Questions For Terraform Associate Certification](https://medium.com/bb-tutorials-and-thoughts/250-practice-questions-for-terraform-associate-certification-7a3ccebe6a1a)
- [All in one course for learning Terraform and gaining the official certification](https://www.udemy.com/course/terraform-beginner-to-advanced/)
- [Deploy Infra in the Azure Cloud using Terraform](https://www.udemy.com/course/deploy-infra-in-the-cloud-using-terraform/)
- [Andrew Brown Platform](https://www.exampro.co/terraform)
- [Bryan Krausen Practice Tests](https://www.udemy.com/course/terraform-associate-practice-exam/)



## Conclusion
Terraform is a constantly evolving, extremely useful IaC solution that can greatly improve the efficiency of our DevOps.
We've only covered the fundamentals to get you started in this article; there's a lot more to Terraform that certainly requires more attention.
