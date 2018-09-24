---
title: Hantering av handelsavdrag
description: "Det här avsnittet beskriver hantering av handelsavdrag för Microsoft Dynamics 365 for Finance and Operations."
author: t-benebo
manager: AnnBe
ms.date: 08/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: t-benebo
ms.search.validFrom: 2018-01-31
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: c3794535cf9230389d7da3f9dbde010e5c48cf2f
ms.openlocfilehash: 907d59f850d8d761e2dd4e04bd288a696f00964d
ms.contentlocale: sv-se
ms.lasthandoff: 08/17/2018

---

# <a name="trade-allowance-management"></a>Hantering av handelsavdrag

[!include [banner](../includes/banner.md)]

Hantering av handelsavdrag hjälper företag att hantera säljfrämjande program som erbjuder monetära ersättningar i form av "prestationslön" till kunder som uppnår volym- och beteendemässiga mål. Funktionens kapacitet är utformad för företag som fokuserar på omfattande kampanj till vinst-processer från kampanjmedelsbudgetering och fördelning, till förmånsavtalsinställningar till anspråksskapande och bearbetning, till betalningsbearbetning, till analys av kampanjens effektivitet.


Den här artikeln ger en översikt över funktionen hantering av handelsavdrag och bekantar dig med vanliga uppgifter som används vid hantering av ett säljfrämjande program. Flera typer av användare som har ansvarsområden inom drift och beslutsfattning förväntas använda den här funktionen för att uppnå respektive mål:

- Fördela godtyckliga medel till valda konton och sätta upp avtal för handelsavdrag för erbjudanden baserade på återfakturering och enstaka engångsbelopp (för en överenskommen tjänst)
- Köra förhandlade kampanjavtal med löpande försäljning och generera återfaktureringskrav
- Beräkna, godkänna och behandla genererade anspråk och skicka dem till Kundreskontra som avdrag för betalningskvittning
- Stämma av kundens korta återbetalning med avdrag för det som har förfallit
- Spåra användningen av kampanjmedel och utvärdera programmets lönsamhet och effektivitet

## <a name="audience-and-purpose"></a>Publik och syfte

Informationen i detta dokument riktar sig till beslutsfattare inom företag som innehar positioner som exempelvis inköpschef, ekonomichef och redovisningschef, och som har ansvar för följande:

- Budget på hög nivå och fördelning av medel
- Planering och analys av försäljningserbjudanden
- Hantera personalen som bearbetar återfaktureringskrav, kör betalningar baserat på marknadsföringsevenemang och kvittar korta återbetalningar och avdrag

Personer i dessa roller söker metoder att uppnå dessa mål:

- Då används marknadsföringkampanjmedel.
- Hantera olika typer av kampanjprogram och förmåner.
- Minska den administrativa belastningen och antalet misstag kopplade till övervakning av kampanjresultat och behandling av ansökningar.
- Förbättra kassaflödesprognoserna genom periodisering för framtida skulder.
- Ha en kvantifierad grund för pågående och framtida kampanjförhandlingar med kunder.

## <a name="promotional-fund-and-trade-allowance-agreement"></a>Avtal för kampanjmedel och handelsavdrag

Ett avtal för handelsavdrag är ett bonusprogram där monetära belöningar i form av prestationslön ska erbjudas kunder som uppnår specifika volymmål och/eller beteendemässiga mål. Kampanjmedel är budgeterade utgifter. På så sätt kan marknadsföringskampanjer fångas.

### <a name="promotional-fund"></a>Kampanjmedel

Medel som är allokerade till avtal om handelsavdrag registreras på sidan **medel**. För att öppna sidan **Medel** väljer du **Försäljning och marknadsföring**\>**Handelsavdrag**\>**Medel**\>**Medel**.

![Sidan Medel](./media/trade-allowance-management-funds-page.png "Sidan Medel")

På sidan **Medel** kan du visa information om kampanjmedel.

Snabbfliken **allmänna** visar perioden som gäller för fonden och dess budgeterade belopp. För att medlen ska allokeras till kampanjavtalet måste fältet **Status** ha värdet **godkänd**.

Snabbfliken **kunder** visar kundhierarkin. För att välja de kunder som medlen avser, drar du dem så att de är under **Medel till kunder**. Den här snabbfliken visat även hur den totala mängden medel fördelas.

