---
title: När du ska återställa en data mart
description: Det här avsnittet innehåller en lista med de omständigheter som kan förbättras genom att du återställer data och omständigheter där det är viktigt att återställa data.
author: jinniew
ms.date: 05/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: bc2c4ee490f3bebd6e7c91609a06f8dfedfcb628
ms.sourcegitcommit: 5916ea2a94ab9af7aac21f0fc44e194d5ce82917
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2021
ms.locfileid: "5989002"
---
# <a name="when-to-reset-a-data-mart"></a><span data-ttu-id="f456c-103">När du ska återställa en data mart</span><span class="sxs-lookup"><span data-stu-id="f456c-103">When to reset a data mart</span></span>

<span data-ttu-id="f456c-104">Det kan ta lång tid att återställa data mart.</span><span class="sxs-lookup"><span data-stu-id="f456c-104">Resetting a data mart can be time consuming.</span></span> <span data-ttu-id="f456c-105">Beroende på vilka omständigheter du behöver, är det inte alltid den här åtgärden som behövs.</span><span class="sxs-lookup"><span data-stu-id="f456c-105">Depending on the circumstances, this action may not be the solution that's needed.</span></span> <span data-ttu-id="f456c-106">Det här avsnittet innehåller en lista med de omständigheter som kan förbättras genom att du återställer data och omständigheter där det är viktigt att återställa data.</span><span class="sxs-lookup"><span data-stu-id="f456c-106">This topic lists the circumstances that might be improved by resetting a data mart, as well as circumstances in which resetting your data mart is unlikely to help.</span></span>  

## <a name="when-do-i-need-to-do-a-data-mart-reset"></a><span data-ttu-id="f456c-107">När måste du återställa data eller vill du återställa data?</span><span class="sxs-lookup"><span data-stu-id="f456c-107">When do I need to do a data mart reset?</span></span>
<span data-ttu-id="f456c-108">Fundera över följande frågor innan du ställer in en data mart.</span><span class="sxs-lookup"><span data-stu-id="f456c-108">Consider the following questions before resetting a data mart.</span></span> <span data-ttu-id="f456c-109">Om du svarar ja på en eller flera frågor kan det visa att organisationen kan ha nytta av att återställa data.</span><span class="sxs-lookup"><span data-stu-id="f456c-109">Answering yes to one or more questions might indicate that your organization can benefit by resetting the data mart.</span></span>

- <span data-ttu-id="f456c-110">Återställdes programdatabasen?</span><span class="sxs-lookup"><span data-stu-id="f456c-110">Was the application database restored?</span></span>
- <span data-ttu-id="f456c-111">Om du har öppnat en supporthändelse och en supporttekniker har uppmanat dig att återställa data mart som en del av ett felsökningssteg.</span><span class="sxs-lookup"><span data-stu-id="f456c-111">If you've opened a support incident that and a support engineer has instructed you to reset the data mart as part of a troubleshooting step?</span></span>
 
## <a name="when-is-it-not-appropriate-to-reset-a-data-mart"></a><span data-ttu-id="f456c-112">När det inte är lämpligt att återställa en data mart?</span><span class="sxs-lookup"><span data-stu-id="f456c-112">When is it not appropriate to reset a data mart?</span></span>
<span data-ttu-id="f456c-113">Det finns vissa omständigheter när vi inte rekommenderar att du återställer en data mart.</span><span class="sxs-lookup"><span data-stu-id="f456c-113">There are some circumstances when we don't recommend resetting a data mart.</span></span> <span data-ttu-id="f456c-114">Dessa omfattar bland annat.</span><span class="sxs-lookup"><span data-stu-id="f456c-114">These include the following.</span></span> 

- <span data-ttu-id="f456c-115">Du upplever prestandaproblem som är kopplade till datasynkronisering.</span><span class="sxs-lookup"><span data-stu-id="f456c-115">You're experiencing performance issues that are associated with a data sync.</span></span> 
- <span data-ttu-id="f456c-116">Om du har ett återkommande återställt mönster på grund av någon av följande orsaker:</span><span class="sxs-lookup"><span data-stu-id="f456c-116">If you have a recurring reset pattern due to any of the following reasons:</span></span> 
  - <span data-ttu-id="f456c-117">**Data som saknas**</span><span class="sxs-lookup"><span data-stu-id="f456c-117">**Missing data**</span></span> 
  - <span data-ttu-id="f456c-118">**Låst integrationstillstånd**</span><span class="sxs-lookup"><span data-stu-id="f456c-118">**Stuck integration state**</span></span> 
  - <span data-ttu-id="f456c-119">**Föråldrade poster** - Föråldrade poster ger inte själva nödvändigtvis rätt att återställa data.</span><span class="sxs-lookup"><span data-stu-id="f456c-119">**Stale records** - Stale records by themselves don't necessarily justify resetting the data mart.</span></span> <span data-ttu-id="f456c-120">Om du har en stor datauppsättning kommer återställningsprocessen att ta en stund att köra, men den är särskilt effektiv för att förbättra systemet.</span><span class="sxs-lookup"><span data-stu-id="f456c-120">If you have a large data set, the reset process will take some time to run, but is unlikely to result in improvement.</span></span>
 
