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
ms.openlocfilehash: 853791d5ffc1d92b9fbafa2acc13cd5543c38196
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275543"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a><span data-ttu-id="3e138-103">Felsöka problem med modulen för dubbelriktad skrivning i Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="3e138-103">Troubleshoot issues with the dual-write module in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3e138-104">Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3e138-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="3e138-105">Det ger särskilt information som kan hjälpa dig att åtgärda problem med **dubbelriktad skrivning** i Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="3e138-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3e138-106">Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen.</span><span class="sxs-lookup"><span data-stu-id="3e138-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="3e138-107">I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.</span><span class="sxs-lookup"><span data-stu-id="3e138-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="3e138-108">Du kan inte läsa in modulen för dubbelriktad skrivning i en Finance and Operations-app</span><span class="sxs-lookup"><span data-stu-id="3e138-108">You can't load the dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="3e138-109">Om du inte kan öppna sidan **dubbelriktad skrivning** genom att välja panelen **dubbelriktad skrivning** i arbetsytan **datahantering** är dataintegrationstjänsten förmodligen nere.</span><span class="sxs-lookup"><span data-stu-id="3e138-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="3e138-110">Skapa en supportbiljett för att begära en omstart av dataintegrationstjänsten.</span><span class="sxs-lookup"><span data-stu-id="3e138-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-entity-map"></a><span data-ttu-id="3e138-111">Fel vid försök att skapa en ny entitetsmappning</span><span class="sxs-lookup"><span data-stu-id="3e138-111">Error when you try to create a new entity map</span></span>

<span data-ttu-id="3e138-112">**Nödvändiga autentiseringsuppgifter för att åtgärda problemet:** Samma användare som ställer in dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="3e138-112">**Required credentials to fix the issue:** The same user that setup dual-write.</span></span>

<span data-ttu-id="3e138-113">Följande felmeddelande kan visas när du försöker konfigurera en ny entitet för dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="3e138-113">You might receive the following error message when you try to configure a new entity for dual-write.</span></span> <span data-ttu-id="3e138-114">Den enda användare som kan skapa en karta är den användare som ställer in anslutningen med dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="3e138-114">The only user that can create a map is the user who setup the dual-write connection.</span></span>

<span data-ttu-id="3e138-115">*Svarsstatuskoden anger inte lyckad: 401 (otillåtet)*</span><span class="sxs-lookup"><span data-stu-id="3e138-115">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>


## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="3e138-116">Fel vid öppning av användargränssnittet med dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="3e138-116">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="3e138-117">Följande felmeddelande kan visas när du försöker komma åt dubbelriktad skrivning från arbetsytan **Datahantering**:</span><span class="sxs-lookup"><span data-stu-id="3e138-117">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="3e138-118">*login.microsoftonline.com vägrade att ansluta.*</span><span class="sxs-lookup"><span data-stu-id="3e138-118">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="3e138-119">Om du vill åtgärda problemet loggar du in på ett InPrivate-fönster i Microsoft Edge, ett inkognitofönster i Chromium eller ett inkognitofönster i Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="3e138-119">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="3e138-120">Du måste också häva blockeringen eller rensa cookies från tredje part.</span><span class="sxs-lookup"><span data-stu-id="3e138-120">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a><span data-ttu-id="3e138-121">Fel vid länkning av miljön för dubbelriktad skrivning eller lägga till en ny entitetsmappning</span><span class="sxs-lookup"><span data-stu-id="3e138-121">Error when you link the environment for dual-write or add a new entity mapping</span></span>

<span data-ttu-id="3e138-122">**Den roll som krävs för att åtgärda problemet:** Systemadministratören i båda Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3e138-122">**Required role to fix the issue:** System administrator in both Finance and Operations apps and Common Data Service.</span></span>

<span data-ttu-id="3e138-123">Du kan stöta på följande fel när du länkar eller skapar kartor:</span><span class="sxs-lookup"><span data-stu-id="3e138-123">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="3e138-124">*Svarsstatuskoden anger inte lyckad: 403 (tokenexchange).<br> Sessions-ID: \<din sessions-id\><br> rotaktivitets-ID: \<din rotaktivitets-id\>*</span><span class="sxs-lookup"><span data-stu-id="3e138-124">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="3e138-125">Det här felet kan uppstå om du inte har tillräcklig behörighet för att länka dubbelriktad skrivning eller skapa kartor.</span><span class="sxs-lookup"><span data-stu-id="3e138-125">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="3e138-126">Det här felet kan också uppstå om Common Data Service-miljön återställdes utan att dubbelriktig skrivning avlänkas.</span><span class="sxs-lookup"><span data-stu-id="3e138-126">This error can also occur if the Common Data Service environment was reset without unlinking dual-write.</span></span> <span data-ttu-id="3e138-127">Alla användare med rollen systemadministratör i båda Finance and Operations-apparna och Common Data Service kan länka dessa miljöer.</span><span class="sxs-lookup"><span data-stu-id="3e138-127">Any user with system administrator role in both Finance and Operations apps and Common Data Service can link the environments.</span></span> <span data-ttu-id="3e138-128">Det är bara användaren som installerar anslutningen för dubbelriktad skrivning som kan lägga till nya entitetsmappningar.</span><span class="sxs-lookup"><span data-stu-id="3e138-128">Only the user who setup the dual-write connection can add new entity maps.</span></span> <span data-ttu-id="3e138-129">Efter installationen kan alla användare med rollen systemadministratör övervaka status och redigera mappningarna.</span><span class="sxs-lookup"><span data-stu-id="3e138-129">After setup, any user with system administrator role can monitor the status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-entity-mapping"></a><span data-ttu-id="3e138-130">Fel när du stoppar entitetsmappningen</span><span class="sxs-lookup"><span data-stu-id="3e138-130">Error when you stop the entity mapping</span></span>

