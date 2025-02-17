## Scenario

Service migration is a tool for easy online and offline migration from local DC to the cloud. With this tool, you can migrate OS, applications, and application data on local computer disks to Tencent Cloud Cloud Virtual Machine (CVM) or Cloud Block Storage (CBS). Offline migration includes offline instance migration and offline data migration.

## Prerequisites

Offline migration requires Cloud Object Storage (COS) support. For the currently COS-supported regions, see [COS Regions](https://intl.cloud.tencent.com/document/product/436/6224). Please ensure that you are located in one of the supported regions.

## Preparations


>- At present, service migration supports image formats of qcow2, vpc, vmdk, and raw. A compressed image format is recommended to shorten the transmission and migration.
> - The COS region to which the image is uploaded should be the same as that where the destination CVM instance is located.
> - For offline migration, the uploaded image file cannot be larger than the capacity of the destination disk. For example, if the image file is 50 GB, the destination system disk should be at least 50 GB.

- Create an image of the server that needs to be migrated as instructed in the image creation document.
 - For Windows, see [Windows Image Production](https://intl.cloud.tencent.com/document/product/213/17815).
 - For Linux, see [Linux Image Production](https://intl.cloud.tencent.com/document/product/213/17814).
- Upload the created image file to COS.
As image files are generally large in size, browser uploads are often interrupted. We recommended using the COSCMD tool to upload the image. For more information, see [COSCMD](https://intl.cloud.tencent.com/document/product/436/10976).
- Get the COS address of the uploaded image.
In the [COS Console](https://console.cloud.tencent.com/cos5/bucket), find the image file you just uploaded and view its information to get the file link.
- Prepare the destination CVM instance. [Click here to purchase >>](https://buy.cloud.tencent.com/cvm?tab=custom&step=1&regionId=8).


## Directions

### Offline Instance Migration

1. Log in to the [CVM Console](https://console.cloud.tencent.com/cvm/overview).
2. In the left sidebar, click **Service Migration** > **[Offline Instance Migration](https://console.cloud.tencent.com/csm/cvm)**, as shown below:
 ![](https://main.qcloudimg.com/raw/616cd42dda6a00f42e9b2b7bba32f2fb.png)
3. Click **Create**.
4. Prepare for instance migration, confirm that everything is good, and click **Next**.
5. Enter the migration configuration information such as task name, COS link, and destination CVM instance and click **Finish** to create the migration task, as shown below:


>- The COS file needs to be set to [public read and private write access](https://intl.cloud.tencent.com/document/product/436/13327).
> - The system disk capacity of the destination instance cannot be smaller than the uploaded image file size; otherwise, the task will fail.
> 
> ![](https://main.qcloudimg.com/raw/1a3ed96a32594c8a4607c9ecd5b3bd08.png)
4. View the progress of the migration task, as shown below:
![](https://main.qcloudimg.com/raw/2b73b44908eee0d3017d69b0d7a3e4fe.png)

### Offline Data Migration

1. Log in to the [CVM Console](https://console.cloud.tencent.com/cvm/overview).
2. In the left sidebar, click **Service Migration** > **[Offline Data Migration](https://console.cloud.tencent.com/csm/cbs?rid=1)**.
3. Click **Create**.
4. Prepare for data migration, confirm that everything is good, and click **Next**.
5. Enter the migration configuration information such as task name, COS link, and destination CVM instance and click **Finish** to create the migration task, as shown below:
> - The destination data disk capacity cannot be smaller than the uploaded image file size; otherwise, the task will fail.
>
![](https://main.qcloudimg.com/raw/6ec8c8cd4f03bcdc5d8d79efaff5be3d.png)



