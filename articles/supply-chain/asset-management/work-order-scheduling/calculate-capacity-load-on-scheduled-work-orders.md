---
title: Beräkna kapacitetsbeläggning på schemalagda arbetsorder
description: I det här avsnittet beskrivs hur du beräknar kapacitetsbeläggning på planerade arbetsorder i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 0c0dd1e306c54d3f99b86ad6f1816d5acabe6c18
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887169"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a><span data-ttu-id="36471-103">Beräkna kapacitetsbeläggning på schemalagda arbetsorder</span><span class="sxs-lookup"><span data-stu-id="36471-103">Calculate capacity load on scheduled work orders</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="36471-104">Du kan beräkna kapacitetsbeläggning på schemalagda arbetsorder för att få en översikt över arbetsbeläggningen för resurser under en viss period.</span><span class="sxs-lookup"><span data-stu-id="36471-104">You can calculate capacity load on scheduled work orders to get an overview of the work load on resources for a specific period.</span></span> <span data-ttu-id="36471-105">Beräkningar kan göras för följande resurser: underhållsarbetare, arbetargrupper, verktyg och tillgångar.</span><span class="sxs-lookup"><span data-stu-id="36471-105">Calculations can be made for the following resources: Maintenance workers, worker groups, tools, and assets.</span></span>

1. <span data-ttu-id="36471-106">Klicka på **Tillgångshantering** > **Förfrågningar** > **Tidsplan** > **Kapacitetsbeläggning**.</span><span class="sxs-lookup"><span data-stu-id="36471-106">Click **Asset management** > **Inquiries** > **Schedule** > **Capacity load**.</span></span>

2. <span data-ttu-id="36471-107">I dialogrutan **Beräkna kapacitetsbeläggning** > fältet **Visa** väljer du vilken beläggningstyp du vill beräkna: "Kapacitet", "Reserverad" eller "Rest".</span><span class="sxs-lookup"><span data-stu-id="36471-107">In the **Calculate capacity load** dialog > **Show** field, select which load type you want to calculate: "Capacity", "Reserved", or "Remainder".</span></span>

3. <span data-ttu-id="36471-108">Välj "Ja" på växlingsknappen **Hoppa över noll** om du inte vill visa resultat som innehåller noll.</span><span class="sxs-lookup"><span data-stu-id="36471-108">Select "Yes" on the **Skip zero** toggle button if you do not want to show results containing zero.</span></span>

4. <span data-ttu-id="36471-109">Välj de resurstyper som du vill beräkna kapacitetsbeläggning för genom att välja "Ja" på de relevanta växlingsknappar: **Arbetare**, **Underhållsarbetargrupp**, **Verktyg** och **Tillgång**.</span><span class="sxs-lookup"><span data-stu-id="36471-109">Select the resource types for which you want to calculate capacity load by selecting "Yes" on the relevant toggle buttons: **Worker**, **Maintenance worker group**, **Tool**, and **Asset**.</span></span>

5. <span data-ttu-id="36471-110">Välj startdatum för beräkningen i fältet **Från datum**.</span><span class="sxs-lookup"><span data-stu-id="36471-110">Select the start date for the calculation in the **From date** field.</span></span>

6. <span data-ttu-id="36471-111">I fältet **Intervalltyp** väljer du intervallet för beräkningen: "dag", "vecka", "månad" eller "kvartal".</span><span class="sxs-lookup"><span data-stu-id="36471-111">In the **Interval type** field, select the interval for the calculation: "Day", "Week", "Month", or "Quarter".</span></span>

7. <span data-ttu-id="36471-112">I fältet **Periodfrekvens** anger du antalet intervaller du vill beräkna.</span><span class="sxs-lookup"><span data-stu-id="36471-112">In the **Period frequency** field, insert the number of intervals you want to calculate.</span></span> <span data-ttu-id="36471-113">Om du till exempel har valt "dag" som intervalltyp och infogar siffran "5" i det här fältet, kommer en beräkning på fem dagar från startdatumet att göras.</span><span class="sxs-lookup"><span data-stu-id="36471-113">For example, if you have selected "Day" as the interval type, and you insert the number "5" in this field, a calculation of five days from the start date will be made.</span></span>

8. <span data-ttu-id="36471-114">Klicka på **OK** för att starta beräkningen.</span><span class="sxs-lookup"><span data-stu-id="36471-114">Click **OK** to start the calculation.</span></span>

<span data-ttu-id="36471-115">I bilden nedan visas resultatet av en beräkning som täcker tre veckor för beläggningstypen "reserverad".</span><span class="sxs-lookup"><span data-stu-id="36471-115">The figure below shows the result of a calculation covering three weeks for the load type "Reserved".</span></span>

![Figur 1](media/08-work-order-scheduling.png)

>[!NOTE]
><span data-ttu-id="36471-117">Om du väljer beläggningstyperna "kapacitet" eller "rest" för beräkningen kommer samma resultat att visas om inga reservationer gjorts för resurserna under den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="36471-117">If you select the load types "Capacity" or "Remainder" for your calculation, the same result will be displayed if no reservations have been made for the resources in the selected period.</span></span>

<span data-ttu-id="36471-118">I [Beräkna kapacitetsbeläggning](../capacity-planning/calculate-capacity-load.md) finns information om hur du beräknar kapacitetsbeläggning på rader för underhållsplanrader och ej schemalagda arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="36471-118">Refer to [Calculate capacity load](../capacity-planning/calculate-capacity-load.md) for information on how to calculate capacity load on maintenance schedule lines and not scheduled work orders.</span></span>

