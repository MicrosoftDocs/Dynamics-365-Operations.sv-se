---
title: Bekräfta betalningsplaner för tillgångsleasing i en batch
description: I det här ämnet beskrivs hur du bekräftar flera betalningsplaner i en batch.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b5a90b96ac598d145e2b0697627de04731b55f59
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "4448210"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a><span data-ttu-id="567e7-103">Bekräfta betalningsplaner för tillgångsleasing i en batch</span><span class="sxs-lookup"><span data-stu-id="567e7-103">Confirm Asset leasing payment schedules in a batch</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="567e7-104">I det här ämnet beskrivs hur du bekräftar flera betalningsplaner i en batch.</span><span class="sxs-lookup"><span data-stu-id="567e7-104">This topic explains how to confirm multiple payment schedules in a batch.</span></span> <span data-ttu-id="567e7-105">Betalningsplaner bekräftas antingen på leasing-till-leasing-basis eller via batchprocessen för bekräftelse.</span><span class="sxs-lookup"><span data-stu-id="567e7-105">Payment schedules are confirmed either on a lease-to-lease basis or through the confirmation batch process.</span></span> <span data-ttu-id="567e7-106">En journalpost kan bara bokföras mot en leasing som har en bekräftad betalningsplan.</span><span class="sxs-lookup"><span data-stu-id="567e7-106">A journal entry can be posted only against a lease that has a confirmed payment schedule.</span></span> <span data-ttu-id="567e7-107">En bekräftelse av betalningsplanen fungerar som ett slutligt godkännande av den finansiella informationen för leasingen.</span><span class="sxs-lookup"><span data-stu-id="567e7-107">Confirmation of the payment schedule serves as a final approval of the financial information for the lease.</span></span> <span data-ttu-id="567e7-108">Alla framtida ändringar av den ekonomiska informationen för leasingen, såsom betalningar och leasingperioden, utgör en leasingjustering och bör bearbetas på detta sätt.</span><span class="sxs-lookup"><span data-stu-id="567e7-108">All future changes to the financial information for the lease, such as payments and the lease term, constitute a lease adjustment and should be processed in that way.</span></span>

<span data-ttu-id="567e7-109">Om du vill bekräfta flera betalningsplaner följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="567e7-109">To confirm multiple payment schedules, follow these steps.</span></span>

1. <span data-ttu-id="567e7-110">Gå till **Leasing av tillgångar \> Periodisk \> Bekräftelsebatch**.</span><span class="sxs-lookup"><span data-stu-id="567e7-110">Go to **Asset leasing \> Periodic \> Confirmation batch**.</span></span>
2. <span data-ttu-id="567e7-111">På sidan **Bekräftelsebatch** väljer du **Bekräftelsebatch**.</span><span class="sxs-lookup"><span data-stu-id="567e7-111">On the **Confirmation batch** page, select **Confirmation batch**.</span></span>
3. <span data-ttu-id="567e7-112">I dialogrutan som visas filtrerar du fram de böcker du vill bekräfta.</span><span class="sxs-lookup"><span data-stu-id="567e7-112">In the dialog box that appears, filter for the books that you want to confirm.</span></span>

    - <span data-ttu-id="567e7-113">Om du vill bekräfta alla böcker i en viss leasinggrupp väljer du gruppen i fältet **Leasinggrupp**.</span><span class="sxs-lookup"><span data-stu-id="567e7-113">To confirm all the books in a specific lease group, select the group in the **Lease group** field.</span></span>
    - <span data-ttu-id="567e7-114">Om du vill bekräfta vissa böcker väljer du böckerna i fältet **Bok-ID**.</span><span class="sxs-lookup"><span data-stu-id="567e7-114">To confirm specific books, select the books in the **Book ID** field.</span></span>
    - <span data-ttu-id="567e7-115">Bekräfta alla böcker genom att aktivera parametern **För alla böcker**.</span><span class="sxs-lookup"><span data-stu-id="567e7-115">To confirm all books, turn on the **For all books** parameter.</span></span>

<span data-ttu-id="567e7-116">Information för de nyligen bekräftade böckerna visas på sidan **Bekräftade böcker**.</span><span class="sxs-lookup"><span data-stu-id="567e7-116">Information for the newly confirmed books is shown on the **Confirmed books** page.</span></span> <span data-ttu-id="567e7-117">När betalningsplanerna har bekräftats kan de ursprungliga redovisningsjournalposterna bokföras mot leasingarna.</span><span class="sxs-lookup"><span data-stu-id="567e7-117">After the payment schedules are confirmed, the initial recognition journal entries can be posted against the leases.</span></span>