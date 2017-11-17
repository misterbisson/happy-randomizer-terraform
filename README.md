# happy-randomizer-terraform

This repository is an extension of the [Happy Randomizer](https://github.com/heyawhite/happy-randomizer), to deploy the application on [Triton](https://www.joyent.com/triton/compute) with [Terraform](https://www.terraform.io/intro/index.html).

## Prerequisites

1. Sign up for a [Triton account](https://lpage.joyent.com/Triton-Free-Trial.html). 
1. Create the Happy Randomizer images. The Packer configuration file is [already included in the GitHub repo](https://github.com/heyawhite/happy-randomizer/blob/master/happy-image.json) and if unmodified, it will create an image named `happy_randomizer` version 1.0.0.
   + Read more instructions on how to [create images with Packer](https://www.joyent.com/blog/create-images-with-packer), you're in luck. 
   + You'll need version 1.0 and version 1.1 of the Happy Randomizer. Details are in the repository's README.
1. Once the images have been deployed, fork this repository.
   + The files refer to the images already deployed to Triton and do not require the local application.

## Modifying the variables

Replace the following variables with your information:

```hcl
variable "triton_account" {
    default = "<username>"
}

variable "triton_key_id" {
    default = "<fingerprint>"
}

variable "dc_name" {
    default = "<dc_name>"
}
```

## Additional resources

+ [Triton Terraform provider docs](https://github.com/terraform-providers/terraform-provider-triton)
+ [Triton CLI and CloudAPI](https://docs.joyent.com/public-cloud/api-access/cloudapi)
