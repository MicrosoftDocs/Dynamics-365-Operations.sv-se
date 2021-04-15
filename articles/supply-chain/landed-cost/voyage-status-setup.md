---
title: Inställning av status för färd
description: I detta avsnitt beskrivs hur man upprättar de statusvärden som användare kan tilldela till färder.
author: sherry-zheng
manager: tfehr
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: b7180cc9ab2d13f2260635d717adb7aab2177ab9
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500896"
---
# <a name="voyage-status-setup"></a><span data-ttu-id="51e36-103">Inställning av status för färd</span><span class="sxs-lookup"><span data-stu-id="51e36-103">Voyage status setup</span></span>

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="51e36-104">På sidan **Status för färd** kan du fastställa de statusvärden som användarna kan tilldela färder.</span><span class="sxs-lookup"><span data-stu-id="51e36-104">On the **Voyage statuses** page, you establish the set of status values that users can assign to voyages.</span></span> <span data-ttu-id="51e36-105">Användarna kan tilldela statusvärden till alla nivåer i en färd, leveransbehållare, inköpsorder och artikel (inköpsrader och överföringsorderrader).</span><span class="sxs-lookup"><span data-stu-id="51e36-105">Users can assign voyage status values to all levels of a voyage: voyage, shipping container, folio, purchase order, and item (purchase lines and transfer order lines).</span></span> <span data-ttu-id="51e36-106">De används för två syften:</span><span class="sxs-lookup"><span data-stu-id="51e36-106">They are used for two purposes:</span></span>

- <span data-ttu-id="51e36-107">Informera användaren om statusen för färd, leveransbehållare, inköpsordern eller artikeln (inköpsrader och överföringsorderrader).</span><span class="sxs-lookup"><span data-stu-id="51e36-107">Inform the user about the status of the voyage, shipping container, folio, purchase order, or item (purchase lines and transfer order lines).</span></span>
- <span data-ttu-id="51e36-108">Begränsa användningen av kostnadsområdet genom att förhindra ändringar eller radering.</span><span class="sxs-lookup"><span data-stu-id="51e36-108">Limit the use of the cost area by preventing modification or deletion.</span></span>

<span data-ttu-id="51e36-109">För att ställa in dina färdstatusar, gå till **Hemtagningskostnad \> Inställningar \> Färdstatusar**.</span><span class="sxs-lookup"><span data-stu-id="51e36-109">To set up your voyage statuses, go to **Landed cost \> Setup \> Voyage statuses**.</span></span> <span data-ttu-id="51e36-110">Där kan du lägga till, ta bort och redigera statusinformation genom att använda knapparna i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="51e36-110">There, you can add, remove, and edit statuses by using the buttons on the Action Pane.</span></span>

<span data-ttu-id="51e36-111">Varje kostnadsområde har sin egen uppsättning och hierarki av statusar.</span><span class="sxs-lookup"><span data-stu-id="51e36-111">Each cost area has its own set and hierarchy of voyage statuses.</span></span> <span data-ttu-id="51e36-112">Därför måste du i fältet **Kostnadsområde** på sidan **Kostnadsstatus** först välja det kostnadsområde som du vill visa eller skapa status för.</span><span class="sxs-lookup"><span data-stu-id="51e36-112">Therefore, on the **Voyage statuses** page, in the **Cost area** field, you must first select the cost area that you want to view or create voyage statuses for.</span></span> <span data-ttu-id="51e36-113">För varje status anges sedan de fält som beskrivs i följande tabell efter behov.</span><span class="sxs-lookup"><span data-stu-id="51e36-113">Then, for each voyage status, set the fields that are described in the following table, as required.</span></span> <span data-ttu-id="51e36-114">Observera att statusen för en sådan kan också ändras automatiskt av systemhändelser, t.ex. regler som upprättats med hjälp av spårningskontrollcentret.</span><span class="sxs-lookup"><span data-stu-id="51e36-114">Note that the status of a voyage can also be automatically changed by system events, such as rules that have been established by using the tracking control center.</span></span>