Snabbfliken **objekt** visar artiklarna som ingår i kampanjen.

### <a name="trade-allowance-agreement"></a>Handelsavdragsavtal

När fonddefinitionen är på plats, är nästa steg i kampanjplaneringen att registrera kampanjavtal (som kallas för handelsavdragsavtal), tilldela medel och definiera resultatmål för varje marknadsföringsevenemang.

Handelsavdragsavtal registreras på sidan **Handelsavdragsavtal**. För att öppna sidan **Handelsavdragsavtal**, välj **Försäljning och marknadsföring**\>**Handelsavdrag**\>**Handelsavdragsavtal**.

![Sidan Handelsavdragsavtal](./media/trade-allowance-management-agreements-page.png "Sidan Handelsavdragsavtal")

#### <a name="header"></a>Huvud

Välj **Rubrik** för att växla till rubrikvyn.

På snabbfliken **allmän** definierar fälten **Order till** och **Order från** perioden då avtalet gäller. Godkännandestatusen **internt godkänd** för avtalet innebär att avtalet ännu inte är giltigt och kan inte användas under bearbetning av försäljningsorder.

Avsnittet **Analys** på snabbfliken **allmänna** innehåller viktiga fält som definierar kvantiteter och kostnader som används för utvärdering av kampanjen:

- Fältet **Basenheter** anger kvantiteten av produkterna som måste säljas till valda kunder innan kampanjen tillämpas.
- Värdet **beräknad försändelsekvantiteten** beräknas baserat på värdet **lyftprocent**, vilket är en planerad målökning för denna kampanj.
- Fältet **Kostnad för handelsavdrag** beräknas utifrån mängden av de olika händelser i handelsavdragsavtalet.

På snabbfliken **kunder** i listan till vänster kan du markera och visa kundgrupperna som ställs in som fördefinierade hierarkier. Du kan sedan välja hela hierarkin eller specifika konton som mål för handelsavdragsavtalet.

På snabbfliken **artiklar** på snabbfliken **artiklar** på sidan **medel** läggs produkter till i avtalet för att koppla företagets försäljning till det avdrag som har kommit överens om.

På snabbfliken **medel**kan du visa de kampanjmedel som är associerade med kontraktet. Du kan också visa avtalets händelsekostnadsallokering. En händelsekostnadsallokering på 100 procent innebär att denna kampanj kommer att finansieras utifrån en fond. Alternativt kan ett händelseavtal ställas ut på flera medel och kan använda lika eller olika procentuell allokering.

#### <a name="lines"></a>Rader

Markera sedan **rader** för att växla till vyn Rader.

Fliken **Marknadsföringshändelser** visar vilka typer av händelser som omfattas av ett avtal. Det finns tre typer: återfakturering, klumpsumma och fakturaavdrag.

När du markerar marknadsföringshändelsen och sedan väljer fliken **belopp** hittas information om händelsen.

![Rader för handelsavdragsavtal](./media/trade-allowance-management-agreements-lines.png "Rader för handelsavdragsavtal")

I avsnittet **Handelsavdragsrader** anger du kvantitet eller beloppsintervall som kunden måste uppnå för definitioner för att erhålla belöningarna.

När det gäller en marknadsföringshändelse av typen **Återfakturering** definierar de övre sektionen av fliken **belopp** regeln som återfakturering tillämpas, genereras och betalas i enlighet med. Exempelvis anger reglerna följande villkor för återfaktureringskravet:

- Det baseras på när försäljningsordern skapades (värdet **Beräkningsdatumtyp** är **Skapad**).
- Den beräknas utifrån försäljningsorderradens belopp före rabatter, inte nettobeloppet, som inkluderar rabatter (värdet **Tagen från** är **Brutto**).
- Den baseras på mängden sålda produkter, inte beloppet (värdet **Radbrytningstyp för rabatt** är **kvantitet**).
- Den beräknas per period om en månad (värdet **ackumulera försäljning per** är **månad**). 
- Kvittas som ett avdrag inte genom att använda A/P (värdet **betalningstyp** är **Kundavdrag**).

