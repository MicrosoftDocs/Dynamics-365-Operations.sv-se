---
title: Pausa och återuppta en transaktion i kassan
description: Det här avsnittet beskriver hur användare kan avbryta pågående transaktioner och sedan återuppta dem senare eller i en annan kassa med Microsoft Dynamics 365 for Retail.
author: jblucher
manager: AnnBe
ms.date: 11/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: ffb04609318c7de4b9ef729a8e03a7f9395806b8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "333908"
---
# <a name="suspend-and-resume-transactions-in-the-point-of-sale-pos"></a><span data-ttu-id="4c032-103">Pausa och återuppta transaktioner i kassan</span><span class="sxs-lookup"><span data-stu-id="4c032-103">Suspend and resume transactions in the point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="4c032-104">Kassaanvändare kan avbryta pågående transaktioner och återuppta dem senare, eller i en annan kassa.</span><span class="sxs-lookup"><span data-stu-id="4c032-104">Point of sale (POS) users can suspend in-progress transactions, and then resume them later or on a different register.</span></span> <span data-ttu-id="4c032-105">Transaktioner avbryts ofta för att snabbt frigöra en kassa för en annan uppgift utan att förlora några framsteg på den aktuella transaktionen.</span><span class="sxs-lookup"><span data-stu-id="4c032-105">Transactions are often suspended to quickly free up a register for a different task without losing any progress on the current transaction.</span></span> <span data-ttu-id="4c032-106">Till exempel n butiksmedarbetare påbörjar behandlingen av en kundtransaktion på en mobil enhet men måste utföra i en kassa med en kassalåda.</span><span class="sxs-lookup"><span data-stu-id="4c032-106">For example, a store associate starts to process a customer's transaction on a mobile device but must complete it on a register that has a cash drawer.</span></span> <span data-ttu-id="4c032-107">I det här fallet kan butiksmedarbetaren pausa transaktionen på mobilenheten och sedan återkalla och återuppta den i en kassa.</span><span class="sxs-lookup"><span data-stu-id="4c032-107">In this case, the store associate can suspend the transaction on the mobile device, and then recall and resume it on a register.</span></span>

## <a name="configure-suspend-and-resume-functionality"></a><span data-ttu-id="4c032-108">Konfigurera funktioner för att pausa och återuppta</span><span class="sxs-lookup"><span data-stu-id="4c032-108">Configure suspend and resume functionality</span></span>

### <a name="pos-operations"></a><span data-ttu-id="4c032-109">POS-operationer</span><span class="sxs-lookup"><span data-stu-id="4c032-109">POS operations</span></span>

<span data-ttu-id="4c032-110">Två [kassaoperationer](pos-operations.md) låter kassan ge stöd för att pausa och återuppta scenarier.</span><span class="sxs-lookup"><span data-stu-id="4c032-110">Two [POS operations](pos-operations.md) let the POS support suspend and resume scenarios.</span></span> <span data-ttu-id="4c032-111">Du kan tilldela dessa operationer som [knappsatser](pos-screen-layouts.md) på transaktionssidan eller välkomstsidan.</span><span class="sxs-lookup"><span data-stu-id="4c032-111">You can assign these operations to [button grids](pos-screen-layouts.md) on the transaction page or the welcome page.</span></span>

- <span data-ttu-id="4c032-112">503: Pausa transaction</span><span class="sxs-lookup"><span data-stu-id="4c032-112">503: Suspend transaction</span></span>
- <span data-ttu-id="4c032-113">504: Återkalla transaktion</span><span class="sxs-lookup"><span data-stu-id="4c032-113">504: Recall transaction</span></span>

### <a name="receipt-template"></a><span data-ttu-id="4c032-114">Kvittomall</span><span class="sxs-lookup"><span data-stu-id="4c032-114">Receipt template</span></span>

<span data-ttu-id="4c032-115">Kassan kan konfigureras för att generera ett utskrivet kvitto om en transaktion avbryts.</span><span class="sxs-lookup"><span data-stu-id="4c032-115">The POS can be configured to generate a printed slip when a transaction is suspended.</span></span> <span data-ttu-id="4c032-116">Detta kvitto kan sedan användas för att snabbt identifiera och återkalla transaktionen senare.</span><span class="sxs-lookup"><span data-stu-id="4c032-116">That slip can then be used to quickly identify and recall the transaction later.</span></span>

