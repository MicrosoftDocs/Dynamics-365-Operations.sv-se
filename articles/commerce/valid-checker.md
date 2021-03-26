---
title: Konsekvenskontroll av butikstransaktion
description: Det här ämnet beskriver funktionen för konsekvenskontroll av transaktioner i Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 10/07/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-01-15
ms.dyn365.ops.version: 10
ms.openlocfilehash: cce0d408ac6d372fb726eff8fa4b0358ec200243
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211005"
---
# <a name="retail-transaction-consistency-checker"></a>Konsekvenskontroll av butikstransaktion

[!include [banner](includes/banner.md)]

Det här ämnet beskriver funktionen för konsekvenskontroll av transaktioner i Microsoft Dynamics 365 Commerce. Konsekvenskontrollen identifierar och isolerar inkonsekventa transaktioner innan de används i bokföringsprocessen för utdrag.

Det går inte att bokföra utdrag om det finns inkonsekventa data i handelstransaktionsregistren. Dataproblemet kan bero på oförutsedda problem i kassaprogrammet, eller om transaktioner har importerats felaktigt från kassasystem från tredje part. Dessa inkonsekvenser kan till exempel uppenbara sig på följande sätt: 

- Transaktionssumman i huvudtabellen stämmer inte överens med transaktionssumman på raderna.
- Radantalet i huvudtabellen stämmer inte överens med antalet rader i transaktionstabellen.
- Momsen i huvudtabellen stämmer inte överens med momsbeloppet på raderna. 

När inkonsekventa transaktioner fångas upp i bokföringsprocessen för utdrag, skapas inkonsekventa försäljningsfakturor och betalningsjournaler, och bokföringsprocessen för utdrag går inte att utföra. När utdragen ska återställas från ett sådant tillstånd krävs komplexa datakorrigeringar av flera transaktionsregister. Konsekvenskontrollen av transaktioner förhindrar sådana problem.

I följande diagram visas bokföringsprocessen där konsekvenskontroll av transaktioner tillämpas.

![Bokföringsprocess för utdrag med konsekvenskontroll av transaktioner](./media/validchecker.png "Bokföringsprocess för utdrag med konsekvenskontroll av butikstransaktioner")

Batchprocessen **Validera butikstransaktioner** kontrollerar att butikens handelstransaktionsregister är konsekventa i följande scenarier.

- **Kundkonto** – Validerar att kundkontot i transaktionsregistren finns i huvudkontorets kundmall.
- **Radräkning** – Validerar att antalet rader, som anges i transaktionshuvudregistret, motsvarar antalet rader i försäljningstransaktionsregistren.
- **Pris inklusive moms** – Validerar att parametern **Pris inklusive moms** är konsekvent på alla transaktionsrader och att priset på försäljningsraden är förenligt med konfigurationen av pris inklusive moms och momsbefrielse.
- **Betalningsbelopp** – Validerar att betalningsposterna stämmer överens med betalningsbeloppet i huvudet, men tar även hänsyn till konfigurationen för öresavrundning i redovisningen.
- **Bruttobelopp** – Validerar att bruttobeloppet i huvudet är summan av nettobeloppen på raderna plus momsbeloppet, men tar också hänsyn till konfigurationen för öresavrundning i redovisningen.
- **Nettobelopp** – Validerar att nettobeloppet i huvudet är summan av nettobeloppen på raderna, men tar också hänsyn till konfigurationen för öresavrundning i redovisningen.
- **Under-/överbetalning** – Validerar att skillnaden mellan bruttobeloppet i huvudet och betalningsbeloppet inte överskrider den maximala konfigurationen av underbetalning/överbetalning, men tar också hänsyn till konfigurationen för öresavrundning i redovisningen.
- **Rabattbelopp** – Validerar att rabattbeloppet för rabattregistren och rabattbeloppet i registren för butikstransaktionsrader är konsekventa och att rabattbeloppet i huvudet är lika med summan av rabattbeloppen på raderna, men tar också hänsyn till konfigurationen för öresavrundning i redovisningen.
- **Radrabatt** – Validerar att radrabatten på transaktionsraden är lika med summan av alla rader i rabattregistren som motsvarar transaktionsraden.
- **Presentkortsartikel** – Det går inte att returnera presentkortsartiklar i Commerce. Saldot på ett presentkort kan dock betalas ut kontant. En presentkortsartikel som bearbetas som en returrad i stället för en utbetalningsrad gör att utdragsbokföringsprocessen misslyckas. Valideringsprocessen för presentkortsartiklar garanterar att de enda returraderna för presentkortsartiklar i transaktionsregistren utgörs av rader för kontantutbetalning av presentkort.
- **Negativt pris** – Validerar att det inte finns några negativa pristransaktionsrader.
- **Artikel och variant** – Validerar att artiklar och varianter på transaktionsraderna finns i artikel- och varianthuvudfilen.
- **Momsbelopp** – Validerar att skatteposterna stämmer med skattebeloppen på raderna.
- **Serienummer** – Validerar att serienumret finns på transaktionsraderna för artiklar som kontrolleras med serienummer.
- **Förtecken** – Validerar att förtecknet på kvantiteten och nettobeloppet är detsamma i alla transaktionsrader.
- **Affärsdatum** – Validerar att de finansiella perioderna för alla affärsdatum för transaktionerna är öppna.
- **Avgifter** – Validerar att avgiftsbeloppen i huvudet och på raderna överensstämmer med konfigurationen av pris, inklusive moms och momsbefrielse.

## <a name="set-up-the-consistency-checker"></a>Ställa in konsekvenskontrollen

Konfigurera batchprocessen "Validera butikstransaktioner" i **Retail och Commerce \> Retail och Commerce IT \> Kassabokföring** för periodiska körningar. Batchjobbet kan schemaläggas utifrån butikens organisationshierarki, vilket påminner om hur processerna "Beräkna utdrag i batch" och "Bokför utdrag i batch" konfigureras. Vi rekommenderar att du konfigurerar den här batchprocessen så att den körs flera gånger under en dag och schemalägga den så att den körs i slutet av varje P-jobbskörning.

## <a name="results-of-validation-process"></a>Resultat av valideringsprocessen

Resultaten av batchprocessens valideringskontroll märks i motsvarande transaktion. Fältet **Valideringsstatus** i transaktionsposten anges antingen till **Slutförd** eller **Fel**, och datumet för den senaste valideringskörningen visas i fältet **Senaste valideringstid**.

Om du vill visa en mer beskrivande feltext som berör ett valideringsfel markerar du aktuell butikstransaktionspost och klickar på **Valideringsfel**.

Transaktionerna som inte klarar valideringskontrollen och de transaktioner som ännu inte validerats används inte i utdragen. Under processen "Beräkna utdrag" meddelas användarna om det finns transaktioner som kan ha inkluderats i uttrycket men inte som inte har det.

Om ett valideringsfel inträffar går det bara att korrigera felet genom att kontakta Microsoft Support. I en framtida version kommer en funktion att läggas till som gör att användarna kan korrigera posterna via användargränssnittet. Funktioner för loggning och granskning kommer också att införas, vilka gör det möjligt att spåra ändringshistoriken.

> [!NOTE]
> Ytterligare valideringsregler för andra scenarier kommer i framtida versioner.


[!INCLUDE[footer-include](../includes/footer-banner.md)]