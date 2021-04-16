---
title: Felsöka åtgärder för mottagande distributionslager
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med mottagande distributionslager i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: f0ea2ee208cdbb8f9fa6668bbcb6e15252a7c1b1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828236"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a><span data-ttu-id="8703c-103">Felsöka åtgärder för mottagande distributionslager</span><span class="sxs-lookup"><span data-stu-id="8703c-103">Troubleshoot inbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8703c-104">I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med mottagande distributionslager i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="8703c-104">This topic describes how to fix common issues that you might encounter while you work with inbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a><span data-ttu-id="8703c-105">Jag får följande felmeddelande: "kvalitetsordern %1 har genererats.</span><span class="sxs-lookup"><span data-stu-id="8703c-105">I receive the following error message: "Quality order %1 has been generated.</span></span> <span data-ttu-id="8703c-106">Det gick inte att hitta klusterprofilen. Kontrollera konfigurationen."</span><span class="sxs-lookup"><span data-stu-id="8703c-106">Cluster profile could not be found please check your configuration."</span></span>

### <a name="issue-description"></a><span data-ttu-id="8703c-107">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="8703c-107">Issue description</span></span>

<span data-ttu-id="8703c-108">Det här felmeddelandet är relaterat till en mottagningsprocess där kvalitetshantering (QMS) aktiveras.</span><span class="sxs-lookup"><span data-stu-id="8703c-108">This error message is related to a receiving process where quality management (QMS) is turned on.</span></span> <span data-ttu-id="8703c-109">Beroende på konfigurationerna i din miljö kan ytterligare information om transaktionen som genererar felmeddelandet hjälpa till att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="8703c-109">Depending on the configurations in your environment, additional details about the transaction that is generating the error message might help fix the issue.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8703c-110">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="8703c-110">Issue resolution</span></span>

<span data-ttu-id="8703c-111">Granska först inställningar för [klusterplockning](set-up-cluster-picking.md) och kontrollera att dina klusterprofiler är korrekt inställda.</span><span class="sxs-lookup"><span data-stu-id="8703c-111">First, review the [cluster picking](set-up-cluster-picking.md) setup, and make sure that your cluster profiles are set up correctly.</span></span> <span data-ttu-id="8703c-112">Du kan inte använda en menyartikel för mobila enheter för klusterplockning om inte klusterprofiler har ställts in.</span><span class="sxs-lookup"><span data-stu-id="8703c-112">You can't use a mobile device menu item for cluster picking unless cluster profiles are set up.</span></span> <span data-ttu-id="8703c-113">Beroende på din miljö kan du också behöva granska andra relaterade konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="8703c-113">Depending on your environment, you might also have to review other related configurations.</span></span>

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a><span data-ttu-id="8703c-114">Inleverans av blandat ID-nummer fungerar inte för dispositionskod utom kredit.</span><span class="sxs-lookup"><span data-stu-id="8703c-114">Mixed license plate receiving doesn't work for any disposition code except Credit.</span></span>

### <a name="issue-description"></a><span data-ttu-id="8703c-115">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="8703c-115">Issue description</span></span>

<span data-ttu-id="8703c-116">När fältet **Åtgärd** för en dispositionskod är inställd på *Kredit* eller *Kassation* kan du bara använda emnyartikeln [Inleverans av blandat ID-nummer](mixed-license-plate-receiving.md) för att behandla returnerade artiklar.</span><span class="sxs-lookup"><span data-stu-id="8703c-116">When the **Action** field for a disposition code is set to *Credit* or *Scrap*, you can use only the [Mixed license plate receiving](mixed-license-plate-receiving.md) menu item to process returned items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8703c-117">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="8703c-117">Issue resolution</span></span>

<span data-ttu-id="8703c-118">Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning.</span><span class="sxs-lookup"><span data-stu-id="8703c-118">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="8703c-119">För närvarande kan endast [dispositionskoder](../service-management/set-up-disposition-codes.md) där fältet **Åtgärd** anges till *Kredit* eller *Kassation* stöds för mottagning av blandade registreringsskyltar.</span><span class="sxs-lookup"><span data-stu-id="8703c-119">Currently, only [disposition codes](../service-management/set-up-disposition-codes.md) where the **Action** field is set to *Credit* or *Scrap* are supported for mixed license plate receiving.</span></span>

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a><span data-ttu-id="8703c-120">När jag kör uppdatera produktinleveranser för en periodisk uppgift bekräftas obekräftade inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="8703c-120">When I run the Update product receipts periodic task, unconfirmed purchase orders are confirmed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="8703c-121">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="8703c-121">Issue description</span></span>

<span data-ttu-id="8703c-122">När du har kört den periodiska uppgiften *Uppdatera produktinleveranser* bekräftar systemet automatiskt obekräftade inköpsorder som har statusen för lagertransaktion *Registrerad*.</span><span class="sxs-lookup"><span data-stu-id="8703c-122">After you run the *Update product receipts* periodic task, the system automatically confirms unconfirmed purchase orders that have an inventory transaction status of *Registered*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8703c-123">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="8703c-123">Issue resolution</span></span>