<span data-ttu-id="4c032-117">Om du vill aktivera kassan att skriva ut ett kvitto måste du lägga till kvittoformatet **Pausad transaktion** till butikens kvittoprofil.</span><span class="sxs-lookup"><span data-stu-id="4c032-117">To enable the POS to print a slip, you must add the **Suspended transaction** receipt format to the store's receipt profile.</span></span> <span data-ttu-id="4c032-118">Du kan utforma kvittoformatet så att det omfattar eller utelämnar specifik information om transaktionen.</span><span class="sxs-lookup"><span data-stu-id="4c032-118">You can design the receipt format so that it includes or excludes specific details about the transaction.</span></span> <span data-ttu-id="4c032-119">Formatet kan exempelvis innehålla en streckkod för skanning.</span><span class="sxs-lookup"><span data-stu-id="4c032-119">For example, the format can include a barcode to support scanning.</span></span>

### <a name="receipt-numbering"></a><span data-ttu-id="4c032-120">Kvittonumrering</span><span class="sxs-lookup"><span data-stu-id="4c032-120">Receipt numbering</span></span>

<span data-ttu-id="4c032-121">När det gäller andra kassatransaktionstyper som genererar ett utskrivet kvitto kan du definiera en nummerserie för pausade transaktioner i avsnittet **Kvittonumrering** i butikens funktionsprofil.</span><span class="sxs-lookup"><span data-stu-id="4c032-121">As for other POS transaction types that generate a printed receipt, you can define a number sequence for suspended transactions in the **Receipt numbering** section of the store's functionality profile.</span></span>

### <a name="void-when-closing-shift"></a><span data-ttu-id="4c032-122">Annullera vid skiftstängning</span><span class="sxs-lookup"><span data-stu-id="4c032-122">Void when closing shift</span></span>

<span data-ttu-id="4c032-123">Du kan använda alternativet **Annullera vid skiftstängning** för att kräva att användare antingen måste slutföra eller annullera alla pausade transaktioner innan de har avslutar sina skift.</span><span class="sxs-lookup"><span data-stu-id="4c032-123">You can use the **Void when closing shift** option to require that users either complete or void any suspended transactions before they close their shift.</span></span> <span data-ttu-id="4c032-124">Under operationen **Avsluta skift** uppmanar kassan användare att visa eller annullera alla utestående pausade transaktioner.</span><span class="sxs-lookup"><span data-stu-id="4c032-124">During the **Close shift** operation, the POS will prompt users to either view or void any outstanding suspended transactions.</span></span>

## <a name="suspend-and-resume-a-transaction"></a><span data-ttu-id="4c032-125">Pausa och återuppta en transaktion</span><span class="sxs-lookup"><span data-stu-id="4c032-125">Suspend and resume a transaction</span></span>

### <a name="suspend-a-transaction"></a><span data-ttu-id="4c032-126">Pausa en transaktion</span><span class="sxs-lookup"><span data-stu-id="4c032-126">Suspend a transaction</span></span>

<span data-ttu-id="4c032-127">Användare som har behörighet och som har en skärmlayout med operationen **Pausa transaktion** kan pausa en transaktion så att den kan återställas senare eller i en annan kassa.</span><span class="sxs-lookup"><span data-stu-id="4c032-127">Users who have sufficient privileges, and who have a screen layout that includes the **Suspend transaction** operation, can suspend a transaction so that it can be recalled later or on a different register.</span></span>

<span data-ttu-id="4c032-128">Transaktioner kan endast pausas om de **inte** innehåller följande typer av rader:</span><span class="sxs-lookup"><span data-stu-id="4c032-128">Transactions can be suspended only if they do **not** contain the following types of lines:</span></span>

- <span data-ttu-id="4c032-129">Aktiva betalningsrader</span><span class="sxs-lookup"><span data-stu-id="4c032-129">Active payment lines</span></span>
- <span data-ttu-id="4c032-130">Presentkortrader (antingen utfärda ett presentkort eller lägga till presentkortets saldo)</span><span class="sxs-lookup"><span data-stu-id="4c032-130">Gift card lines (either to issue a gift card or to add to the gift card balance)</span></span>

<span data-ttu-id="4c032-131">En pausad transaktion påverkar inte försäljningsinformation eller lagertillgänglighetsinformation för butiken.</span><span class="sxs-lookup"><span data-stu-id="4c032-131">A suspended transaction doesn't affect sales information or inventory availability information for the store.</span></span>