När det gäller en marknadsföringshändelse för typen **klumpsumma** visar fliken **belopp** vilken kvantitet som ska betalas till kund i form av ett avdrag som kunden får en särskild prestanda. Godkännandestatusen **öppna** anger att klumpsumman ännu inte har betalats.

Om du vill tillämpa avtalet till försäljningsorder som uppfyller villkoren i avtalet måste avtalets status vara **bekräftat**. 

## <a name="perform-sales-under-the-planned-merchandising-event-and-generate-bill-back-claims"></a>Utför försäljning under den planerade försäljningshändelsen och generera återfaktureringskrav

När du skapar en försäljningsorder med rader som uppfyller bestämmelserna i avtalet kan du visa relaterad information på sidan **försäljningsorder** genom att välja **försäljningsorderrad**\>**visa**\>**Prisinformation**.

På sidan **prisinformation**på snabbfliken **rabatter** kan försäljningsansvarig se en strukturlista från giltigt handelsavdragsavtal (rabattprogram-ID visas) och det totala beloppet som gäller för raden. Detta belopp visas även i fältet **Rabattbelopp** i avsnittet **Marginalberäkning** på sidan **Prisinformation**.

När försäljningsfakturan bokförs skapas motsvarande återfaktureringskrav för varje fakturarad.

> [!NOTE]
> För att visa sidan **prisinformation** på sidan **parametrar för kundreskontra** på fliken **priser**, markera kryssrutan **aktivera prisinformation**. I

## <a name="process-claims-and-pass-them-as-deductions-to-ar"></a>Bearbeta anspråk och skicka dem som avdrag till kundreskontra

Nästa steg i processen för hantering av återfakturering är att granska, beräkna, godkänna anspråk och konvertera dem till avdrag.

Återfakturerings-workbench är där ägaren av kampanjavtalet regelbundet granskar och bearbetar de anspråk som genereras. Det är också där administratören för kundreskontra omvandlar godkända anspråk till avdrag eller regelbundna utbetalningar beroende på betalningsmetoden för anspråket.

På sidan **Återfakturerings-workbench** kan du granska anspråksraderna. Om anspråket är i status **Att omberäknas** måste de räknas om för en ackumulerande effekt.

### <a name="recalculate-claims"></a>Beräkna om anspråk

Markera om du vill omberäkna anspråk, i åtgärdsfönstret, **Ackumulera**. I dialogrutan **ackumulera rabatter** markerar du sedan kunden.

Till följd av omräkning skapar programmet nya anspråk för beloppen för att justera det ursprungliga anspråket till kvalificerade belopp per enhet. En anspråksjustering genereras för varje unik kombination av en kund, en artikel, en valuta, en måttenhet, lagerdimensioner, ekonomiska dimensioner och en momsgrupp. De här anspråksjusteringarna har samma referens till försäljningsordern och fakturanumret som de anspråk som har justerats (det vill säga de anspråk som ursprungligen har skapats från dokumentet). Till skillnad från det ursprungliga anspråket har inte justeringsanspråk värden i fälten som beskriver den ursprungliga försäljningsorderradens belopp och kvantitet.

Efter att omberäkningen är klar ändras status för anspråket till **beräknat**. För att godkänna anspråken väljer du **Ackumulera** i åtgärdspanelen.

### <a name="process-claims-and-pass-them-to-ar"></a>Bearbeta anspråk och skicka till kundreskontra

Anspråken är nu redo att bearbetas av kundreskontra. Välj **Bearbeta** för att bearbeta dem i åtgärdsfönstret. 

Vid bearbetning av anspråk har status ändrats till **Markera** och anger att en journalbokföring (journalen som bokförts är periodiseringsjournalen för rabatt enligt parametrarna för kundreskontra) orsakade följande händelser: 

- Anspråk har överförts till tillfälliga kundsaldot som avdrag.
- Rabattperiodiseringskontot har krediterats för att representera framtida ansvar för kunden.
- Utgiftskontot för rabatt debiterades för att känna igen den kostnad som uppstod i samband med försäljning.

För att slutföra processen måste kundreskontraansvarig hantera periodiseringsavdrag genom att föra över dem till kundsaldot som en kreditfaktura (skuld). 

