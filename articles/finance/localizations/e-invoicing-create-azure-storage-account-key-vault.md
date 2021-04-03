---
title: Skapa ett Azure Storage-konto och ett nyckelvalv
description: I det här avsnittet beskrivs hur du skapar ett Azure Storage-konto och nyckelvalv.
author: gionoder
manager: AnnBe
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 14463abe7782d786d286fcc619dee00ce85bb620
ms.sourcegitcommit: 4adc57b0e43d9627dca70762ac941762ec4934e2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/22/2021
ms.locfileid: "5479355"
---
# <a name="create-an-azure-storage-account-and-a-key-vault"></a><span data-ttu-id="d2c13-103">Skapa ett Azure Storage-konto och ett nyckelvalv</span><span class="sxs-lookup"><span data-stu-id="d2c13-103">Create an Azure storage account and a key vault</span></span>

[!include [banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="d2c13-104">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="d2c13-104">Prerequisites</span></span>

<span data-ttu-id="d2c13-105">Innan du kan slutföra stegen i det här ämnet måste du se till att följande uppgifter har slutförts:</span><span class="sxs-lookup"><span data-stu-id="d2c13-105">Before you can complete the steps in this topic, you must make sure that the following tasks have been completed:</span></span>

- <span data-ttu-id="d2c13-106">Skapa en nyckelvalvresurs i Azure.</span><span class="sxs-lookup"><span data-stu-id="d2c13-106">Create a key vault resource in Azure.</span></span> <span data-ttu-id="d2c13-107">Mer information om mått finns i [Om Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).</span><span class="sxs-lookup"><span data-stu-id="d2c13-107">For more information, see [About Azure Key Vault](https://docs.microsoft.com/azure/key-vault/general/overview).</span></span>
- <span data-ttu-id="d2c13-108">Skapa ett Azure Storage-konto (Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="d2c13-108">Create an Azure storage account (Blob storage).</span></span> <span data-ttu-id="d2c13-109">Mer information finns i [Underhålla Azure Storage-kontot](https://docs.microsoft.com/azure/storage/blobs/).</span><span class="sxs-lookup"><span data-stu-id="d2c13-109">For more information, see [Maintaining Azure Storage Account](https://docs.microsoft.com/azure/storage/blobs/).</span></span>

## <a name="overview"></a><span data-ttu-id="d2c13-110">Översikt</span><span class="sxs-lookup"><span data-stu-id="d2c13-110">Overview</span></span>

<span data-ttu-id="d2c13-111">I det här avsnittet ska du utföra två huvudsteg:</span><span class="sxs-lookup"><span data-stu-id="d2c13-111">In this topic, you will complete two main steps:</span></span>

- <span data-ttu-id="d2c13-112">Konfigurera Azure Storage-kontot för att hämta lagringskontots URI.</span><span class="sxs-lookup"><span data-stu-id="d2c13-112">Set up the Azure storage account to get the storage account URI.</span></span>
- <span data-ttu-id="d2c13-113">Ställ in nyckelvalvet för att lagra lagringskontots URI.</span><span class="sxs-lookup"><span data-stu-id="d2c13-113">Set up the key vault to store the storage account URI.</span></span>

## <a name="set-up-the-azure-storage-account-to-get-the-storage-account-uri"></a><span data-ttu-id="d2c13-114">Konfigurera Azure Storage-kontot för att hämta lagringskontots URI</span><span class="sxs-lookup"><span data-stu-id="d2c13-114">Set up the Azure storage account to get the storage account URI</span></span>

1. <span data-ttu-id="d2c13-115">Öppna det lagringskonto som du vill använda med tillägget elektroniska fakturering.</span><span class="sxs-lookup"><span data-stu-id="d2c13-115">Open the storage account that you plan to use with the Electronic invoicing add-on.</span></span>
2. <span data-ttu-id="d2c13-116">Gå till **Blob Service** \> **Behållare** och skapa en ny behållare.</span><span class="sxs-lookup"><span data-stu-id="d2c13-116">Go to **Blob service** \> **Containers**, and create a new container.</span></span>
3. <span data-ttu-id="d2c13-117">Ange ett namn på behållaren och ställ in fältet **Offentlig åtkomstnivå** på **Privat (ingen anonym åtkomst)**.</span><span class="sxs-lookup"><span data-stu-id="d2c13-117">Enter a name for the container, and set the **Public access level** field to **Private (no anonymous access)**.</span></span>
4. <span data-ttu-id="d2c13-118">Öppna behållaren och gå till **Inställningar \> Åtkomstpolicy**.</span><span class="sxs-lookup"><span data-stu-id="d2c13-118">Open the container, and go to **Settings \> Access policy**.</span></span>
5. <span data-ttu-id="d2c13-119">Välj **Lägg till policy** om du vill lägga till en lagrad åtkomstpolicy.</span><span class="sxs-lookup"><span data-stu-id="d2c13-119">Select **Add policy** to add a stored access policy.</span></span>
6. <span data-ttu-id="d2c13-120">Ange fältet **Identifierare** och **Behörigheter** efter behov.</span><span class="sxs-lookup"><span data-stu-id="d2c13-120">Set the **Identifier** and **Permissions** fields as appropriate.</span></span> <span data-ttu-id="d2c13-121">I fältet **Behörigheter** bör du välja alla behörigheter.</span><span class="sxs-lookup"><span data-stu-id="d2c13-121">In the **Permissions** field, you should select all permissions.</span></span>

    ![Bevilja behörighet för Blob Storage](media/e-Invoicing-services-create-azure-resources-grant-blob-permissions.png)

7. <span data-ttu-id="d2c13-123">Ange start- och utgångsdatum.</span><span class="sxs-lookup"><span data-stu-id="d2c13-123">Enter the start and expiry dates.</span></span> <span data-ttu-id="d2c13-124">Utgångsdatumet måste vara i framtiden.</span><span class="sxs-lookup"><span data-stu-id="d2c13-124">The expiry date should be in future.</span></span>
8. <span data-ttu-id="d2c13-125">Klicka på **OK** om du vill spara policy och spara sedan ändringarna i behållaren.</span><span class="sxs-lookup"><span data-stu-id="d2c13-125">Select **OK** to save the policy, and then save your changes to the container.</span></span>
9. <span data-ttu-id="d2c13-126">Gå tillbaka till lagringskontot och öppna **Lagringsutforskaren (förhandsversion)**.</span><span class="sxs-lookup"><span data-stu-id="d2c13-126">Return to the storage account, and open **Storage Explorer (preview)**.</span></span>
10. <span data-ttu-id="d2c13-127">Högerklicka på behållaren och välj sedan **Hämta signatur för delad åtkomst**.</span><span class="sxs-lookup"><span data-stu-id="d2c13-127">Right-click the container, and then select **Get Shared Access Signature**.</span></span>
11. <span data-ttu-id="d2c13-128">I dialogrutan **Signatur för delad åtkomst** kopiera och spara värdet **URI**.</span><span class="sxs-lookup"><span data-stu-id="d2c13-128">In the **Shared Access Signature** dialog box, copy and store the value in the **URI** field.</span></span> <span data-ttu-id="d2c13-129">Det här värdet används i nästa procedur och kallas för *Signatur för delad åtkomst URI*.</span><span class="sxs-lookup"><span data-stu-id="d2c13-129">This value will be used in the next procedure and will be referred to as the *shared access signature URI*.</span></span>

    ![Markera och kopiera URI-värdet](media/e-Invoicing-services-create-azure-resources-select-and-copy-uri.png)

## <a name="set-up-the-key-vault-to-store-the-storage-account-uri"></a><span data-ttu-id="d2c13-131">Ställ in nyckelvalvet för att lagra lagringskontots URI</span><span class="sxs-lookup"><span data-stu-id="d2c13-131">Set up the key vault to store the storage account URI</span></span>

1. <span data-ttu-id="d2c13-132">Öppna det nyckelvalv som du vill använda med tillägget elektroniska fakturering.</span><span class="sxs-lookup"><span data-stu-id="d2c13-132">Open the key vault that you intend to use with the Electronic invoicing add-on.</span></span>
2. <span data-ttu-id="d2c13-133">Gå till **Inställning** \> **Hemligheter** och välj sedan **Generera/importera** om du vill skapa en ny hemlighet.</span><span class="sxs-lookup"><span data-stu-id="d2c13-133">Go to **Settings** \> **Secrets**, and then select **Generate/Import** to create a new secret.</span></span>
3. <span data-ttu-id="d2c13-134">På sidan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="d2c13-134">On the **Create a secret** page, in the **Upload options** field, select **Manual**.</span></span>
4. <span data-ttu-id="d2c13-135">Ange namnet på hemligheten.</span><span class="sxs-lookup"><span data-stu-id="d2c13-135">Enter the name of the secret.</span></span> <span data-ttu-id="d2c13-136">Det här namnet används under installationen av tjänsten i RCS (Regulatory Configuration Service) och kommer att kallas *nyckelvalvets hemliga namn*.</span><span class="sxs-lookup"><span data-stu-id="d2c13-136">This name will be used during setup of the service in Regulatory Configuration Service (RCS) and will be referred to as the *key vault secret name*.</span></span>
5. <span data-ttu-id="d2c13-137">I fältet **Värde** markera **Signatur för delad åtkomst URI** och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="d2c13-137">In the **Value** field, select **Shared Access Signature URI**, and then select **Create**.</span></span>
6. <span data-ttu-id="d2c13-138">Ställ in åtkomstprincipen så att tillägget elektronisk fakturering på den korrekta nivån för säker åtkomst till den hemlighet som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="d2c13-138">Set up the access policy to grant the Electronic invoicing add-on the correct level of secure access to the secret you created.</span></span> <span data-ttu-id="d2c13-139">Gå till **Inställningar \> Åtkomstprinciper** och välj **Lägg till åtkomstprincip**.</span><span class="sxs-lookup"><span data-stu-id="d2c13-139">Go to **Settings \> Access policy**, and select **Add Access Policy**.</span></span>
7. <span data-ttu-id="d2c13-140">Ange de hemliga behörigheterna för åtgärderna **Hämta** och **Lista**.</span><span class="sxs-lookup"><span data-stu-id="d2c13-140">Set the secret permissions for the **Get** and **List** operations.</span></span>

    ![Bevilja tjänståtkomst](media/e-Invoicing-services-create-azure-resources-grant-service-access.png)

8. <span data-ttu-id="d2c13-142">Ange certifikatbehörigheter för åtgärderna **Hämta** och **Lista**.</span><span class="sxs-lookup"><span data-stu-id="d2c13-142">Set the certificate permissions for **Get** and **List** operations.</span></span>

    ![Bevilja certifikatbehörighet](media/e-Invoicing-services-create-azure-resources-grant-certificate-permission.png)

9. <span data-ttu-id="d2c13-144">I fältet **Välj huvudkonto**, välj **Inget valt**.</span><span class="sxs-lookup"><span data-stu-id="d2c13-144">In the **Select principal** field, select **None selected**.</span></span>
10. <span data-ttu-id="d2c13-145">I dialogrutan **Primär** välj primär genom att lägga till **Tjänst för e-fakturering**.</span><span class="sxs-lookup"><span data-stu-id="d2c13-145">In the **Principal** dialog box, select the principal by adding **e-Invoicing Service**.</span></span>
11. <span data-ttu-id="d2c13-146">Välj **Lägg till** och välj sedan **Spara ändringar i nyckelvalv**.</span><span class="sxs-lookup"><span data-stu-id="d2c13-146">Select **Add**, and then select **Save Key Vault changes**.</span></span>
12. <span data-ttu-id="d2c13-147">På sidan **Översikt** kopiera värdet **DNS-namn** för nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="d2c13-147">On the **Overview** page, copy the **DNS name** value for the key vault.</span></span> <span data-ttu-id="d2c13-148">Det här värdet kommer att användas under installationen av tjänsten i RCS och kallas *nyckelvalv-URI*.</span><span class="sxs-lookup"><span data-stu-id="d2c13-148">This value will be used during setup of the service in RCS and will be referred as the *key vault URI*.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]

