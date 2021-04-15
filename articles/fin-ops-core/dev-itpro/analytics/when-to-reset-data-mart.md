---
title: När du ska återställa en data mart
description: Det här avsnittet innehåller en lista med de omständigheter som kan förbättras genom att du återställer data och omständigheter där det är viktigt att återställa data.
author: jinniew
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: c88994a336528650bf8ab6e239c873fa6cd36c46
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754154"
---
# <a name="when-to-reset-a-data-mart"></a><span data-ttu-id="7cd20-103">När du ska återställa en data mart</span><span class="sxs-lookup"><span data-stu-id="7cd20-103">When to reset a data mart</span></span>

<span data-ttu-id="7cd20-104">Det kan ta lång tid att återställa data mart.</span><span class="sxs-lookup"><span data-stu-id="7cd20-104">Resetting a data mart can be time consuming.</span></span> <span data-ttu-id="7cd20-105">Beroende på vilka omständigheter du behöver, är det inte alltid den här åtgärden som behövs.</span><span class="sxs-lookup"><span data-stu-id="7cd20-105">Depending on the circumstances, this action may not be the solution that's needed.</span></span> <span data-ttu-id="7cd20-106">Det här avsnittet innehåller en lista med de omständigheter som kan förbättras genom att du återställer data och omständigheter där det är viktigt att återställa data.</span><span class="sxs-lookup"><span data-stu-id="7cd20-106">This topic lists the circumstances that might be improved by resetting a data mart, as well as circumstances in which resetting your data mart is unlikely to help.</span></span>  

## <a name="when-do-you-need-to-do-a-data-mart-reset"></a><span data-ttu-id="7cd20-107">När måste du återställa data eller vill du återställa data?</span><span class="sxs-lookup"><span data-stu-id="7cd20-107">When do you need to do a data mart reset?</span></span>
<span data-ttu-id="7cd20-108">Fundera över följande frågor innan du ställer in en data mart.</span><span class="sxs-lookup"><span data-stu-id="7cd20-108">Consider the following questions before resetting a data mart.</span></span> <span data-ttu-id="7cd20-109">Om du svarar ja på en eller flera frågor kan det visa att organisationen kan ha nytta av att återställa data.</span><span class="sxs-lookup"><span data-stu-id="7cd20-109">Answering yes to one or more questions might indicate that your organization can benefit by resetting the data mart.</span></span>

- <span data-ttu-id="7cd20-110">Appdatabasen har återställts, men datatorgets databas återställdes inte.</span><span class="sxs-lookup"><span data-stu-id="7cd20-110">The application database was restored, but the data mart database was not restored.</span></span>
- <span data-ttu-id="7cd20-111">Du kan se felaktiga data för en redovisningsperiod, vilket inte är resultatet av ett problem med rapportdesignen.</span><span class="sxs-lookup"><span data-stu-id="7cd20-111">You see incorrect data for an accounting period, which isn't the result of an issue with the report design.</span></span>
- <span data-ttu-id="7cd20-112">Du ser felaktiga data under en redovisningsperiod och poster anges under Integrationsförsök på sidan **Integrationsstatus** i rapportdesigner (starta rapportdesigner och välj **Verktyg > Integrationsstatus**).</span><span class="sxs-lookup"><span data-stu-id="7cd20-112">You see incorrect data for an accounting period, and records are listed under Integration attempts on the **Integration status** page in Report Designer (start the Report Designer and select **Tools > Integration status**).</span></span>
- <span data-ttu-id="7cd20-113">Du har öppnat en supporthändelse och en supporttekniker har uppmanat dig att återställa data den som ett del av ett felsökningssteg.</span><span class="sxs-lookup"><span data-stu-id="7cd20-113">You've opened a support incident and a support engineer has instructed you to reset the data mart as part of a troubleshooting step.</span></span>
 
## <a name="when-its-not-appropriate-to-reset-a-data-mart"></a><span data-ttu-id="7cd20-114">När det inte är lämpligt att återställa en data mart?</span><span class="sxs-lookup"><span data-stu-id="7cd20-114">When it's not appropriate to reset a data mart?</span></span>
<span data-ttu-id="7cd20-115">Det finns vissa omständigheter när vi inte rekommenderar att du återställer en data mart.</span><span class="sxs-lookup"><span data-stu-id="7cd20-115">There are some circumstances when we don't recommend resetting a data mart.</span></span> <span data-ttu-id="7cd20-116">Dessa omfattar bland annat.</span><span class="sxs-lookup"><span data-stu-id="7cd20-116">These include the following.</span></span> 

