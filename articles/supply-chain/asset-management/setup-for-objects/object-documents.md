---
title: Tillgångsdokument
description: I det här avsnittet beskrivs tillgångsdokument i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5b791fd3e060c4f4ecdb1ca599a6041d421db74
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024550"
---
# <a name="asset-documents"></a><span data-ttu-id="4faed-103">Tillgångsdokument</span><span class="sxs-lookup"><span data-stu-id="4faed-103">Asset documents</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="4faed-104">I det här avsnittet beskrivs tillgångsdokument i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="4faed-104">This topic explains asset documents in Asset Management.</span></span>

<span data-ttu-id="4faed-105">I tillgångshantering kan du ställa in dokument så att de automatiskt är relaterade till jobbtyper, tillgångstillverkare, tillgångstyper eller tillgångar, till exempel.</span><span class="sxs-lookup"><span data-stu-id="4faed-105">In Asset Management, you can set up documents so that they are automatically related to job types, asset manufacturers, asset types, or assets, for example.</span></span> <span data-ttu-id="4faed-106">Den här funktionen är användbar när uppdaterade dokumentversioner släpps.</span><span class="sxs-lookup"><span data-stu-id="4faed-106">This functionality is useful when updated document versions are released.</span></span> <span data-ttu-id="4faed-107">I så fall behöver du bara placera det uppdaterade dokumentet på standardplatsen som du använder för Finance and Operations-dokumenten och bifoga dokumentet till den tillgångsdokumentpost som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="4faed-107">In that case, you just have to put the updated document in the standard location that you use for your Finance and Operations documents, and attach the document to the asset document record that you've created.</span></span> <span data-ttu-id="4faed-108">Det uppdaterade dokumentet kan sedan nås från menyalternativen **alla tillgångar**, **aktiva tillgångar**, **mina aktiva tillgångar**, **alla arbetsorder** och **aktiva arbetsorderjobb**.</span><span class="sxs-lookup"><span data-stu-id="4faed-108">The updated document can then be accessed from the **All assets**, **Active assets**, **My active assets**, **All work orders**, and **Active work order jobs** menu items.</span></span> <span data-ttu-id="4faed-109">Processen för att bifoga dokument till en tillgångsdokumentpost använder hanteringssystemet för standarddokument.</span><span class="sxs-lookup"><span data-stu-id="4faed-109">The process for attaching documents to an asset document record uses the standard document handling system.</span></span>

<span data-ttu-id="4faed-110">**Exempel 1:** ett dokument som är relaterat till en jobbtyp kan beskriva en procedur för den jobbtypen.</span><span class="sxs-lookup"><span data-stu-id="4faed-110">**Example 1:** A document that is related to a job type might describe a procedure for that job type.</span></span>

<span data-ttu-id="4faed-111">**Exempel 2:** ett dokument som är relaterat till en kombination av en tillgångstyp, tillverkare och modell kan vara standardhandboken för den valda modellen för tillgångstillverkarmodell.</span><span class="sxs-lookup"><span data-stu-id="4faed-111">**Example 2:** A document that is related to a combination of an asset type, manufacturer, and model might be the standard manual for the selected asset manufacturer model.</span></span>

## <a name="create-asset-document-relation"></a><span data-ttu-id="4faed-112">Skapa relation till tillgångsdokument</span><span class="sxs-lookup"><span data-stu-id="4faed-112">Create asset document relation</span></span>

