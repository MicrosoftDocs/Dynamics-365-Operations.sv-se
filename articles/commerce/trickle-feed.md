---
title: Indroppningsbaserat orderskapande för butikstransaktioner
description: Det här ämnet beskriver det indroppningsbaserade orderskapandet för butikstransaktioner i Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 09/04/2020
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
ms.openlocfilehash: 79f99b9b401de3e3bcca6ec5a13a3b4f7bad6f8c
ms.sourcegitcommit: 5b620f670ac0f403a0fdcdeb9c3f970b163191ee
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/04/2020
ms.locfileid: "3766746"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a><span data-ttu-id="5e440-103">Indroppningsbaserat orderskapande för butikstransaktioner</span><span class="sxs-lookup"><span data-stu-id="5e440-103">Trickle feed-based order creation for retail store transactions</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5e440-104">I Dynamics 365 Retail version 10.0.4 och tidigare utförs bokföring av utdrag i slutet av dagen och alla transaktioner bokförs i slutet av dagen.</span><span class="sxs-lookup"><span data-stu-id="5e440-104">In Dynamics 365 Retail versions 10.0.4 and earlier, statement posting is an end-of-day operation and all transactions are posted in the books at the end of the day.</span></span> <span data-ttu-id="5e440-105">Stora transaktioner måste sedan bearbetas i ett begränsat tidsfönster, som ibland leder till låsningar och transaktionsbokföringsfel.</span><span class="sxs-lookup"><span data-stu-id="5e440-105">Large transactions must then be processed in a limited time window, sometimes resulting in load and locks and statement posting failures.</span></span> <span data-ttu-id="5e440-106">Återförsäljare kan heller inte identifiera intäkter och betalningar i sin bokföring under dagen.</span><span class="sxs-lookup"><span data-stu-id="5e440-106">Retailers also can't recognize revenue and payments in their books throughout the day.</span></span>

<span data-ttu-id="5e440-107">Med indroppningsbaserat orderskapande som introducerades i Retail version 10.0.5 bearbetas transaktioner under dagen, och endast den ekonomiska avstämningen av anbud och andra transaktioner för likviditetshantering bearbetas vid slutet av dagen.</span><span class="sxs-lookup"><span data-stu-id="5e440-107">With trickle feed-based order creation introduced in Retail version 10.0.5, transactions are processed throughout the day, and only the financial reconciliation of tenders and other cash management transactions are processed at the end of the day.</span></span> <span data-ttu-id="5e440-108">Den här funktionen delar upp belastningen av att skapa försäljningsorder, fakturor och betalningar under dagen, vilket ger bättre uppfattad prestanda och större möjlighet att känna igen intäkter och betalningar i bokföringen nära realtid.</span><span class="sxs-lookup"><span data-stu-id="5e440-108">This functionality splits the load of creating sales orders, invoices, and payments throughout the day, providing better perceived performance and the ability to recognize revenue and payments in the books in near real-time.</span></span> 


## <a name="how-to-use-trickle-feed-based-posting"></a><span data-ttu-id="5e440-109">Så här använder du indroppningsbaserad bokföring</span><span class="sxs-lookup"><span data-stu-id="5e440-109">How to use trickle feed-based posting</span></span>
  
1. <span data-ttu-id="5e440-110">Om du vill aktivera indroppningsbaserad bokföring av butikstransaktioner aktiverar du funktionen **Butiksutdrag – Indroppning**med hjälp av Funktionshantering.</span><span class="sxs-lookup"><span data-stu-id="5e440-110">To enable trickle feed-based posting of retail transactions, enable the feature named **Retail statements - Trickle feed** using Feature management.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5e440-111">Innan du aktiverar den här funktionen måste du se till att det inte finns några utdrag som väntar på att bokföras.</span><span class="sxs-lookup"><span data-stu-id="5e440-111">Before you enable the feature, make sure that no pending statements are waiting to be posted.</span></span>

