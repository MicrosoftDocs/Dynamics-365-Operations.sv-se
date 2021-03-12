---
title: Bokföra journalposter för övergångsjustering i Leasing av tillgångar
description: I det här avsnittet beskrivs de funktioner som gör att du kan låta en leasingportfölj övergå till de nya redovisningsstandarderna för leasing, Accounting Standards Codification Topic 842 (ASC 842) och International Financial Reporting Standard 16 (IFRS 16).
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
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 51ae41e22507d77f32b8b0f4685cce797fd19cff
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969563"
---
# <a name="post-transition-adjustment-journal-entries-in-asset-leasing"></a><span data-ttu-id="59978-103">Bokföra journalposter för övergångsjustering i Leasing av tillgångar</span><span class="sxs-lookup"><span data-stu-id="59978-103">Post transition adjustment journal entries in Asset leasing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="59978-104">I det här avsnittet beskrivs de funktioner som gör att du kan låta en leasingportfölj övergå till de nya redovisningsstandarderna för leasing: Accounting Standards Codification Topic 842 (ASC 842), som är standarden för god redovisningssed i USA (US GAAP, Generally Accepted Accounting Principles), samt International Financial Reporting Standard 16 (IFRS 16).</span><span class="sxs-lookup"><span data-stu-id="59978-104">This topic describes the functionality that lets you transition a lease portfolio to the new lease accounting standards: Accounting Standards Codification Topic 842 (ASC 842), which is the standard in Generally Accepted Accounting Principles in the US (US GAAP), and International Financial Reporting Standard 16 (IFRS 16).</span></span>

<span data-ttu-id="59978-105">Information om hur du konfigurerar en bok för övergången till de nya standarderna finns i [Konfigurera leasingböcker](set-up-lease-books.md).</span><span class="sxs-lookup"><span data-stu-id="59978-105">For information about how to set up a book for the transition to the new standards, see [Set up lease books](set-up-lease-books.md).</span></span>

<span data-ttu-id="59978-106">När du skapar en journalpost för en övergångsjustering skapas en journalpost.</span><span class="sxs-lookup"><span data-stu-id="59978-106">When you create a transition adjustment journal entry, a journal entry is generated.</span></span> <span data-ttu-id="59978-107">Den här posten återspeglar balansräkningens inverkan på registreringen av leasingen enligt de nya standarderna på detta datum.</span><span class="sxs-lookup"><span data-stu-id="59978-107">This entry reflects the balance sheet impact of recording the lease under the new standards on that date.</span></span> <span data-ttu-id="59978-108">Rätt tillgångskonto debiteras det bokförda värdet på detta datum och skuldkontot krediteras.</span><span class="sxs-lookup"><span data-stu-id="59978-108">The appropriate asset account is debited for the carrying amount on that date, and the liability account is credited.</span></span> <span data-ttu-id="59978-109">Skillnaden debiteras eller krediteras balanserade vinstmedel.</span><span class="sxs-lookup"><span data-stu-id="59978-109">The difference is either debited or credited to retained earnings.</span></span>

<span data-ttu-id="59978-110">Om du vill bokföra en övergångsjustering i enlighet med de nya redovisningsstandarderna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="59978-110">To post a transition adjustment in compliance with the new accounting standards, follow these steps.</span></span>

1. <span data-ttu-id="59978-111">På sidan **Sammanfattning av leasing** väljer du leasingen och väljer sedan **Böcker**.</span><span class="sxs-lookup"><span data-stu-id="59978-111">On the **Lease summary** page, select the lease, and then select **Books**.</span></span>
2. <span data-ttu-id="59978-112">Välj **Betalningsplan** i boken.</span><span class="sxs-lookup"><span data-stu-id="59978-112">In the book, select **Payment schedule**.</span></span>
3. <span data-ttu-id="59978-113">I dialogrutan **Betalningsplan** väljer du **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="59978-113">In the **Payment schedule** dialog box, select **Confirm**.</span></span> <span data-ttu-id="59978-114">Stäng sedan dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="59978-114">Then close the dialog box.</span></span>
4. <span data-ttu-id="59978-115">Välj **Övergångsjustering**.</span><span class="sxs-lookup"><span data-stu-id="59978-115">Select **Transition adjustment**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="59978-116">En övergångsjustering kan bara skapas för leasingböcker som har tilldelats till en bok där fältet **Övergångsbok** är tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="59978-116">A transition adjustment can be created only for lease books that are assigned to a book where the **Transition book** field is available.</span></span> <span data-ttu-id="59978-117">Om värdet i fältet **Leasingens start** är senare än övergångsdatumet, kommer värdet i fältet **Övergångsjustering** inte att uppdateras.</span><span class="sxs-lookup"><span data-stu-id="59978-117">If the value in the **Lease commencement** field is later than the transition date, the value in the **Transition adjustment** field won't be updated.</span></span>

5. <span data-ttu-id="59978-118">För att visa journalposten väljer du **Journaler för leasing av tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="59978-118">To view the journal entry, select **Asset leasing journals**.</span></span>
6. <span data-ttu-id="59978-119">Välj den nya journalen och välj sedan **Bokför**.</span><span class="sxs-lookup"><span data-stu-id="59978-119">Select the new journal, and then select **Post**.</span></span>
