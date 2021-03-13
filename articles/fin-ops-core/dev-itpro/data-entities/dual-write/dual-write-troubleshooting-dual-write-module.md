---
title: Felsöka problem med dubbelriktad skrivning i Finance and Operations-appar
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 3ffeb2de0acc1761bccf62a1a124852c504e2a3a
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "5131255"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a><span data-ttu-id="1c23c-103">Felsöka problem med dubbelriktad skrivning i Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="1c23c-103">Troubleshoot dual-write issues in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="1c23c-104">Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1c23c-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="1c23c-105">Det ger särskilt information som kan hjälpa dig att åtgärda problem med **dubbelriktad skrivning** i Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="1c23c-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c23c-106">Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="1c23c-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="1c23c-107">I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.</span><span class="sxs-lookup"><span data-stu-id="1c23c-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="1c23c-108">Du kan inte läsa in modulen för dubbelriktad skrivning i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="1c23c-108">You can't load the dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="1c23c-109">Om du inte kan öppna sidan **dubbelriktad skrivning** genom att välja panelen **dubbelriktad skrivning** i arbetsytan **datahantering** är dataintegrationstjänsten förmodligen nere.</span><span class="sxs-lookup"><span data-stu-id="1c23c-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="1c23c-110">Skapa en supportbiljett för att begära en omstart av dataintegrationstjänsten.</span><span class="sxs-lookup"><span data-stu-id="1c23c-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-table-map"></a><span data-ttu-id="1c23c-111">Fel vid försök att skapa en ny tabellmappning</span><span class="sxs-lookup"><span data-stu-id="1c23c-111">Error when you try to create a new table map</span></span>

<span data-ttu-id="1c23c-112">**Nödvändiga autentiseringsuppgifter för att åtgärda problemet:** Samma användare som ställer in dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="1c23c-112">**Required credentials to fix the issue:** The same user that setup dual-write.</span></span>

<span data-ttu-id="1c23c-113">Följande felmeddelande kan visas när du försöker konfigurera en ny tabell för dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="1c23c-113">You might receive the following error message when you try to configure a new table for dual-write.</span></span> <span data-ttu-id="1c23c-114">Den enda användare som kan skapa en karta är den användare som ställer in anslutningen med dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="1c23c-114">The only user that can create a map is the user who setup the dual-write connection.</span></span>

<span data-ttu-id="1c23c-115">*Svarsstatuskoden anger inte lyckad: 401 (otillåtet)*</span><span class="sxs-lookup"><span data-stu-id="1c23c-115">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>


## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="1c23c-116">Fel vid öppning av användargränssnittet med dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="1c23c-116">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="1c23c-117">Följande felmeddelande kan visas när du försöker komma åt dubbelriktad skrivning från arbetsytan **Datahantering**:</span><span class="sxs-lookup"><span data-stu-id="1c23c-117">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="1c23c-118">*login.microsoftonline.com vägrade att ansluta.*</span><span class="sxs-lookup"><span data-stu-id="1c23c-118">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="1c23c-119">Om du vill åtgärda problemet loggar du in på ett InPrivate-fönster i Microsoft Edge, ett inkognitofönster i Chromium eller ett inkognitofönster i Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="1c23c-119">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="1c23c-120">Du måste också häva blockeringen eller rensa cookies från tredje part.</span><span class="sxs-lookup"><span data-stu-id="1c23c-120">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a><span data-ttu-id="1c23c-121">Fel vid länkning av miljön för dubbelriktad skrivning eller tillägg av en ny tabellmappning</span><span class="sxs-lookup"><span data-stu-id="1c23c-121">Error when you link the environment for dual-write or add a new table mapping</span></span>

<span data-ttu-id="1c23c-122">**Den roll som krävs för att åtgärda problemet:** Systemadministratören i båda Finance and Operations-appar och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1c23c-122">**Required role to fix the issue:** System administrator in both Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="1c23c-123">Du kan stöta på följande fel när du länkar eller skapar kartor:</span><span class="sxs-lookup"><span data-stu-id="1c23c-123">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="1c23c-124">*Svarsstatuskoden anger inte lyckad: 403 (tokenexchange).<br> Session s-ID: \<your session id\><br> Rotaktivitets-ID: \<your root activity id\>*</span><span class="sxs-lookup"><span data-stu-id="1c23c-124">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="1c23c-125">Det här felet kan uppstå om du inte har tillräcklig behörighet för att länka dubbelriktad skrivning eller skapa kartor.</span><span class="sxs-lookup"><span data-stu-id="1c23c-125">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="1c23c-126">Det här felet kan också uppstå om Dataverse-miljön återställdes utan att dubbelriktig skrivning avlänkas.</span><span class="sxs-lookup"><span data-stu-id="1c23c-126">This error can also occur if the Dataverse environment was reset without unlinking dual-write.</span></span> <span data-ttu-id="1c23c-127">Alla användare med rollen systemadministratör i båda Finance and Operations-apparna och Dataverse kan länka dessa miljöer.</span><span class="sxs-lookup"><span data-stu-id="1c23c-127">Any user with system administrator role in both Finance and Operations apps and Dataverse can link the environments.</span></span> <span data-ttu-id="1c23c-128">Det är bara användaren som installerar anslutningen för dubbelriktad skrivning som kan lägga till nya tabellmappningar.</span><span class="sxs-lookup"><span data-stu-id="1c23c-128">Only the user who setup the dual-write connection can add new table maps.</span></span> <span data-ttu-id="1c23c-129">Efter installationen kan alla användare med rollen systemadministratör övervaka status och redigera mappningarna.</span><span class="sxs-lookup"><span data-stu-id="1c23c-129">After setup, any user with system administrator role can monitor the status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-table-mapping"></a><span data-ttu-id="1c23c-130">Fel när du stoppar tabellmappningen</span><span class="sxs-lookup"><span data-stu-id="1c23c-130">Error when you stop the table mapping</span></span>

