---
title: Återföra bokförda leasingtransaktioner
description: I det här ämnet beskrivs hur du återför en bokförd leasingtransaktion. Alla transaktioner som skapas via Leasing av tillgångar kan återföras.
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
ms.openlocfilehash: 3e4908ddab2650e5ff7e4a28bf916604d165d08c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969538"
---
# <a name="reverse-posted-lease-transactions"></a><span data-ttu-id="fa36e-104">Återföra bokförda leasingtransaktioner</span><span class="sxs-lookup"><span data-stu-id="fa36e-104">Reverse posted lease transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fa36e-105">Alla transaktioner som skapas via Leasing av tillgångar kan återföras.</span><span class="sxs-lookup"><span data-stu-id="fa36e-105">Any transaction that is created through Asset leasing can be reversed.</span></span> <span data-ttu-id="fa36e-106">Transaktioner som återförs via Leasing av tillgångar uppdaterar dina leasingdata.</span><span class="sxs-lookup"><span data-stu-id="fa36e-106">Transactions that are reversed through Asset leasing update your lease data.</span></span> <span data-ttu-id="fa36e-107">Det innebär att de också uppdaterar de redovisade värdena för leasingskulden och ROU-tillgången (tillgången med nyttjanderätt).</span><span class="sxs-lookup"><span data-stu-id="fa36e-107">Therefore, they also update the carrying values of the lease liability and right-of-use (ROU) asset.</span></span>

<span data-ttu-id="fa36e-108">Om du vill skapa en återföringstransaktion för en leasing följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="fa36e-108">To create a reversing transaction for a lease, follow these steps.</span></span>

1. <span data-ttu-id="fa36e-109">På antingen sidan **Transaktioner för tillgångar** eller sidan **Skuldtransaktioner** väljer du transaktionen och väljer sedan **Återför transaktion**.</span><span class="sxs-lookup"><span data-stu-id="fa36e-109">On either the **Asset transactions** page or the **Liability transactions** page, select the transaction, and then select **Reverse transaction**.</span></span>
2. <span data-ttu-id="fa36e-110">I dialogrutan som visas kan du redigera datumet när återföringsposten kommer att bokföras.</span><span class="sxs-lookup"><span data-stu-id="fa36e-110">In the dialog box that appears, you can edit the date when the reversing entry will be posted.</span></span> <span data-ttu-id="fa36e-111">Som standard är fältet **Datum** inställt på transaktionsbokföringsdatumet för den transaktion som du har valt.</span><span class="sxs-lookup"><span data-stu-id="fa36e-111">By default, the **Date** field is set to the transaction posting date of the transaction that you selected.</span></span> <span data-ttu-id="fa36e-112">Återföringsposten kan inte bokföras tidigare än det ursprungliga bokföringsdatumet för den valda transaktionen.</span><span class="sxs-lookup"><span data-stu-id="fa36e-112">The reversing entry can't be posted earlier than the original posting date of the selected transaction.</span></span>
3. <span data-ttu-id="fa36e-113">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa36e-113">Select **OK**.</span></span> <span data-ttu-id="fa36e-114">En journalpost bokförs som återför den valda transaktionen.</span><span class="sxs-lookup"><span data-stu-id="fa36e-114">A journal entry is posted that reverses the entry that you selected.</span></span> <span data-ttu-id="fa36e-115">Återföringen visas på sidan **Transaktioner för tillgångar** eller sidan **Skuldtransaktioner** och nettosumman för det aktuella saldo som visas på sidan uppdateras.</span><span class="sxs-lookup"><span data-stu-id="fa36e-115">The reversal is shown on the **Asset transactions** or **Liability transactions** page, and the net total of the current balance that is shown on the page is updated.</span></span>

<span data-ttu-id="fa36e-116">När du väljer **Återförd spårning** visas en dialogruta där både de ursprungliga transaktionerna och de återförda transaktionerna visas, tillsammans med ett länkat nummer som kallas *spårningsnummer*.</span><span class="sxs-lookup"><span data-stu-id="fa36e-116">When you select **Reverse tracing**, a dialog box appears that shows both the original transactions and the reversed transactions, together with a linked number that is known as a *trace number*.</span></span> <span data-ttu-id="fa36e-117">Om du vill göra återföringarna lättare att förstå och förbättra synligheten kan du spåra återföringar genom att använda leasingplanerna.</span><span class="sxs-lookup"><span data-stu-id="fa36e-117">To make the reversals easier to understand and to improve visibility, you can also track reversals by using the lease schedules.</span></span>

<span data-ttu-id="fa36e-118">I fältet **Senaste journalnummer** på sidan **Tidsplanera** visas journalnumren för transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="fa36e-118">The **Latest journal number** field on the **Schedule** page shows the journal numbers of transactions.</span></span> <span data-ttu-id="fa36e-119">När en transaktion återförs uppdateras det här fältet med journalnumret för en återföringstransaktion.</span><span class="sxs-lookup"><span data-stu-id="fa36e-119">When a transaction is reversed, this field is updated with the journal number of a reversing transaction.</span></span> <span data-ttu-id="fa36e-120">Kryssrutan **Återförd** är dessutom markerad för att visa att transaktionen har återförts och fältet **Bokförd** markeras.</span><span class="sxs-lookup"><span data-stu-id="fa36e-120">Additionally, the **Reversed** check box is selected to indicate that the transaction is reversed, and the **Posted** field is selected.</span></span>

