---
title: Sömlös offline-växlare för presentkort och kreditnotor
description: Det här ämnet innehåller en översikt över förbättringar som ger en sömlös offline-växel för specifika betalningstyper.
author: rubendel
ms.date: 02/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 20120-02-28
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 47867447e6d16a0fb4542c17ab184068300b2c1c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019967"
---
# <a name="seamless-offline-switch-for-gift-card-and-credit-memo-operations"></a><span data-ttu-id="6cfe8-103">Sömlös offline-växlare för presentkort och kreditnotor</span><span class="sxs-lookup"><span data-stu-id="6cfe8-103">Seamless offline switch for gift card and credit memo operations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6cfe8-104">Om en kassaenhet (POS) förlorar sin anslutning till kanaldatabasen, kan de flesta kassaoperationer och transaktioner som pågår fortsätta efter att kassören har fått ett varningsmeddelande om att anslutningen bryts.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-104">If a point of sale (POS) device loses its connection to the channel database, most POS operations and transactions that were in progress can proceed after the cashier receives a warning message about the loss of connectivity.</span></span> <span data-ttu-id="6cfe8-105">I vissa fall har transaktioner emellertid element som är beroende av realtidsservice och dessa element stöds inte när kassan.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-105">However, in some cases, transactions have elements that rely on the real-time service, and those elements aren't supported when the POS is offline.</span></span> <span data-ttu-id="6cfe8-106">I det här avsnittet beskrivs vissa funktioner som hjälper dig att minska den förlorade anslutningen i dessa scenarier.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-106">This topic describes some functionality that helps reduce the impact of lost connectivity in these scenarios.</span></span>

## <a name="completing-gift-card-transactions-in-offline-mode"></a><span data-ttu-id="6cfe8-107">Slutför presentkortstransaktioner i offlineläge</span><span class="sxs-lookup"><span data-stu-id="6cfe8-107">Completing gift card transactions in offline mode</span></span>

<span data-ttu-id="6cfe8-108">Interna presentkort är beroende av realtidsservice, eftersom saldot för presentkort måste hanteras centralt i Microsoft Dynamics 365 Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-108">Internal gift cards depend on the real-time service, because the balance for the gift cards must be centrally maintained in Microsoft Dynamics 365 Commerce Headquarters.</span></span> <span data-ttu-id="6cfe8-109">För att förhindra bedrägerier eller andra synkroniseringsproblem låses presentkort så snart de har lagts till i en transaktion.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-109">To help prevent fraud or other synchronization issues, gift cards are locked as soon as they are added to a transaction.</span></span> <span data-ttu-id="6cfe8-110">Låsfunktionen ser till att ett presentkort inte kan användas på flera terminaler samtidigt.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-110">The locking function ensures that a gift card can't be used on multiple terminals at the same time.</span></span> <span data-ttu-id="6cfe8-111">När transaktionen har slutförts uppdateras presentkortet och tas bort.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-111">When a transaction is completed, the gift card is updated and unlocked.</span></span>

<span data-ttu-id="6cfe8-112">Om kassan förlorar anslutningen efter att ett presentkort har lagts till i en transaktion, kan det dock bli oanvändbart.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-112">However, if the POS loses connectivity after a gift card has been added to a transaction, the gift card can become unusable.</span></span> <span data-ttu-id="6cfe8-113">För att förhindra att den här situationen har Dynamics 365 Commerce en parameter som aktiverar transaktioner som inkluderar en presentkortsrad som ska slutföras medan kassan är offline.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-113">To help prevent this situation, Dynamics 365 Commerce has a parameter that enables transactions that include a gift card line to be completed while the POS is offline.</span></span> <span data-ttu-id="6cfe8-114">När den här parametern är aktiverad sparas presentkortstransaktioner som tvingas offline tillsammans med offline-transaktioner och de synkroniseras till Commerce-administration när offline-transaktioner synkroniseras.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-114">When this parameter is turned on, gift card transactions that are forced offline will be saved together with offline transactions, and they will be synced to Commerce Headquarters when the offline transactions are synced.</span></span> <span data-ttu-id="6cfe8-115">Synkroniseringen låser även upp presentkortet så att det kan användas i en annan terminal.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-115">The synchronization will also unlock the gift card so that it can be used at another terminal.</span></span>

<span data-ttu-id="6cfe8-116">Om du vill att funktionen ska ingå presentkortstransaktioner efter att du växlat till offlineläge, gå till fliken **Bokföring** på sidan **Commerce-parametrar**.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-116">To enable the functionality to conclude gift card transactions after switching to offline mode, go to the **Posting** tab on the **Commerce parameters** page.</span></span> <span data-ttu-id="6cfe8-117">På den fliken letar du upp snabbfliken **presentkort** och ställer in **Tillåt presentkortstransaktioner i offlineläge** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-117">On that tab, locate the **Gift card** fasttab and set **Allow concluding gift card transactions in offline mode** to **Yes**.</span></span>

