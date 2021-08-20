---
title: Momsberäkning för allmänna journalrader
description: Det här ämnet förklarar hur moms beräknas för olika typer av konton (leverantör, kund, redovisning och projekt) på allmänna journalrader.
author: EricWang
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: EricWang
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 96a87e5de3fb247e4554a64ecff3a4c63477b6a70f7a969b80f538601cda08bb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746378"
---
# <a name="sales-tax-calculation-on-general-journal-lines"></a>Momsberäkning för allmänna journalrader
[!include [banner](../includes/banner.md)]

Det här ämnet förklarar hur moms beräknas för olika typer av konton (leverantör, kund, redovisning och projekt) på allmänna journalrader.

Processen kan delas in i tre steg:

- Bestämma momsriktningen.

- Avgör vilket momsbelopp som ska lagras i ett tillfälligt momsregister.

- Bestäm momsbeloppet och kontot på verifikationen.

## <a name="determine-the-sales-tax-direction"></a>Bestämma momsriktningen

Hur momsriktningen bestäms beror på typen av konto i verifikationen. Momsriktningen bestäms av kombinationen av kontotypen och momskoden. De följande avsnitten är möjligheterna i mer detaljerat. 

### <a name="account-type-is-project"></a>Kontotyp är projekt

Om en verifikation har en journalrad där kontotypen är **projekt**, använder alla journalrader i verifikationen samma momsriktning. På bilden nedan visas regeln. Följande poäng visar de möjliga momsriktningarna för projektkonton.

•   Om momskoden är importavgift är momsriktningen importavgift.

•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.

•   Om momskoden är Inomeuropeisk moms är momsriktningen Utgående moms.

•   Om momskoden är återfört tillägg moms är momsriktningen Utgående moms.

Annars är momsriktningen Ingående moms.

Följande diagram visar regeln grafiskt.

![Momsriktningsmöjligheter för projektkonton.](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-vendor"></a>Kontotypen är leverantör

Om en verifikation har en journalrad där kontotypen är **leverantör**, använder alla journalrader i verifikationen samma momsriktning. Följande poäng visar de möjliga momsriktningarna för leverantörskonton. 

•   Om momskoden är importavgift är momsriktningen importavgift.

•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.

•   Om momskoden är Inomeuropeisk moms är momsriktningen Utgående moms.

•   Om momskoden är återfört tillägg moms är momsriktningen Utgående moms.

Annars är momsriktningen Ingående moms.

Följande diagram visar regeln grafiskt.

![Momsriktningsmöjligheter för leverantörskonton.](media/Sales-Tax-Direction-Vendor.jpg)

### <a name="account-type-is-customer"></a>Kontotyp är kund

Om en verifikation har en journalrad där kontotypen är **kund**, använder alla journalrader i verifikationen samma momsriktning. Följande poäng visar de möjliga momsriktningarna för kundkonton.

•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.

•   Om momskoden är Inomeuropeisk moms är momsriktningen Ingående moms.

•   Om momskoden är återfört tillägg moms är momsriktningen Ingående moms.

Annars är momsriktningen Utgående moms.

Följande diagram visar regeln grafiskt.

![Momsriktningsmöjligheter för kundkonton.](media/Sales-Tax-Direction-Customer.jpg)

### <a name="account-type-is-ledger"></a>Kontotypen är Redovisning

Följande illustration visar den regel som gäller när en verifikation bara har journalrader där kontotypen är **redovisning**. Följande poäng visar de möjliga momsriktningarna för redovisningskonton.

•   Om momskoden är importavgift är momsriktningen importavgift.

•   Om momskoden är momsbefriad är momsriktningen är skattefritt inköp.

Annars, om journalbeloppet är debet (positivt), är momsriktningen för Ingående moms. Om journalbeloppet är kredit (negativ), är momsriktningen Utgående moms.

Följande diagram visar regeln grafiskt.

![Momsriktningsmöjligheter för redovisningskonton.](media/Sales-Tax-Direction-Ledger.jpg)

#### <a name="override-the-sales-tax-direction"></a>Åsidosätt momsriktningen

Du kan åsidosätta momsriktningen när verifikationen bara innehåller rader där kontotypen är **redovisning**.

Gå till **Redovisning \> Kontoplan \> Konton \> Huvudkonton** och välj snabbfliken **Juridisk person åsidosätter**.

## <a name="determine-the-sales-tax-amount"></a>Bestämma momsbelopp

I det här avsnittet beskrivs hur tecknet för momsbelopp beräknas.

![Sidan för momstransaktioner.](media/sales-tax-amount-sign.jpg)

I följande register visas den allmänna regeln för bestämning av momsriktning och tecken på momsbelopp i det tillfälliga momsregistret.

| Journalradsbelopp | Momsriktning  | Momsbelopptecken |
|---------------------|----------------------|-----------------------|
| Positiva            | Ingående moms | Positiva              |
| Positiva            | Utgående moms    | Negativa              |
| Negativa            | Ingående moms | Negativa              |
| Negativa            | Utgående moms    | Positiva              |

Det finns en särskild regel för verifikationer som bara har raderna **Projekt** eller **Redovisning** när en moms grupp eller artikelmomsgrupp har valts på raden **Redovisning**. Denna regel styrs genom funktionen **Aktivera funktionen för oboeroende momsberäkning för allmänna journaler**. När den här funktionen inaktiveras använder momsbeloppet för raden **redovisning** debet-/kreditriktningen för raden **projekt**. När den här funktionen aktiveras använder momsbeloppet för raden **redovisning** debet-/kreditriktningen. I följande tabeller visas regeln för varje scenario. 

**Regel när funktionen är aktiverad**

| Journalradbelopp för projekt | Momsriktning  | Momsbelopptecken |
|--------------------------------|----------------------|-----------------------|
| Positiva                       | Ingående moms | Positiva              |
| Negativa                       | Ingående moms | Negativa              |

**Regel när funktionen är inaktiverad**

| Journalradbelopp för redovisning  | Momsriktning  | Momsbelopptecken |
|--------------------------------|----------------------|-----------------------|
| Positiva                       | Ingående moms | Positiva              |
| Negativa                       | Ingående moms | Negativa              |

## <a name="determine-the-sales-tax-amount-and-account-on-the-voucher"></a>Bestäm momsbeloppet och kontot på verifikationen

När du bokför moms hämtas huvudkontot från profilen för redovisningens bokföringsgrupprofil. När moms inkommer använder systemet det konto för ingående moms som anges i profilen. För moms som ska betalas använder systemet det konto för utgående moms som anges i profilen.

Tabellen nedan visar den allmänna regeln.

| Momsriktning  | Momsbelopptecken | Momskonto      | Belopp på verifikationen |
|----------------------|-----------------------|------------------------|-------------------|
| Ingående moms | Positiva              | Konto för ingående moms | Positiv (Debet)  |
| Ingående moms | Negativa              | Konto för ingående moms | Negativ (kredit)  |
| Utgående moms    | Positiva              | Konto för utgående moms    | Negativ (kredit)  |
| Utgående moms    | Negativa              | Konto för utgående moms    | Positiv (Debet)  |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
