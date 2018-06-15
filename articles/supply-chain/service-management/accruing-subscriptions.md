---
title: Periodisera abonnemang
description: "Med serviceabonnemang periodiserar du manuellt intäkt i perioderna efter det datum då du fakturerat en avgiftstransaktion."
author: YuyuScheller
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: acbf7432c9487cbefaf24a2a98772c8f0ec7ffe6
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="accruing-subscriptions"></a><span data-ttu-id="8160f-103">Periodisera abonnemang</span><span class="sxs-lookup"><span data-stu-id="8160f-103">Accruing subscriptions</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="8160f-104">Med serviceabonnemang periodiserar du manuellt intäkt i perioderna efter det datum då du fakturerat en avgiftstransaktion.</span><span class="sxs-lookup"><span data-stu-id="8160f-104">With service subscriptions, you manually accrue revenue in the periods following the date when you invoiced a fee transaction.</span></span>

<span data-ttu-id="8160f-105">Periodiseringsperioder skapas för den fakturaperiod som du anger för abonnemangsavgiften och perioderna baseras på abonnemangets periodkod.</span><span class="sxs-lookup"><span data-stu-id="8160f-105">Accrual periods are created for the invoice period that you set up for the subscription fee, and the accrual periods are based on the period code of the subscription.</span></span>

<span data-ttu-id="8160f-106">Du kan periodisera och återföra periodiserade intäkter.</span><span class="sxs-lookup"><span data-stu-id="8160f-106">You can accrue and reverse accrued revenue.</span></span>

## <a name="reverse-accruals-of-credit-amounts"></a><span data-ttu-id="8160f-107">Återför periodisering vid kreditbelopp</span><span class="sxs-lookup"><span data-stu-id="8160f-107">Reverse accruals of credit amounts</span></span>

<span data-ttu-id="8160f-108">Om du krediterar fakturerade abonnemangsbelopp kan du använda två olika metoder för att återföra de periodiserade summorna.</span><span class="sxs-lookup"><span data-stu-id="8160f-108">If you credit invoiced subscription amounts, you can use two methods to reverse the accrual amounts:</span></span>

  - <span data-ttu-id="8160f-109">Du kan återföra varje transaktion för upplupen intäkt individuellt innan du skapar ett kreditfakturaförslag för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="8160f-109">You can reverse each accrued revenue transaction individually before you create the credit note proposal for the transaction.</span></span> <span data-ttu-id="8160f-110">Det här är manuella metoden.</span><span class="sxs-lookup"><span data-stu-id="8160f-110">This is the manual method.</span></span> <span data-ttu-id="8160f-111">(manuell)</span><span class="sxs-lookup"><span data-stu-id="8160f-111">(manual)</span></span>

  - <span data-ttu-id="8160f-112">Du kan låta de periodiserade summorna återföras på det datum då kreditfakturan bokförs eller på det ursprungliga bokföringsdatumet för periodiseringen.</span><span class="sxs-lookup"><span data-stu-id="8160f-112">You can have the accrued amounts reversed on the date where the credit note is posted or on the original posting date of the accrual.</span></span>

