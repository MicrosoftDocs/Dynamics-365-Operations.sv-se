---
title: Skicka vidare returnerade artiklar för inspektion
description: När du registrerar en returnerad artikel kan du fastställa att den ska skickas på inspektion innan den returneras till ett lager eller avyttras på något annat sätt.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSJournalTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cbb43bc4f696935bba9fca6435eb73fc9a2e5149
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3202110"
---
# <a name="pass-returned-items-on-to-inspection"></a><span data-ttu-id="d725a-103">Skicka vidare returnerade artiklar för inspektion</span><span class="sxs-lookup"><span data-stu-id="d725a-103">Pass returned items on to inspection</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="d725a-104">När du registrerar en returnerad artikel kan du fastställa att den ska skickas på inspektion innan den returneras till ett lager eller avyttras på något annat sätt.</span><span class="sxs-lookup"><span data-stu-id="d725a-104">When registering a returned item, you may determine that an item should be sent for inspection before it is returned to inventory or disposed of in some other way.</span></span>

1.  <span data-ttu-id="d725a-105">Klicka på **Lagerhantering** \> **Journaler** \> **Artikelinförsel** \> **Artikelinförsel**.</span><span class="sxs-lookup"><span data-stu-id="d725a-105">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Item arrival**.</span></span>
    
    <span data-ttu-id="d725a-106">\-eller-</span><span class="sxs-lookup"><span data-stu-id="d725a-106">\-or-</span></span>
    
    <span data-ttu-id="d725a-107">Klicka på **Lagerhantering** \> **Journaler** \> **Artikelinförsel** \> **Produktionsinleverans**.</span><span class="sxs-lookup"><span data-stu-id="d725a-107">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Production input**.</span></span>

2.  <span data-ttu-id="d725a-108">I formuläret **Platsjournal** registrera inleveransen av en artikel på normalt sätt</span><span class="sxs-lookup"><span data-stu-id="d725a-108">On the **Location journal** form, register the receipt of an item as usual.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="d725a-109">Information om hur du registrerar inleverans av returnerade artiklar finns i <A href="register-the-receipt-of-returned-items.md">registrera inleverans av returnerade artiklar</A></span><span class="sxs-lookup"><span data-stu-id="d725a-109">For information about registering the receipt of returned items, see <A href="register-the-receipt-of-returned-items.md">Register the receipt of returned items</A></span></span></P>



3.  <span data-ttu-id="d725a-110">På fliken **standardvärden** i området **Hanteringssätt** markerar du rutan **karantänhantering**.</span><span class="sxs-lookup"><span data-stu-id="d725a-110">On the **Default values** tab, in the **Mode of handling** area, select the **Quarantine management** box.</span></span>

<span data-ttu-id="d725a-111">Då skapas en karantänorder och personen eller avdelningen som utför inspektioner svarar på ordern via formuläret **Karantänorder**.</span><span class="sxs-lookup"><span data-stu-id="d725a-111">This will prompt the system to create a quarantine order, and the person or department that performs inspections will respond to this order using the **Quarantine order** form.</span></span>

## <a name="see-also"></a><span data-ttu-id="d725a-112">Se även</span><span class="sxs-lookup"><span data-stu-id="d725a-112">See also</span></span>

[<span data-ttu-id="d725a-113">Föra returnerade artiklar genom inspektionen</span><span class="sxs-lookup"><span data-stu-id="d725a-113">Take returned items through inspection</span></span>](take-returned-items-through-inspection.md)

[<span data-ttu-id="d725a-114">Ange hur returnerade artiklar ska avyttras</span><span class="sxs-lookup"><span data-stu-id="d725a-114">Specify how to dispose of returned items</span></span>](specify-how-to-dispose-of-returned-items.md)