## <a name="revoke-a-reversed-transaction"></a><span data-ttu-id="fa36e-121">Återkalla en återförd transaktion</span><span class="sxs-lookup"><span data-stu-id="fa36e-121">Revoke a reversed transaction</span></span>

<span data-ttu-id="fa36e-122">Om du vill återkalla en återförd transaktion följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="fa36e-122">To revoke a reversed transaction, follow these steps.</span></span>

1. <span data-ttu-id="fa36e-123">Välj den ursprungliga transaktionen på någon av sidorna **Tidsplanera** eller **Transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="fa36e-123">On either the **Schedule** page or the **Transactions** page, select the original transaction.</span></span>
2. <span data-ttu-id="fa36e-124">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="fa36e-124">Follow one of these steps:</span></span>

    - <span data-ttu-id="fa36e-125">Om du har valt transaktionen på sida **Tidsplanera** följer du stegen för att skapa en journal i [Skapa månadsvisa poster i redovisningsjournal i en batch](create-monthly-journals-batch.md).</span><span class="sxs-lookup"><span data-stu-id="fa36e-125">If you selected the transaction on the **Schedule** page, follow the steps for creating a journal in [Create monthly journal entries in a batch](create-monthly-journals-batch.md).</span></span> <span data-ttu-id="fa36e-126">Du måste bokföra journalen manuellt.</span><span class="sxs-lookup"><span data-stu-id="fa36e-126">You must manually post the journal.</span></span>
    - <span data-ttu-id="fa36e-127">Om du har valt transaktionen på sidan **Transaktioner** väljer du **Återför transaktion**.</span><span class="sxs-lookup"><span data-stu-id="fa36e-127">If you selected the transaction on the **Transactions** page, select **Reverse transaction**.</span></span> <span data-ttu-id="fa36e-128">Du får ett meddelande om att denna återkallning är en återkallning av en tidigare återföring, och att du kan redigera bokföringsdatumet för återkallningen.</span><span class="sxs-lookup"><span data-stu-id="fa36e-128">You receive a message that states that this revocation is a revocation of an earlier reversal, and that you can edit the posting date for this revocation.</span></span> <span data-ttu-id="fa36e-129">Generella affärsvalideringar påverkar dock de datum som kan anges i fältet **Datum**.</span><span class="sxs-lookup"><span data-stu-id="fa36e-129">However, general business validations affect the dates that can be entered in the **Date** field.</span></span> 

3. <span data-ttu-id="fa36e-130">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="fa36e-130">Select **OK**.</span></span> <span data-ttu-id="fa36e-131">En journalpost bokförs som återför den valda transaktionen.</span><span class="sxs-lookup"><span data-stu-id="fa36e-131">A journal entry is posted that reverses the entry that you selected.</span></span> <span data-ttu-id="fa36e-132">Återföringen visas på sidan **Transaktioner** och nettosumman i det aktuella saldot återställs till det som ingick före den första återföringen.</span><span class="sxs-lookup"><span data-stu-id="fa36e-132">The reversal is shown on the **Transactions** page, and the net total current balance is restored to what it was before the first reversal.</span></span> <span data-ttu-id="fa36e-133">Därför är den inverkan som återföringen hade på saldona negerad.</span><span class="sxs-lookup"><span data-stu-id="fa36e-133">Therefore, the impact that the reversal had on the balances is negated.</span></span>

<span data-ttu-id="fa36e-134">När du väljer **Återförd spårning** visas en dialogruta där både de ursprungliga transaktionerna och de återförda transaktionerna visas, tillsammans med ett spårningsnummer.</span><span class="sxs-lookup"><span data-stu-id="fa36e-134">When you select **Reverse tracing**, a dialog box appears that shows both the original transactions and the reversed transactions, together with a linked trace number.</span></span>

<span data-ttu-id="fa36e-135">Du kan också spåra återkallningarna med hjälp av lämplig sida för **planer**.</span><span class="sxs-lookup"><span data-stu-id="fa36e-135">You can also track revocations by using the appropriate **Schedules** page.</span></span> <span data-ttu-id="fa36e-136">Fältet **Återför** rensas och fältet **Journal bokförd** markeras.</span><span class="sxs-lookup"><span data-stu-id="fa36e-136">The **Reverse** field is cleared, whereas the **Journal posted** field is selected.</span></span> <span data-ttu-id="fa36e-137">Dessutom uppdateras fältet **Senaste journalnummer** med journalnumret för återkallningstransaktionen och fältet **Journalnummer** uppdateras med numret på återföringsjournalen.</span><span class="sxs-lookup"><span data-stu-id="fa36e-137">Additionally, the **Latest journal number** field is updated with the journal number of the revocation transaction, and the **Journal number** field is updated with the reversal journal number.</span></span>
