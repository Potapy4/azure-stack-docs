---
title: How to install IoT Hub on Azure Stack Hub
description: Learn how to install the IoT Hub resource provider on Azure Stack Hub.
author: yiyiguo
ms.author: yiygu
ms.service: azure-stack
ms.topic: how-to
ms.date: 3/3/2020 
zone_pivot_groups: state-connected-disconnected
---

# How to install IoT Hub on Azure Stack Hub

[!INCLUDE [preview-banner](../includes/iot-hub-preview.md)]

This article shows you how to download and install the IoT Hub resource provider, making it available to offer to customers for subscription. The installation process of IoT Hub takes about 2 hours.

## Download IoT Hub

[!INCLUDE [prereqs](../includes/resource-provider-va-package-download-common.md)]

<!-- ### Connected Scenario -->
::: zone pivot="state-connected"
If your Azure Stack Hub can access the Azure Marketplace, follow the steps in this section to download and install IoT Hub and its dependencies. 

To download IoT Hub for a connected deployment, complete the following steps:

1. Sign in to Azure Stack Hub administrator portal. 
2. Select **Marketplace Management** on the left, then select **Resource providers**, then click on **+ Add from Azure**.

    [![Marketplace RP search](media/iot-hub-rp-install/marketplace-rp-add-from-azure.png)](media/iot-hub-rp-install/marketplace-rp-add-from-azure.png#lightbox)

3. Filter for "IoT Hub" if necessary, then select the **IoT Hub** package.

    [![Marketplace IoT Hub RP](../operator/media/iot-hub-rp-install/download1.png)](../operator/media/iot-hub-rp-install/download1.png#lightbox)

4. On the **IoT Hub** package page, select **Download**

    [![IoT Hub package details](../operator/media/iot-hub-rp-install/download2.png)](../operator/media/iot-hub-rp-install/download2.png#lightbox)

5. Wait for the package download to complete. The status will show **Downloading**, and can take up to 10 minutes.

    [![IoT Hub package downloading status](../operator/media/iot-hub-rp-install/download3.png)](../operator/media/iot-hub-rp-install/download3.png#lightbox)

6. Once the package is downloaded, the status will change to **Not installed** in the **Marketplace management** page.

    [![IoT Hub package downloaded not installed](../operator/media/iot-hub-rp-install/download4.png)](../operator/media/iot-hub-rp-install/download4.png#lightbox)
::: zone-end

<!-- ### Disconnected or partially connected scenario -->
::: zone pivot="state-disconnected"
[!INCLUDE [prereqs](../includes/resource-provider-va-package-download-disconnected.md)]
::: zone-end

## Install IoT Hub

1. If you haven't already, sign in to the Azure Stack Hub administrator portal, select **Marketplace Management** on the left, select **Resource providers**.
2. Click on the **IoT Hub** row, then **Start Installation**.

    [![IoT Hub RP waiting for install](../operator/media/iot-hub-rp-install/install1.png)](../operator/media/iot-hub-rp-install/install1.png#lightbox)

3. Click on **Install Prerequisites**.

    [![IoT Hub RP install prerequisites](../operator/media/iot-hub-rp-install/install2.png)](../operator/media/iot-hub-rp-install/install2.png#lightbox)

4. The status of the installation can be tracked in the notification pane. This step will take about 10 minutes.

    [![IoT Hub RP install prerequisites installing](../operator/media/iot-hub-rp-install/install3.png)](../operator/media/iot-hub-rp-install/install3.png#lightbox)

5. Wait for the installation of the prerequisites to complete. This step usually takes somewhere between 5-10 minutes depending on the environment.

    [![IoT Hub RP prepare secrets](../operator/media/iot-hub-rp-install/install4.png)](../operator/media/iot-hub-rp-install/install4.png#lightbox)

6. Click on **Add Certificates** under **Prepare Secrets**. Provide the pfx certificate created in prerequisites.

    [![IoT Hub RP prepare secrets - upload certificate](../operator/media/iot-hub-rp-install/install5.png)](../operator/media/iot-hub-rp-install/install5.png#lightbox)

7. Browse and provide the pfx that was created and the password (the input to the script)

    [![IoT Hub RP prepare secrets - pick certificate](../operator/media/iot-hub-rp-install/install6.png)](../operator/media/iot-hub-rp-install/install6.png#lightbox)

    [![IoT Hub RP prepare secrets - provide password](../operator/media/iot-hub-rp-install/install61.png)](../operator/media/iot-hub-rp-install/install61.png#lightbox)

8. Click on **Install** under **Install Resource Provider**.

    [![IoT Hub RP prepare secrets - complete](../operator/media/iot-hub-rp-install/install7.png)](../operator/media/iot-hub-rp-install/install7.png#lightbox)

9. Once the installation starts, deployment status can be found in the Marketplace or in the notification pane.

    [![IoT Hub RP install in progress](../operator/media/iot-hub-rp-install/install8.png)](../operator/media/iot-hub-rp-install/install8.png#lightbox)

10. Installation can take between 90 – 120 minutes. Wait for the installation to complete.

    [![IoT Hub RP install complete](../operator/media/iot-hub-rp-install/install91.png)](../operator/media/iot-hub-rp-install/install91.png#lightbox)

    [![Marketplace RPs - installed RPs](../operator/media/iot-hub-rp-install/install92.png)](../operator/media/iot-hub-rp-install/install92.png#lightbox)

The IoT Hub resource provider is installed successfully! To get started, complete the following steps:

1. If this is the first time you're offering a service, start with the [Offer services to users](tutorial-offer-services.md) tutorial. Then continue with the next tutorial, [Test a service offering](tutorial-test-offer.md).

2. If a subscription already exists, update the associated offer/plan to include **Microsoft.Devices** service. Go to **Plan** -> **Choose the plan to update** -> **Add Service and quota**.

3. Add **Microsoft.Devices Service** and click **Save**.

    [![Add IoT Hub service to plan](../operator/media/iot-hub-rp-install/pd2.png)](../operator/media/iot-hub-rp-install/pd2.png#lightbox)

4. You are all set! IoT Hubs can now be created.

## Next steps

To learn more about managing IoT Hub on Azure Stack Hub, see [How to manage IoT Hub on Azure Stack Hub](iot-hub-rp-manage.md). To learn how to use IoT Hub, refer to the [Azure IoT Hub documentation](/azure/iot-hub).