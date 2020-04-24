---
title: Kreditgrupper för kund
description: Det här avsnittet innehåller information om kundkreditgrupper.
author: mikefalkner
manager: AnnBe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 90d75493b928bfa4edafeef7730bc272c9146192
ms.sourcegitcommit: cd8a28be0acf31c547db1b8f6703dd4b0f62940c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261267"
---
# <a name="customer-credit-groups"></a><span data-ttu-id="4c917-103">Kreditgrupper för kund</span><span class="sxs-lookup"><span data-stu-id="4c917-103">Customer credit groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c917-104">Du kan definiera grupper av kunder som har en delad kreditgräns.</span><span class="sxs-lookup"><span data-stu-id="4c917-104">You can define groups of customers who have a shared credit limit.</span></span> <span data-ttu-id="4c917-105">Den individuella kreditgränsen som definieras på kundfakturakontot beaktas också.</span><span class="sxs-lookup"><span data-stu-id="4c917-105">The individual credit limit that is defined on the customer invoice account is also considered.</span></span>

<span data-ttu-id="4c917-106">Medlemmar i en kundkreditgrupp kan väljas från olika juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="4c917-106">Members of a customer credit group can be selected from different legal entities.</span></span> <span data-ttu-id="4c917-107">När du lägger till en kund i listan med kunder i kundkreditgruppen ändras utgångsdatumet för kreditgränsen för varje kund till utgångsdatumet som tilldelas gruppen.</span><span class="sxs-lookup"><span data-stu-id="4c917-107">When you add a customer to the list of customers in the customer credit group, the expiration date of the credit limit for each customer is changed to the expiration date that is assigned to the group.</span></span>

<span data-ttu-id="4c917-108">Du kan ställa in kundkreditgrupper på sidan **kundkreditgrupper** (**kredithantering \> kundkreditgrupper \> kundkreditgrupper**).</span><span class="sxs-lookup"><span data-stu-id="4c917-108">You can set up customer credit groups on the **Customer credit groups** page (**Credit management \> Customer credit groups \> Customer credit groups**).</span></span>

1. <span data-ttu-id="4c917-109">I fälten **Gruppnummer** och **Beskrivning** ande en identifierare och en beskrivning för gruppen.</span><span class="sxs-lookup"><span data-stu-id="4c917-109">In the **Group number** and **Description** fields, enter an identifier and description for the group.</span></span>
2. <span data-ttu-id="4c917-110">I fälten **kreditgräns** och **valuta** anger du den kreditgräns och valuta som ska användas när systemet kontrollerar kreditgränsen för någon medlem i gruppen.</span><span class="sxs-lookup"><span data-stu-id="4c917-110">In the **Credit limit** and **Currency** fields, enter the credit limit and currency that should be used when the system checks the credit limit for any member of the group.</span></span>
3. <span data-ttu-id="4c917-111">I fältet **kreditgräns till dagens datum** anger du det datum då kreditgränsen förfaller.</span><span class="sxs-lookup"><span data-stu-id="4c917-111">In the **Credit limit to date** field, enter the date when the credit limit expires.</span></span> <span data-ttu-id="4c917-112">Kundkreditgrupper måste ha utgångsdatum.</span><span class="sxs-lookup"><span data-stu-id="4c917-112">Customer credit groups must have an expiration date.</span></span>

<span data-ttu-id="4c917-113">När du har ställt in en kundkreditgrupp kan du lägga till kunder i den genom att ange deras juridiska person och kundens konto-ID.</span><span class="sxs-lookup"><span data-stu-id="4c917-113">After you've finished setting up a customer credit group, you can add customers to it by specifying their legal entity and customer account ID.</span></span> <span data-ttu-id="4c917-114">När du lägger till en ny kund i en kundkreditgrupp söker systemet efter samma kundkonto i alla juridiska personer och ber dig lägga till det i kundkreditgruppen.</span><span class="sxs-lookup"><span data-stu-id="4c917-114">When you add a new customer to a customer credit group, the system searches for the same customer account across all legal entities and prompts you to add it to the customer credit group.</span></span>

<span data-ttu-id="4c917-115">Använd menyn **Åldersfördelade saldon** om du vill visa information om åldersfördelade saldon för alla fakturakunder i en kundkreditgrupp.</span><span class="sxs-lookup"><span data-stu-id="4c917-115">Use the **Aged balances** menu to view the details of the aging balance for all invoice customers in a customer credit group.</span></span> <span data-ttu-id="4c917-116">Sidan **Åldersfördelat saldo** visas en översikt över de åldersfördelade saldona för kundkontona för fakturor.</span><span class="sxs-lookup"><span data-stu-id="4c917-116">The **Aging balance** page shows a summary of the aged balances for the invoice customer accounts.</span></span>
