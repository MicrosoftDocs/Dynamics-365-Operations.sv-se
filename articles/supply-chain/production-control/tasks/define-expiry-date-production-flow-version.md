--- 
title: "Definiera ett utgångsdatum för en produktionsflödesversion"
description: "För att slutföra giltigheten och bearbetningen av en produktionsflödesversion ett visst datum, eller för att planera ett byte av en aktiv version mot en ny version, måste du ange ett utgångsdatum för versionen."
author: cvocph
manager: AnnBe
ms.date: 10/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6fabeb31720a60bf97d08dabf8ed87ac6af7cbf7
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a><span data-ttu-id="f4422-103">Definiera ett utgångsdatum för en produktionsflödesversion</span><span class="sxs-lookup"><span data-stu-id="f4422-103">Define an expiry date for a production flow version</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f4422-104">För att slutföra giltigheten och bearbetningen av en produktionsflödesversion ett visst datum, eller för att planera ett byte av en aktiv version mot en ny version, måste du ange ett utgångsdatum för versionen.</span><span class="sxs-lookup"><span data-stu-id="f4422-104">To end the validity and the processing of a production flow version on a given date, or to plan replacement of an active version with a new version, you have to set an expiry date on the version.</span></span> <span data-ttu-id="f4422-105">Det är inte nödvändigt att inaktivera versionen.</span><span class="sxs-lookup"><span data-stu-id="f4422-105">It is not necessary to deactivate the version.</span></span>


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a><span data-ttu-id="f4422-106">Ange en utgångsdatum för att slutföra en produktionsflödesversion</span><span class="sxs-lookup"><span data-stu-id="f4422-106">Set an expiration date to end a production flow version</span></span>
1. <span data-ttu-id="f4422-107">Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="f4422-107">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="f4422-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f4422-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f4422-109">Markera alla produktionsflöden som har en redan definierad version.</span><span class="sxs-lookup"><span data-stu-id="f4422-109">Select any production flow that has a version that is already defined.</span></span>  
3. <span data-ttu-id="f4422-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f4422-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="f4422-111">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="f4422-111">Click Edit.</span></span>
5. <span data-ttu-id="f4422-112">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="f4422-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="f4422-113">I fältet Utgångsdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="f4422-113">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="f4422-114">För utgångsdatumet kommer ingen ny version att startas eller aktiveras.</span><span class="sxs-lookup"><span data-stu-id="f4422-114">For the expiration date, a new version will not start or become activated.</span></span> <span data-ttu-id="f4422-115">Du kan heller inte längre skapa eller starta jobb för detta produktionsflöde.</span><span class="sxs-lookup"><span data-stu-id="f4422-115">It will also no longer be possible to create or start jobs for this production flow.</span></span> <span data-ttu-id="f4422-116">Du kan fortfarande utföra startade jobb efter utgångsdatumet.</span><span class="sxs-lookup"><span data-stu-id="f4422-116">You can still complete started jobs after the expiration date.</span></span>  


