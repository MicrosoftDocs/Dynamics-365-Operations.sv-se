---
title: Periodisera abonnemang
description: "Med serviceabonnemang periodiserar du manuellt intäkt i perioderna efter det datum då du fakturerat en avgiftstransaktion."
author: ShylaThompson
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: acbf7432c9487cbefaf24a2a98772c8f0ec7ffe6
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="accruing-subscriptions"></a>Periodisera abonnemang 

[!include [banner](../includes/banner.md)]


Med serviceabonnemang periodiserar du manuellt intäkt i perioderna efter det datum då du fakturerat en avgiftstransaktion.

Periodiseringsperioder skapas för den fakturaperiod som du anger för abonnemangsavgiften och perioderna baseras på abonnemangets periodkod.

Du kan periodisera och återföra periodiserade intäkter.

## <a name="reverse-accruals-of-credit-amounts"></a>Återför periodisering vid kreditbelopp

Om du krediterar fakturerade abonnemangsbelopp kan du använda två olika metoder för att återföra de periodiserade summorna.

  - Du kan återföra varje transaktion för upplupen intäkt individuellt innan du skapar ett kreditfakturaförslag för transaktionen. Det här är manuella metoden. (manuell)

  - Du kan låta de periodiserade summorna återföras på det datum då kreditfakturan bokförs eller på det ursprungliga bokföringsdatumet för periodiseringen.

Mer information finns i [Abonnemangsparametrar (formulär)](https://technet.microsoft.com/en-us/library/aa619615.aspx).

## <a name="setup-requirements"></a>Installationskrav

Om du ska kunna periodisera intäkter måste följande datakrav uppfyllas.

## <a name="account-setup"></a>Kontoinställning

Kontona **PIA - abonnemang** och **upplupen intäkt - abonnemang** måste ställas in modulen **projekt**.

När du bokför periodiserad intäkt debiteras kontot **PIA - abonnemang** med den periodiserade summan och kontot **Upplupen intäkt - Abonnemang** krediteras med den periodiserade summan.

## <a name="set-up-accounts-for-accrual-of-subscription-revenue"></a>Ställ in konton för periodisering av abonnemangsintäkter

1.  Klicka på **Projekthantering och redovisning** \> **Inställningar** \> **Bokföring** \> **Inställning av redovisningsbokföring**.

2.  Klicka på fliken **intäktskonton** och markera **PIA - abonnemang** eller **upplupen intäkt - abonnemang** om du vill ställa in kontona.

## <a name="subscription-group-setup"></a>Inställning av abonnemangsgrupp

För att kunna periodisera intäkter för abonnemang, måste kryssrutan **Periodisera intäkter** vara markerad. Den finns i formuläret **abonnemangsgrupper** för en grupp som är kopplad till abonnemanget. Klicka på **Servicehantering** \> **Inställning** \> **Serviceabonnemang** \> **Abonnemangsgrupper**.

## <a name="enable-revenue-accrual-on-a-subscription-group"></a>Aktivera intäktsperiodisering för en abonnemangsgrupp

1.  Klicka på **Servicehantering** \> **Inställning** \> **Serviceabonnemang** \> **Abonnemangsgrupper**.

## <a name="periods"></a>Perioder

Du måste ange en faktureringsperiodkod. Om du inte vill periodisera intäkt inom samma tidsintervall som du använder för fakturering måste du även skapa en periodiseringsperiod.

I följande tabell får du en översikt över vilka periodiseringsperioder du kan ange för vilka faktureringsperioder:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Faktureringsperiod</p></th>
<th><p>Periodiseringsperiod</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>År</strong></p></td>
<td><ul>
<li><p><strong>År</strong></p></li>
<li><p><strong>Kvartal</strong></p></li>
<li><p><strong>Månad</strong></p></li>
<li><p><strong>Dag</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Kvartal</strong></p></td>
<td><ul>
<li><p><strong>Kvartal</strong></p></li>
<li><p><strong>Månad</strong></p></li>
<li><p><strong>Dag</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Månad</strong></p></td>
<td><ul>
<li><p><strong>Månad</strong></p></li>
<li><p><strong>Dag</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Vecka</strong></p></td>
<td><ul>
<li><p><strong>Dag</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Dag</strong></p></td>
<td><ul>
<li><p><strong>Dag</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>

Ställa in faktureringsperioden är en obligatorisk del av den övergripande inställningen av abonnemangsgrupp. Du kan bestämma om att ange en periodiseringsperiod för abonnemangsgruppen. Om du anger en periodiseringsperiod för abonnemangsgruppen, föreslås denna period i fältet **Periodkod**. Det här fältet finns i formuläret **Periodisera abonnemangsintäkt** när du periodiserar abonnemangsintäkt. Periodiseringsperioden är dock valfri information om abonnemangsgruppen.


> [!NOTE]
> <P>Använd följande sökväg för att öppna formuläret <STRONG>Periodisera abonnemangsintäkt</STRONG>. Klicka på <STRONG>Servicehantering</STRONG> &gt; <STRONG>Periodisk</STRONG> &gt; <STRONG>Serviceabonnemang</STRONG> &gt; <STRONG>Periodisera abonnemangsintäkt</STRONG>.</P>


## <a name="transactions"></a>Transaktioner

Du kan kontrollera antalet redovisningstransaktioner som skapas när du bokför periodiserad intäkt. Definiera om redovisningstransaktionerna ska skapas som en totalsumma eller per rad på prenumerationer.

## <a name="specify-the-level-of-posting-details-to-display-for-accrued-transactions"></a>Ange detaljnivån för bokföringarna som ska visas för periodiserade transaktioner

1.  Klicka på **Projekthantering och redovisning** \> **Inställningar** \> **Parametrar för projekthantering och redovisning**.

2.  På fliken **Ekonomi** i fältet **Faktura**, välj **Total** eller **Rad**.


## <a name="see-also"></a>Se även

[Periodisera abonnemangsintäkt](accrue-subscription-revenue.md)

  



