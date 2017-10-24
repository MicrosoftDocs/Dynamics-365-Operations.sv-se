---
title: "Bokföringskonton för avyttrande av anläggningstillgångar"
description: "Det här avsnittet innehåller information om hur du ställer in redovisningsbokföringskonton för avyttring av tillgångar."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0129eae177d44100b09c2b7bce553dd5bde5ce0c
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="fixed-asset-disposal-posting-accounts"></a><span data-ttu-id="66654-103">Bokföringskonton för avyttrande av anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="66654-103">Fixed asset disposal posting accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="66654-104">Det här avsnittet innehåller information om hur du ställer in redovisningsbokföringskonton för avyttring av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="66654-104">This article explains how to set up general ledger posting accounts for disposing of assets.</span></span>

<span data-ttu-id="66654-105">På sidan Bokföringsprofiler för anläggningstillgångar, på snabbfliken Redovisningskonto, välj Avyttrande - försäljning och Avyttrande - kassation om du vill ställa in bokföringar till redovisningen.</span><span class="sxs-lookup"><span data-stu-id="66654-105">In the Fixed asset posting profiles page, on the Ledger accounts FastTab, select Disposal - sale and Disposal - scrap to set up postings to the ledger.</span></span>

<span data-ttu-id="66654-106">För båda transaktionstyperna krediteras huvudbokskontot för anläggningstillgångens avyttringsvärde.</span><span class="sxs-lookup"><span data-stu-id="66654-106">For both transaction types, the ledger account is credited for the disposal value of the fixed asset.</span></span> <span data-ttu-id="66654-107">Debiteringen bokförs till ett motkonto, vilket exempelvis kan vara ett bankkonto.</span><span class="sxs-lookup"><span data-stu-id="66654-107">The debit is posted to an offset account, which might be, for example, a bank account.</span></span> <span data-ttu-id="66654-108">Om en anläggningstillgång säljs till en kund används kundens konto istället för motkontot.</span><span class="sxs-lookup"><span data-stu-id="66654-108">If a fixed asset is sold to a customer, the customer account is used instead of the offset account.</span></span>

<span data-ttu-id="66654-109">Klicka på Avyttrande och klicka sedan på Kassation och skapa sedan detaljerade konton för att återföra anläggningstillgångens bokförda nettovärde.</span><span class="sxs-lookup"><span data-stu-id="66654-109">Click Disposal and then click Sale or Scrap, and then set up detailed accounts to reverse the net book value of the fixed asset.</span></span> <span data-ttu-id="66654-110">Du kan även ange information i fälten för Bokför värde och Försäljningsvärdetyp i sidan Parametrar för avyttrande.</span><span class="sxs-lookup"><span data-stu-id="66654-110">You can also enter information in the Post value and Sales value type fields in the Disposal parameters page.</span></span> 

<span data-ttu-id="66654-111">Avyttrandetransaktionen för en tillgång i en lågvärdespool minskar det bokförda nettovärdet för lågvärdespoolen med enbart avyttringsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="66654-111">The disposal transaction for an asset in a low-value pool reduces the net book value of the low-value pool by the disposed amount only.</span></span> <span data-ttu-id="66654-112">När försäljningen av en tillgång är större än det bokförda nettovärdet av lågvärdespoolen, minskar emellertid det bokförda nettovärdet till noll.</span><span class="sxs-lookup"><span data-stu-id="66654-112">However, when the sale of an asset is exceeds the net book value of the low-value pool, the net book value is reduced to zero.</span></span>