| <span data-ttu-id="51e36-115">Fält</span><span class="sxs-lookup"><span data-stu-id="51e36-115">Field</span></span> | <span data-ttu-id="51e36-116">beskrivning</span><span class="sxs-lookup"><span data-stu-id="51e36-116">Description</span></span> |
|---|---|
| <span data-ttu-id="51e36-117">Sjötransportens status</span><span class="sxs-lookup"><span data-stu-id="51e36-117">Voyage status</span></span> | <span data-ttu-id="51e36-118">Ange namn på färdstatus.</span><span class="sxs-lookup"><span data-stu-id="51e36-118">Enter the name of the voyage status.</span></span> |
| <span data-ttu-id="51e36-119">beskrivning</span><span class="sxs-lookup"><span data-stu-id="51e36-119">Description</span></span> | <span data-ttu-id="51e36-120">Ange en beskrivning av färdstatusen.</span><span class="sxs-lookup"><span data-stu-id="51e36-120">Enter a description of the voyage status.</span></span> |
| <span data-ttu-id="51e36-121">Ändra</span><span class="sxs-lookup"><span data-stu-id="51e36-121">Modify</span></span> | <span data-ttu-id="51e36-122">Markera den här kryssrutan om användare får ändra dem som har den här statusen.</span><span class="sxs-lookup"><span data-stu-id="51e36-122">Select this check box if users are allowed to modify voyages that have this status.</span></span> |
| <span data-ttu-id="51e36-123">Radera</span><span class="sxs-lookup"><span data-stu-id="51e36-123">Delete</span></span> | <span data-ttu-id="51e36-124">Markera den här kryssrutan om användare får ta bort dem som har den här statusen.</span><span class="sxs-lookup"><span data-stu-id="51e36-124">Select this check box if users are allowed to delete voyages that have this status.</span></span> |
| <span data-ttu-id="51e36-125">Obligatoriskt</span><span class="sxs-lookup"><span data-stu-id="51e36-125">Mandatory</span></span> | <span data-ttu-id="51e36-126">Markera den här kryssrutan om du vill att färdstatus ska vara obligatorisk så att den inte kan hoppas över.</span><span class="sxs-lookup"><span data-stu-id="51e36-126">Select this check box to make the voyage status mandatory, so that it can't be skipped.</span></span> |
| <span data-ttu-id="51e36-127">Överordnad</span><span class="sxs-lookup"><span data-stu-id="51e36-127">Parent</span></span> | <span data-ttu-id="51e36-128">Använd det här fältet om du vill upprätta en hierarki bland statusvärdena.</span><span class="sxs-lookup"><span data-stu-id="51e36-128">Use this field to establish a hierarchy among the status values.</span></span> <span data-ttu-id="51e36-129">Färdstatus för en hierarki kan ändras (antingen manuellt eller automatiskt) bara nedåt i hierarkin, från överordnad status till något av dess underordnade status.</span><span class="sxs-lookup"><span data-stu-id="51e36-129">Voyage statuses can be changed (either manually or automatically) only downward in the hierarchy, from a parent status to one of its child statuses.</span></span>

> [!NOTE]
> <span data-ttu-id="51e36-130">Du måste bara ställa in de speciella statusar som din organisation använder.</span><span class="sxs-lookup"><span data-stu-id="51e36-130">You have to set up only the specific voyage statuses that your organization uses.</span></span> <span data-ttu-id="51e36-131">Typiska statusen för dessa är *Bekräftat*, *Varor på väg*, *Mottagen*, *Redo för kostnadsredovisning* och *Kostnadsberäkna*.</span><span class="sxs-lookup"><span data-stu-id="51e36-131">Typical voyage statuses include *Confirmed*, *Goods in transit*, *Received*, *Ready for costing*, and *Costed*.</span></span> <span data-ttu-id="51e36-132">Andra status kan dock finnas med.</span><span class="sxs-lookup"><span data-stu-id="51e36-132">However, other statuses might be present.</span></span>