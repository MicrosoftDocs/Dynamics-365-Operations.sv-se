---
title: Felsöka åtgärder för mottagande distributionslager
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med mottagande distributionslager i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 71f590ec01b757de298bd2692fdbdb0324843376
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970266"
---
# <a name="troubleshoot-inbound-warehouse-operations"></a><span data-ttu-id="a37cf-103">Felsöka åtgärder för mottagande distributionslager</span><span class="sxs-lookup"><span data-stu-id="a37cf-103">Troubleshoot inbound warehouse operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a37cf-104">I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med mottagande distributionslager i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a37cf-104">This topic describes how to fix common issues that you might encounter while you work with inbound warehouse operations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-quality-order-1-has-been-generated-cluster-profile-could-not-be-found-please-check-your-configuration"></a><span data-ttu-id="a37cf-105">Jag får följande felmeddelande: "kvalitetsordern %1 har genererats.</span><span class="sxs-lookup"><span data-stu-id="a37cf-105">I receive the following error message: "Quality order %1 has been generated.</span></span> <span data-ttu-id="a37cf-106">Det gick inte att hitta klusterprofilen. Kontrollera konfigurationen."</span><span class="sxs-lookup"><span data-stu-id="a37cf-106">Cluster profile could not be found please check your configuration."</span></span>

### <a name="issue-description"></a><span data-ttu-id="a37cf-107">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="a37cf-107">Issue description</span></span>

<span data-ttu-id="a37cf-108">Det här felmeddelandet är relaterat till en mottagningsprocess där kvalitetshantering (QMS) aktiveras.</span><span class="sxs-lookup"><span data-stu-id="a37cf-108">This error message is related to a receiving process where quality management (QMS) is turned on.</span></span> <span data-ttu-id="a37cf-109">Beroende på konfigurationerna i din miljö kan ytterligare information om transaktionen som genererar felmeddelandet hjälpa till att åtgärda problemet.</span><span class="sxs-lookup"><span data-stu-id="a37cf-109">Depending on the configurations in your environment, additional details about the transaction that is generating the error message might help fix the issue.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a37cf-110">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="a37cf-110">Issue resolution</span></span>

<span data-ttu-id="a37cf-111">Granska först inställningar för [klusterplockning](set-up-cluster-picking.md) och kontrollera att dina klusterprofiler är korrekt inställda.</span><span class="sxs-lookup"><span data-stu-id="a37cf-111">First, review the [cluster picking](set-up-cluster-picking.md) setup, and make sure that your cluster profiles are set up correctly.</span></span> <span data-ttu-id="a37cf-112">Du kan inte använda en menyartikel för mobila enheter för klusterplockning om inte klusterprofiler har ställts in.</span><span class="sxs-lookup"><span data-stu-id="a37cf-112">You can't use a mobile device menu item for cluster picking unless cluster profiles are set up.</span></span> <span data-ttu-id="a37cf-113">Beroende på din miljö kan du också behöva granska andra relaterade konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="a37cf-113">Depending on your environment, you might also have to review other related configurations.</span></span>

## <a name="mixed-license-plate-receiving-doesnt-work-for-any-disposition-code-except-credit"></a><span data-ttu-id="a37cf-114">Inleverans av blandat ID-nummer fungerar inte för dispositionskod utom kredit.</span><span class="sxs-lookup"><span data-stu-id="a37cf-114">Mixed license plate receiving doesn't work for any disposition code except Credit.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a37cf-115">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="a37cf-115">Issue description</span></span>

<span data-ttu-id="a37cf-116">När fältet **Åtgärd** för en dispositionskod är inställd på *Kredit* eller *Kassation* kan du bara använda emnyartikeln [Inleverans av blandat ID-nummer](mixed-license-plate-receiving.md) för att behandla returnerade artiklar.</span><span class="sxs-lookup"><span data-stu-id="a37cf-116">When the **Action** field for a disposition code is set to *Credit* or *Scrap*, you can use only the [Mixed license plate receiving](mixed-license-plate-receiving.md) menu item to process returned items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a37cf-117">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="a37cf-117">Issue resolution</span></span>

<span data-ttu-id="a37cf-118">Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning.</span><span class="sxs-lookup"><span data-stu-id="a37cf-118">Microsoft has evaluated this issue and has determined that it's a feature limitation.</span></span> <span data-ttu-id="a37cf-119">För närvarande kan endast [dispositionskoder](../service-management/set-up-disposition-codes.md) där fältet **Åtgärd** anges till *Kredit* eller *Kassation* stöds för mottagning av blandade registreringsskyltar.</span><span class="sxs-lookup"><span data-stu-id="a37cf-119">Currently, only [disposition codes](../service-management/set-up-disposition-codes.md) where the **Action** field is set to *Credit* or *Scrap* are supported for mixed license plate receiving.</span></span>

## <a name="when-i-run-the-update-product-receipts-periodic-task-unconfirmed-purchase-orders-are-confirmed"></a><span data-ttu-id="a37cf-120">När jag kör uppdatera produktinleveranser för en periodisk uppgift bekräftas obekräftade inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="a37cf-120">When I run the Update product receipts periodic task, unconfirmed purchase orders are confirmed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="a37cf-121">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="a37cf-121">Issue description</span></span>

<span data-ttu-id="a37cf-122">När du har kört den periodiska uppgiften *Uppdatera produktinleveranser* bekräftar systemet automatiskt obekräftade inköpsorder som har statusen för lagertransaktion *Registrerad*.</span><span class="sxs-lookup"><span data-stu-id="a37cf-122">After you run the *Update product receipts* periodic task, the system automatically confirms unconfirmed purchase orders that have an inventory transaction status of *Registered*.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="a37cf-123">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="a37cf-123">Issue resolution</span></span>

<span data-ttu-id="a37cf-124">En ny funktion för hantering av inkommande last *Överinleverans av lastkvantiteter* åtgärdar problemet.</span><span class="sxs-lookup"><span data-stu-id="a37cf-124">A new inbound load handling feature, *Over receipt of load quantities*, fixes this issue.</span></span> <span data-ttu-id="a37cf-125">För att aktivera denna funktion, gå till [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktivera följande funktioner (i den ordning de är listade i):</span><span class="sxs-lookup"><span data-stu-id="a37cf-125">To turn on this feature, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), and turn on the following features (in the order that they are listed in):</span></span>

1. <span data-ttu-id="a37cf-126">Associera lagertransaktioner för inköpsorder med last</span><span class="sxs-lookup"><span data-stu-id="a37cf-126">Associate purchase order inventory transactions with load</span></span>
1. <span data-ttu-id="a37cf-127">Överinleverans av beläggningskvantiteter</span><span class="sxs-lookup"><span data-stu-id="a37cf-127">Over receipt of load quantities</span></span>

<span data-ttu-id="a37cf-128">Mer information finns i [bokföra registrerade produktkvantiteter mot inköpsorder](inbound-load-handling.md#post-registered-quantities).</span><span class="sxs-lookup"><span data-stu-id="a37cf-128">For more information, see [Post registered product quantities against purchase orders](inbound-load-handling.md#post-registered-quantities).</span></span>
