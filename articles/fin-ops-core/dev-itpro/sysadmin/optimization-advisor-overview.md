---
title: Rådgivning om optimering – översikt
description: Det här avsnittet beskrivs hur du kan använda optimerings-advisor för att säkerställa optimal konfiguration av Finance and Operations.
author: roxanadiaconu
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SelfHealingWorkspace
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: sericks
ms.search.validFrom: 2017-12-01
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 241be956fb5026fdbf65d4a24aa7f0202b654189
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/03/2021
ms.locfileid: "6339166"
---
# <a name="optimization-advisor-overview"></a>Rådgivning om optimering – översikt

[!include [banner](../includes/banner.md)]

Det här avsnittet beskrivs hur du kan använda optimerings-advisor för att säkerställa optimal konfiguration av Finance and Operations.

## <a name="overview"></a>Översikt

Felaktig konfiguration och inställning av en modul kan allvarligt påverka tillgängligheten för programfunktioner, systemprestanda och smidiga affärsprocesser. Kvaliteten på affärsdata (exempelvis att data är korrekta, kompletta och rena) påverkar också systemets prestanda och organisationens beslutsfattningsförmåga, produktivitet, och så vidare.

Arbetsytan **Optimerings-advisor** är ett verktyg som låter privilegierade användare, affärsanalytiker, funktionskonsulter och IT-supportfunktioner identifiera problem i modulkonfiguration och affärsdata. Optimerings-advisor föreslår metodtips för modulkonfigurationen och identifierar affärsdata som är inaktuell eller felaktig.

Optimerings-advisor kör regelbundet en uppsättning metodregler. En standarduppsättning regler finns, men användare kan också skapa regler som är specifika för deras anpassningar, lösningar från oberoende programvaruleverantörer (ISV) och affärsdata. Mer information om hur du skapar regler finns i [Skapa regler för Rådgivning om optimering](./create-rules-optimization-advisor.md).

När ett brott mot en regel upptäcks skapas en optimeringsmöjlighet och visas på arbetsytan **Optimerings-advisor**. En användare kan vidta lämpliga korrigeringsåtgärder direkt från arbetsytan **Optimerings-advisor**.

Affärsmöjligheter kan vara företagsspecifika eller mellan företag, beroende på vilken typ av inställningar och data som har godkänts. Affärsmöjligheter mellan företag kan visas från alla företag. Du måste först välja företaget för att visa alla affärsmöjligheter för ett specifikt företag.

Standardsäkerhetsprinciper gäller för optimeringsmöjligheter. Exempelvis visas optimeringsmöjligheter som är relaterade till konfigurationen av modulen **Lagerstyrning** bara för användare som har åtkomst till lagerhantering och kan ändra inställningarna.

När du utför en åtgärd på några optimeringsmöjligheter beräknar systemet effekten av affärsmöjligheten med avseende på minskning av affärsprocessernas körtid. Funktionen är tyvärr inte tillgänglig för alla optimeringsmöjligheter.

Om du vill veta mer om klassificering av optimering kan titta på kort [ptimerings-advisor i Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=MRsAzgFCUSQ)-video.

## <a name="optimization-rules"></a>Optimeringsregler

För att visa en fullständig lista över regler för optimerings-advisor och se hur ofta reglerna utvärderas, gå till **Systemadministration**&gt;**Periodiska uppgifter**&gt;**Underhåll diagnostikregel – validering**. Endast regler som har statusen **Aktivstatus** utvärderas. Utvärderingsfrekvensen kan anges till **Dagligen**, **Varje vecka**, **Varje månad** eller **Ej tidsplanerad**.

För att utlösa utvärderingen av ej tidsplanerade regler eller utvärdera periodiska regler utanför deras fördefinierad plan går du till **Systemadministration**&gt;**Periodiska uppgifter**&gt;**Diagnostikregel – validering av tidsplan**. I dialogrutan **Diagnostikregel – validering**, välj en utvärderingsfrekvens. Alla regler som innehåller den angivna frekvensen kommer att utvärderas.

Den aktuella uppsättningen optimeringsregler kan delas in i följande kategorier.

### <a name="module-configuration-and-setup"></a>Modulkonfiguration och inställning

Inställningarna av lagerstyrning är en komplicerad process. För att underlätta processen, har vissa regler införts för att verifiera korrekt inställning. Till exempel validerar en regel inställningen av lagerställets platsdirektiv för fasta lagerplatser för produktvarianten för försäljningsorder och överföringsorder.

Dessutom reglerar vissa regler om funktioner som har aktiverats faktiskt används. En regel bestämmer till exempel om du använder modulen **Huvudplanering**. Om regeln bestämmer att du inte använder modulen, skapas en optimeringsmöjlighet för att föreslå att du inaktiverar planeringsprocesserna.

### <a name="system-configuration"></a>Systemkonfiguration

Om specifik funktionalitet som styrs av en konfigurationsnyckel inte används, skapas en optimeringsmöjlighet som föreslår att du inaktiverar konfigurationsnyckeln. Exempel på konfigurationsnycklar inkluderar **Faktisk/nominell vikt**, **Budgetplanering**, **Projekt** och **Lista över godkända leverantörer**.

### <a name="business-data-consistency-and-cleanup"></a>Överensstämmelse och rensning av affärsdata

Om huvuddata inte är korrekt (till exempel om du har måttenhetskonverteringar för enheter som inte har definierats, eller om du har måttenhetskonverteringar som innehåller en division med 0 \[noll\]), skapas en optimeringsmöjlighet för att föreslå att du korrigerar data. 

Om du har för många historikposter för batchjobb, föråldrade artiklar, stängda behållningsposter för lageraktiverade artiklar etc, eller om dessa poster och artiklar är för gamla, skapas optimeringsmöjligheter för att du ska rensa upp data. Genom att hålla dina data rena kan du förbättra systemets totala prestanda.

### <a name="best-practices"></a>Regelverk

Om du inte kör några affärsprocesser enligt metodtipsen (om du till exempel kör förstängning av lager innan lagret stängs eller om du använder schemalagda batcher för batchöverföring för redovisningsjournaler) informerar optimeringsmöjligheter dig om metodtips och ber dig att följa den.

## <a name="optimization-opportunities"></a>Optimeringsmöjligheter

Om du vill visa optimeringsmöjligheter som skapas vid bedömningen av optimeringsregler öppna arbetsytan **Optimerings-advisor**.

På denna arbetsyta kan du visa mer information om en affärsmöjlighet genom att markera **Mer information**. Om du vill att systemet ska åtgärda och korrigera inställningarna, rensa data och så vidare, så att du inte behöver öppna tillhörande sidor själv anger du **Vidta åtgärder**.

Det finns inga arbetsflöden för optimeringsmöjligheter. När du har valt **Vidta åtgärder** eller använda en sökväg för navigering i dialogrutan **Mer information** försvinner optimeringsmöjligheten från listan. Om korrigerande åtgärder inte helt löser ett problem kommer affärsmöjligheten att skapas igen nästa gång som regeln utvärderas.

Om en affärsmöjlighet inte gäller för din roll kan du välja **Dölj från min lista**. Även om regeln bakom affärsmöjligheten utlöses igen senare visas inte affärsmöjligheten i listan.

Markera affärsmöjligheten som skapades av regeln om du vill inaktivera utvärdering av särskilda regler och välj sedan **Inaktivera analys**.

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa regler för rådgivning om optimering](./create-rules-optimization-advisor.md)

[Optimerings-advisor i Dynamics 365 for Finance and Operations (Video)](https://www.youtube.com/watch?v=MRsAzgFCUSQ)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]