---
title: Bokför införseljournalen för returnerade produkter
description: Bokför införseljournalen för returnerade produkter
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverview
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 63659288ab8551e458f6e92a5045c72441ff68cc
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2019
ms.locfileid: "1743289"
---
# <a name="post-arrival-journal-for-returned-products"></a><span data-ttu-id="9e36f-103">Bokför införseljournalen för returnerade produkter</span><span class="sxs-lookup"><span data-stu-id="9e36f-103">Post arrival journal for returned products</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="9e36f-104">Om du vill bearbeta en retur, validera först returkvantiteten, uppdatera kvantitetsfältet i artikelinförseljournalen.</span><span class="sxs-lookup"><span data-stu-id="9e36f-104">To process a return, first validate the return quantity, update the quantity field in the item arrival journal.</span></span> <span data-ttu-id="9e36f-105">Därefter välja en dispositionskod eller ange att de returnerade artiklarna måste kontrolleras.</span><span class="sxs-lookup"><span data-stu-id="9e36f-105">Then select a disposition code or indicate that the returned items have to be inspected.</span></span> <span data-ttu-id="9e36f-106">När du har slutfört de här stegen kan du bokföra artikelinförseljournalen för returordern.</span><span class="sxs-lookup"><span data-stu-id="9e36f-106">After completing these steps, you can post the item arrival journal for the return order.</span></span>

1.  <span data-ttu-id="9e36f-107">Klicka på **Lagerhantering** \> **Periodisk** \> **Införselöversikt**.</span><span class="sxs-lookup"><span data-stu-id="9e36f-107">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="9e36f-108">I filtret **inställningsnamn** väljer du **returorder**.</span><span class="sxs-lookup"><span data-stu-id="9e36f-108">In the **Setup name** filter, select **Return order**.</span></span>

3.  <span data-ttu-id="9e36f-109">Om listan med inleveranser är lång kan du använda fälten i området **Intervall** för att begränsa listan.</span><span class="sxs-lookup"><span data-stu-id="9e36f-109">If the list of receipts is long, use the fields in the **Range** area to narrow the list.</span></span>

4.  <span data-ttu-id="9e36f-110">Hitta raden för den returorder som du vill bokföra, markera rutan **Välj för införsel** och klicka på **Starta införsel**.</span><span class="sxs-lookup"><span data-stu-id="9e36f-110">Locate the line of the return order that you want to post, select its **Select for arrival** box, and then click **Start arrival**.</span></span>

5.  <span data-ttu-id="9e36f-111">Klicka på **journaler**\>**visa införsel från inleveranser** för att öppna formuläret **platsjournal**.</span><span class="sxs-lookup"><span data-stu-id="9e36f-111">Click **Journals** \> **Show arrivals from receipts** to open the **Location journal** form.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="9e36f-112">Om du vill visa detaljerad information markerar du en journal och klickar på <STRONG>Rader</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="9e36f-112">To view detailed information, select a journal, and then click <STRONG>Lines</STRONG>.</span></span></P>


6.  <span data-ttu-id="9e36f-113">Gör de uppdateringar som du vill göra och klicka sedan på **Bokför**.</span><span class="sxs-lookup"><span data-stu-id="9e36f-113">Make any necessary updates, and then click **Post**.</span></span>

<span data-ttu-id="9e36f-114">När journalen har bokförts registreras de returnerade artiklarna i lagret och formuläret **Returorder** visar information om att artiklarna har inlevererats till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="9e36f-114">After the journal is posted, the returned items are registered in inventory, and the **Return orders** form indicates that the items have arrived at the warehouse.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e36f-115">Se även</span><span class="sxs-lookup"><span data-stu-id="9e36f-115">See also</span></span>

<span data-ttu-id="9e36f-116">[Platsjournal (formulär)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="9e36f-116">[Location journal (form)](https://technet.microsoft.com/library/aa584822\(v=ax.60\))</span></span>

  


