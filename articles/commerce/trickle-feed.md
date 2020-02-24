---
title: Indroppningsbaserat orderskapande för butikstransaktioner
description: Det här ämnet beskriver det indroppningsbaserade orderskapandet för butikstransaktioner i Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3f691017ad06d3416e4ba0e86d7a0bc207aba5bd
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004284"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions-public-preview"></a><span data-ttu-id="fb415-103">Indroppningsbaserat orderskapande för butikstransaktioner (Allmän förhandsgranskning)</span><span class="sxs-lookup"><span data-stu-id="fb415-103">Trickle feed-based order creation for retail store transactions (Public preview)</span></span>

[!include [banner](includes/banner.md)]



<span data-ttu-id="fb415-104">I Dynamics 365 Retail version 10.0.4 och tidigare utförs bokföring av utdrag i slutet av dagen och alla transaktioner bokförs i slutet av dagen.</span><span class="sxs-lookup"><span data-stu-id="fb415-104">In Dynamics 365 Retail versions 10.0.4 and earlier, statement posting is an end-of-day operation and all transactions are posted in the books at the end of the day.</span></span> <span data-ttu-id="fb415-105">Stora transaktioner måste sedan bearbetas i ett begränsat tidsfönster, som ibland leder till låsningar och transaktionsbokföringsfel.</span><span class="sxs-lookup"><span data-stu-id="fb415-105">Large transactions must then be processed in a limited time window, sometimes resulting in load and locks and statement posting failures.</span></span> <span data-ttu-id="fb415-106">Återförsäljare kan heller inte identifiera intäkter och betalningar i sin bokföring under dagen.</span><span class="sxs-lookup"><span data-stu-id="fb415-106">Retailers also can't recognize revenue and payments in their books throughout the day.</span></span>

<span data-ttu-id="fb415-107">I den allmänna förhandsgranskningen av indroppningsbaserat orderskapande i Retail version 10.0.5 bearbetas transaktioner under dagen, och endast den ekonomiska avstämningen av anbud och andra transaktioner för likviditetshantering bearbetas vid slutet av dagen.</span><span class="sxs-lookup"><span data-stu-id="fb415-107">With the public preview of trickle feed-based order creation introduced in Retail version 10.0.5, transactions are processed throughout the day, and only the financial reconciliation of tenders and other cash management transactions are processed at the end of the day.</span></span> <span data-ttu-id="fb415-108">Den här funktionen delar upp belastningen av att skapa försäljningsorder, fakturor och betalningar under dagen, vilket ger bättre uppfattad prestanda och större möjlighet att känna igen intäkter och betalningar i bokföringen nära realtid.</span><span class="sxs-lookup"><span data-stu-id="fb415-108">This functionality splits the load of creating sales orders, invoices, and payments throughout the day, providing better perceived performance and the ability to recognize revenue and payments in the books in near real-time.</span></span> 


## <a name="how-to-use-trickle-feed-based-posting"></a><span data-ttu-id="fb415-109">Så här använder du indroppningsbaserad bokföring</span><span class="sxs-lookup"><span data-stu-id="fb415-109">How to use trickle feed-based posting</span></span>
  
1. <span data-ttu-id="fb415-110">Om du vill aktivera indroppningsbaserad bokföring av transaktioner går du till **Systemadministration > Inställningar > Licenskonfiguration** och inaktiverar nyckeln **Utdrag**.</span><span class="sxs-lookup"><span data-stu-id="fb415-110">To enable trickle feed-based posting of transactions, go to **System administration > Set up > License configuration** and disable the the **Statements** key.</span></span>

2. <span data-ttu-id="fb415-111">På samma sida aktiverar du licensnyckeln **Utdrag (indroppning) – förhandsgranskning**.</span><span class="sxs-lookup"><span data-stu-id="fb415-111">On the same page, enable the **Statements (trickle feed) – Preview** license key.</span></span> <span data-ttu-id="fb415-112">När du aktiverar den här nyckeln måste du se till att det inte finns några utdrag som väntar på att bokföras.</span><span class="sxs-lookup"><span data-stu-id="fb415-112">When you enable this key, make sure there are no pending statements waiting to be posted.</span></span> 

    > [!Important]
    > <span data-ttu-id="fb415-113">Innan du aktiverar licensnyckeln **Utdrag (indroppning) – förhandsgranskning** ser du till att inga utdrag väntar på att bokföras.</span><span class="sxs-lookup"><span data-stu-id="fb415-113">Before you enable the **Statements (trickle feed) – Preview** license key, make sure that no pending statements are waiting to be posted.</span></span>

