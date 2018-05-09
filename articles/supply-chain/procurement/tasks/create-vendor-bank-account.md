--- 
title: "Skapa ett leverantörsbankkonto"
description: "Den här proceduren visar hur du skapar ett bakkonto för en leverantör."
author: mkirknel
manager: AnnBe
ms.date: 08/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3d4977ae0c1ce613b044e59161c96461027411f2
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-vendor-bank-account"></a><span data-ttu-id="ee3d2-103">Skapa ett leverantörsbankkonto</span><span class="sxs-lookup"><span data-stu-id="ee3d2-103">Create a vendor bank account</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ee3d2-104">Den här proceduren visar hur du skapar ett bakkonto för en leverantör.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-104">This procedure shows you how to create a bank account for a vendor.</span></span> <span data-ttu-id="ee3d2-105">Du kan köra den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-105">You can use this procedure in demo data company USMF.</span></span>

1. <span data-ttu-id="ee3d2-106">Gå till Anskaffning och källa > Leverantörer > Alla leverantörer.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-106">Go to Procurement and sourcing > Vendors > All vendors.</span></span>
2. <span data-ttu-id="ee3d2-107">Markera leverantören som du vill skapa ett bankkonto för, och klicka sedan på länken för leverantörskonto-ID.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-107">Select the vendor that you want to create a bank account for, and then click the link on the Vendor account ID.</span></span>
3. <span data-ttu-id="ee3d2-108">Klicka på Leverantör i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-108">On the Action Pane, click Vendor.</span></span>
4. <span data-ttu-id="ee3d2-109">Klicka på bankkonton.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="ee3d2-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-110">Click New.</span></span>
6. <span data-ttu-id="ee3d2-111">I fältet Bankkonto, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-111">In the Bank account field, type a value.</span></span>
    * <span data-ttu-id="ee3d2-112">Detta ID ska användas för att identifiera bankkontot på leverantörsposten.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-112">This ID will be used to identify the bank account on the vendor record.</span></span>  
7. <span data-ttu-id="ee3d2-113">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-113">In the Name field, type a value.</span></span>
8. <span data-ttu-id="ee3d2-114">Ange eller välj ett värde i fältet Bankgrupper.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-114">In the Bank groups field, enter or select a value.</span></span>
9. <span data-ttu-id="ee3d2-115">Välj ett alternativ i fältet Organisationsnummertyp.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-115">In the Routing number type field, select an option.</span></span>
    * <span data-ttu-id="ee3d2-116">Det är denna typ av organisationsnummer som används för internationella betalningar.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-116">This is the type of routing number that’s used for international payments.</span></span>  
10. <span data-ttu-id="ee3d2-117">Skriv ett värde i fältet Bankkontonummer.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-117">In the Bank account number field, type a value.</span></span>
11. <span data-ttu-id="ee3d2-118">Skriv ett värde i fältet SWIFT-kod.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-118">In the SWIFT code field, type a value.</span></span>
12. <span data-ttu-id="ee3d2-119">Ange ett värde i fältet IBAN.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-119">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="ee3d2-120">IBAN-numret måste vara i rätt format.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-120">The IBAN number must be in the correct format.</span></span> <span data-ttu-id="ee3d2-121">Till exempel kan du använda DE89370400440532013000.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-121">For example, you could use DE89370400440532013000.</span></span>  
    * <span data-ttu-id="ee3d2-122">Statusen på bankkontot är Aktiv, om det aktiva datumet har nåtts och utgångsdatumet inte har överskridits.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-122">The status of the bank account is Active if the Active date has been reached, and the Expiration date has not been exceeded.</span></span> <span data-ttu-id="ee3d2-123">Den är också aktiv om båda fälten Aktivt datum och Utgångsdatum är tomma.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-123">It’s also active if both the Active date and Expiration date fields are blank.</span></span> <span data-ttu-id="ee3d2-124">Om datumen i båda fälten Aktivt datum och Utgångsdatum infaller senare är elektroniska betalningar inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-124">If the dates in both the Active date and Expiration date fields are in the future electronic payments are not available.</span></span> <span data-ttu-id="ee3d2-125">Andra betalningstyper är tillgängliga och bankkontot är aktivt.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-125">Other payment types are available and the bank account is active.</span></span>  
13. <span data-ttu-id="ee3d2-126">Expandera avsnittet Inställningar.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-126">Expand the Setup section.</span></span>
14. <span data-ttu-id="ee3d2-127">Skriv ett värde i fältet Textkod.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-127">In the Text code field, type a value.</span></span>
    * <span data-ttu-id="ee3d2-128">Det här fältet anger en kod som ska visas på mottagarens bankutdrag.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-128">This field specifies a code that will appear on the bank statement of the recipient.</span></span>  
15. <span data-ttu-id="ee3d2-129">Skriv ett värde i fältet Meddelande till bank.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-129">In the Message to bank field, type a value.</span></span>
16. <span data-ttu-id="ee3d2-130">Ange ett värde i fältet Kursreferens.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-130">In the Exchange reference field, type a value.</span></span>
    * <span data-ttu-id="ee3d2-131">Detta är referensnumret för terminskurser eller fasta kurser.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-131">This is the reference number for any forward-term or fixed-term rate of exchange.</span></span>  
17. <span data-ttu-id="ee3d2-132">Ange eller välj ett värde i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-132">In the Currency field, enter or select a value.</span></span>
    * <span data-ttu-id="ee3d2-133">När förauktoriseringar utfärdas ger det här avsnittet en översikt över deras status (väntande eller godkänd).</span><span class="sxs-lookup"><span data-stu-id="ee3d2-133">When prenotes are issued, this section provides an overview of their status (pending or approved).</span></span>  
18. <span data-ttu-id="ee3d2-134">Expandera avsnittet Adresser.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-134">Expand the Address section.</span></span>
19. <span data-ttu-id="ee3d2-135">Expandera avsnittet Förauktoriseringar.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-135">Expand the Prenotes section.</span></span>
20. <span data-ttu-id="ee3d2-136">Expandera avsnittet Kontaktinformation.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-136">Expand the Contact information section.</span></span>
21. <span data-ttu-id="ee3d2-137">Ange ett värde i fältet Telefon.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-137">In the Telephone field, type a value.</span></span>
22. <span data-ttu-id="ee3d2-138">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-138">Close the page.</span></span>
23. <span data-ttu-id="ee3d2-139">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-139">Click Edit.</span></span>
24. <span data-ttu-id="ee3d2-140">Expandera avsnittet Betalning.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-140">Expand the Payment section.</span></span>
25. <span data-ttu-id="ee3d2-141">Välj det konto som du nyss skapat i fältet Bankkonto.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-141">In the Bank  account field, select the account that you’ve just created.</span></span>
26. <span data-ttu-id="ee3d2-142">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-142">Click Save.</span></span>
    * <span data-ttu-id="ee3d2-143">Adressen kan ärvas från bankgruppen, om en sådan har angetts, eller så kan du lägga till den här.</span><span class="sxs-lookup"><span data-stu-id="ee3d2-143">The address may be inherited from the bank group, if one is specified, or you can add it here.</span></span>  


