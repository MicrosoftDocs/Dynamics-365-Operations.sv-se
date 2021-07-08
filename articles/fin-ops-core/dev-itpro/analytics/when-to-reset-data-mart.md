---
title: Vanliga frågor om återställ datatorg
description: Det här avsnittet innehåller svar på vanliga frågor om återställ datatorg.
author: jinniew
ms.date: 06/09/2021
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
ms.openlocfilehash: 7cd96c7bc698986ef1ef07ca88479a3d49f22924
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266619"
---
# <a name="data-mart-resets-faq"></a><span data-ttu-id="8d518-103">Vanliga frågor om återställ datatorg</span><span class="sxs-lookup"><span data-stu-id="8d518-103">Data mart resets FAQ</span></span>

<span data-ttu-id="8d518-104">Det här avsnittet innehåller svar på vanliga frågor om återställ datatorg.</span><span class="sxs-lookup"><span data-stu-id="8d518-104">This topic provides answers to some frequently asked questions about data mart resets.</span></span> <span data-ttu-id="8d518-105">En återställning av datatorg kan vara en tidskrävande process och, beroende på omständigheter, kanske inte är den lösning som krävs.</span><span class="sxs-lookup"><span data-stu-id="8d518-105">A reset of the data mart can be a time-consuming process and, depending on the circumstances, might not be the solution that is required.</span></span> <span data-ttu-id="8d518-106">Därför innehåller det här avsnittet information om omständigheter där återställ datatorg kan hjälpa till och situationer där den är till hjälp.</span><span class="sxs-lookup"><span data-stu-id="8d518-106">Therefore, this topic includes information about circumstances where a data mart reset might help and also circumstances where it's unlikely to help.</span></span>

## <a name="what-is-a-data-mart-reset"></a><span data-ttu-id="8d518-107">Vad är återställning av datatorg?</span><span class="sxs-lookup"><span data-stu-id="8d518-107">What is a data mart reset?</span></span>

<span data-ttu-id="8d518-108">En återställ datatorg inaktiverar integrationsuppgifterna, raderar alla data för datatorg och aktiverar sedan integrationen på nytt.</span><span class="sxs-lookup"><span data-stu-id="8d518-108">A data mart reset will disable the integration tasks, delete all the data mart data, and then re-enable integration.</span></span>

<span data-ttu-id="8d518-109">För att säkerställa att gamla data inte infogas kan en återställ datatorg startas först när befintliga uppgifter har slutförts.</span><span class="sxs-lookup"><span data-stu-id="8d518-109">To ensure that old data isn't inserted, a data mart reset can be started only after existing tasks are completed.</span></span> <span data-ttu-id="8d518-110">Om du försöker återställa datatorg innan alla uppgifter har slutförts kanske du får ett meddelande som till exempel: "återställ datatorg kunde inte bearbetas på grund av en aktiv uppgift.</span><span class="sxs-lookup"><span data-stu-id="8d518-110">If you try to reset the data mart before all tasks are completed, you might receive a message such as, "The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="8d518-111">Försök igen senare."</span><span class="sxs-lookup"><span data-stu-id="8d518-111">Please try again later."</span></span>

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a><span data-ttu-id="8d518-112">När måste du återställa data eller vill du återställa data?</span><span class="sxs-lookup"><span data-stu-id="8d518-112">When do I have to do a data mart reset?</span></span>

<span data-ttu-id="8d518-113">Om ett eller flera av följande gäller i din situation kan din organisation dra fördel av en återställ datatorg:</span><span class="sxs-lookup"><span data-stu-id="8d518-113">If one or more of the following statements apply to your situation, your organization can benefit from a data mart reset:</span></span>

- <span data-ttu-id="8d518-114">Återställdes programdatabasen.</span><span class="sxs-lookup"><span data-stu-id="8d518-114">The application database was restored.</span></span>
- <span data-ttu-id="8d518-115">Du har öppnat en supportbegäran och en supporttekniker har uppmanat dig att återställa datatorg som ett del av ett felsökningssteg.</span><span class="sxs-lookup"><span data-stu-id="8d518-115">You opened a support ticket, and a Support engineer instructed you to reset the data mart as part of a troubleshooting step.</span></span>
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a><span data-ttu-id="8d518-116">När är återställa en datatorg inte lämpligt?</span><span class="sxs-lookup"><span data-stu-id="8d518-116">When is a data mart reset inappropriate?</span></span>

