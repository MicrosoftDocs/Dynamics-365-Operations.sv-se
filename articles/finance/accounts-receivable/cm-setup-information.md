---
title: Inställning för kredithantering
description: I det här avsnittet beskrivs de inställningar som krävs för kredithantering.
author: mikefalkner
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4cfb747c9a510474d0ca27a595158cd6e6d24359a37f665f64b4c640536874aa
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6723953"
---
# <a name="credit-management-setup"></a>Inställning för kredithantering 

[!include [banner](../includes/banner.md)]

## <a name="credit-management-workflows"></a>Arbetsflöden för kredithantering

Gå till **Kredit och inkasso \> Inställningar \> Arbetsflöde för kredithantering** för att definiera vilka arbetsflöden som används för att hantera justeringar av kreditgränser.

- Du kan skapa ett arbetsflöde som gör att du kan godkänna en batch med kreditgränsjusteringar genom ett enda godkännande.
- Du kan lägga till ett arbetsflöde på radnivå så att justeringar av kreditgräns kan godkännas individuellt.
- Du kan skapa ett arbetsflöde för frisläppning som automatiskt dirigerar undantag till en arbetsflödesprocess.

## <a name="blocking-rules"></a>Spärrningsregler

### <a name="ranking-payment-terms"></a>Rangordna betalningsvillkor

Du kan spärra en försäljningsorder om betalningsvillkoren på ordern inte matchar standard betalningsvillkoren för kunden. Men ibland kan betalningsvillkoren skilja sig åt men du vill inte vänta med att spärra ordern. Du kan rangordna betalningsvillkor så att vissa av dem får samma rangordning, medan andra har en högre eller lägre rangordning.

Om rangordningarna för betalningsvillkor är aktiva och om betalningsvillkoren för ordern har en högre rangordning än standard betalningsvillkoren för kunden kommer försäljningsordern att spärras.

För att ställa in rangordning av betalningsvillkoren gå till **Kredit och inkasso \> Inställningar \> Inställningar för kredithantering \>Rangordna betalningsvillkoren**  

### <a name="ranking-settlement-discounts"></a>Rangordna kvittningsrabatter

Du kan spärra en försäljningsorder om kassarabatten på ordern inte matchar standard kassarabatten för kunden. Men ibland kan kassarabatten skilja sig åt men du vill inte vänta med att spärra ordern. Du kan rangordna kassarabatten så att vissa av dem får samma rangordning, medan andra har en högre eller lägre rangordning.

Om rangordningarna för kassarabatter är aktiva och kassarabatten för ordern har en högre rangordning än standard kassarabatten för kunden kommer försäljningsordern att spärras.

För att ställa in rangordning av betalningsvillkoren gå till **Kredit och inkasso \> Inställningar \> Inställningar för kredithantering \>Rangordna kvittningsrabatter**  

## <a name="reasons"></a>Orsaker

Flera typer av orsaker används vid kredithantering:

- Spärrorsaker anger varför en försäljningsorder spärrades.
- Frisläppningsorsaker tilldelas en order när den frigörs från spärrning.
- Statusorsaker anger varför en kontostatus har tilldelats en kund.

Du kan ställa in orsaken på sidan **kredithanteringsorsaker** (**kredit och inkasso \> inställningar \> kredithantering \> inställning för kredithantering**).

1. I fältet **Orsakstyp** välj typ av orsak: **spärr**, **frisläppning** eller **status**.
2. I fältet **Orsak** anger du ett namn för orsaken.
3. Ange en orsakskod i fältet **Beskrivning**.

## <a name="credit-management-groups"></a>Kredithanteringsgrupper

Kredithanteringsgrupper används för att identifiera kunder eller kundgrupper som har samma egenskaper för kredithantering. Kredithanteringsgrupper kan till exempel användas för att bestämma spärr- och exkluderingsreglerna för kredithantering för kunder.

Du kan skapa kredithanteringsgrupper på sidan **kredithanteringsgrupper** (**kredit och inkasso \> inställningar > inställning för kredithantering \> kredithanteringsgrupper**).

1. Klicka på **Nytt** för att skapa en ny rad.
2. Ange ID för gruppen. ID kan ha upp till tecken.
3. I fältet **Beskrivning**, ange ett namn för gruppen. Namnet kan ha upp till 60 tecken.

Kredithanteringsgruppen tilldelas till en kund på snabbfliken **kredit och inkasso** på sidan **alla kunder** (**kundreskontra \> kunder \> alla kunder**).

## <a name="account-statuses"></a>Kontostatus

Du kan skapa kontostatusar för att identifiera ett kundkontos kreditposition. Du kan definiera en status och dess inverkan på fakturerings- och leveransspärrprocesserna. Kontostatus kan också användas för att bestämma spärrningsregler för en kund.

Du kan skapa kontostatus på sidan **kontostatus** (**kredit och inkasso \> inställningar > inställning för kredithantering \> kontostatus**).

1. Lägg till en kontostatus och ange en beskrivning som representerar kreditställningen för en kund. Använd till exempel **Normal** om du vill ange att en kund är på en bra position och att öppna order är beroende av standardbearbetning för kredithantering.
2. I fälten **fakturering** och **leverans spärrad** väljer du den typ av spärr som ska göras för kunder med denna kontostatus. Du kan spärra all bearbetning, spärra fakturabearbetning eller inte spärra bearbetning när kreditgränsreglerna tillämpas.

## <a name="scoring-groups"></a>Bedömningsgrupper

