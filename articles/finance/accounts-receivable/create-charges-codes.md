---
title: Skapa avgiftskoder
description: I det här avsnittet beskrivs hur du konfigurerar debiteringskoder för både Leverantörsreskontra och Kundreskontra.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MarkupTable
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 034be190890a67fd0921d40fffdc704b9d6d5df7
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/19/2022
ms.locfileid: "8014089"
---
# <a name="create-charges-codes"></a>Skapa avgiftskoder

I det här avsnittet beskrivs hur du konfigurerar debiteringskoder för både Leverantörsreskontra och Kundreskontra. Om din organisation kräver att försäljningsbelopp eller inköpsbelopp spåras i tillägg till radartiklar på en försäljnings- eller inköpsorder, kan du använda avgiftskoder i det här syftet. Du betalar till exempel frakt och försäkring på en inköpsorder, och dessa belopp specificeras separat på inköpsordern. Du kan ange om dessa belopp ska bokföras på utgiftskonton eller läggas till i kostnaden för artiklarna.

## <a name="set-up-charges-codes-for-accounts-receivable"></a>Ställa in avgiftskoder för kundreskontra

Om du vill skapa avgiftskoder för kundreskontra följer du dessa steg.

1. Gå till **Kundreskontra** &gt; **Ställa in avgifter** &gt; **Avgiftskod**.
2. Välj **Ny**.
3. I fältet **Avgiftskod** ange en kod för avgiften.
3. Ange en beskrivning av avgiften i fältet för **beskrivning**.
4. Valfritt: I fältet **Momsgrupp för artikel**, välj en artikelmomsgrupp.
5. På snabbfliken **Bokföring** anger du hur avgiften ska debiteras och krediteras automatiskt.
6. Om du valde **Redovisningskonto** som debettyp eller kredittyp ska du ange bokföringstypen i fältet **Bokföring** och ange huvudkontot i fältet **konto**.

### <a name="example"></a>Exempel

Din kund betalar avgiften. Det läggs därför till i försäljningsordersummorna. Då ställa in följande bokföringsinformation:

- I fältet **Typ** i avsnittet **Debet** väljer du **Kund/Leverantör** för att lägga till fakturadebiteringen på kundens konto.
- I fältet **Typ** i avsnittet **Kredit** välj **Redovisningskonto**. Fältet **Konto**, välj huvudkontot för intäkter från fakturaavgifter.

> [!NOTE]
> Om debettypen eller kredittypen för den valda koden är antingen **Huvudbokskonto** eller **Artikel** kan du ange en annan valuta för debiteringstransaktionen.

Du kan skriva ut texten för avgifter på det språk som är tilldelad kunden. Välj **Översättningar** om du vill ange texten för debiteringskoden på andra språk.

## <a name="set-up-charges-codes-for-accounts-payable"></a>Ställa in avgiftskoder för leverantörsreskontra

Om du vill skapa avgiftskoder för leverantörsreskontra följer du dessa steg.

1. Gör något av följande:

    - Gå till **Leverantörsreskontra** &gt; **Avgifter** **inställningar** &gt; **Avgiftskod**.
    - Gå till **Anskaffning och källa** &gt; **Inställningar** &gt; **Avgifter** &gt; **Avgiftskod**.

2. Välj **Ny**.
3. I fältet **Avgiftskod** ange en kod för avgiften.
3. Ange en beskrivning av avgiften i fältet för **beskrivning**.
4. Valfritt: I fältet **Momsgrupp för artikel**, välj en artikelmomsgrupp.
5. Valfritt: I fältet **Högsta beloppet**, ange det högsta tillåtna beloppet för tilläggskoden.

    Det här fältet används för att validera tillägg för leverantörsfakturor. För att aktivera validering av avgifter, markera kryssrutan **Aktivera fakturamatchningsvalidering** på fliken **Fakturavalidering** på sidan **Parametrar för leverantörsreskontra**.

    > [!IMPORTANT]
    > Om du vill validera tillägg för fakturor måste du också skapa en instans av en policyregeltyp som baseras på avgifter för den specifika leverantörsfakturapolicyn.

6. På snabbfliken **Bokföring** anger du hur avgiften ska debiteras och krediteras automatiskt.
7. Om du valde **Redovisningskonto** som debettyp eller kredittyp ska du ange bokföringstypen i fältet **Debetbokföring** och **Kreditbokföring** och ange huvudkontot i fälten **Debetkonto** och **Kreditkonto**.
8. Om du vill aktivera jämförelse av debiteringsvärden för en faktura som innehåller tillägg från motsvarande inköpsorderhuvud eller -rader markerar du kryssrutan **Jämför inköpsorder- och fakturavärden**.

### <a name="example"></a>Exempel

Du kan registrera kostnaden som en utgift, som en del av summan för inköpsordern eller leverantörsfakturan. Följ dessa steg för att ställa in information om inlägg. 

- I fältet **Typ** i avsnittet **Kredit** väljer du **Kund/Leverantör** för att lägga till fakturadebiteringen på leverantörens konto.
- I fältet **Typ** i avsnittet **Debet** välj **Redovisningskonto**. Fältet **Konto**, välj huvudkontot för utgifter från fakturaavgifter.

Följ dessa steg om du vill ställa in bokföringsinformation så att enhetskostnaden läggs till artikelkostnaden.

- I fältet **Typ** i avsnittet **Kredit** väljer du **Kund/Leverantör** för att lägga till fakturadebiteringen på leverantörens konto.
- I fältet **Typ** i avsnittet **Debet**, välj **Artikel** för att lägga till avgiften på artikelkostnaden.

> [!NOTE]
> Du kanske vill använda en annan valuta än den som anges på inköpsordern eller fakturan. Du kan ange en annan valuta om debettypen eller kredittypen för den valda koden är antingen **Huvudbokskonto** eller **Artikel**.

Du kan skriva ut texten för avgifter på det språk som är tilldelad kunden. Välj **Översättningar** om du vill ange texten för debiteringskoden på andra språk.
