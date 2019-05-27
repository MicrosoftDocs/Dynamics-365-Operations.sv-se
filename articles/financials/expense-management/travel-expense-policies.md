---
title: Definiera utgiftspolicyer
description: Du kan definiera utgiftspolicyer som dina medarbetare måste följa i samband med att de anger och skickar in utgiftsrapporter och reserekvisitioner i Microsoft Dynamics 365 for Finance and Operations.
author: ryansandness
manager: AnnBe
ms.date: 04/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, TrvPolicyRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f0ff56f0ff106bc168b6a27612e08743a539a07
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1514449"
---
# <a name="expense-policies"></a><span data-ttu-id="b640b-103">Utgiftspolicy</span><span class="sxs-lookup"><span data-stu-id="b640b-103">Expense policies</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b640b-104">Du kan definiera policyer som dina medarbetare måste följa i samband med att de anger och skickar in utgiftsrapporter och reserekvisitioner.</span><span class="sxs-lookup"><span data-stu-id="b640b-104">You can define policies that your workers must follow when entering and submitting expense reports and travel requisitions.</span></span>         
<span data-ttu-id="b640b-105">Om du använder utgiftsprinciper kan det hjälpa dig att hantera dina utgifter på ett effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="b640b-105">Implementing expense policies can help you manage expenses effectively.</span></span>         

<span data-ttu-id="b640b-106">Du kan till exempel ange en policy för hotellutgifter i New York, som anger att utgiften per natt inte får överstiga 250 USD.</span><span class="sxs-lookup"><span data-stu-id="b640b-106">For example, you can set a policy for hotel expenses in New York City, which states that the per night expense cannot exceed USD 250.</span></span>       
<span data-ttu-id="b640b-107">Om en anställd skickar utgiftsrapporter eller en reserekvisition där rumspriset överstiger detta belopp kommer systemet att meddela</span><span class="sxs-lookup"><span data-stu-id="b640b-107">If a worker submits an expense report or a travel requisition in which the room rate exceeds this amount, the system will notify the</span></span>        
<span data-ttu-id="b640b-108">medarbetaren att policybeloppet för utgiften har överskridits.</span><span class="sxs-lookup"><span data-stu-id="b640b-108">worker that the policy amount for the expense has been exceeded.</span></span> <span data-ttu-id="b640b-109">Du kan konfigurera det meddelande som medarbetaren får i samband med att du</span><span class="sxs-lookup"><span data-stu-id="b640b-109">You can configure the message that the worker will receive when you</span></span>        
<span data-ttu-id="b640b-110">definierar policyn.</span><span class="sxs-lookup"><span data-stu-id="b640b-110">define the policy.</span></span>      
        
<span data-ttu-id="b640b-111">Du kan definiera tre olika typer av policy:</span><span class="sxs-lookup"><span data-stu-id="b640b-111">You can define three types of policies:</span></span>         
        
- <span data-ttu-id="b640b-112">Varnings – Tillåter medarbetaren att skicka in en utgiftsrapport eller en reserekvisition, men utgiften markeras för samtliga godkännare samt</span><span class="sxs-lookup"><span data-stu-id="b640b-112">Warning – Allows the worker to submit an expense report or travel requisition but the expense will be marked for all approvers and</span></span>        
  <span data-ttu-id="b640b-113">för senare rapportering.</span><span class="sxs-lookup"><span data-stu-id="b640b-113">for later reporting.</span></span>        

- <span data-ttu-id="b640b-114">Fel – Kräver att medarbetaren reviderar utgiften så att denna uppfyller policykraven innan utgiftsrapporten eller reserekvisitionen lämnas in.</span><span class="sxs-lookup"><span data-stu-id="b640b-114">Error – Requires the worker to revise the expense to comply with the policy before submitting the expense report or travel requisition.</span></span>       
 
 - <span data-ttu-id="b640b-115">Motivering – Kräver att medarbetaren eller en chef anger en motivering för att policybeloppet har överskridits innan utgiftsrapporten eller reserekvisitionen lämnas in.</span><span class="sxs-lookup"><span data-stu-id="b640b-115">Justification – Requires the worker or a manager to enter a justification for exceeding the policy amount before submitting the expense report or travel requisition.</span></span>        

# <a name="policy-tips"></a><span data-ttu-id="b640b-116">Policytips</span><span class="sxs-lookup"><span data-stu-id="b640b-116">Policy tips</span></span>
<span data-ttu-id="b640b-117">Här är några förslag som kan hjälpa dig när du skapar nya policyer för kostnadshantering.</span><span class="sxs-lookup"><span data-stu-id="b640b-117">Here are a few suggestions that can assist you whe creating new policies for expense management.</span></span> 
* <span data-ttu-id="b640b-118">Principer är giltighetsdatum och börjar inte gälla om policyn skapas med ett datum efter det datum då kostnaden inträffade.</span><span class="sxs-lookup"><span data-stu-id="b640b-118">Policies are date effective and won't take effect if the policy is created with a date after the date that the expense occurred.</span></span> <span data-ttu-id="b640b-119">Om du till exempel skapar en ny policy idag för att upprätthålla en maximal måltidskostnaden av 50 USD, kontrolleras inte alla befintliga utgifter som anges i igår mot den här policy.</span><span class="sxs-lookup"><span data-stu-id="b640b-119">For example, if you are creating a new policy today to enforce a maximum meal expense of $50, then any existing expenses entered as of yesterday won't be checked against this policy.</span></span>
* <span data-ttu-id="b640b-120">När du skapar en policy för en utgiftskategori som kan specificeras, bör du lägga till ett villkor för utgiftsradtypen.</span><span class="sxs-lookup"><span data-stu-id="b640b-120">When creating a policy for an expense category that can be itemized, consider adding a condition for expense line type.</span></span> <span data-ttu-id="b640b-121">Vissa policyer t.ex. krav på inleverans, kanske inte stämmer överens med specificerade rader och ska bara användas på rubrikraden eller en rad som inte har specificerats.</span><span class="sxs-lookup"><span data-stu-id="b640b-121">Some policies such as requiring a receipt may not make sense for itemized lines and should only be applied to the header line or a non-itemized line.</span></span> 

# <a name="when-to-evaluate-policies"></a><span data-ttu-id="b640b-122">När policyer ska utvärderas</span><span class="sxs-lookup"><span data-stu-id="b640b-122">When to evaluate policies</span></span>

<span data-ttu-id="b640b-123">I parametrar för utgiftshantering finns det ett alternativ som antingen utvärderar utgiftshanteringspolicyer när en rad sparas eller när en utgiftsrapport skickas.</span><span class="sxs-lookup"><span data-stu-id="b640b-123">In expense management parameters, there is an option to either evaluate expense management policies when a line is saved or when an expense report is submitted.</span></span> <span data-ttu-id="b640b-124">Om du väljer att utvärdera när en rad sparas ser du till att användarna har tidigare insyn i vad de behöver göra för att slutföra sina utgiftsrapporter samtidigt.</span><span class="sxs-lookup"><span data-stu-id="b640b-124">If you choose to evaluate when a line is saved this ensures that users have earlier visibility into what they need to do to complete their expense report all at once.</span></span> <span data-ttu-id="b640b-125">Annars kan du fördröja policyutvärdering och spara tid om du har validering inträffat i slutet, under inlämning till arbetsflödet.</span><span class="sxs-lookup"><span data-stu-id="b640b-125">Otherwise, you can delay policy evaluation and save time if you have validation occur at the end, during submission to workflow.</span></span>