Du kan ställa in poänggrupper för att definiera riskfaktorer och kriterier som används för att mäta dem. När information om en kund tillämpas på en resultatgrupp beräknas en poäng för varje riskfaktor och används för att placera kunden i en riskgrupp. Riskgruppen kan användas för att identifiera kreditvärdighet och för att beräkna automatiska kreditgränser.

Du kan skapa poänggrupper på sidan **poänggrupper** (**kredit och inkasso \> inställningar \> inställning för kredithantering \> risk \> poänggrupper**).

1. Skapa en poänggrupp och ange ett namn för den.
2. Ange en beskrivning för att ytterligare beskriva poänggruppen.
3. Välj en grupptyp. Det finns åtta fördefinierade typer. Du kan också välja **användardefinierad** för att definiera en grupptyp som passar bättre för din organisation.
4. Välj en resultattyp för att definiera hur poänggruppen ska beräkna riskpoängen. Följande alternativ är tillgängliga:

    - **Intervall** – Använd det här alternativet om du vill definiera ett intervall med värden som ska användas för att beräkna poäng.
    - **Användardefinierad** – Använd det här alternativet om du manuellt vill definiera en lista med värden som ska användas för poängen.

5. Om du har valt **intervall** som poängtyp, lägger du till rader för att definiera intervallet av värden och motsvarande resultat.

    1. I fältet **från värde** anger du det lägsta värdet i intervallet.
    2. I fältet **till värde** anger du det högsta värdet i intervallet.
    3. I fältet **Poäng** anger du poängen som ska tilldelas när värdet som anges finns i intervallet "från"/"till".

    Om du har valt **användardefinierad** som poängtyp, lägger du till rader för att definiera användardefinierade värden och motsvarande resultat.

    1. I fältet **värde** anger du det användardefinierade värde som ska tillhandahållas av kundinformationen.
    2. I fältet **Poäng** anger du poängen som ska tilldelas när värdet som anges finns i intervallet "från"/"till".

## <a name="risk-classification"></a>Riskklassificering

Du kan definiera riskbedömningar som kan tilldelas till kunder, baserat på deras riskpoäng. Riskpoängen beräknas genom att kundinformationen jämförs med kundinformationen för varje resultatgrupp. Poängen summeras och totala poängen jämförs med värdena i riskgruppinställningarna för att identifiera den riskgrupp som kunden tillhör. Riskgruppens poäng används sedan för att definiera spärr- och exkluderingsregler för kredithantering för kunden.

Du kan ställa in riskgrupper på sidan **Riskbedömningar** (**kredit och inkasso \> inställningar \> inställning för kredithantering \> risk \> riskklassificering**).

1. Ange ett risk grupps-ID.
2. Ange en beskrivning för att ytterligare förklara riskgruppen.
3. Ange ett antal resultat som ska användas för att avgöra vilka kunder som tillhör riskgruppen.
4. Välj en riskgruppsindikator för att ange den symbol som representerar riskgruppen.

## <a name="guaranteeinsurance-types"></a>Garanti-/försäkringstyper

Du kan ställa in garanti-/försäkringstyper på sidan **garanti/försäkringstyper** (**kredit och inkasso \> inställningar \> inställning för kredithantering \> försäkring och garantier \> försäkrings- och garantityper**).

1. Ange en garanti eller försäkringstyp som identifierar namn på borgenär eller försäkringsagent.
2. Ange en beskrivning som beskriver borgenär/försäkringsagent.

## <a name="coverage-types"></a>Försäkringstyper

Täckningstyper kan användas för att ytterligare klassificera försäkringsbrev. De kan inte användas med garantier.

Du kan lägga till täckningstyper på sidan **Täckningstyper** (**kredit och inkasso \> inställningar \> inställning för kredithantering \> försäkring och garantier \> täckningstyper**).

1. Ange en täckningstyp som identifierar den typ av täckning som ska läggas till som försäkring eller garanti.
2. Ange en beskrivning av täckningstypen.

## <a name="automatic-credit-limits"></a>Automatiska kreditgränser

Du kan skapa kriterier för automatiska kreditgränser på sidan **automatiska kreditgränser** (**kredit och inkasso \> inställningar \> inställning för kredithantering \> risk \> automatiska kreditgränser**).

1. Välj en riskgrupp som den automatiska kreditgränsen ska tilldelas till.
2. Välj valuta för den automatiska kreditgränsen. Du kan skapa flera automatiska kreditgränser i olika valutor för samma riskgrupp.
3. Ange intäktsbeloppet som representerar den maximala företagsintäkten som kan användas för den här automatiska kreditgränsen. När kreditgränser skapas jämförs intäktsbeloppet med ett intäktsvärde som finns på sidan **Finance** (**kundreskontra \> alla kunder \> välj en kund \> allmän \> statistik \> ekonomi**). Systemet använder det senaste värdet i avsnittet **översikt**.

Följ dessa steg för att lägga till rader som representerar den kreditgräns som kommer att genereras utifrån de valda kriterierna.

1. Välj en resultatgrupp som definierar kundinformationen som ska användas för att beräkna kreditgränsen.
2. Välj den jämförelseoperator som definierar hur poänggruppens informationen ska utvärderas.
3. Ange det värde som ska jämföras med värdet som angetts för poänggruppen.
4. Ange den kreditgräns som ska tilldelas om kundinformationen matchar värdet som angetts för poänggruppen. Du kan till exempel skapa en automatisk kreditgräns för den **lägsta** poänggruppen. Om åren i företaget är en av poänggrupperna kan du definiera en rad som tilldelar en 100 000 kreditgräns om kunden har haft verksamheten fem år och en annan rad som tilldelar en 200 000 kreditgräns om kunden har haft verksamheten i 10 år.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]