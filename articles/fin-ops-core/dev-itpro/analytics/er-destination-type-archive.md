---
title: Arkivera ER-målstyp
description: Det här ämnet ger information om hur du konfigurerar en arkivdestination för varje MAPP- eller FIL-komponent i ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8797a68507a5116c6adbf1f2d805838fa507958c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745595"
---
# <a name="archive-destination"></a><span data-ttu-id="35d15-103">Arkivmål</span><span class="sxs-lookup"><span data-stu-id="35d15-103">Archive destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="35d15-104">Du kan konfigurera en arkivdestination för varje MAPP- eller FIL-komponent i ett ER-format (elektronisk rapportering) som har konfigurerats för att generera utgående dokument.</span><span class="sxs-lookup"><span data-stu-id="35d15-104">You can configure an archive destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="35d15-105">Baserat på destinationsinställningen lagras ett genererat dokument som en bilaga till en post i ER-jobblistan.</span><span class="sxs-lookup"><span data-stu-id="35d15-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span>

<span data-ttu-id="35d15-106">Du kan använda detta alternativ för att skicka de genererade dokumentet till en Microsoft SharePoint-mapp eller till Microsoft Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="35d15-106">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="35d15-107">Ställ in **Aktiverad** till **Ja** för att skicka utdata till en mål som definierats av den valda dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="35d15-107">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="35d15-108">Endast dokumenttyper där gruppen är inställd på **Fil** kan väljas.</span><span class="sxs-lookup"><span data-stu-id="35d15-108">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="35d15-109">Du kan ange dokument [typer](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) på **Organisationsadministration** \> **Dokumenthantering** \> **Dokumenttyper**.</span><span class="sxs-lookup"><span data-stu-id="35d15-109">You define document [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="35d15-110">Konfigurationen för ER-mål är samma som konfigurationen för dokumenthanteringssystemet.</span><span class="sxs-lookup"><span data-stu-id="35d15-110">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="35d15-111">[![Sida för dokumenttyper](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="35d15-111">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="35d15-112">Platsen avgör var filen sparas.</span><span class="sxs-lookup"><span data-stu-id="35d15-112">The location determines where the file is saved.</span></span> <span data-ttu-id="35d15-113">När målen **Arkiv** har aktiverats kan resultaten sparas i jobbarkivet.</span><span class="sxs-lookup"><span data-stu-id="35d15-113">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="35d15-114">Du kan visa resultaten via **Organisationsadministration** \> **Elektronisk rapportering** \> **Arkiverade elektroniska rapporteringsjobb**.</span><span class="sxs-lookup"><span data-stu-id="35d15-114">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="35d15-115">Välj en dokumenttyp för jobbarkivet genom att navigera till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering** \> **Parametrar för elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="35d15-115">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="35d15-116">Mer information finns i [Konfigurera ramverket för elektronisk rapportering (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="35d15-116">For more information, [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="35d15-117">SharePoint</span><span class="sxs-lookup"><span data-stu-id="35d15-117">SharePoint</span></span>

<span data-ttu-id="35d15-118">Du kan spara en fil i en viss SharePoint-mapp.</span><span class="sxs-lookup"><span data-stu-id="35d15-118">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="35d15-119">Du definierar standard SharePoint-server via **Organisationsadministration** \> **Dokumenthantering** \> **Dokumenthanteringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="35d15-119">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="35d15-120">På fliken **SharePoint**, konfigurera SharePoint-mappen.</span><span class="sxs-lookup"><span data-stu-id="35d15-120">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="35d15-121">Sedan kan du välja den mapp där ER-utdata ska sparas.</span><span class="sxs-lookup"><span data-stu-id="35d15-121">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="35d15-122">**SharePoint**-platsen måste väljas i dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="35d15-122">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="35d15-123">[![Markera SharePoint-mappen](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="35d15-123">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="35d15-124">Azure Storage</span><span class="sxs-lookup"><span data-stu-id="35d15-124">Azure Storage</span></span>

<span data-ttu-id="35d15-125">När dokumenttypens plats är inställd på **Azure Storage** kan du spara en fil i Azure Storage.</span><span class="sxs-lookup"><span data-stu-id="35d15-125">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="35d15-126">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="35d15-126">Additional resources</span></span>

- [<span data-ttu-id="35d15-127">Översikt över elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="35d15-127">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="35d15-128">Destinationer för elektronisk rapportering (ER)</span><span class="sxs-lookup"><span data-stu-id="35d15-128">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="35d15-129">Konfigurera dokumenthantering</span><span class="sxs-lookup"><span data-stu-id="35d15-129">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)