<span data-ttu-id="3e138-131">Följande felmeddelande kan visas när du försöker att stoppa entitetsmappningen:</span><span class="sxs-lookup"><span data-stu-id="3e138-131">You might receive the following error message when you try to stop the entity mappings:</span></span>

<span data-ttu-id="3e138-132">*\[Förbjudet\], \[{"status":403,"source":"","message":"Fel från token exchange: Användaren har inte rätt att komma åt anslutning dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Fjärrservern returnerade ett fel: (403) Förbjudet.*</span><span class="sxs-lookup"><span data-stu-id="3e138-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="3e138-133">Det här felet uppstår när den länkade Common Data Service-miljön inte är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="3e138-133">This error occurs when the linked Common Data Service environment isn't available.</span></span>

<span data-ttu-id="3e138-134">Lös problemet genom att skapa en biljett till dataintegrationsteamet.</span><span class="sxs-lookup"><span data-stu-id="3e138-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="3e138-135">Koppla nätverksspårningen så att dataintegrationsteamet kan markera kartorna som **Inte körs** i servern.</span><span class="sxs-lookup"><span data-stu-id="3e138-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>

## <a name="error-while-trying-to-start-an-entity-mapping"></a><span data-ttu-id="3e138-136">Fel vid försök att starta en entitetsmappningen</span><span class="sxs-lookup"><span data-stu-id="3e138-136">Error while trying to start an entity mapping</span></span>

<span data-ttu-id="3e138-137">Du kan få ett felmeddelande som följande när du försöker ange status för en mappning som ska **köras**:</span><span class="sxs-lookup"><span data-stu-id="3e138-137">You might receive an error like the following when you try to set that state of a mapping to **Running**:</span></span>

<span data-ttu-id="3e138-138">*Det gick inte att slutföra inledande datasynkronisering. Fel: del i dubbelriktad skrivning - registrering av plugin-program misslyckades: Det gick inte att skapa metadata för sökning för dubbelriktad skrivning.*</span><span class="sxs-lookup"><span data-stu-id="3e138-138">*Unable to complete initial data sync. Error: dual-write failure - plugin registration failed: Unable to build dual-write lookup metadata. Error object reference not set to an instance of an object.*</span></span>

<span data-ttu-id="3e138-139">Korrigeringen för det här felet beror på orsaken till felet:</span><span class="sxs-lookup"><span data-stu-id="3e138-139">The fix for this error depends on the cause of the error:</span></span>

+ <span data-ttu-id="3e138-140">Om mappningen har beroende mappningar ska du se till att aktivera de beroende mappningarna för den här entitetsmappningen.</span><span class="sxs-lookup"><span data-stu-id="3e138-140">If the mapping has dependent mappings, then make sure to enable the dependent mappings of this entity mapping.</span></span>
+ <span data-ttu-id="3e138-141">Mappningen kanske saknar käll- eller målfält.</span><span class="sxs-lookup"><span data-stu-id="3e138-141">The mapping might be missing source or destination fields.</span></span> <span data-ttu-id="3e138-142">Om ett fält i Finance and Operations-appen saknas följer du stegen i avsnittet [Entitetsfält som saknas problem i kartor](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps).</span><span class="sxs-lookup"><span data-stu-id="3e138-142">If a field in the Finance and Operations app is missing, then follow the steps in the section [Missing entity fields issue on maps](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps).</span></span> <span data-ttu-id="3e138-143">Om ett fält i Common Data Service saknas klickar du på knappen **Uppdatera entiteter** på mappningen så att fälten automatiskt fylls i igen i mappningen.</span><span class="sxs-lookup"><span data-stu-id="3e138-143">If a field in Common Data Service is missing, then click **Refresh entities** button on the mapping so that the fields are automatically populated back into the mapping.</span></span>
