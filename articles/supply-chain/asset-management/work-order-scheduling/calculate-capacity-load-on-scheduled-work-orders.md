---
title: Beräkna kapacitetsbeläggning på schemalagda arbetsorder
description: I det här avsnittet beskrivs hur du beräknar kapacitetsbeläggning på planerade arbetsorder i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5a6063db7a63975f439da9f20adec07de9103014
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5264908"
---
# <a name="calculate-capacity-load-on-scheduled-work-orders"></a><span data-ttu-id="a2a59-103">Beräkna kapacitetsbeläggning på schemalagda arbetsorder</span><span class="sxs-lookup"><span data-stu-id="a2a59-103">Calculate capacity load on scheduled work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="a2a59-104">Du kan beräkna kapacitetsbeläggning på schemalagda arbetsorder för att få en översikt över arbetsbeläggningen för resurser under en viss period.</span><span class="sxs-lookup"><span data-stu-id="a2a59-104">You can calculate capacity load on scheduled work orders to get an overview of the work load on resources for a specific period.</span></span> <span data-ttu-id="a2a59-105">Beräkningar kan göras för följande resurser: underhållsarbetare, arbetargrupper, verktyg och tillgångar.</span><span class="sxs-lookup"><span data-stu-id="a2a59-105">Calculations can be made for the following resources: Maintenance workers, worker groups, tools, and assets.</span></span>

1. <span data-ttu-id="a2a59-106">Klicka på **Tillgångshantering** > **Förfrågningar** > **Tidsplan** > **Kapacitetsbeläggning**.</span><span class="sxs-lookup"><span data-stu-id="a2a59-106">Click **Asset management** > **Inquiries** > **Schedule** > **Capacity load**.</span></span>

2. <span data-ttu-id="a2a59-107">I dialogrutan **Beräkna kapacitetsbeläggning** fältet > **Visa** väljer du vilken beläggningstyp du vill beräkna: **Kapacitet**, **Reserverad** eller **Rest**.</span><span class="sxs-lookup"><span data-stu-id="a2a59-107">In the **Calculate capacity load** dialog > **Show** field, select which load type you want to calculate: **Capacity**, **Reserved**, or **Remainder**.</span></span>

3. <span data-ttu-id="a2a59-108">Välj **Ja** på växlingsknappen **Hoppa över noll** om du inte vill visa resultat som innehåller noll.</span><span class="sxs-lookup"><span data-stu-id="a2a59-108">Select **Yes** on the **Skip zero** toggle button if you do not want to show results containing zero.</span></span>

4. <span data-ttu-id="a2a59-109">Välj de resurstyper som du vill beräkna kapacitetsbeläggning för genom att välja **Ja** på de relevanta växlingsknappar: **Arbetare**, **Underhållsarbetargrupp**, **Verktyg** och **Tillgång**.</span><span class="sxs-lookup"><span data-stu-id="a2a59-109">Select the resource types for which you want to calculate capacity load by selecting **Yes** on the relevant toggle buttons: **Worker**, **Maintenance worker group**, **Tool**, and **Asset**.</span></span>

5. <span data-ttu-id="a2a59-110">Välj startdatum för beräkningen i fältet **Från datum**.</span><span class="sxs-lookup"><span data-stu-id="a2a59-110">Select the start date for the calculation in the **From date** field.</span></span>

6. <span data-ttu-id="a2a59-111">I fältet **Intervalltyp** väljer du intervallet för beräkningen: **dag**, **vecka**, **månad** eller **kvartal**.</span><span class="sxs-lookup"><span data-stu-id="a2a59-111">In the **Interval type** field, select the interval for the calculation: **Day**, **Week**, **Month**, or **Quarter**.</span></span>

7. <span data-ttu-id="a2a59-112">I fältet **Periodfrekvens** anger du antalet intervaller du vill beräkna.</span><span class="sxs-lookup"><span data-stu-id="a2a59-112">In the **Period frequency** field, insert the number of intervals you want to calculate.</span></span> <span data-ttu-id="a2a59-113">Om du till exempel har valt **dag** som intervalltyp och infogar siffran "5" i det här fältet, kommer en beräkning på fem dagar från startdatumet att göras.</span><span class="sxs-lookup"><span data-stu-id="a2a59-113">For example, if you have selected **Day** as the interval type, and you enter the number "5" in this field, a calculation of five days from the start date will be made.</span></span>

8. <span data-ttu-id="a2a59-114">Klicka på **OK** för att starta beräkningen.</span><span class="sxs-lookup"><span data-stu-id="a2a59-114">Click **OK** to start the calculation.</span></span>

<span data-ttu-id="a2a59-115">I bilden nedan visas resultatet av en beräkning som täcker tre veckor för beläggningstypen **reserverad**.</span><span class="sxs-lookup"><span data-stu-id="a2a59-115">The figure below shows the result of a calculation covering three weeks for the load type **Reserved**.</span></span>

![Figur 1](media/08-work-order-scheduling.png)

[!NOTE]
<span data-ttu-id="a2a59-117">Om du väljer beläggningstyperna **kapacitet** eller **rest** för beräkningen kommer samma resultat att visas om inga reservationer gjorts för resurserna under den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="a2a59-117">If you select the load types **Capacity** or **Remainder** for your calculation, the same result will be displayed if no reservations have been made for the resources in the selected period.</span></span>

<span data-ttu-id="a2a59-118">För information om hur du beräknar kapacitetsbelastning på underhållsscheman och inte schemalagda arbetsordrar, se [Beräkna kapacitetsbeläggning](../capacity-planning/calculate-capacity-load.md).</span><span class="sxs-lookup"><span data-stu-id="a2a59-118">For information about how to calculate capacity load on maintenance schedule lines and not scheduled work orders, refer to [Calculate capacity load](../capacity-planning/calculate-capacity-load.md).</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]