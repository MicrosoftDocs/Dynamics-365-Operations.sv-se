---
title: Felsöka problem med modulen för dubbelriktad skrivning i Finance and Operations-appar
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem med dubbelriktad skrivning i Finance and Operations-appar.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 34c10e38400a72a670a93f2a72d0aa7a4aed561a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172770"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a><span data-ttu-id="6c8f9-103">Felsöka problem med modulen för dubbelriktad skrivning i Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="6c8f9-103">Troubleshoot issues with the Dual-write module in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="6c8f9-104">Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="6c8f9-105">Det ger särskilt information som kan hjälpa dig att åtgärda problem med **dubbelriktad skrivning** i Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6c8f9-106">Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="6c8f9-107">I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="6c8f9-108">Du kan inte läsa in modulen för dubbelriktad skrivning i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="6c8f9-108">You can't load the Dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="6c8f9-109">Om du inte kan öppna sidan **dubbelriktad skrivning** genom att välja panelen **dubbelriktad skrivning** i arbetsytan **datahantering** är dataintegrationstjänsten förmodligen nere.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="6c8f9-110">Skapa en supportbiljett för att begära en omstart av dataintegrationstjänsten.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-entity-mapping"></a><span data-ttu-id="6c8f9-111">Fel vid försök att skapa en ny entitetsmappning</span><span class="sxs-lookup"><span data-stu-id="6c8f9-111">Error when you try to create a new entity mapping</span></span>

<span data-ttu-id="6c8f9-112">**Nödvändiga autentiseringsuppgifter för att åtgärda problemet:** Azure AD klientadministratör</span><span class="sxs-lookup"><span data-stu-id="6c8f9-112">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="6c8f9-113">Följande felmeddelande kan visas när du försöker konfigurera en ny entitet för dubbelriktad skrivning:</span><span class="sxs-lookup"><span data-stu-id="6c8f9-113">You might receive the following error message when you try to configure a new entity for dual-write:</span></span>

<span data-ttu-id="6c8f9-114">*Svarsstatuskoden anger inte lyckad: 401 (otillåtet)*</span><span class="sxs-lookup"><span data-stu-id="6c8f9-114">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>

<span data-ttu-id="6c8f9-115">Det här felet beror på att endast en Azure AD-klientadministratör kan lägga till en ny entitetsmappning.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-115">This error occurs because only an Azure AD tenant admin can add a new entity mapping.</span></span>

<span data-ttu-id="6c8f9-116">För att åtgärda problemet loggar du in på Finance and Operations-appen som en Azure AD-administratörsklient.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-116">To fix the issue, sign in to the Finance and Operations app as an Azure AD admin tenant.</span></span> <span data-ttu-id="6c8f9-117">Du måste också gå till web.PowerApps.com och förnya anslutningen.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-117">You must also go to web.PowerApps.com and revalidate your connection.</span></span>

## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="6c8f9-118">Fel vid öppning av användargränssnittet med dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="6c8f9-118">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="6c8f9-119">Följande felmeddelande kan visas när du försöker komma åt dubbelriktad skrivning från arbetsytan **Datahantering**:</span><span class="sxs-lookup"><span data-stu-id="6c8f9-119">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="6c8f9-120">*login.microsoftonline.com vägrade att ansluta.*</span><span class="sxs-lookup"><span data-stu-id="6c8f9-120">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="6c8f9-121">Om du vill åtgärda problemet loggar du in på ett InPrivate-fönster i Microsoft Edge, ett inkognitofönster i Chromium eller ett inkognitofönster i Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-121">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="6c8f9-122">Du måste också häva blockeringen eller rensa cookies från tredje part.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-122">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a><span data-ttu-id="6c8f9-123">Fel vid länkning av miljön för dubbelriktad skrivning eller lägga till en ny entitetsmappning</span><span class="sxs-lookup"><span data-stu-id="6c8f9-123">Error when you link the environment for dual-write or add a new entity mapping</span></span>

<span data-ttu-id="6c8f9-124">**Nödvändiga autentiseringsuppgifter för att åtgärda problemet:** Azure AD klientadministratör</span><span class="sxs-lookup"><span data-stu-id="6c8f9-124">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="6c8f9-125">Du kan stöta på följande fel när du länkar eller skapar kartor:</span><span class="sxs-lookup"><span data-stu-id="6c8f9-125">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="6c8f9-126">*Svarsstatuskoden anger inte lyckad: 403 (tokenexchange).<br> Sessions-ID: \<din sessions-id\><br> rotaktivitets-ID: \<din rotaktivitets-id\>*</span><span class="sxs-lookup"><span data-stu-id="6c8f9-126">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="6c8f9-127">Det här felet kan uppstå om du inte har tillräcklig behörighet för att länka dubbelriktad skrivning eller skapa kartor.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-127">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="6c8f9-128">Du måste använda ett Azure AD-klientadministratörskonto för att länka miljöer och lägga till nya entitetsmappningar.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-128">You must use an Azure AD tenant admin account to link environments and add new entity mappings.</span></span> <span data-ttu-id="6c8f9-129">När du har konfigurerat kan du dock använda ett icke-administratörskonto för att övervaka status och redigera mappningarna.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-129">However, after setup, you can use a non-admin account to monitor status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-entity-mapping"></a><span data-ttu-id="6c8f9-130">Fel när du stoppar entitetsmappningen</span><span class="sxs-lookup"><span data-stu-id="6c8f9-130">Error when you stop the entity mapping</span></span>

<span data-ttu-id="6c8f9-131">Följande felmeddelande kan visas när du försöker att stoppa entitetsmappningen:</span><span class="sxs-lookup"><span data-stu-id="6c8f9-131">You might receive the following error message when you try to stop the entity mappings:</span></span>

<span data-ttu-id="6c8f9-132">*\[Förbjudet\], \[{"status":403,"source":"","message":"Fel från token exchange: Användaren har inte rätt att komma åt anslutning dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Fjärrservern returnerade ett fel: (403) Förbjudet.*</span><span class="sxs-lookup"><span data-stu-id="6c8f9-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="6c8f9-133">Det här felet uppstår när den länkade Common Data Service-miljön inte är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-133">This error occurs when the linked Common Data Service environment isn't available.</span></span>

<span data-ttu-id="6c8f9-134">Lös problemet genom att skapa en biljett till dataintegrationsteamet.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="6c8f9-135">Koppla nätverksspårningen så att dataintegrationsteamet kan markera kartorna som **Inte körs** i servern.</span><span class="sxs-lookup"><span data-stu-id="6c8f9-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>
