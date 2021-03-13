---
title: Arkivera ER-målstyp
description: Det här ämnet innehåller information om hur du konfigurerar en arkivdestination för varje MAPP- eller FIL-komponent i ett ER-format (elektronisk rapportering).
author: NickSelin
manager: AnnBe
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0067024d7a29e2a1db3b7fdba9ea3c6a63aad648
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094139"
---
# <a name="archive-er-destination-type"></a><span data-ttu-id="3bf14-103">Arkivera ER-målstyp</span><span class="sxs-lookup"><span data-stu-id="3bf14-103">Archive ER destination type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3bf14-104">Du kan konfigurera en arkivdestination för varje **Mapp**- eller **Fil**-komponent i ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument.</span><span class="sxs-lookup"><span data-stu-id="3bf14-104">You can configure an archive destination for each **Folder** or **File** component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="3bf14-105">Baserat på destinationsinställningen lagras ett genererat dokument som en bilaga till en post i ER-jobblistan.</span><span class="sxs-lookup"><span data-stu-id="3bf14-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span> <span data-ttu-id="3bf14-106">Visa resultaten genom att gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Arkiverade elektroniska rapporteringsjobb**.</span><span class="sxs-lookup"><span data-stu-id="3bf14-106">To view the results, go to **Organization administration** \> **Electronic reporting** \> **Electronic reporting jobs**.</span></span>

<span data-ttu-id="3bf14-107">Du kan använda detta alternativ för att skicka de genererade dokumentet till en Microsoft SharePoint-mapp eller till Microsoft Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="3bf14-107">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="3bf14-108">Ställ in **Aktiverad** till **Ja** för att skicka utdata till en mål som definierats av den valda dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="3bf14-108">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="3bf14-109">Endast dokumenttyper där gruppen är inställd på **Fil** kan väljas.</span><span class="sxs-lookup"><span data-stu-id="3bf14-109">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="3bf14-110">Du kan ange dokument [typer](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) på **Organisationsadministration** \> **Dokumenthantering** \> **Dokumenttyper**.</span><span class="sxs-lookup"><span data-stu-id="3bf14-110">You define document [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="3bf14-111">Konfigurationen för ER-mål är samma som konfigurationen för dokumenthanteringssystemet.</span><span class="sxs-lookup"><span data-stu-id="3bf14-111">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="3bf14-112">[![Sida för dokumenttyper](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="3bf14-112">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="3bf14-113">Platsen avgör var filen sparas.</span><span class="sxs-lookup"><span data-stu-id="3bf14-113">The location determines where the file is saved.</span></span> <span data-ttu-id="3bf14-114">När målen **Arkiv** har aktiverats kan resultaten sparas i jobbarkivet.</span><span class="sxs-lookup"><span data-stu-id="3bf14-114">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="3bf14-115">Du kan visa resultaten via **Organisationsadministration** \> **Elektronisk rapportering** \> **Arkiverade elektroniska rapporteringsjobb**.</span><span class="sxs-lookup"><span data-stu-id="3bf14-115">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="3bf14-116">Välj en dokumenttyp för jobbarkivet genom att navigera till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering** \> **Parametrar för elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="3bf14-116">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="3bf14-117">Mer information finns i [Konfigurera ramverket för elektronisk rapportering (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="3bf14-117">For more information, see [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="3bf14-118">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3bf14-118">SharePoint</span></span>

<span data-ttu-id="3bf14-119">Du kan spara en fil i en viss SharePoint-mapp.</span><span class="sxs-lookup"><span data-stu-id="3bf14-119">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="3bf14-120">Du definierar standard SharePoint-server via **Organisationsadministration** \> **Dokumenthantering** \> **Dokumenthanteringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="3bf14-120">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="3bf14-121">På fliken **SharePoint**, konfigurera SharePoint-mappen.</span><span class="sxs-lookup"><span data-stu-id="3bf14-121">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="3bf14-122">Sedan kan du välja den mapp där ER-utdata ska sparas.</span><span class="sxs-lookup"><span data-stu-id="3bf14-122">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="3bf14-123">**SharePoint**-platsen måste väljas i dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="3bf14-123">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="3bf14-124">[![Markera SharePoint-mappen](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="3bf14-124">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="3bf14-125">Azure Storage</span><span class="sxs-lookup"><span data-stu-id="3bf14-125">Azure Storage</span></span>

<span data-ttu-id="3bf14-126">När dokumenttypens plats är inställd på **Azure Storage** kan du spara en fil i Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="3bf14-126">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

> [!NOTE] 
> <span data-ttu-id="3bf14-127">I ER-ramverket lagras filer permanent i Azure blobminne till skillnad från ramverket för datahantering som tillämpar den bevarande principen om sju dagar för dokument som måste bearbetas.</span><span class="sxs-lookup"><span data-stu-id="3bf14-127">The ER framework permanently stores files in Azure Blob storage unlike the Data management framework that applies the seven-day retention policy for documents that must be processed.</span></span> <span data-ttu-id="3bf14-128">Mer information finns i [API för att hämta meddelandestatus](../data-entities/recurring-integrations.md#api-for-getting-message-status) och [Statuskontroll-API](../data-entities/data-management-api.md#status-check-api).</span><span class="sxs-lookup"><span data-stu-id="3bf14-128">For more information, see [API for getting message status](../data-entities/recurring-integrations.md#api-for-getting-message-status) and [Status check API](../data-entities/data-management-api.md#status-check-api).</span></span> <span data-ttu-id="3bf14-129">De ER-relaterade filerna lagras i Azure blobminne som bilagor till programtabellposter så länge det behövs.</span><span class="sxs-lookup"><span data-stu-id="3bf14-129">The ER-related files will be stored in Azure Blob storage as attachments of application table records as long as necessary.</span></span> <span data-ttu-id="3bf14-130">En enda fil raderas från Azure blobminne tillsammans med den programtabellpost som filen var kopplad till.</span><span class="sxs-lookup"><span data-stu-id="3bf14-130">A single file will be deleted from Azure Blob storage along with the application table record that this file was attached to.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3bf14-131">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3bf14-131">Additional resources</span></span>

- [<span data-ttu-id="3bf14-132">Översikt över elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="3bf14-132">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="3bf14-133">Destinationer för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="3bf14-133">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="3bf14-134">Konfigurera dokumenthantering</span><span class="sxs-lookup"><span data-stu-id="3bf14-134">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)