![Presentkortsinställning för offline](../media/gift.png)

<span data-ttu-id="6cfe8-119">Commerce-parametrar cachelagras normalt.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-119">Commerce parameters are typically cached.</span></span> <span data-ttu-id="6cfe8-120">När den här parametern har uppdaterats och distributionsplanen har initierats för att synkronisera ändringen till kanalen, kan ändringen därför ta upp till 24 timmar innan ändringen börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-120">Therefore, after the setting of this parameter is updated, and the distribution schedule is initiated to sync the change to the channel, the change can take up to 24 hours to take effect.</span></span> <span data-ttu-id="6cfe8-121">Återställ Microsoft Internet Information Services (IIS) om du vill att ändringen ska börja gälla omedelbart.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-121">To make the change effective immediately, reset Microsoft Internet Information Services (IIS).</span></span>

## <a name="completing-credit-memo-transactions-in-offline-mode"></a><span data-ttu-id="6cfe8-122">Slutför transaktioner för kreditnota i offlineläge</span><span class="sxs-lookup"><span data-stu-id="6cfe8-122">Completing credit memo transactions in offline mode</span></span>

<span data-ttu-id="6cfe8-123">Precis som interna presentkort underhålls kreditnotor centralt i Commerce-administration.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-123">Like internal gift cards, credit memos are centrally maintained in Commerce Headquarters.</span></span> <span data-ttu-id="6cfe8-124">Commerce har en parameter som gör att transaktioner för kreditnota kan slutföras medan kassan är offline.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-124">Commerce has a parameter that enables credit memo transactions to be completed while the POS is offline.</span></span> <span data-ttu-id="6cfe8-125">Den här parametern fungerar som den presentkortsparameter som nämndes i föregående avsnitt.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-125">This parameter works like the gift card parameter that was mentioned in the previous section.</span></span> <span data-ttu-id="6cfe8-126">När parametern aktiveras synkroniseras de transaktioner för kreditnota som försätts i offlineläge till kanaldatabasen, tillsammans med andra transaktioner som utfördes medan kassan var offline.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-126">When the parameter is turned on, credit memo transactions that are forced offline will be synced back to the channel database, together with other transactions that were performed while the POS was offline.</span></span>

<span data-ttu-id="6cfe8-127">Om du vill att funktionen ska ingå transaktioner för kreditnota efter att du växlat till offlineläge, gå till fliken **Bokföring** på sidan **Commerce-parametrar**.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-127">To enable the functionality to conclude credit memo transactions after switching to offline mode, go to the **Posting** tab on the **Commerce parameters** page.</span></span> <span data-ttu-id="6cfe8-128">På den fliken letar du upp snabbfliken **kreditnota** och ställer in **Tillåt transaktioner för kreditnota i offlineläge** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-128">On that tab, locate the **Credit memo** fasttab and set **Allow concluding credit memo transactions in offline mode** to **Yes**.</span></span>

![Inställning för kreditnota offline](../media/creditmemo.png)

<span data-ttu-id="6cfe8-130">Commerce-parametrar cachelagras normalt.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-130">Commerce parameters are typically cached.</span></span> <span data-ttu-id="6cfe8-131">När den här parametern har uppdaterats och distributionsplanen har initierats för att synkronisera ändringen till kanalen, kan ändringen därför ta upp till 24 timmar innan ändringen börjar gälla.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-131">Therefore, after the setting of this parameter is updated, and the distribution schedule is initiated to sync the change to the channel, the change can take up to 24 hours to take effect.</span></span> <span data-ttu-id="6cfe8-132">Återställ IIS om du vill att ändringen ska börja gälla omedelbart.</span><span class="sxs-lookup"><span data-stu-id="6cfe8-132">To make the change effective immediately, reset IIS.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6cfe8-133">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="6cfe8-133">Related topics</span></span>

- [<span data-ttu-id="6cfe8-134">Offline kassafunktionalitet (POS)</span><span class="sxs-lookup"><span data-stu-id="6cfe8-134">Offline point of sale (POS) functionality</span></span>](../pos-offline-functionality.md)
- [<span data-ttu-id="6cfe8-135">Verksamhet för online- och offlinekassor (POS)</span><span class="sxs-lookup"><span data-stu-id="6cfe8-135">Online and offline point of sale (POS) operations</span></span>](../pos-operations.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]