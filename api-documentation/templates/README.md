# Templates

### **About** <a id="h_38662886431538421857939"></a>

A template is a virtual machine encapsulated into a file, making it possible to rapidly deploy new VMs.

### **Paperspace Templates \(Base Images\)** <a id="h_54358796281538421950459"></a>

Paperspace offers stock templates which include only the Operating System and Paperspace software. A list of base images can be found [here](https://support.paperspace.com/hc/en-us/articles/216595797).

![](https://support.paperspace.com/hc/article_attachments/115000813253/mceclip1.png)

### Custom Templates <a id="h_46622161111538421956755"></a>

{% hint style="danger" %}
**Note:** There are some additional steps to create a Template from a Linux VM. To create a Linux Template, please follow [these instructions](https://support.paperspace.com/hc/en-us/articles/115000098214-How-to-create-a-Template-from-a-Linux-machine).
{% endhint %}

A custom template can be created from an existing VM.  The custom template contains the entire disk image of the original VM.  Once a template has been successfully created, it appears as a custom template in the Templates tab in the console.

![](https://support.paperspace.com/hc/article_attachments/115000819174/mceclip0.png)

**Limitations:** Templates are Machine Type and Region specific. Therefore, if you create a P5000 Windows template in AMS1, that template can only be used to create more  P5000 Windows VMs in the Amsterdam data center. 

{% hint style="info" %}
**ProTip:** Check out our guides for creating [Windows](https://support.paperspace.com/hc/en-us/articles/221163168-How-to-use-machine-templates-Teams-) and [Linux](https://support.paperspace.com/hc/en-us/articles/115000098214-How-to-create-a-Template-from-a-Linux-machine) Templates.
{% endhint %}

**Custom Templates & Active Directory**  

Templates must not be AD joined.  Templates are meant to include only the base operating system and programs/settings configured as needed. When a custom template is used to provision a new machine for an AD user, it will be automatically joined to your domain.  

## **Custom Template Pricing**

Snapshot pricing is based on the size of your instance.

| **Size** | 50GB | 100GB | 250GB | 500GB | 1TB | 2TB |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **Price** | $3.50 | $6 | $11 | $17 | $24 | $42 |

