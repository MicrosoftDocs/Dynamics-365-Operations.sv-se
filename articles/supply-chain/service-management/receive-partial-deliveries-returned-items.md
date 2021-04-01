---
title: Ta emot delleveranser med returnerade artiklar
description: Delvisa leveranser definieras i termer av returorderrader, inte returorderleveranser.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
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
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: da4020afc8832ed9bef88f5387533ee6cd09645b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234811"
---
# <a name="receive-partial-deliveries-of-returned-items"></a><span data-ttu-id="13b17-103">Ta emot delleveranser med returnerade artiklar</span><span class="sxs-lookup"><span data-stu-id="13b17-103">Receive partial deliveries of returned items</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="13b17-104">Delvisa leveranser definieras i termer av returorderrader, inte returorderleveranser.</span><span class="sxs-lookup"><span data-stu-id="13b17-104">Partial deliveries are defined in terms of return order lines, not return order shipments.</span></span>

<span data-ttu-id="13b17-105">Om du därför inlevererar hela kvantiteten som anges på en returorderrad men du får inte får något inlevererat från de andra raderna på returordern anses leveransen inte vara en delleverans.</span><span class="sxs-lookup"><span data-stu-id="13b17-105">This means that if you receive the full quantity that is indicated on one return order line, but you receive nothing from the other lines in the return order, the delivery is not a partial delivery.</span></span> <span data-ttu-id="13b17-106">Om en returorderrad kräver att 10 enheter av en artikel ska returneras, men du du bara får fyra inlevererade enheter är leveransen en delleverans.</span><span class="sxs-lookup"><span data-stu-id="13b17-106">However, if a return order line requires 10 units of a particular item to be returned, but you receive only four, it is a partial delivery.</span></span>

<span data-ttu-id="13b17-107">Om en returleverans innehåller mindre än den fullständiga kvantiteten på en returorderrad kan du lägga leveransen åt sidan och vänta in resten av den returnerade kvantiteten, eller så kan du välja att registrera och bokföra delkvantiteten.</span><span class="sxs-lookup"><span data-stu-id="13b17-107">If a return shipment contains less than the full quantity of a return order line, you can set the shipment aside and wait for the rest of the returned quantity to arrive, or you can register and post the partial quantity.</span></span>

## <a name="register-and-post-a-partial-quantity"></a><span data-ttu-id="13b17-108">Registrera och bokföra en delkvantitet</span><span class="sxs-lookup"><span data-stu-id="13b17-108">Register and post a partial quantity</span></span>

1.  <span data-ttu-id="13b17-109">När du har valt en returorder för införsel i formuläret **Införselöversikt - lagerställe: %1, plats: %2, journalnamn: %3** klickar du på **starta införsel** för att skapa införseljournalen och klickar sedan på **journaler** \> **Visa införsel från inleveranser** för att öppna formuläret **platsjournal**.</span><span class="sxs-lookup"><span data-stu-id="13b17-109">After you select a return order for arrival on the **Arrival overview - Warehouse: %1, Dock: %2, Journal name: %3** form, click **Start arrival** to create the arrival journal, and then click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>

2.  <span data-ttu-id="13b17-110">Välj den journalrad som du vill arbeta med och klickar sedan på **rader** för att öppna formuläret **Journalrader, platser**.</span><span class="sxs-lookup"><span data-stu-id="13b17-110">Select the line of the journal that you want to work with, and then click **Lines** to open the **Journal lines, locations** form.</span></span>

3.  <span data-ttu-id="13b17-111">Markera raden för det artikelnummer som endast en delkvantitet har levererats för och klicka på **Funktioner** \> **Dela** för att öppna formuläret **Dela**.</span><span class="sxs-lookup"><span data-stu-id="13b17-111">Select the line of the item number for which only a partial quantity has arrived, and then click **Functions** \> **Split** to open the **Split** form.</span></span>

4.  <span data-ttu-id="13b17-112">I fältet **Dela kvantitet**, ange kvantiteten för det totala antalet artiklar som har tagits emot i fältet och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="13b17-112">In the **Split quantity** field, enter the quantity for the total number of items that have been received, and then click **OK**.</span></span>

5.  <span data-ttu-id="13b17-113">I formuläret **Journalrader, platser** markerar du raden för den kvantitet med artiklar som har levererats och klickar på **bokför**.</span><span class="sxs-lookup"><span data-stu-id="13b17-113">On the **Journal lines, locations** form, select the line for the quantity of items that has arrived, and then click **Post**.</span></span> <span data-ttu-id="13b17-114">Du kan bokföra raden för den ytterligare kvantiteten efter att artiklarna har levererats.</span><span class="sxs-lookup"><span data-stu-id="13b17-114">You can post the line for the additional quantity after the items have arrived.</span></span>






[!INCLUDE[footer-include](../../includes/footer-banner.md)]