<span data-ttu-id="1c23c-131">Följande felmeddelande kan visas när du försöker att stoppa tabellmappningen:</span><span class="sxs-lookup"><span data-stu-id="1c23c-131">You might receive the following error message when you try to stop the table mappings:</span></span>

<span data-ttu-id="1c23c-132">*\[Förbjudet\], \[{"status":403,"source":"","message":"Fel från token exchange: Användaren har inte rätt att komma åt anslutning dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Fjärrservern returnerade ett fel: (403) Förbjudet.*</span><span class="sxs-lookup"><span data-stu-id="1c23c-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="1c23c-133">Det här felet uppstår när den länkade Dataverse-miljön inte är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="1c23c-133">This error occurs when the linked Dataverse environment isn't available.</span></span>

<span data-ttu-id="1c23c-134">Lös problemet genom att skapa en biljett till dataintegrationsteamet.</span><span class="sxs-lookup"><span data-stu-id="1c23c-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="1c23c-135">Koppla nätverksspårningen så att dataintegrationsteamet kan markera kartorna som **Inte körs** i servern.</span><span class="sxs-lookup"><span data-stu-id="1c23c-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>

## <a name="error-while-trying-to-start-a-table-mapping"></a><span data-ttu-id="1c23c-136">Fel vid försök att starta en tabellmappning</span><span class="sxs-lookup"><span data-stu-id="1c23c-136">Error while trying to start a table mapping</span></span>

<span data-ttu-id="1c23c-137">Du kan få ett felmeddelande som följande när du försöker ange status för en mappning som ska **köras**:</span><span class="sxs-lookup"><span data-stu-id="1c23c-137">You might receive an error like the following when you try to set that state of a mapping to **Running**:</span></span>

<span data-ttu-id="1c23c-138">*Det gick inte att slutföra inledande datasynkronisering. Fel: del i dubbelriktad skrivning - registrering av plugin-program misslyckades: Det gick inte att skapa metadata för sökning för dubbelriktad skrivning.*</span><span class="sxs-lookup"><span data-stu-id="1c23c-138">*Unable to complete initial data sync. Error: dual-write failure - plugin registration failed: Unable to build dual-write lookup metadata. Error object reference not set to an instance of an object.*</span></span>

<span data-ttu-id="1c23c-139">Korrigeringen för det här felet beror på orsaken till felet:</span><span class="sxs-lookup"><span data-stu-id="1c23c-139">The fix for this error depends on the cause of the error:</span></span>

+ <span data-ttu-id="1c23c-140">Om mappningen har beroende mappningar ska du se till att aktivera de beroende mappningarna för den här tabellmappningen.</span><span class="sxs-lookup"><span data-stu-id="1c23c-140">If the mapping has dependent mappings, then make sure to enable the dependent mappings of this table mapping.</span></span>
+ <span data-ttu-id="1c23c-141">Mappningen kanske saknar käll- eller målkolumner.</span><span class="sxs-lookup"><span data-stu-id="1c23c-141">The mapping might be missing source or destination columns.</span></span> <span data-ttu-id="1c23c-142">Om en kolumn i Finance and Operations-appen saknas följer du stegen i avsnittet [Tabellkolumner som saknas problem i kartor](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps).</span><span class="sxs-lookup"><span data-stu-id="1c23c-142">If a column in the Finance and Operations app is missing, then follow the steps in the section [Missing table columns issue on maps](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps).</span></span> <span data-ttu-id="1c23c-143">Om en kolumn i Dataverse saknas klickar du på knappen **Uppdatera tabeller** på mappningen så att kolumnerna automatiskt fylls i igen i mappningen.</span><span class="sxs-lookup"><span data-stu-id="1c23c-143">If a column in Dataverse is missing, then click **Refresh tables** button on the mapping so that the columns are automatically populated back into the mapping.</span></span>