<span data-ttu-id="8d518-117">Det finns vissa omständigheter när vi inte rekommenderar att du återställer en data mart:</span><span class="sxs-lookup"><span data-stu-id="8d518-117">Here are some of the circumstances where we don't recommend that you reset the data mart:</span></span>

- <span data-ttu-id="8d518-118">Du upplever prestandaproblem som är kopplade till datasynkronisering.</span><span class="sxs-lookup"><span data-stu-id="8d518-118">You're experiencing performance issues that are associated with data synchronization.</span></span>
- <span data-ttu-id="8d518-119">Om du har ett återkommande återställt mönster på grund av någon av följande orsaker:</span><span class="sxs-lookup"><span data-stu-id="8d518-119">You have a recurring reset pattern for any of the following reasons:</span></span>

    - <span data-ttu-id="8d518-120">**Data som saknas** – Om du ser att data saknas öppnar du ett supportärende hos Microsoft för att granska ditt rapportformat och eventuella problem med datasynkronisering.</span><span class="sxs-lookup"><span data-stu-id="8d518-120">**Missing data** – If you notice that data is missing, open a support ticket with Microsoft to review your report format and possible data synchronization issues.</span></span>
    - <span data-ttu-id="8d518-121">**Låst integrationstillstånd**</span><span class="sxs-lookup"><span data-stu-id="8d518-121">**Stuck integration state**</span></span>
    - <span data-ttu-id="8d518-122">**Föråldrade poster** - Föråldrade poster ger inte själva nödvändigtvis rätt att återställa datatorg.</span><span class="sxs-lookup"><span data-stu-id="8d518-122">**Stale records** – Stale records by themselves don't necessarily justify a data mart reset.</span></span> <span data-ttu-id="8d518-123">Om du har en stor datauppsättning kommer återställningsprocessen att ta en stund att köra, men den är särskilt effektiv för att förbättra systemet.</span><span class="sxs-lookup"><span data-stu-id="8d518-123">If you have a large data set, the reset process will take some time to run but is unlikely to lead to any improvement.</span></span>

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a><span data-ttu-id="8d518-124">Om jag återställer datatorg, förlorar jag rapporter som jag redan har utformat?</span><span class="sxs-lookup"><span data-stu-id="8d518-124">If I reset the data mart, will I lose reports that I've already designed?</span></span>

<span data-ttu-id="8d518-125">Nej.</span><span class="sxs-lookup"><span data-stu-id="8d518-125">No.</span></span> <span data-ttu-id="8d518-126">Dina rapporter lagras i SQL-register som inte påverkas av en återställd data mart.</span><span class="sxs-lookup"><span data-stu-id="8d518-126">Your reports are stored in SQL tables that aren't affected by a data mart reset.</span></span> <span data-ttu-id="8d518-127">Om du är orolig för att förlora rapporter som du har utformat, kan du backa upp designerna som du inte vill förlora.</span><span class="sxs-lookup"><span data-stu-id="8d518-127">If you're concerned about losing reports that you've designed, you can back up the designs that you don't want to lose.</span></span> <span data-ttu-id="8d518-128">Om du vill säkerhetskopiera designer öppnar du rapportdesignern och går till **Företag \> Företag \> Byggblock \> Exportera**.</span><span class="sxs-lookup"><span data-stu-id="8d518-128">To back up designs, open Report Designer, and go to **Company \> Companies \> Building Blocks \> Export**.</span></span>
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a><span data-ttu-id="8d518-129">Måste alla användare stänga systemet innan jag kan återställa data mart?</span><span class="sxs-lookup"><span data-stu-id="8d518-129">Do all users have to exit the system before I can reset the data mart?</span></span>

<span data-ttu-id="8d518-130">Nej.</span><span class="sxs-lookup"><span data-stu-id="8d518-130">No.</span></span> <span data-ttu-id="8d518-131">Användarna kan fortsätta att arbeta i systemet när data mart återställs.</span><span class="sxs-lookup"><span data-stu-id="8d518-131">Users can continue to work in the system during a data mart reset.</span></span> <span data-ttu-id="8d518-132">De kan dock inte komma åt rapporter som har skapats med Financial Reporter förrän återställningen är klar.</span><span class="sxs-lookup"><span data-stu-id="8d518-132">However, until the reset is completed, users won't be able to access any reports that were created by using Financial Reporter.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
