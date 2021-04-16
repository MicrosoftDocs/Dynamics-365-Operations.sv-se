---
title: Beräkna kapacitetsbeläggning
description: I det här avsnittet beskrivs hur du beräknar kapacitetsbeläggning i Tillgångshantering.
author: johanhoffmann
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetCapacityLoad, EntAssetWorkOrderCapacityLoadCalculate, EntAssetWorkOrderCapacityLoad
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ba4b9ef43e27f689e1f10d2ee8f10f6ea4bf43ed
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821739"
---
# <a name="calculate-capacity-load"></a><span data-ttu-id="0fedc-103">Beräkna kapacitetsbeläggning</span><span class="sxs-lookup"><span data-stu-id="0fedc-103">Calculate capacity load</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="0fedc-104">I Tillgångshantering kan du beräkna kapacitetsbeläggningen på:</span><span class="sxs-lookup"><span data-stu-id="0fedc-104">In Asset Management, you can calculate capacity load on:</span></span>

- <span data-ttu-id="0fedc-105">rader för underhållsschema</span><span class="sxs-lookup"><span data-stu-id="0fedc-105">maintenance schedule lines</span></span>  
- <span data-ttu-id="0fedc-106">arbetsorder som ännu inte har planerats</span><span class="sxs-lookup"><span data-stu-id="0fedc-106">work orders that have not yet been scheduled</span></span>  
- <span data-ttu-id="0fedc-107">schemalagda arbetsorder</span><span class="sxs-lookup"><span data-stu-id="0fedc-107">scheduled work orders</span></span>

<span data-ttu-id="0fedc-108">Detta är användbart om du vill få en översikt över förväntad kapacitetsbeläggning för en viss period.</span><span class="sxs-lookup"><span data-stu-id="0fedc-108">This is useful if you want to get an overview of expected capacity load for a specific period.</span></span> <span data-ttu-id="0fedc-109">Beräkning av kapacitetsbeläggnin kan göras på alla tillgångar eller valda tillgångar.</span><span class="sxs-lookup"><span data-stu-id="0fedc-109">Calculation of capacity load can be done on all assets or selected assets.</span></span> <span data-ttu-id="0fedc-110">Du kan också utföra en beräkning av aktiviteter för underhållsstopp och arbetsorderpooler.</span><span class="sxs-lookup"><span data-stu-id="0fedc-110">You can also make a calculation on maintenance downtime activities or work order pools.</span></span>

1. <span data-ttu-id="0fedc-111">Klicka på **Tillgångshantering** > **Förfrågningar** > **Kapacitetsbeläggning**, eller **Tillgångshantering** > **Allmänt** > **Arbetsorderpooler** > **Alla arbetsorderpooler** / **Aktiva arbetsorderpooler** > välj arbetsorderpool i listan > knappen **Kapacitetsbeläggning**, eller **Tillgångshantering** > **Allmänt** > **Aktiviteter för underhållsstopp** > **Alla aktiviteter för underhållsstopp** / **Aktiva aktiviteter för underhållsstopp** > välj aktiviteter för underhåll i listan > knappen **Kapacitetsbeläggning**.</span><span class="sxs-lookup"><span data-stu-id="0fedc-111">Click **Asset management** > **Inquiries** > **Capacity load**, or **Asset management** > **Common** > **Work order pools** > **All work order pools** / **Active work order pools** > select work order pool in the list > **Capacity load** button, or **Asset management** > **Common** > **Maintenance downtime activities** > **All maintenance downtime activities** / **Active maintenance downtime activities** > select maintenance activity in the list > **Capacity load** button.</span></span>

2. <span data-ttu-id="0fedc-112">I dialogrutan **Beräkna kapacitetsbeläggning** väljer du en period för beräkningen i fälten **Startdatum/tid** och **Slutdatum/tid.**</span><span class="sxs-lookup"><span data-stu-id="0fedc-112">In the **Calculate capacity load** dialog, select a period for the calculation in the **Start date/time** and **End date/time** fields.</span></span>

3. <span data-ttu-id="0fedc-113">Välj "Ja" på växlingsknappen **Inkludera underhållssschema** om du vill inkludera rader för underhållsschema i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="0fedc-113">Select "Yes" on the **Include maintenance schedule** toggle button if you want to include maintenance schedule lines in the calculation.</span></span>

4. <span data-ttu-id="0fedc-114">Välj "Ja" på växlingsknappen **Inkludera arbetsorder** om du vill inkludera arbetsorderjobb i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="0fedc-114">Select "Yes" on the **Include work order** toggle button if you want to include work order jobs in the calculation.</span></span>

5. <span data-ttu-id="0fedc-115">Du kan använda fältet **Nivå** för att indikera hur detaljerad beräkningen av kapacitetsbeläggningsrader ska vara gällande funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="0fedc-115">You can use the **Level** field to indicate how detailed you want the capacity load lines to be regarding functional locations.</span></span> 

    <span data-ttu-id="0fedc-116">Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla underhållsschemarader och arbetsorder för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå.</span><span class="sxs-lookup"><span data-stu-id="0fedc-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines and work orders for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
    
    <span data-ttu-id="0fedc-117">Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla underhållsschemarader och alla arbetsorder på de funktionsplatsnivåer som de är relaterade till.</span><span class="sxs-lookup"><span data-stu-id="0fedc-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines and all work orders on all the functional location levels to which they are related.</span></span>

6. <span data-ttu-id="0fedc-118">Klicka på **OK** för att starta beräkningen.</span><span class="sxs-lookup"><span data-stu-id="0fedc-118">Click **OK** to start the calculation.</span></span>

7. <span data-ttu-id="0fedc-119">I **Gruppera efter...**-grupper klickar du på de relevanta knapparna för att visa den obligatoriska detaljnivån för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="0fedc-119">In the **Group by...** groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="0fedc-120">I bildrutan nedan markeras de valda knapparna **Gruppera efter** med blå färg.</span><span class="sxs-lookup"><span data-stu-id="0fedc-120">In the screenshot below, the selected **Group by** buttons are highlighted in blue color.</span></span> <span data-ttu-id="0fedc-121">Klicka på en knapp för att aktivera och inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="0fedc-121">Click on a button to activate or deactivate it.</span></span>

    ![Figur 1](media/01-capacity-planning.png)

>[!NOTE]
><span data-ttu-id="0fedc-123">Om du bara vill fokusera på kapacitetsplanering för schemalagda arbetsorder läser du i [Beräkna kapacitetsbeläggning på schemalagda arbetsorder](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).</span><span class="sxs-lookup"><span data-stu-id="0fedc-123">If you want to focus only on capacity planning regarding scheduled work orders, see [Calculate capacity load on scheduled work orders](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]