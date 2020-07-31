# aws-service-catalog-playground

learn [aws service catalog](https://aws.amazon.com/servicecatalog/)


**Concepts**

* products are cloudformation templates
* portfolio is collection of products
    * access to portfolios is via IAM users, groups, roles
* IT administrator creates products and portfolios and grants access
* End user accesses products and deploys them
* example use cases: approved self-service products from Solution Factory
    * e.g. static web site. S3 + CloudFormation + WAF + ACM (certificate) + Route 53 (hosted zone, domain)
    * e.g. Oracle RDS DB with all security, tags, etc. in place
* can include/reference existing product(s) in your product cloudformation template.  This *enables modular composition and nesting*.

---

## Example Use Case | Static Website

The following is a simple example of a "Static Website" product for the service catalog.  It's an S3 bucket with website enabled for it.  This product is purposely kept simple to keep the focus on Service Catalog, but a product can be make up of anything that can be expressed via a [CloudFormation](https://aws.amazon.com/cloudformation/) template.

---

**Define Launch Constraint**

the IAM role the cloudformation stack provisioning runs under

> Allows you to assign an IAM role that is used to provision the resources at launch, so you can restrict user permissions without impacting users' ability to provision products from the catalog.

Launch constraint for a product must be added at Portfolio level

see [AWS Service Catalog Launch Constraints](https://docs.aws.amazon.com/servicecatalog/latest/adminguide/constraints-launch.html)

![](https://www.evernote.com/l/AAEuQZJz9txN57hBHQ_YjHxkmMy2PKfk_n4B/image.png)

![](https://www.evernote.com/l/AAGWKIl7gwBBZZp0e3tVRncOU8Nr43Ejk1QB/image.png)

Assign Users, Groups, Roles for Portfolio

![](https://www.evernote.com/l/AAEmfWaG4XFBpZg1lD01vTdLzcfPJJhD1PkB/image.png)

End User Provisioning

![](https://www.evernote.com/l/AAGZ53tBPRhKtKih91cNdEkPVfbzy8ZvAuwB/image.png)

![](https://www.evernote.com/l/AAFPNtkC3RtNQKvtClfk9DtbTJDK7vGZwNkB/image.png)

Constraint Types

![](https://www.evernote.com/l/AAFEX2cQG6JMjoqo43FvVusSVzyc6IJx0bAB/image.png)

Template constraints allow you to limit/constrain CloudFormation template parameters. see [AWS Service Catalog Template Constraints](https://docs.aws.amazon.com/servicecatalog/latest/adminguide/catalogs_constraints_template-constraints.html)

![](https://www.evernote.com/l/AAEKZRBwiMFGkazlL5DplxIRoAHEyypLAWAB/image.png)

CloudFormation Outputs

![](https://www.evernote.com/l/AAEIVmNsWvVOd7g9Owq5hE5-EY8jiBrVrD0B/image.png)

End User Provisioned Products List

![](https://www.evernote.com/l/AAHRU3p5liNGU5H0sG5nf7NGLKBeFQi-jHkB/image.png)

Admin add new product version

![](https://www.evernote.com/l/AAF1Sxv2QSlHOJ30uexkIEq9o6qy-euT8AwB/image.png)

End user Update Provisioned Product

![](https://www.evernote.com/l/AAHeS278JfpGTqEKD6sgC8qloUdbSEja6Y8B/image.png)

End user view Resource changes

![](https://www.evernote.com/l/AAHerkaUhrJIIL0cCZpn2JgwDL4gJNaicVkB/image.png)

End user provisioning update

![](https://www.evernote.com/l/AAFGpxwfjU1Dh6IdXzZzryFP7zT0yGAMxw4B/image.png)

S3 static website hosting routing rules added (the update)

![](https://www.evernote.com/l/AAEnMMkQ431GiIqAI50H-BAeO4oSneboKTQB/image.png)

"Backing" CloudFormation Stack Details

![](https://www.evernote.com/l/AAGr49-QQOBJE6I-V_E5_ohqBxvXwhOCql4B/image.png)

## Resources

* [AWS Service Catalog Documentation](https://docs.aws.amazon.com/servicecatalog/index.html)
* [aws-samples/aws-service-catalog-reference-architectures](https://github.com/aws-samples/aws-service-catalog-reference-architectures)
* [AWS Service Catalog - Getting Started](https://www.youtube.com/watch?v=A9kKy6WhqVA&t=318s)
* [AWS re:Invent 2018: Streamlining Application Development with AWS Service Catalog (DEV328)](https://www.youtube.com/watch?v=jvAAiWxYQwg)
* [AWS CloudFormation support for AWS Service Catalog products](https://aws.amazon.com/blogs/mt/how-to-launch-secure-and-governed-aws-resources-with-aws-cloudformation-and-aws-service-catalog/)