För att starta uppgiften, på åtgärdsfönstret på sidan **kund** anger du **samla in**\>**kvitta transaktioner**. Sedan på sidan **kvitta transaktioner** väljer du **funktioner**\>**återfaktureringsprogram**. Denna rabattsida visar alla återfaktureringskrav som har bearbetats tidigare.

Om du vill skapa en kreditfaktura markerar du kryssrutan **Markera** för alla rader och väljer sedan **funktioner**\>**Skapa kreditfaktura**.

Vid skapande av en kreditfaktura bokförs en journal. (Journalen som bokförs är KR-förbrukningsjournalen enligt kundreskontraparametrarna.) Som ett resultat har real skuldbelopp (kredit) flyttats till kundens saldo. Ekonomiskt innebär detta att följande händelser har inträffat:

- Kundens kundfordringar har krediterats.
- Rabattperiodiseringskontot har debiterats.

För att godkänna en marknadsföringshändelse av typen **klumpsumma** väljer du händelsen på sidan **Handelsavdragsavtal** på fliken **belopp** och väljer **Godkänn**.

## <a name="settle-the-deduction-that-is-due-and-the-customer-short-pay-by-using-the-deduction-workbench"></a>Kvitta avdraget som förfaller och kundens korta återbetalning med avdrags-workbench

Ofta, i avvaktan på återfakturering, väljer kunder valda fakturor med kort återbetalning. För att undvika problem med avstämning i framtiden registrerar kundreskontraansvarig de korta återbetalningar som avdrag när han eller hon registrerar de faktiska kundbetalningarna. På avdrags-workbench, kan sedan dessa kundavdrag enkelt kvittas mot kravbeloppen som företaget är skyldig.

Om du vill registrera kundens korta återbetalningar i betalningsjournalen väljer du **kundreskontra**\>**betalningar**\>**betalningsjournal** och skapar en ny betalningsjournal. I åtgärdsfönstret markerar du sedan **avdrag**. På sidan **avdrag** kan du skapa och följa upp det belopp som har återbetalades kort.

En insamlingsansvarig är nu ansvarig för kvittning av öppna kreditfakturatransaktioner och korta återbetalningstransaktionen mot varandra i avdrags-workbench.

Om du vill hantera avdrag, välj **Försäljning och marknadsföring**\>**Handelsavdrag**\>**Avdrag**\>**Avdrags-workbench**. Den övre delen av sidan innehåller rader som representerar korta återbetalningar från kunden. Den nedre delen av sidan innehåller kundernas öppna kredittransaktioner. 

Om du vill kvitta avdraget mot den öppna transaktionen, markerar du avdragsraden och markerar raden på fliken Öppna transaktioner. På åtgärdsfönstret klickar du på Underhåll > Matcha.

Status för de ursprungliga anspråken är nu inställd på **slutförd**.

## <a name="analyze-the-effectiveness-of-the-promotion-and-fund-consumption"></a>Analysera effektiviteten hos kampanjen och fondförbrukning

Om du vill få en översikt över programmets viktig statistik och användning av fonden, kan du använda flera rapporter och analytiska vyer som är tillgängliga i Hantering av handelsavdrag.

På sidan **Aktivitet för handelsavdrag** visar fliken **översikt** de huvudsakliga detaljerna i handelsavdragsavtalet. De övriga flikarna visar mer detaljerad information om de associerade dokumenten, betalningarna och andra händelser som hör till programmet.

Fliken **sammanfattning** visar det totala antalet produkter som har sålts under kampanjen, det försäljningsbelopp som har fakturerats och återfakturering och klumpsummor som har betalats.

Fliken **Återfaktureringskredit** innehåller detaljerad information om återfakturering som kunden har krediterats.

Om du vill få en mer analytisk översikt av de olika resultatmåtten för kampanjen kan du använda analysvyn. Gå till analysvyn genom att klicka på **Försäljning och marknadsföring**\>**Handelsavdrag**\>**Handelsavdragsavtal**. Klicka på **Analys** på åtgärdsfönstret.  

Om du vill få en mer analytisk översikt av de olika resultatmåtten för kampanjen kan du använda analysvyn. Gå till analysvyn genom att klicka på **Försäljning och marknadsföring**\>**Handelsavdrag**\>**Handelsavdragsavtal**. Klicka på **Analys** på åtgärdsfönstret. 