### <a name="resume-a-suspended-transaction"></a><span data-ttu-id="4c032-132">Återkalla en pausad transaktion</span><span class="sxs-lookup"><span data-stu-id="4c032-132">Resume a suspended transaction</span></span>

<span data-ttu-id="4c032-133">Pausade transaktioner kan återkallas och återuppta i samma butik av alla användare som har tillräcklig behörighet och som även har en layout som innehåller operationen **återkalla transaktion**.</span><span class="sxs-lookup"><span data-stu-id="4c032-133">Suspended transactions can be recalled and resumed in the same store by any user who has sufficient privileges, and who also has a layout that includes the **Recall transaction** operation.</span></span>

<span data-ttu-id="4c032-134">För att snabbt och enkelt återkalla en pausad transaktion, skanna streckkoden på den utskrivna bilden medan du tittar på listan över transaktioner från operationen **återkalla transaktion**.</span><span class="sxs-lookup"><span data-stu-id="4c032-134">To quickly and easily recall a suspended transaction, scan the barcode on the printed slip while you're viewing the list of transactions from the **Recall transaction** operation.</span></span>

### <a name="considerations-for-offline-mode"></a><span data-ttu-id="4c032-135">Att tänka på vid offlineläge</span><span class="sxs-lookup"><span data-stu-id="4c032-135">Considerations for offline mode</span></span>

- <span data-ttu-id="4c032-136">En transaktion som avbryts när kassan är i online-läge kan inte återupptas i offlineläge eftersom data inte synkroniseras till offlinedatabasen.</span><span class="sxs-lookup"><span data-stu-id="4c032-136">Any transaction that is suspended while the POS is in online mode can't be resumed in offline mode, because the data isn't synced to the offline database.</span></span>
- <span data-ttu-id="4c032-137">Om du pausar en transaktion när kassan är offline, kan du återkalla den i offlineläge under förutsättning att kassan inte växlar tillbaka till onlineläge när som helst när du inaktiverar transaktionen.</span><span class="sxs-lookup"><span data-stu-id="4c032-137">If you suspend a transaction while the POS is in offline mode, you can recall it in offline mode, provided that the POS wasn't switched back to online mode at any time since you suspended the transaction.</span></span> <span data-ttu-id="4c032-138">När kassan ändras tillbaka till online-läge, flyttas data om pausade transaktioner till onlinedatabasen och tas bort från offlinedatabasen.</span><span class="sxs-lookup"><span data-stu-id="4c032-138">When the POS is switched back to online mode, data about suspended transactions is moved to the online database and removed from the offline database.</span></span> <span data-ttu-id="4c032-139">Transaktionerna kan därför bara återupptas i online-läge.</span><span class="sxs-lookup"><span data-stu-id="4c032-139">Therefore, the transactions can be resumed only in online mode.</span></span> <span data-ttu-id="4c032-140">Om du ändrar tillbaka kassan till offlineläge kan du inte återuppta den pausade transaktionen eftersom den redan har tagits bort från offlinedatabasen.</span><span class="sxs-lookup"><span data-stu-id="4c032-140">If you switch the POS back to offline mode, you won't be able to resume those suspended transaction, because they have already been removed from the offline database.</span></span>

### <a name="void-a-suspended-transaction"></a><span data-ttu-id="4c032-141">Annullera en pausad transaktion</span><span class="sxs-lookup"><span data-stu-id="4c032-141">Void a suspended transaction</span></span>

<span data-ttu-id="4c032-142">Du kan annullera pausade transaktioner antingen genom att återkalla transaktionen och sedan utföra operationen **Annullera transaktion**, eller genom att välja transaktionen i listan **återkalla transaktion** och välja **annullera** i appfältet.</span><span class="sxs-lookup"><span data-stu-id="4c032-142">You can void suspended transactions either by recalling the transaction and then performing the **Void transaction** operation, or by selecting the transaction in the **Recall transaction** list and selecting **Void** on the app bar.</span></span> <span data-ttu-id="4c032-143">Alternativt kan butiken konfigureras för att uppmana användare att annullera pausade transaktioner när de har avslutat sina skift.</span><span class="sxs-lookup"><span data-stu-id="4c032-143">Alternatively, the store can be configured to prompt users to void suspended transactions when they close their shift.</span></span>