<span data-ttu-id="8160f-113">Mer information finns i [Abonnemangsparametrar (formulär)](https://technet.microsoft.com/en-us/library/aa619615.aspx).</span><span class="sxs-lookup"><span data-stu-id="8160f-113">For more information, see [Subscription parameters (form)](https://technet.microsoft.com/en-us/library/aa619615.aspx).</span></span>

## <a name="setup-requirements"></a><span data-ttu-id="8160f-114">Installationskrav</span><span class="sxs-lookup"><span data-stu-id="8160f-114">Setup requirements</span></span>

<span data-ttu-id="8160f-115">Om du ska kunna periodisera intäkter måste följande datakrav uppfyllas.</span><span class="sxs-lookup"><span data-stu-id="8160f-115">To accrue revenue, make sure that the following data requirements are met:</span></span>

## <a name="account-setup"></a><span data-ttu-id="8160f-116">Kontoinställning</span><span class="sxs-lookup"><span data-stu-id="8160f-116">Account setup</span></span>

<span data-ttu-id="8160f-117">Kontona **PIA - abonnemang** och **upplupen intäkt - abonnemang** måste ställas in modulen **projekt**.</span><span class="sxs-lookup"><span data-stu-id="8160f-117">The **WIP - subscription** and the **Accrued revenue - subscription** accounts must be set up in the **Project** module.</span></span>

<span data-ttu-id="8160f-118">När du bokför periodiserad intäkt debiteras kontot **PIA - abonnemang** med den periodiserade summan och kontot **Upplupen intäkt - Abonnemang** krediteras med den periodiserade summan.</span><span class="sxs-lookup"><span data-stu-id="8160f-118">When you post accrued revenue, the **WIP - subscription** account is debited with the accrual amount, and the **Accrued revenue - subscription** account is credited with the accrual amount.</span></span>

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a><span data-ttu-id="8160f-119">Ställ in konton för periodisering av abonnemangsintäkter</span><span class="sxs-lookup"><span data-stu-id="8160f-119">Set up accounts for accrual of subscription revenue</span></span>

1.  <span data-ttu-id="8160f-120">Klicka på **Projekthantering och redovisning** \> **Inställningar** \> **Bokföring** \> **Inställning av redovisningsbokföring**.</span><span class="sxs-lookup"><span data-stu-id="8160f-120">Click **Project management and accounting** \> **Setup** \> **Posting** \> **Ledger posting setup**.</span></span>

2.  <span data-ttu-id="8160f-121">Klicka på fliken **intäktskonton** och markera **PIA - abonnemang** eller **upplupen intäkt - abonnemang** om du vill ställa in kontona.</span><span class="sxs-lookup"><span data-stu-id="8160f-121">Click the **Revenue accounts** tab, and select **WIP - subscription** or **Accrued revenue - subscription** to set up the accounts.</span></span>

## <a name="subscription-group-setup"></a><span data-ttu-id="8160f-122">Inställning av abonnemangsgrupp</span><span class="sxs-lookup"><span data-stu-id="8160f-122">Subscription group setup</span></span>

<span data-ttu-id="8160f-123">För att kunna periodisera intäkter för abonnemang, måste kryssrutan **Periodisera intäkter** vara markerad.</span><span class="sxs-lookup"><span data-stu-id="8160f-123">To be able to accrue revenue for subscriptions, the **Accrue revenue** check box must be selected.</span></span> <span data-ttu-id="8160f-124">Den finns i formuläret **abonnemangsgrupper** för en grupp som är kopplad till abonnemanget.</span><span class="sxs-lookup"><span data-stu-id="8160f-124">This is found on the **Subscription groups** form for the group that is attached to the subscription.</span></span> <span data-ttu-id="8160f-125">Klicka på **Servicehantering** \> **Inställning** \> **Serviceabonnemang** \> **Abonnemangsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="8160f-125">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

## <a name="enable-revenue-accrual-on-a-subscription-group"></a><span data-ttu-id="8160f-126">Aktivera intäktsperiodisering för en abonnemangsgrupp</span><span class="sxs-lookup"><span data-stu-id="8160f-126">Enable revenue accrual on a subscription group</span></span>

1.  <span data-ttu-id="8160f-127">Klicka på **Servicehantering** \> **Inställning** \> **Serviceabonnemang** \> **Abonnemangsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="8160f-127">Click **Service management** \> **Setup** \> **Service subscriptions** \> **Subscription groups**.</span></span>

## <a name="periods"></a><span data-ttu-id="8160f-128">Perioder</span><span class="sxs-lookup"><span data-stu-id="8160f-128">Periods</span></span>

<span data-ttu-id="8160f-129">Du måste ange en faktureringsperiodkod.</span><span class="sxs-lookup"><span data-stu-id="8160f-129">You must set up an invoicing period code.</span></span> <span data-ttu-id="8160f-130">Om du inte vill periodisera intäkt inom samma tidsintervall som du använder för fakturering måste du även skapa en periodiseringsperiod.</span><span class="sxs-lookup"><span data-stu-id="8160f-130">Unless you want to accrue revenue in the same time intervals as you use for invoicing, you must also set up an accrual period.</span></span>

<span data-ttu-id="8160f-131">I följande tabell får du en översikt över vilka periodiseringsperioder du kan ange för vilka faktureringsperioder:</span><span class="sxs-lookup"><span data-stu-id="8160f-131">The following table provides an overview of which accrual periods can be set up for each invoicing period:</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="8160f-132">Faktureringsperiod</span><span class="sxs-lookup"><span data-stu-id="8160f-132">Invoicing period</span></span></p></th>
<th><p><span data-ttu-id="8160f-133">Periodiseringsperiod</span><span class="sxs-lookup"><span data-stu-id="8160f-133">Accrual period</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8160f-134"><strong>År</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-134"><strong>Years</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8160f-135"><strong>År</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-135"><strong>Years</strong></span></span></p></li>
<li><p><span data-ttu-id="8160f-136"><strong>Kvartal</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-136"><strong>Quarter</strong></span></span></p></li>
<li><p><span data-ttu-id="8160f-137"><strong>Månad</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-137"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="8160f-138"><strong>Dag</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-138"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8160f-139"><strong>Kvartal</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-139"><strong>Quarter</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8160f-140"><strong>Kvartal</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-140"><strong>Quarter</strong></span></span></p></li>
<li><p><span data-ttu-id="8160f-141"><strong>Månad</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-141"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="8160f-142"><strong>Dag</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-142"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8160f-143"><strong>Månad</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-143"><strong>Month</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8160f-144"><strong>Månad</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-144"><strong>Month</strong></span></span></p></li>
<li><p><span data-ttu-id="8160f-145"><strong>Dag</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-145"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8160f-146"><strong>Vecka</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-146"><strong>Week</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8160f-147"><strong>Dag</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-147"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8160f-148"><strong>Dag</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-148"><strong>Day</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="8160f-149"><strong>Dag</strong></span><span class="sxs-lookup"><span data-stu-id="8160f-149"><strong>Day</strong></span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="8160f-150">Ställa in faktureringsperioden är en obligatorisk del av den övergripande inställningen av abonnemangsgrupp.</span><span class="sxs-lookup"><span data-stu-id="8160f-150">Setting up the invoicing period is a mandatory part of the overall subscription group setup.</span></span> <span data-ttu-id="8160f-151">Du kan bestämma om att ange en periodiseringsperiod för abonnemangsgruppen.</span><span class="sxs-lookup"><span data-stu-id="8160f-151">You can decide whether to also set up an accrual period for the subscription group.</span></span> <span data-ttu-id="8160f-152">Om du anger en periodiseringsperiod för abonnemangsgruppen, föreslås denna period i fältet **Periodkod**.</span><span class="sxs-lookup"><span data-stu-id="8160f-152">If you set up an accrual period for the subscription group, this period is suggested in the **Period code** field.</span></span> <span data-ttu-id="8160f-153">Det här fältet finns i formuläret **Periodisera abonnemangsintäkt** när du periodiserar abonnemangsintäkt.</span><span class="sxs-lookup"><span data-stu-id="8160f-153">This field is found in the **Accrue subscription revenue** form, when you accrue subscription revenue.</span></span> <span data-ttu-id="8160f-154">Periodiseringsperioden är dock valfri information om abonnemangsgruppen.</span><span class="sxs-lookup"><span data-stu-id="8160f-154">However, the accrual period is optional information about the subscription group.</span></span>


> [!NOTE]
> <P><span data-ttu-id="8160f-155">Använd följande sökväg för att öppna formuläret <STRONG>Periodisera abonnemangsintäkt</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8160f-155">Use the following path to open the <STRONG>Accrue subscription revenue</STRONG> form.</span></span> <span data-ttu-id="8160f-156">Klicka på <STRONG>Servicehantering</STRONG> &gt; <STRONG>Periodisk</STRONG> &gt; <STRONG>Serviceabonnemang</STRONG> &gt; <STRONG>Periodisera abonnemangsintäkt</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8160f-156">Click <STRONG>Service management</STRONG> &gt; <STRONG>Periodic</STRONG> &gt; <STRONG>Service subscriptions</STRONG> &gt; <STRONG>Accrue subscription revenue</STRONG>.</span></span></P>


## <a name="transactions"></a><span data-ttu-id="8160f-157">Transaktioner</span><span class="sxs-lookup"><span data-stu-id="8160f-157">Transactions</span></span>

<span data-ttu-id="8160f-158">Du kan kontrollera antalet redovisningstransaktioner som skapas när du bokför periodiserad intäkt.</span><span class="sxs-lookup"><span data-stu-id="8160f-158">You can control the number of ledger transactions that are created when you post accrued revenue.</span></span> <span data-ttu-id="8160f-159">Definiera om redovisningstransaktionerna ska skapas som en totalsumma eller per rad på prenumerationer.</span><span class="sxs-lookup"><span data-stu-id="8160f-159">On subscriptions, define if the ledger transactions should be created as a total or per line.</span></span>

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a><span data-ttu-id="8160f-160">Ange detaljnivån för bokföringarna som ska visas för periodiserade transaktioner</span><span class="sxs-lookup"><span data-stu-id="8160f-160">Specify the level of posting details to display for accrued transactions</span></span>

1.  <span data-ttu-id="8160f-161">Klicka på **Projekthantering och redovisning** \> **Inställningar** \> **Parametrar för projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="8160f-161">Click **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>

2.  <span data-ttu-id="8160f-162">På fliken **Ekonomi** i fältet **Faktura**, välj **Total** eller **Rad**.</span><span class="sxs-lookup"><span data-stu-id="8160f-162">On the **Financial** tab, in the **Invoice** field, select **Total** or **Line**.</span></span>


## <a name="see-also"></a><span data-ttu-id="8160f-163">Se även</span><span class="sxs-lookup"><span data-stu-id="8160f-163">See also</span></span>

[<span data-ttu-id="8160f-164">Periodisera abonnemangsintäkt</span><span class="sxs-lookup"><span data-stu-id="8160f-164">Accrue subscription revenue</span></span>](accrue-subscription-revenue.md)

  


