---
title: Definiera ett utgångsdatum för en produktionsflödesversion
description: För att slutföra giltigheten och bearbetningen av en produktionsflödesversion ett visst datum, eller för att planera ett byte av en aktiv version mot en ny version, måste du ange ett utgångsdatum för versionen.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 87063653eb78209caaefd3fafa7783f425e710b7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257301"
---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a><span data-ttu-id="cea67-103">Definiera ett utgångsdatum för en produktionsflödesversion</span><span class="sxs-lookup"><span data-stu-id="cea67-103">Define an expiry date for a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cea67-104">För att slutföra giltigheten och bearbetningen av en produktionsflödesversion ett visst datum, eller för att planera ett byte av en aktiv version mot en ny version, måste du ange ett utgångsdatum för versionen.</span><span class="sxs-lookup"><span data-stu-id="cea67-104">To end the validity and the processing of a production flow version on a given date, or to plan replacement of an active version with a new version, you have to set an expiry date on the version.</span></span> <span data-ttu-id="cea67-105">Det är inte nödvändigt att inaktivera versionen.</span><span class="sxs-lookup"><span data-stu-id="cea67-105">It is not necessary to deactivate the version.</span></span>


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a><span data-ttu-id="cea67-106">Ange en utgångsdatum för att slutföra en produktionsflödesversion</span><span class="sxs-lookup"><span data-stu-id="cea67-106">Set an expiration date to end a production flow version</span></span>
1. <span data-ttu-id="cea67-107">Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="cea67-107">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="cea67-108">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="cea67-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="cea67-109">Markera alla produktionsflöden som har en redan definierad version.</span><span class="sxs-lookup"><span data-stu-id="cea67-109">Select any production flow that has a version that is already defined.</span></span>  
3. <span data-ttu-id="cea67-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="cea67-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="cea67-111">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="cea67-111">Click Edit.</span></span>
5. <span data-ttu-id="cea67-112">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="cea67-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="cea67-113">I fältet Utgångsdatum anger du datum och tid.</span><span class="sxs-lookup"><span data-stu-id="cea67-113">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="cea67-114">För utgångsdatumet kommer ingen ny version att startas eller aktiveras.</span><span class="sxs-lookup"><span data-stu-id="cea67-114">For the expiration date, a new version will not start or become activated.</span></span> <span data-ttu-id="cea67-115">Du kan heller inte längre skapa eller starta jobb för detta produktionsflöde.</span><span class="sxs-lookup"><span data-stu-id="cea67-115">It will also no longer be possible to create or start jobs for this production flow.</span></span> <span data-ttu-id="cea67-116">Du kan fortfarande utföra startade jobb efter utgångsdatumet.</span><span class="sxs-lookup"><span data-stu-id="cea67-116">You can still complete started jobs after the expiration date.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]