---
title: Utföra fakturauppdateringar för returer
description: Denna funktion stöder även de affärsprocesser som många företag använder som väljer att fakturera returorder och försäljningsorder samtidigt och av samma person.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f962641f7fdae18a360567d6f37348fabbfc302
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "364383"
---
# <a name="perform-invoice-updates-for-returns"></a><span data-ttu-id="db63e-103">Utföra fakturauppdateringar för returer</span><span class="sxs-lookup"><span data-stu-id="db63e-103">Perform invoice updates for returns</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="db63e-104">En returorder i är en typ av försäljningsorder som har markerats som en returorder.</span><span class="sxs-lookup"><span data-stu-id="db63e-104">A return order is a type of sales order that is marked as a returned order.</span></span> <span data-ttu-id="db63e-105">Därför används listsidan **alla försäljningsorder** för att generera fakturor för returorder i stället för formuläret **returorder**.</span><span class="sxs-lookup"><span data-stu-id="db63e-105">Therefore, the **All sales orders** list page is used to generate invoices for return orders instead of the **Return orders** form.</span></span> <span data-ttu-id="db63e-106">Denna funktion stöder även de affärsprocesser som många företag använder som väljer att fakturera returorder och försäljningsorder samtidigt och av samma person.</span><span class="sxs-lookup"><span data-stu-id="db63e-106">This functionality supports the business processes of organizations that choose to have return orders and sales orders invoiced at the same time and by the same person.</span></span>

<span data-ttu-id="db63e-107">Eftersom fakturan för en returnerad artikel är för ett negativt belopp kallas den kreditfaktura.</span><span class="sxs-lookup"><span data-stu-id="db63e-107">Because the invoice for a returned item is for a negative amount, it is called a credit note.</span></span>

<span data-ttu-id="db63e-108">När du ställer in fakturauppdateringen för batchbearbetning måste försäljningsordern **Returnerad order** ha returradstatusen **Inlevererad**, vilket betyder att orderns följesedel har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="db63e-108">When you set up the invoice update for batch processing, the sales order of type **Returned order** must have a return line status of **Received**, which indicates that the order's packing slip has been updated.</span></span>

## <a name="post-an-invoice-for-a-return-order"></a><span data-ttu-id="db63e-109">Bokföra en faktura för en returorder</span><span class="sxs-lookup"><span data-stu-id="db63e-109">Post an invoice for a return order</span></span>

1.  <span data-ttu-id="db63e-110">Klicka på **Kundreskontra** \> **Vanligt** \> **Försäljningsorder** \> **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="db63e-110">Click **Accounts receivable** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="db63e-111">Välj en försäljningsorder för vilken **returnerad order** visas i fältet **Ordertyp**.</span><span class="sxs-lookup"><span data-stu-id="db63e-111">Select a sales order for which **Returned order** is displayed in the **Order type** field.</span></span>

3.  <span data-ttu-id="db63e-112">I åtgärdsrutan på fliken **Faktura** i gruppen **Generera**, klicka på **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="db63e-112">On the Action Pane, on the **Invoice** tab, in the **Generate** group, click **Invoice**.</span></span>

4.  <span data-ttu-id="db63e-113">Välj fliken **Parameters**, markera kryssrutan **Bokföring**.</span><span class="sxs-lookup"><span data-stu-id="db63e-113">On the **Parameters** tab, select the **Posting** check box.</span></span>

5.  <span data-ttu-id="db63e-114">Gå igenom informationen i formuläret och gör de ändringar som behövs.</span><span class="sxs-lookup"><span data-stu-id="db63e-114">Review information in the form and make any changes that are needed.</span></span>

6.  <span data-ttu-id="db63e-115">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="db63e-115">Click **OK**.</span></span> <span data-ttu-id="db63e-116">Kreditfakturan är bokförd.</span><span class="sxs-lookup"><span data-stu-id="db63e-116">The credit note is posted.</span></span>

## <a name="see-also"></a><span data-ttu-id="db63e-117">Se även</span><span class="sxs-lookup"><span data-stu-id="db63e-117">See also</span></span>

[<span data-ttu-id="db63e-118">Följesedelsuppdateringar för returer</span><span class="sxs-lookup"><span data-stu-id="db63e-118">Packing slip updates for returns</span></span>](packing-slip-updates-returns.md)

  