- <span data-ttu-id="7cd20-117">När orsaken inte finns i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="7cd20-117">Anytime the reason isn’t listed in this topic.</span></span>
- <span data-ttu-id="7cd20-118">Du upplever prestandaproblem som är kopplade till datasynkronisering. Det hjälper inte att återställa data.</span><span class="sxs-lookup"><span data-stu-id="7cd20-118">You're experiencing performance issues that are associated with a data sync. In this circumstance, resetting the data mart probably won't help.</span></span>
- <span data-ttu-id="7cd20-119">Om du har ett återkommande återställt mönster på grund av någon av följande orsaker:</span><span class="sxs-lookup"><span data-stu-id="7cd20-119">If you have a recurring reset pattern due to any of the following reasons:</span></span> 
  - <span data-ttu-id="7cd20-120">**Saknade data** - Först måste du eliminera problem med rapportdesign och tidssynkronisering med datasynkronisering, till exempel observerar du att faktakartan inte har körts sedan saknade data publicerades.</span><span class="sxs-lookup"><span data-stu-id="7cd20-120">**Missing data** - First, eliminate report design issues and data sync timing issues, for example, you observe that the fact map hasn’t run since missing data was posted.</span></span>
  - <span data-ttu-id="7cd20-121">**Integrationstillståndet ligger kvar** - Om integrationen är långsam eller verkar liga kvar är det osannolikt att det kommer att lösa problemet att återställa data mart.</span><span class="sxs-lookup"><span data-stu-id="7cd20-121">**Stuck integration state** - If the integration is slow or seems stuck, resetting the data mart is unlikely to resolve the issue.</span></span>
  - <span data-ttu-id="7cd20-122">**Det går inte att återställa** - Om ett antal försök att slutföra en återställning har gjorts och misslyckas på grund av att data saknas rekommenderar vi att du öppnar en supporthändelse och arbetar med en supporttekniker för att analysera din situation innan du försöker återställa data igen.</span><span class="sxs-lookup"><span data-stu-id="7cd20-122">**Attempts to reset have been unsuccessful** - If a number of attempts to complete a reset have been made, and have been unsuccessful because of missing data, we recommend opening a support incident and working with a support engineer to analyze your situation before attempting to reset the data mart again.</span></span>
  - <span data-ttu-id="7cd20-123">**Föråldrade poster** - Föråldrade poster ger inte själva nödvändigtvis rätt att återställa data.</span><span class="sxs-lookup"><span data-stu-id="7cd20-123">**Stale records** - Stale records by themselves don't necessarily justify resetting the data mart.</span></span> <span data-ttu-id="7cd20-124">Om du har en stor datauppsättning kommer återställningsprocessen att ta en stund att köra, men den är särskilt effektiv för att förbättra systemet.</span><span class="sxs-lookup"><span data-stu-id="7cd20-124">If you have a large data set, the reset process will take some time to run, but is unlikely to result in improvement.</span></span>
 
## <a name="what-a-data-mart-reset-does-not-do"></a><span data-ttu-id="7cd20-125">Vad en återställd data mart inte gör</span><span class="sxs-lookup"><span data-stu-id="7cd20-125">What a data mart reset does not do</span></span>  
- <span data-ttu-id="7cd20-126">En återställning startas först när befintliga uppgifter har slutförts.</span><span class="sxs-lookup"><span data-stu-id="7cd20-126">A reset will only start when existing tasks are complete.</span></span> <span data-ttu-id="7cd20-127">På så sätt ser du till att gamla data inte infogas.</span><span class="sxs-lookup"><span data-stu-id="7cd20-127">This ensures that old data is not inserted.</span></span> <span data-ttu-id="7cd20-128">Då kanske ett meddelande visas, till exempel "Återställning av data mart kunde inte bearbetas på grund av en aktiv uppgift.</span><span class="sxs-lookup"><span data-stu-id="7cd20-128">At this point you may see a message such as, “The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="7cd20-129">Försök igen senare."</span><span class="sxs-lookup"><span data-stu-id="7cd20-129">Please try again later.”</span></span>
- <span data-ttu-id="7cd20-130">När du återställer den inaktiveras integrationsuppgifterna och all data från data mart tas bort.</span><span class="sxs-lookup"><span data-stu-id="7cd20-130">The reset will disable the integration tasks and delete all the data mart data.</span></span> <span data-ttu-id="7cd20-131">Integrationen aktiveras igen.</span><span class="sxs-lookup"><span data-stu-id="7cd20-131">The integration is re-enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="7cd20-132">Följande punkter anger två saker som du *inte* gör när du återställer data.</span><span class="sxs-lookup"><span data-stu-id="7cd20-132">The following points specify two things that resetting a data mart will *not* do.</span></span> <br>
> - <span data-ttu-id="7cd20-133">Återställningar rensar inte rapportdesigner.</span><span class="sxs-lookup"><span data-stu-id="7cd20-133">Resets do not clear report designs.</span></span> <br>
> - <span data-ttu-id="7cd20-134">När du återställer rensas inte företagsdata eller användardata om de inte har valts.</span><span class="sxs-lookup"><span data-stu-id="7cd20-134">Resets do not clear company data or user data unless selected.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]