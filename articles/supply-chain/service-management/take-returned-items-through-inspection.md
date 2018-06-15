---
title: "Föra returnerade artiklar genom inspektionen"
description: "Föra returnerade artiklar genom inspektionen"
author: YuyuScheller
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: df209cfdbdef591e9f24161b3651316c43d69ee0
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---


# <a name="take-returned-items-through-inspection"></a><span data-ttu-id="16720-103">Föra returnerade artiklar genom inspektionen</span><span class="sxs-lookup"><span data-stu-id="16720-103">Take returned items through inspection</span></span> 

[!include [banner](../includes/banner.md)]


1.  <span data-ttu-id="16720-104">Klicka på **Lagerhantering** \> **Periodisk** \> **Kvalitetshantering** \> **Karantänorder**.</span><span class="sxs-lookup"><span data-stu-id="16720-104">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="16720-105">Leta upp den orderrad som motsvarar den returnerade artikel som du inspekterar.</span><span class="sxs-lookup"><span data-stu-id="16720-105">Locate the order line that corresponds to the returned item that you are inspecting.</span></span>

    > [!NOTE]
    > <P><span data-ttu-id="16720-106">En karantänorder kan bara associeras med ett enda artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="16720-106">A quarantine order can be associated with just a single item number.</span></span> <span data-ttu-id="16720-107">Om 10 artiklar med olika artikelnummer returneras i en enda leverans och skickas till karantän skapas 10 enskilda karantänorder.</span><span class="sxs-lookup"><span data-stu-id="16720-107">If 10 items that have different item numbers are returned in a single shipment and sent to quarantine, 10 individual quarantine orders are created.</span></span></P>

3.  <span data-ttu-id="16720-108">Gör ett val i fältet **Dispositionskod** om du vill ange vad som ska göras med artikeln och hur du hanterar den relaterade ekonomiska transaktionen när du har undersökt artikeln.</span><span class="sxs-lookup"><span data-stu-id="16720-108">After examining the item, make a selection in the **Disposition code** field to indicate what should be done with the item and how to handle the related financial transaction.</span></span> <span data-ttu-id="16720-109">Du kan till exempel välja att returnera artikeln till lagret och återbetala kunden, kassera artikeln och skicka ett byte till kunden eller returnera artikeln till kunden utan kredit.</span><span class="sxs-lookup"><span data-stu-id="16720-109">Examples include returning the item to stock and refunding the customer, scrapping the item and sending a replacement to the customer, or returning the item to the customer without credit.</span></span>
    
    > [!NOTE]
    > <P><span data-ttu-id="16720-110">Om samma dispositionskod inte kan anges för flera returnerade artiklar från en batch med artiklar som har samma artikelnummer, måste du dela karantänordern (<STRONG>Funktioner</STRONG> &gt; <STRONG>Dela</STRONG>) för att kunna tilldela olika dispositionskoder till varje delbatch.</span><span class="sxs-lookup"><span data-stu-id="16720-110">If multiple returned items in a single item number batch cannot be assigned the same disposition code, you must split the quarantine order (<STRONG>Functions</STRONG> &gt; <STRONG>Split</STRONG>) to assign a different disposition code to each sub-batch.</span></span></P>


4.  <span data-ttu-id="16720-111">När du är klar med inspektionen klickar du på **Rapportera som färdigt** för att släppa de returnerade artiklarna och skapa en post i en artikelinförseljournal.</span><span class="sxs-lookup"><span data-stu-id="16720-111">When you are finished with the inspection, click **Report as finished** to release the returned items and create an item arrival journal entry.</span></span> <span data-ttu-id="16720-112">Den person eller avdelning som tar emot artiklarna bearbetar sedan journalen för att artiklarna ska kunna returneras till lagret.</span><span class="sxs-lookup"><span data-stu-id="16720-112">The person or department that receives the items then processes the journal for the items to be returned to inventory.</span></span>
    
    <span data-ttu-id="16720-113">–eller–</span><span class="sxs-lookup"><span data-stu-id="16720-113">–or–</span></span>
    
    <span data-ttu-id="16720-114">Avsluta karantänordern och flytta tillbaka artiklarna till lagret direkt med någon av knappfunktionerna för **Lager**.</span><span class="sxs-lookup"><span data-stu-id="16720-114">End the quarantine order, and move the items back into inventory directly by using one of the **Inventory** functions.</span></span>

5.  <span data-ttu-id="16720-115">Stäng formuläret så att ändringarna sparas.</span><span class="sxs-lookup"><span data-stu-id="16720-115">Close the form to save your changes.</span></span>

## <a name="see-also"></a><span data-ttu-id="16720-116">Se även</span><span class="sxs-lookup"><span data-stu-id="16720-116">See also</span></span>

[<span data-ttu-id="16720-117">Ange hur returnerade artiklar ska avyttras</span><span class="sxs-lookup"><span data-stu-id="16720-117">Specify how to dispose of returned items</span></span>](specify-how-to-dispose-of-returned-items.md)

  