3. <span data-ttu-id="fb415-114">Det aktuella utdragsdokumentet delas upp i två olika typer: transaktionsutdrag och bokslut.</span><span class="sxs-lookup"><span data-stu-id="fb415-114">The current statement document will be split into two different types; transactional statement and financial statement.</span></span>

      - <span data-ttu-id="fb415-115">Transaktionsutdraget hämtar alla ej bokförda och validerade transaktioner och skapa försäljningsorder, försäljningsfakturor, betalnings- och rabattjournaler samt intäkts-utgiftstransaktioner i den takt du konfigurerar.</span><span class="sxs-lookup"><span data-stu-id="fb415-115">The transactional statement will pick up all unposted and validated transactions and create sales orders, sales invoices, payment and discount journals, and income-expense transactions at the cadence that you configure.</span></span> <span data-ttu-id="fb415-116">Du bör konfigurera den här processen så att den körs med hög frekvens så att dokument skapas när butikstransaktionerna överförs till Headquarters via P-jobbet.</span><span class="sxs-lookup"><span data-stu-id="fb415-116">You should configure this process to run at a high frequency so that documents are created when the transactions are uploaded into Headquarters through the P-job.</span></span> <span data-ttu-id="fb415-117">När du använder utdragsdokumentet som redan skapar försäljningsorder och försäljningsfakturor behöver du inte konfigurera batchjobbet **Bokföring av lager**.</span><span class="sxs-lookup"><span data-stu-id="fb415-117">With the transactional statement that already creates sales orders and sales invoices, there is no real need to configure the **Post inventory** batch job.</span></span> <span data-ttu-id="fb415-118">Du kan dock fortfarande använda det för att uppfylla specifika affärsbehov som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="fb415-118">However, you can still use it to meet specific business requirements that you may have.</span></span>  
      
     - <span data-ttu-id="fb415-119">Bokslutet är utformat för att skapas i slutet av dagen och stöder bara stängningsmetoden **Skift.**</span><span class="sxs-lookup"><span data-stu-id="fb415-119">The financial statement is designed to be created at the end of the day and only supports the closing method of **Shift**.</span></span> <span data-ttu-id="fb415-120">Detta utdrag begränsas till den ekonomiska avstämningen och skapar endast journaler för avvikelsebeloppen mellan det räknade beloppet och transaktionsbeloppet för de olika anbuden, tillsammans med journaler för andra likviditetshanteringstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="fb415-120">This statement will be limited to financial reconciliation and will only create the journals for the difference amounts between counted amount and transaction amount for the different tenders, along with journals for other cash management transactions.</span></span>   

4. <span data-ttu-id="fb415-121">Om du vill beräkna transaktionsutdraget klickar du på **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Beräkna transaktionsutdrag i batch**.</span><span class="sxs-lookup"><span data-stu-id="fb415-121">To calculate the transactional statement, click **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate transactional statements in batch**.</span></span> <span data-ttu-id="fb415-122">Om du vill bokföra transaktionsutdrag i batch klickar du på **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Bokför transaktionsutdrag i batch**.</span><span class="sxs-lookup"><span data-stu-id="fb415-122">To post the transactional statement statements in batch, click **Retail and Commerce > Retail and Commerce IT > POS Posting > Post transactional statements in batch**.</span></span>

5. <span data-ttu-id="fb415-123">Om du vill beräkna bokslutet klickar du på **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Beräkna bokslutet i batch**.</span><span class="sxs-lookup"><span data-stu-id="fb415-123">To calculate the financial statement, click **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate financial statements in batch**.</span></span> <span data-ttu-id="fb415-124">Om du vill bokföra bokslutet i batch klickar du på **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Bokför bokslutet i batch**.</span><span class="sxs-lookup"><span data-stu-id="fb415-124">To post the financial statements in batch, click **Retail and Commerce > Retail and Commerce IT > POS Posting > Post financial statements in batch**.</span></span>

> [!NOTE]
> <span data-ttu-id="fb415-125">Menyalternativen **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Beräkna utdrag i batch** och **Retail och Commerce >Retail och Commerce IT > Kassabokföring > Bokför utdrag i batch** tas bort i den nya funktionen.</span><span class="sxs-lookup"><span data-stu-id="fb415-125">The menu items **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate statements in batch** and **Retail and Commerce > Retail and Commerce IT > POS Posting > Post statements in batch** are removed with this new feature.</span></span>

<span data-ttu-id="fb415-126">Alternativt kan transaktions- och bokslutstyper skapas manuellt.</span><span class="sxs-lookup"><span data-stu-id="fb415-126">Alternately, transactional and financial statement types can be created manually.</span></span> <span data-ttu-id="fb415-127">Gå till **Retail och Commerce > Kanaler > Butiker** och klicka på **Utdrag**.</span><span class="sxs-lookup"><span data-stu-id="fb415-127">Go to **Retail and Commerce > Channels > Stores** and click **Statements**.</span></span> <span data-ttu-id="fb415-128">Klicka på **Ny** och välj sedan den typ av utdrag som du vill skapa.</span><span class="sxs-lookup"><span data-stu-id="fb415-128">Click **New** and then choose the type of statement that you want to create.</span></span> <span data-ttu-id="fb415-129">Fält på sidan **Utdrag** och åtgärder under **Utdragsgrupper** på sidan visar relevanta data och åtgärder baserade på den valda utdragstypen.</span><span class="sxs-lookup"><span data-stu-id="fb415-129">Fields on the **Statements** page and actions under the **Statement group** of the page will show relevant data and actions based on the selected statement type.</span></span>
