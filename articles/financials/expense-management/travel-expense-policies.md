---
title: Definiera utgiftspolicyer
description: "Du kan definiera utgiftspolicyer som dina medarbetare måste följa i samband med att de anger och skickar in utgiftsrapporter och reserekvisitioner i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition."
author: saraschi2
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi2
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 63bf043124797b328116fd7951913eaeda6ff97b
ms.openlocfilehash: e04fae56cf0ed988b267477ba1ed327e8e8f72c0
ms.contentlocale: sv-se
ms.lasthandoff: 01/12/2018

---

# <a name="expense-policies"></a><span data-ttu-id="0fdff-103">Utgiftspolicy</span><span class="sxs-lookup"><span data-stu-id="0fdff-103">Expense policies</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0fdff-104">Du kan definiera policyer som dina medarbetare måste följa i samband med att de anger och skickar in utgiftsrapporter och reserekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="0fdff-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span> <span data-ttu-id="0fdff-105">Om du använder utgiftsprinciper kan det hjälpa dig att hantera dina utgifter på ett effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="0fdff-105">Implementing expense policies can help you manage expenses effectively.</span></span> 

<span data-ttu-id="0fdff-106">Du kan till exempel ange en policy för hotellutgifter i New York, som anger att utgiften per natt inte får överstiga 250 USD.</span><span class="sxs-lookup"><span data-stu-id="0fdff-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span> <span data-ttu-id="0fdff-107">Om en medarbetare skickar in en utgiftsrapport eller en reserekvisition där rumstaxan överstiger detta belopp, kommer systemet att meddela medarbetaren att policybeloppet för utgiften har överskridits.</span><span class="sxs-lookup"><span data-stu-id="0fdff-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="0fdff-108">Du kan konfigurera det meddelande som medarbetaren får i samband med att du definierar policyn.</span><span class="sxs-lookup"><span data-stu-id="0fdff-108">You can configure the message that the worker will receive when you define the policy.</span></span> 

<span data-ttu-id="0fdff-109">Du kan definiera tre olika typer av policy:</span><span class="sxs-lookup"><span data-stu-id="0fdff-109">You can define three types of policies:</span></span> 

 - <span data-ttu-id="0fdff-110">Varnings – Tillåter medarbetaren att skicka in en utgiftsrapport eller en reserekvisition, men utgiften markeras för samtliga godkännare samt</span><span class="sxs-lookup"><span data-stu-id="0fdff-110">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>  
 <span data-ttu-id="0fdff-111">för senare rapportering.</span><span class="sxs-lookup"><span data-stu-id="0fdff-111">for later reporting.</span></span> 
 - <span data-ttu-id="0fdff-112">Fel – Kräver att medarbetaren reviderar utgiften så att denna uppfyller policykraven innan utgiftsrapporten eller reserekvisitionen lämnas in.</span><span class="sxs-lookup"><span data-stu-id="0fdff-112">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span> 
 - <span data-ttu-id="0fdff-113">Motivering – Kräver att medarbetaren eller en chef anger en motivering för att policybeloppet har överskridits innan utgiftsrapporten eller reserekvisitionen lämnas in.</span><span class="sxs-lookup"><span data-stu-id="0fdff-113">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span> 

<span data-ttu-id="0fdff-114">Du kan också ange ett datumintervall för när utgiftspolicyerna är giltiga.</span><span class="sxs-lookup"><span data-stu-id="0fdff-114">You can also set up a date range for which expense policies are in effect.</span></span> <span data-ttu-id="0fdff-115">Exempelvis kan flygpriserna mellan Sverige och New York vara höga under semestertider.</span><span class="sxs-lookup"><span data-stu-id="0fdff-115">For example, airline fares for flights between Denmark and New York City can be expensive during the peak holiday travel season.</span></span> <span data-ttu-id="0fdff-116">Du kan definiera en regel för flygutgifter som begränsar flygkostnaderna till New York till 5 000 DKK, och du kan även ange att denna regel ska vara giltig mellan den 15 mars och den 15 september.</span><span class="sxs-lookup"><span data-stu-id="0fdff-116">You can define a flight expense rule that restricts the cost of flights to New York City to a limit of DKK 5000, and you can specify that this rule be in effect between March 15 and September 15.</span></span> 