2. <span data-ttu-id="5e440-112">Det aktuella utdragsdokumentet delas upp i två typer: transaktionsutdrag och bokslut.</span><span class="sxs-lookup"><span data-stu-id="5e440-112">The current statement document will be split into two types: transactional statement and financial statement.</span></span>

      - <span data-ttu-id="5e440-113">Transaktionsutdraget hämtar alla ej bokförda och validerade transaktioner och skapa försäljningsorder, försäljningsfakturor, betalnings- och rabattjournaler samt intäkts-utgiftstransaktioner i den takt du konfigurerar.</span><span class="sxs-lookup"><span data-stu-id="5e440-113">The transactional statement will pick up all unposted and validated transactions and create sales orders, sales invoices, payment and discount journals, and income-expense transactions at the cadence that you configure.</span></span> <span data-ttu-id="5e440-114">Du bör konfigurera den här processen så att den körs med hög frekvens så att dokument skapas när butikstransaktionerna överförs till Headquarters via P-jobbet.</span><span class="sxs-lookup"><span data-stu-id="5e440-114">You should configure this process to run at a high frequency so that documents are created when the transactions are uploaded into Headquarters through the P-job.</span></span> <span data-ttu-id="5e440-115">När du använder utdragsdokumentet som redan skapar försäljningsorder och försäljningsfakturor behöver du inte konfigurera batchjobbet **Bokföring av lager**.</span><span class="sxs-lookup"><span data-stu-id="5e440-115">With the transactional statement that already creates sales orders and sales invoices, there is no real need to configure the **Post inventory** batch job.</span></span> <span data-ttu-id="5e440-116">Du kan dock fortfarande använda det för att uppfylla specifika affärsbehov som du kan ha.</span><span class="sxs-lookup"><span data-stu-id="5e440-116">However, you can still use it to meet specific business requirements that you may have.</span></span>  
      
     - <span data-ttu-id="5e440-117">Bokslutet är utformat för att skapas i slutet av dagen och stöder bara stängningsmetoden **Skift.**</span><span class="sxs-lookup"><span data-stu-id="5e440-117">The financial statement is designed to be created at the end of the day and only supports the closing method of **Shift**.</span></span> <span data-ttu-id="5e440-118">Detta utdrag begränsas till den ekonomiska avstämningen och skapar endast journaler för avvikelsebeloppen mellan det räknade beloppet och transaktionsbeloppet för de olika anbuden, tillsammans med journaler för andra likviditetshanteringstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="5e440-118">This statement will be limited to financial reconciliation and will only create the journals for the difference amounts between counted amount and transaction amount for the different tenders, along with journals for other cash management transactions.</span></span>   

3. <span data-ttu-id="5e440-119">Om du vill beräkna transaktionsutdraget går du till **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Beräkna transaktionsutdrag i batch**.</span><span class="sxs-lookup"><span data-stu-id="5e440-119">To calculate the transactional statement, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate transactional statements in batch**.</span></span> <span data-ttu-id="5e440-120">Om du vill bokföra transaktionsutdrag i batch går du till **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Bokför transaktionsutdrag i batch**.</span><span class="sxs-lookup"><span data-stu-id="5e440-120">To post the transactional statements in batch, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Post transactional statements in batch**.</span></span>

4. <span data-ttu-id="5e440-121">Om du vill beräkna bokslutet går du till **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Beräkna bokslutet i batch**.</span><span class="sxs-lookup"><span data-stu-id="5e440-121">To calculate the financial statement, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate financial statements in batch**.</span></span> <span data-ttu-id="5e440-122">Om du vill bokföra bokslutet i batch går du till **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Bokför bokslutet i batch**.</span><span class="sxs-lookup"><span data-stu-id="5e440-122">To post the financial statements in batch, go to **Retail and Commerce > Retail and Commerce IT > POS Posting > Post financial statements in batch**.</span></span>

> [!NOTE]
> <span data-ttu-id="5e440-123">Menyalternativen **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Beräkna utdrag i batch** och **Retail och Commerce >Retail och Commerce IT > Kassabokföring > Bokför utdrag i batch** tas bort i den nya funktionen.</span><span class="sxs-lookup"><span data-stu-id="5e440-123">The menu items **Retail and Commerce > Retail and Commerce IT > POS Posting > Calculate statements in batch** and **Retail and Commerce > Retail and Commerce IT > POS Posting > Post statements in batch** are removed with this new feature.</span></span>

<span data-ttu-id="5e440-124">Alternativt kan transaktions- och bokslutstyper skapas manuellt.</span><span class="sxs-lookup"><span data-stu-id="5e440-124">Alternately, transactional and financial statement types can be created manually.</span></span> <span data-ttu-id="5e440-125">Gå till **Retail och Commerce > Kanaler > Butiker** och klicka på **Utdrag**.</span><span class="sxs-lookup"><span data-stu-id="5e440-125">Go to **Retail and Commerce > Channels > Stores** and click **Statements**.</span></span> <span data-ttu-id="5e440-126">Klicka på **Ny** och välj sedan den typ av utdrag som du vill skapa.</span><span class="sxs-lookup"><span data-stu-id="5e440-126">Click **New** and then choose the type of statement that you want to create.</span></span> <span data-ttu-id="5e440-127">Fält på sidan **Utdrag** och åtgärder under **Utdragsgrupper** på sidan visar relevanta data och åtgärder baserade på den valda utdragstypen.</span><span class="sxs-lookup"><span data-stu-id="5e440-127">Fields on the **Statements** page and actions under the **Statement group** of the page will show relevant data and actions based on the selected statement type.</span></span>
