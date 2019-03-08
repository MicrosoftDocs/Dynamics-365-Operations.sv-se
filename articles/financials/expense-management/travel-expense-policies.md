---
title: Definiera utgiftspolicyer
description: Du kan definiera utgiftspolicyer som dina medarbetare måste följa i samband med att de anger och skickar in utgiftsrapporter och reserekvisitioner i Microsoft Dynamics 365 for Finance and Operations.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04eaff110fea021ddee32be650be540894eb703b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "342441"
---
# <a name="expense-policies"></a><span data-ttu-id="cd3f0-103">Utgiftspolicy</span><span class="sxs-lookup"><span data-stu-id="cd3f0-103">Expense policies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cd3f0-104">Du kan definiera policyer som dina medarbetare måste följa i samband med att de anger och skickar in utgiftsrapporter och reserekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="cd3f0-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span>         
<span data-ttu-id="cd3f0-105">Om du använder utgiftsprinciper kan det hjälpa dig att hantera dina utgifter på ett effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="cd3f0-105">Implementing expense policies can help you manage expenses effectively.</span></span>         

<span data-ttu-id="cd3f0-106">Du kan till exempel ange en policy för hotellutgifter i New York, som anger att utgiften per natt inte får överstiga 250 USD.</span><span class="sxs-lookup"><span data-stu-id="cd3f0-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span>       
<span data-ttu-id="cd3f0-107">Om en anställd skickar utgiftsrapporter eller en reserekvisition där rumspriset överstiger detta belopp kommer systemet att meddela</span><span class="sxs-lookup"><span data-stu-id="cd3f0-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the</span></span>        
<span data-ttu-id="cd3f0-108">medarbetaren att policybeloppet för utgiften har överskridits.</span><span class="sxs-lookup"><span data-stu-id="cd3f0-108">worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="cd3f0-109">Du kan konfigurera det meddelande som medarbetaren får i samband med att du</span><span class="sxs-lookup"><span data-stu-id="cd3f0-109">You can configure the message that the worker will receive when you</span></span>        
<span data-ttu-id="cd3f0-110">definierar policyn.</span><span class="sxs-lookup"><span data-stu-id="cd3f0-110">define the policy.</span></span>      
        
<span data-ttu-id="cd3f0-111">Du kan definiera tre olika typer av policy:</span><span class="sxs-lookup"><span data-stu-id="cd3f0-111">You can define three types of policies:</span></span>         
        
- <span data-ttu-id="cd3f0-112">Varnings – Tillåter medarbetaren att skicka in en utgiftsrapport eller en reserekvisition, men utgiften markeras för samtliga godkännare samt</span><span class="sxs-lookup"><span data-stu-id="cd3f0-112">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>        
  <span data-ttu-id="cd3f0-113">för senare rapportering.</span><span class="sxs-lookup"><span data-stu-id="cd3f0-113">for later reporting.</span></span>        

- <span data-ttu-id="cd3f0-114">Fel – Kräver att medarbetaren reviderar utgiften så att denna uppfyller policykraven innan utgiftsrapporten eller reserekvisitionen lämnas in.</span><span class="sxs-lookup"><span data-stu-id="cd3f0-114">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span>       
 
  - <span data-ttu-id="cd3f0-115">Motivering – Kräver att medarbetaren eller en chef anger en motivering för att policybeloppet har överskridits innan utgiftsrapporten eller reserekvisitionen lämnas in.</span><span class="sxs-lookup"><span data-stu-id="cd3f0-115">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span>        
 
  <span data-ttu-id="cd3f0-116">Du kan också ange ett datumintervall för när utgiftspolicyerna är giltiga.</span><span class="sxs-lookup"><span data-stu-id="cd3f0-116">You can also set up a date range for which expense policies are in effect.</span></span> <span data-ttu-id="cd3f0-117">Exempelvis flygpriserna mellan Danmark</span><span class="sxs-lookup"><span data-stu-id="cd3f0-117">For example, airline fares for flights between Denmark</span></span>      
  <span data-ttu-id="cd3f0-118">och New York kan vara höga under semestertider.</span><span class="sxs-lookup"><span data-stu-id="cd3f0-118">and New York City can be expensive during the peak holiday travel season.</span></span> <span data-ttu-id="cd3f0-119">Du kan definiera en regel för flygpriser som begränsar</span><span class="sxs-lookup"><span data-stu-id="cd3f0-119">You can define a flight expense rule that restricts the</span></span>      
  <span data-ttu-id="cd3f0-120">kostnaden för flygbiljetter till New York till 5000 DKK och du kan ange att regeln ska gälla mellan 15 mars och</span><span class="sxs-lookup"><span data-stu-id="cd3f0-120">cost of flights to New York City to a limit of DKK 5000, and you can specify that this rule be in effect between March 15 and</span></span>      
  <span data-ttu-id="cd3f0-121">15 september.</span><span class="sxs-lookup"><span data-stu-id="cd3f0-121">September 15.</span></span>
