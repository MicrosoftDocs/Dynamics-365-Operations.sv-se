---
title: Beräkna artikelprognos
description: I det här avsnittet beskrivs hur du beräknar artikelprognos i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetItemForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1cea3b6cfd42348285985122ae905f8ea9f3facb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260044"
---
# <a name="calculate-item-forecast"></a><span data-ttu-id="03007-103">Beräkna artikelprognos</span><span class="sxs-lookup"><span data-stu-id="03007-103">Calculate item forecast</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="03007-104">På samma sätt som du kan göra beräkningar av kapacitetsbeläggning, som beskrivs i föregående avsnitt, kan du också göra artikelprognosberäkningar för:</span><span class="sxs-lookup"><span data-stu-id="03007-104">Just as you can make capacity load calculations, which are described in the previous section, you can also make item forecast calculations on:</span></span>

- <span data-ttu-id="03007-105">rader för underhållsschema</span><span class="sxs-lookup"><span data-stu-id="03007-105">maintenance schedule lines</span></span>  
- <span data-ttu-id="03007-106">arbetsorder som ännu inte har planerats</span><span class="sxs-lookup"><span data-stu-id="03007-106">work orders that have not yet been scheduled</span></span>  
- <span data-ttu-id="03007-107">schemalagda arbetsorder</span><span class="sxs-lookup"><span data-stu-id="03007-107">scheduled work orders</span></span>

<span data-ttu-id="03007-108">Detta är användbart om du vill få en översikt över förväntad artikelförbrukning (reservdelar och andra artiklar som krävs för att slutföra arbetsorder) för en viss period.</span><span class="sxs-lookup"><span data-stu-id="03007-108">This is useful if you want to get an overview of expected item consumption (spare parts as well as other items required for completing work orders) for a specific period.</span></span> <span data-ttu-id="03007-109">Beräkning av artikelprognos kan göras på alla tillgångar eller valda tillgångar.</span><span class="sxs-lookup"><span data-stu-id="03007-109">Calculation of item forecast can be done on all assets or selected assets.</span></span> <span data-ttu-id="03007-110">Du kan också göra en beräkning av aktiviteten underhållsstopp (**Alla aktiviteter för underhållsstopp** eller **Aktiva aktiviteter för underhållsstopp**) eller på en arbetsorderpool (**Alla arbetsorderpooler** eller **Aktiva arbetsorderpooler**).</span><span class="sxs-lookup"><span data-stu-id="03007-110">You can also make a calculation on a maintenance downtime activity (**All maintenance downtime activities** or **Active maintenance downtime activities**), or on a work order pool (**All work order pools** or **Active work order pools**).</span></span>

1. <span data-ttu-id="03007-111">Klicka på **Tillgångshantering** > **Förfrågningar** > **Artikelprognos**, eller **Tillgångshantering** > **Allmänt** > **Arbetsorderpooler** > **Alla arbetsorderpooler** / **Aktiva arbetsorderpooler** > välj arbetsorderpool i listan > knappen **Artikelprognos**, eller **Tillgångshantering** > **Allmänt** > **Aktiviteter för underhållsstopp** > **Alla aktiviteter för underhållsstopp** / **Aktiva aktiviteter för underhållsstopp** > välj aktiviteter för underhållsstopp i listan > knappen **Artikelprognos**.</span><span class="sxs-lookup"><span data-stu-id="03007-111">Click **Asset management** > **Inquiries** > **Item forecast**, or **Asset management** > **Common** > **Work order pools** > **All work order pools** / **Active work order pools** > select work order pool in the list > **Item forecast** button, or **Asset management** > **Common** > **Maintenance downtime activities** > **All maintenance downtime activities** / **Active maintenance downtime activities** > select maintenance downtime activity in the list > **Item forecast** button.</span></span>

2. <span data-ttu-id="03007-112">I dialogrutan **Beräkna artikelprognos** väljer du en period för beräkningen i fälten **Startdatum/tid** och **Slutdatum/tid.**</span><span class="sxs-lookup"><span data-stu-id="03007-112">In the **Calculate item forecast** dialog, select a period for the calculation in the **Start date/time** and **End date/time** fields.</span></span>

3. <span data-ttu-id="03007-113">Välj "Ja" på växlingsknappen **Inkludera underhållssschema** om du vill inkludera rader för underhållsschema i prognosberäkningen.</span><span class="sxs-lookup"><span data-stu-id="03007-113">Select "Yes" on the **Include maintenance schedule** toggle button if you want to include maintenance schedule lines in the forecast calculation.</span></span>

4. <span data-ttu-id="03007-114">Välj "Ja" på växlingsknappen **Inkludera arbetsorder** om du vill inkludera arbetsorderjobb i prognosberäkningen.</span><span class="sxs-lookup"><span data-stu-id="03007-114">Select "Yes" on the **Include work order** toggle button if you want to include work order jobs in the forecast calculation.</span></span>

5. <span data-ttu-id="03007-115">Du kan använda fältet **Nivå** för att indikera hur detaljerade artikelprognosraderna ska vara gällande funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="03007-115">You can use the **Level** field to indicate how detailed you want the item forecast lines to be regarding functional locations.</span></span> 

      <span data-ttu-id="03007-116">Om du till exempel infogar siffran "1" i fältet och har en funktionsplatsstruktur med flera nivåer, visas alla underhållsschemarader och arbetsorder för en funktionsplats på den översta nivån, och därmed kan också de timmar som finns på en rad läggas till från funktionsplatser på en lägre nivå.</span><span class="sxs-lookup"><span data-stu-id="03007-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location structure, all maintenance schedule lines and work orders for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> 
  
      <span data-ttu-id="03007-117">Om du infogar siffran "0" i fältet **Nivå** visas ett detaljerat resultat med alla underhållsschemarader och alla arbetsorder på den funktionsplatsnivå som de är relaterade till.</span><span class="sxs-lookup"><span data-stu-id="03007-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all maintenance schedule lines and all work orders on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="03007-118">Klicka på **OK** för att starta beräkningen.</span><span class="sxs-lookup"><span data-stu-id="03007-118">Click **OK** to start the calculation.</span></span>

7. <span data-ttu-id="03007-119">I **Gruppera efter...**-grupper klickar du på de relevanta knapparna för att visa den obligatoriska detaljnivån för beräkningen.</span><span class="sxs-lookup"><span data-stu-id="03007-119">In the **Group by...** groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="03007-120">I bildrutan nedan markeras de valda knapparna **Gruppera efter** med blå färg.</span><span class="sxs-lookup"><span data-stu-id="03007-120">In the screenshot below, the selected **Group by** buttons are highlighted in blue color.</span></span> <span data-ttu-id="03007-121">Klicka på en knapp för att aktivera och inaktivera den.</span><span class="sxs-lookup"><span data-stu-id="03007-121">Click on a button to activate or deactivate it.</span></span>

8. <span data-ttu-id="03007-122">Klicka på knappen **Visa dimensioner** om du vill visa produkt-, lagrings- eller spårningsdimensioner som hör till artiklarna.</span><span class="sxs-lookup"><span data-stu-id="03007-122">Click the **Display dimensions** button if you want to see the product, storage, or tracking dimensions related to the items.</span></span> <span data-ttu-id="03007-123">Markera relevanta kryssrutor och klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="03007-123">Select the relevant check boxes, and click **OK**.</span></span>

![Figur 1](media/02-capacity-planning.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]