1. <span data-ttu-id="4faed-113">Välj **tillgångshantering** \> **inställningar** \> **tillgångsdokumenet**.</span><span class="sxs-lookup"><span data-stu-id="4faed-113">Select **Asset management** \> **Setup** \> **Asset documents**.</span></span>
2. <span data-ttu-id="4faed-114">Välj **ny** om du vill skapa en tillgångsdokumentpost.</span><span class="sxs-lookup"><span data-stu-id="4faed-114">Select **New** to create an asset document record.</span></span>
3. <span data-ttu-id="4faed-115">Beroende på hur specifik du vill att dokumentrelationen ska vara, gör du relevanta val i ett eller flera av följande fält: **tillgångstyp**, **tillverkare**, **modell**, **tillgång**, **jobbtypkategori**, **Jobbtyp**, **Jobbtypvariant** och **jobbkrav**.</span><span class="sxs-lookup"><span data-stu-id="4faed-115">Depending on how specific you want the document relation to be, make relevant selections in one or more of the following fields: **Asset type**, **Manufacturer**, **Model**, **Asset**, **Job type category**, **Job type**, **Job type variant**, and **Job requirement**.</span></span> <span data-ttu-id="4faed-116">Alternativen som är tillgängliga i fälten **jobbtypvariant** och **jobbehov** beror på ditt val i fältet **jobbtyp**.</span><span class="sxs-lookup"><span data-stu-id="4faed-116">The options that are available in the **Job type variant** and **Job requirement** fields depend on your selection in the **Job type** field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4faed-117">När systemet söker efter dokument som ska relateras till en tillgång eller en arbetsorder går tillgångshanteraren igenom alla tillgångsdokumentposter för att kontrollera om det finns en möjlig matchning.</span><span class="sxs-lookup"><span data-stu-id="4faed-117">When the system searches for documents that should be related to an asset or a work order, Asset Management goes through all asset document records to check for a possible match.</span></span> <span data-ttu-id="4faed-118">Den kontrollerar alltid den mest specifika kombinationen först.</span><span class="sxs-lookup"><span data-stu-id="4faed-118">It always checks the most specific combination first.</span></span> <span data-ttu-id="4faed-119">Med andra ord söker tillgångshantering först efter en matchning för fältet **jobbehov**.</span><span class="sxs-lookup"><span data-stu-id="4faed-119">In other words, Asset Management first checks for a match for the **Job requirement** field.</span></span> <span data-ttu-id="4faed-120">Om ingen matchning hittas söker den efter en matchning för fältet **jobbtypvariant** och så vidare.</span><span class="sxs-lookup"><span data-stu-id="4faed-120">If no match is found, it checks for a match for the **Job type variant** field.</span></span> <span data-ttu-id="4faed-121">Om ingen matchning hittas söker den efter en matchning för fältet **jobbtyp** och så vidare.</span><span class="sxs-lookup"><span data-stu-id="4faed-121">If no match is found, it checks for a match for the **Job type** field, and so on.</span></span> <span data-ttu-id="4faed-122">Som du kan se i layouten på sidan **tillgångsdokument** innebär detta att, för att hitta den mest specifika kombinationen, kontrollerar tillgångshantering varje post från höger till vänster för en matchning.</span><span class="sxs-lookup"><span data-stu-id="4faed-122">As you can see in the layout of the **Asset documents** page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match.</span></span> <span data-ttu-id="4faed-123">Flera dokument kan vara relaterade till en tillgång eller en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="4faed-123">Several documents might be related to an asset or a work order.</span></span> <span data-ttu-id="4faed-124">Du kan redigera servicenivån på en underhållsbegäran eller en arbetsorder som du behöver.</span><span class="sxs-lookup"><span data-stu-id="4faed-124">You can edit the service level on a maintenance request or a work order as you require.</span></span>

4. <span data-ttu-id="4faed-125">Välj **bilagor**.</span><span class="sxs-lookup"><span data-stu-id="4faed-125">Select **Attachments**.</span></span> <span data-ttu-id="4faed-126">Standardsidan **dokumenthantering** visas.</span><span class="sxs-lookup"><span data-stu-id="4faed-126">The standard **Document handling** page appears.</span></span>
5. <span data-ttu-id="4faed-127">Ställ in de dokument eller noteringar som ska kopplas till tillgångsdokumentposten.</span><span class="sxs-lookup"><span data-stu-id="4faed-127">Set up the documents or notes that should be attached to the asset document record.</span></span> <span data-ttu-id="4faed-128">När du bifogar dokument visar fältet **bilagor** antalet dokument som är relaterade till posten.</span><span class="sxs-lookup"><span data-stu-id="4faed-128">After you attach documents, the **Attachments** field shows the number of documents that are related to the record.</span></span>