<span data-ttu-id="8703c-124">En ny funktion för hantering av inkommande last *Överinleverans av lastkvantiteter* åtgärdar problemet.</span><span class="sxs-lookup"><span data-stu-id="8703c-124">A new inbound load handling feature, *Over receipt of load quantities*, fixes this issue.</span></span> <span data-ttu-id="8703c-125">För att aktivera denna funktion, gå till [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktivera följande funktioner (i den ordning de är listade i):</span><span class="sxs-lookup"><span data-stu-id="8703c-125">To turn on this feature, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the following features (in the order that they are listed in):</span></span>

1. <span data-ttu-id="8703c-126">Associera lagertransaktioner för inköpsorder med last</span><span class="sxs-lookup"><span data-stu-id="8703c-126">Associate purchase order inventory transactions with load</span></span>
1. <span data-ttu-id="8703c-127">Överinleverans av beläggningskvantiteter</span><span class="sxs-lookup"><span data-stu-id="8703c-127">Over receipt of load quantities</span></span>

<span data-ttu-id="8703c-128">Mer information finns i [bokföra registrerade produktkvantiteter mot inköpsorder](inbound-load-handling.md#post-registered-quantities).</span><span class="sxs-lookup"><span data-stu-id="8703c-128">For more information, see [Post registered product quantities against purchase orders](inbound-load-handling.md#post-registered-quantities).</span></span>

## <a name="when-i-register-inbound-orders-i-receive-the-following-error-message-the-quantity-is-not-valid"></a><span data-ttu-id="8703c-129">När jag registrerar inkommande order får jag följande felmeddelande: "Kvantiteten är inte giltig."</span><span class="sxs-lookup"><span data-stu-id="8703c-129">When I register inbound orders, I receive the following error message: "The quantity is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="8703c-130">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="8703c-130">Issue description</span></span>

<span data-ttu-id="8703c-131">Om fältet **Grupperingspolicy för ID-nummer** anges till *Användardefinierad* för ett mobilt enhetsmenyalternativ som används för att registrera inkommande beställningar får du ett felmeddelande ("Antalet är inte giltigt") och du kan inte slutföra registreringen.</span><span class="sxs-lookup"><span data-stu-id="8703c-131">If the **License plate grouping policy** field is set to *User defined* for a mobile device menu item that is used to register inbound orders, you receive an error message ("The quantity is not valid"), and you can't complete the registration.</span></span>

### <a name="issue-cause"></a><span data-ttu-id="8703c-132">Problemorsak</span><span class="sxs-lookup"><span data-stu-id="8703c-132">Issue cause</span></span>

<span data-ttu-id="8703c-133">När *Användardefinierad* används som licens för grupperingspolicy, delar systemet upp det inkommande lagret i separat ID-nummer, enligt enhetssekvensgruppen.</span><span class="sxs-lookup"><span data-stu-id="8703c-133">When *User defined* is used as a license plate grouping policy, the system splits the incoming inventory into separate license plates, as indicated by the unit sequence group.</span></span> <span data-ttu-id="8703c-134">Om batch- eller serienummer används för att spåra artikeln som levereras måste kvantiteterna för varje batch eller serienummer anges per ID-nummer den som registreras.</span><span class="sxs-lookup"><span data-stu-id="8703c-134">If batch or serial numbers are used to track the item that is being received, the quantities of each batch or serial must be specified per license plate that is registered.</span></span> <span data-ttu-id="8703c-135">Om kvantiteten som har angetts för ett ID-nummer överskrider den kvantitet som fortfarande måste tas emot för de aktuella dimensionerna, visas felmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="8703c-135">If the quantity that is specified for a license plate exceeds the quantity that must still be received for the current dimensions, you receive the error message.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8703c-136">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="8703c-136">Issue resolution</span></span>

<span data-ttu-id="8703c-137">När du registrerar ett objekt med hjälp av ett mobilt enhetsmenyalternativ där fältet **Grupperingspolicy för ID-nummer** anges till *Användardefinierad*, kan systemet kräva att du bekräftar eller anger ID-nummer, batch-nummer eller serienummer.</span><span class="sxs-lookup"><span data-stu-id="8703c-137">When you register an item by using a mobile device menu item where the **License plate grouping policy** field is set to *User defined*, the system might require that you confirm or enter license plate numbers, batch numbers, or serial numbers.</span></span>

<span data-ttu-id="8703c-138">På sidan för ID-nummer bekräftelse visar systemet den kvantitet som har tilldelats för det aktuella ID-numret.</span><span class="sxs-lookup"><span data-stu-id="8703c-138">On the license plate confirmation page, the system will show the quantity that is allocated for the current license plate.</span></span> <span data-ttu-id="8703c-139">På batch- eller seriebekräftelsesidorna visar systemet den kvantitet som fortfarande måste mottas på det aktuella ID-numret.</span><span class="sxs-lookup"><span data-stu-id="8703c-139">On the batch or serial confirmation pages, the system will show the quantity that must still be received on the current license plate.</span></span> <span data-ttu-id="8703c-140">Det kommer även att innehålla ett fält där du kan ange den kvantitet som ska registreras för kombinationen av ID- och batch- eller serienummer.</span><span class="sxs-lookup"><span data-stu-id="8703c-140">It will also include a field where you can enter the quantity to register for that combination of license plate and batch or serial number.</span></span> <span data-ttu-id="8703c-141">Se då till att kvantiteten som registreras för ID-numret inte överstiger den kvantitet som fortfarande måste tas emot.</span><span class="sxs-lookup"><span data-stu-id="8703c-141">In this case, make sure that the quantity that is being registered for the license plate doesn't exceed the quantity that must still be received.</span></span>

<span data-ttu-id="8703c-142">Alternativt, om för många ID-nummer genereras vid inkommande orderregistrering kan värdet på fältet **Grupperingspolicy för ID-nummer** ändras till *Gruppering av ID-nummer*, en ny enhetssekvensgrupp kan tilldelas objektet eller alternativet **Gruppering av ID-nummer** för enhetsseriegruppen kan inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="8703c-142">Alternatively, if too many license plates are being generated on inbound order registration, the value of the **License plate grouping policy** field can be changed to *License plate grouping*, a new unit sequence group can be assigned to the item, or the **License plate grouping** option for the unit sequence group can be inactivated.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