## <a name="what-is-a-data-mart-reset"></a><span data-ttu-id="f456c-121">Vad är återställning av data mart?</span><span class="sxs-lookup"><span data-stu-id="f456c-121">What is a data mart reset?</span></span>
- <span data-ttu-id="f456c-122">En återställning startas först när befintliga uppgifter har slutförts.</span><span class="sxs-lookup"><span data-stu-id="f456c-122">A reset will only start when existing tasks are complete.</span></span> <span data-ttu-id="f456c-123">På så sätt ser du till att gamla data inte infogas.</span><span class="sxs-lookup"><span data-stu-id="f456c-123">This ensures that old data is not inserted.</span></span> <span data-ttu-id="f456c-124">Då kanske ett meddelande visas, till exempel "Återställning av data mart kunde inte bearbetas på grund av en aktiv uppgift.</span><span class="sxs-lookup"><span data-stu-id="f456c-124">At this point you may see a message such as, “The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="f456c-125">Försök igen senare."</span><span class="sxs-lookup"><span data-stu-id="f456c-125">Please try again later.”</span></span>
- <span data-ttu-id="f456c-126">När du återställer den inaktiveras integrationsuppgifterna och all data från data mart tas bort.</span><span class="sxs-lookup"><span data-stu-id="f456c-126">The reset will disable the integration tasks and delete all the data mart data.</span></span> <span data-ttu-id="f456c-127">Integrationen aktiveras igen.</span><span class="sxs-lookup"><span data-stu-id="f456c-127">The integration is re-enabled.</span></span>

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a><span data-ttu-id="f456c-128">Om jag återställer data mart, förlorar jag rapporter som jag redan har utformat?</span><span class="sxs-lookup"><span data-stu-id="f456c-128">If I reset the data mart, will I lose reports that I've already designed?</span></span> 
<span data-ttu-id="f456c-129">Nej, dina rapporter lagras i SQL-register som inte påverkas av en återställd data mart.</span><span class="sxs-lookup"><span data-stu-id="f456c-129">No, your reports are stored in SQL tables that are not impacted by a reset of the data mart.</span></span> <span data-ttu-id="f456c-130">Om du är orolig för att förlora rapporter som du har utformat, kan du backa upp designerna som du inte vill förlora.</span><span class="sxs-lookup"><span data-stu-id="f456c-130">If you are concerned about losing any reports you've designed, you can back up the designs that you don't want to lose.</span></span> <span data-ttu-id="f456c-131">Om du vill säkerhetskopiera dem öppnar du rapportdesignern och går till **Företag > Företag > Byggblock > Exportera**.</span><span class="sxs-lookup"><span data-stu-id="f456c-131">To back them up, open Report Designer and go to **Company > Companies > Building Blocks > Export**.</span></span>
 
## <a name="is-it-necessary-for-all-users-to-exit-the-system-to-reset-the-data-mart"></a><span data-ttu-id="f456c-132">Måste alla användare stänga systemet för att återställa data mart?</span><span class="sxs-lookup"><span data-stu-id="f456c-132">Is it necessary for all users to exit the system to reset the data mart?</span></span>
<span data-ttu-id="f456c-133">Nej, användarna kan fortsätta att arbeta i systemet när data mart återställs.</span><span class="sxs-lookup"><span data-stu-id="f456c-133">No, users can continue working in the system during the data mart reset.</span></span> <span data-ttu-id="f456c-134">De kan dock inte komma åt rapporter som har skapats med Financial Reporter förrän återställningen är klar.</span><span class="sxs-lookup"><span data-stu-id="f456c-134">However, they won’t be able to access any reports that were created with Financial Reporter until the reset is finished.</span></span> 

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
