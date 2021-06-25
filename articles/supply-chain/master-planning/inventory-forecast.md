---
title: Lagerprognoser
description: I det här avsnittet beskrivs funktionerna för leverans- och efterfrågeprognoser som kan användas för att skapa lagerprognoser i Microsoft Dynamics 365 Supply Chain Management.
author: crytt
ms.date: 06/08/2021
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ForecastSales, ForecastPurch, ForecastInvent
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a7ed310ebdef130b0fb09c5db19397398dc5042
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216852"
---
# <a name="inventory-forecasts"></a>Lagerprognoser

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du visar och skapar lagerprognoser. Du kan skapa och visa rader för leverans- och efterfrågeprognoser för artiklar, artikelgrupper, artikelallokeringsnycklar, kundkonton, kundgrupper, leverantörskonton och leverantörsgrupper.

För varje prognosrad kan du välja den prognosmodell som används. Du kan sedan ange artikeln eller artikelgruppen samt kvantiteten eller transaktionsbeloppet. Du kan också konfigurera en tidsplan för att använda prognoskvantiteten.

Raderna för leverans- och efterfrågeprognoser skapar en lagerprognos för samma kombination av en artikel och en modell. Denna lagerprognos representerar ett saldo mellan tillgång och efterfrågan som angetts för samma artikel. Den kan inte ändras. Lagerprognosen gör det lättare för lagerhanteringsteamet att granska förväntade ändringar av lagerbehållningen för en artikel under den kommande period som har prognosticerats.

När du har angett dina tillgångar och/eller efterfrågan kan du göra en prognosplanering för att beräkna bruttobehov för material och kapacitet, samt för att generera planerade order.

## <a name="view-and-manually-enter-forecast-lines"></a><a name="manual-entry"></a>Visa och ange prognosrader manuellt

Använd den här proceduren för att skapa nya prognosrader för produkter manuellt.

Det finns också andra sätt att skapa prognosrader:

- [Generera en statistisk baslinjeprognos](generate-statistical-baseline-forecast.md).
- [Importera historiska data för efterfrågeprognoser](import-historical-data.md).
- [Generera prognosen genom att skapa en Machine Learning-webbtjänst för Microsoft Azure](demand-forecasting-setup.md).
- [Importera rader för efterfråge- och inflödesprognoser med hjälp av datahanteringsramverket (dataentiteterna ForecastDemandForecastEntryStaging och ForecastSupplyForecastEntryStaging)](../../dev-itpro/data-entities/data-entities-data-packages.md).

I enlighet med tabellen i steg 1 visas finns olika sätt att komma åt sidorna som används.

1. Beroende på vilken typ av enhet som du vill skapa en prognos för och den typ av prognos som du vill skapa, öppnar du en tillgång, efterfrågan eller lagerprognossida på det sätt som beskrivs i följande tabell.

    | Enhet | Instruktioner |
    |---|---|
    | Frisläppta produkter | <ol><li>Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.</li><li>Välj den produkt som du vill skapa en prognos för.</li><li>I åtgärdsfönstret, på fliken **Plan** väljer du i gruppen **Prognos** bland **Efterfrågeprognos**, **Inflödesprognos** och **Lagerprognos** beroende på den typ av prognos som du vill arbeta med.</li></ol> |
    | Frisläppta produktvarianter | <ol><li>Gå till **Produktinformationshantering \> Produkter \> Frisläppta produktvarianter**.</li><li>Välj den variant som du vill skapa en prognos för.</li><li>I åtgärdsfönstret, på fliken **Plan** väljer du i gruppen **Prognos** bland **Efterfrågeprognos**, **Inflödesprognos** och **Lagerprognos** beroende på den typ av prognos som du vill arbeta med.</li></ol> |
    | Artikelgrupper | <ol><li>Gå till **Lagerhantering \> Inställningar \> Lager \> Artikelgrupper**.</li><li>Välj den artikelgrupp som du vill skapa en prognos för.</li><li>I åtgärdsfönstret väljer du **Prognosticering \> Efterfrågan**, **Prognosticering \> Tillgång** eller **Prognosticerring \> Lagerprognos**, beroende på den typ av prognos som du vill arbeta med.</li></ol> |
    | Artikelallokeringsnycklar | <ol><li>Gå till **Lagerhantering \> Inställningar \> Prognos**.</li><li>Välj den allokeringsnyckel för artikel som du vill skapa en prognos för.</li><li>I åtgärdsfönstret väljer du **Efterfrågeprognos**.</li></ol> |
    | Kunder | <ol><li>Gå till **Huvudplanering \> Prognosticering \> Manuell prognosangivelse \> Kunder**.</li><li>Välj den kund som du vill skapa en prognos för.</li><li>I åtgärdsfönstret väljer du **Definiera efterfrågeprognos**.</li></ol> |
    | Kundgrupper | <ol><li>Gå till **Huvudplanering \> Prognosticering \> Manuell prognosangivelse \> Kundgrupper**.</li><li>Välj den kundgrupp som du vill skapa en prognos för.</li><li>I åtgärdsfönstret väljer du **Definiera efterfrågeprognos**.</li></ol> |
    | Leverantörer | <ol><li>Gå till **Huvudplanering \> Prognosticering \> Manuell prognosangivelse \> Leverantörer**.</li><li>Välj den leverantör som du vill skapa en prognos för.</li><li>I åtgärdssfönstret väljer du **Post** för att öppna sidan **Inflödesprognos**.</li></ol> |
    | Leverantörsgrupper | <ol><li>Gå till **Huvudplanering \> Prognosticering \> Manuell prognosangivelse \> Leverantörsgrupper**.</li><li>Välj den leverantörsgrupp som du vill skapa en prognos för.</li><li>I åtgärdssfönstret väljer du **Post** för att öppna sidan **Inflödesprognos**.</li></ol> | 
    | Alla rader | <ul><li>Gå till **Huvudplanering \> Prognosticering \> Rader för efterfrågeprognosticering** eller **Huvudplanering \> Prognosticering \> Rader för inflödesprognos** beroende på den prognostyp som du vill arbeta med.</li></ul> |

    Beroende på vad du väljer visas sidan **Inflödesprognos** eller sidan **Efterfrågeprognos**. Här visas alla befintliga prognosrader för posten som du valde innan du öppnade sidan.

1. I åtgärdsfönstret väljer du **Ny** för att lägga till en prognosrad i rutnätet på sidans övre del.
1. På den nya raden, i fältet **Modell**, väljer du den prognosmodell som ska användas. Ange sedan annan information som krävs, exempelvis artikel, artikelgrupp, kund- eller leverantörskonto eller -grupp, artikelkvantitet eller totalt transaktionsbelopp. Fullständig information om fälten som är tillgängliga på sidorna **Inflödesprognos** och **Efterfrågeprognos** finns i de senare avsnitten i detta ämne.
1. Om du vill fördela prognosen över perioden väljer du fliken **Översikt** och sedan **Allokera prognos** i verktygsfältet.
1. I rutnätet **Allokering** granskar du tidshorisonten och de tidsintervall som används för att distribuera prognoskvantiteterna.

## <a name="supply-forecast-lines"></a>Leveransprognosrader

Med inflödesprognosen kan du skapa en plan för artiklar som måste köpas in. Den informerar anskaffnings- och inköpspersonal om vad de förväntas beställa.

Du kan ange en inflödesprognos per artikel, artikelgrupp, artikelallokeringsnyckel, leverantör och leverantörsgrupp. Information om alla sätt att öppna sidan **Inflödesprognos** för olika entiteter och poster finns i avsnittet [Visa och ange prognosrader manuellt](#manual-entry) tidigare i detta ämne.

Den övre delen av sidan **Inflödesprognos** innehåller ett rutnät med rader för inflödesprognos samt en uppsättning flikar som du kan använda för att visa och ange mer information om en vald prognosrad. Den nedre delen av sidan innehåller ett rutnät för **allokering**.

I följande delavsnitt beskrivs alla fält som är tillgängliga på respektive flik samt alla kommandon som är tillgängliga i sidans åtgärdsfönster och i verktygsfältet på fliken **Översikt**.

### <a name="action-pane-commands-on-the-supply-forecast-page"></a>Kommandon i åtgärdsfönstret på sidan Inflödesprognos

I följande tabell beskrivs de kommandon som är tillgängliga i åtgärdsfönstret på sidan **Inflödesprognos**.

| Kommando | beskrivning |
|---|---|
| Spara | Spara de aktuella inställningarna. |
| Redigera | Aktivera de inställningar på sidan som ska redigeras. |
| Nytt | Lägg till en prognosrad i det övre rutnätet. |
| Delete | Ta bort den valda prognosraden från det övre rutnätet. |
| Prognossaldon | Visa prognossaldon som har beräknats för den valda radens modell-ID för aktuellt räkenskapsår. Saldona delas in per period (månad). |
| Kassaflödesprognoser | Visa prognostransaktioner som har allokerats till redovisningen. Mer information finns i [Kassaflödesprognoser](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Lager \> Visa dimensioner | Välj de lagerdimensioner som ska visas i rutnätet på fliken **Översikt**. |

### <a name="toolbar-commands-on-the-overview-tab-of-the-supply-forecast-page"></a>Verktygsfältskommandon på fliken Översikt på sidan inflödesprognos

I följande tabell beskrivs de kommandon som är tillgängliga i verktygsfältet på fliken **Översikt** på sidan **Inflödesprognos**.

| Kommando | beskrivning |
|---|---|
| Allokera prognos | Om du använder en allokeringsmetod genererar du de enskilda tidsplaneringsraderna för prognostransaktionen. Radens kvantitet fördelas därefter per datum (enligt valda tidsintervall), kvantitet och belopp för hela tidshorisonten. |
| Massuppdatering | Öppna sidan **Redigera prognostransaktioner**. (Se avsnittet [Massuppdatering av prognostransaktioner](#bulk-update) längre fram i detta avsnitt.) |
| Lagerprognos | Öppna en vy på sidan **Lagerprognos** som har filtrerats för den valda artikel-/modellkombinationen. (Se avsnittet [Lagerprognos](#inventory-forecast) längre fram i detta avsnitt.) |
| Skapa artikelbehov | Öppna en dialogruta där du kan skapa artikelbehov och försäljningsorder- eller artikeljournalrader för projektrelaterade prognostransaktioner. Även om det här kommandot är tillgängligt för både rader för inflödesprognoser och rader för efterfrågeprognoser, kan det inte användas på sidan **Inflödesprognos**. |

### <a name="the-overview-tab-on-the-supply-forecast-page"></a>Fliken Översikt på sidan Inflödesprognos

I följande tabell beskrivs fälten på fliken **Översikt** på sidan **Inflödesprognos**.

| Fält | beskrivning |
|---|---|
| **Modell** | Den prognosmodell som transaktionen är kopplad till. |
| **Datum** | Startdatumet för transaktionen. |
| **Leverantörskonto** | Det leverantörskonto som har kopplats till transaktionen. |
| **Leverantörsgrupp** | Den leverantörsgrupp som har kopplats till transaktionen. |
| **Artikelnummer** | Identifieraren för artikeln. |
| **Artikelgrupp** | Den artikelgrupp som transaktionen är kopplad till. |
| **Artikelallokeringsnyckel** | Den artikelallokeringsnyckel som är kopplad till prognosen. |
| **FV-kvantitet** | Prognoskvantiteten i den angivna nominella viktenheten. |
| **FV-enhet** | Den nominella viktenhet som artikeln köps in i. Värdet hämtas automatiskt från artikelinställningarna. |
| **Antal** | Prognoskvantiteten i den angivna inköpsenheten. |
| **Enhet** | Den enhet som artikelns köps in i . Värdet hämtas automatiskt från artikelinställningarna. Du kan emelelrtid ändra den om enhetsomvandlingar har ställts in. |
| **Belopp** | Det bruttobelopp – minus rabatter – som prognostransaktionen bidrar med till prognosen. |
| **Valuta** | Den valutakod som används för prognostransaktionen. Standardvalutan anges automatiskt, men du kan också välja en annan valuta. |
| (Övriga dimensioner) | Ytterligare dimensioner kan visas som kolumner i rutnätet. Välj **Visa dimensioner** i åtgärdsfönstret om du vill välja de ytterligare dimensioner som visas. |

### <a name="the-general-tab-on-the-supply-forecast-page"></a>Fliken Allmänt på sidan Inflödesprognos

På fliken **Allmänt** visas mer information om raden som för närvarande är markerad på fliken **Översikt**. En del av informationen upprepas från fliken **Översikt**. I tabellen nedan beskrivs de fält som är unika för fliken **Allmänt**.

| Fält | beskrivning |
|---|---|
| Rapport | Ange detta alternativ som *Ja* om du vill inkludera transaktionen i rapporten. |
| Kommentarer | Ange exentuella kommentarer som du har gällande prognostransaktionen. |
| Aktiva | Markera denna kryssruta för att inkludera transaktionen i budgetrapporten. |
| Inkludera i kassaflödesprognoser | Välj denna kryssruta om du vill allokera prognostransaktionen till redovisningen. Inställningen för den här kryssrutan kan inte ändras för rapportering av transaktioner. |
| Momsgrupp | Den momsgrupp som används för att ange momsen för prognostransaktionen. |
| Artikelmomsgrupp | Den artikelmomsgrupp som används för att ange momsen för prognostransaktionen. |
| Metod | <p>Välj den metod som används för att allokera prognostransaktionen:</p><ul><li>**Ingen** – Ingen allokering sker.</li><li>**Period** – Prognosticera samma kvantitet för respektive period. Om du väljer det här värdet anger du en kvantitet i fältet **Per** samt en tidsenhet i fältet **Enhet**.</li><li>**Nyckel** – Allokera prognosen i enlighet med den periodallokeringsnyckel som du anger i fältet **Periodnyckel**. Den här metoden kan användas när hänsyn ska tas till säsongsvariationer.</li></ol>|
| Per | <p>Ange antalet framtida tidsintervaller som prognosen sträcker sig över. Detta fältet blir bara tillgängligt när du väljer *Period* i fältet **Metod**.</p><p>Du väljer exempelvis *Period* i fältet **Metod**, anger *1* i fältet **Per** och väljer *Månader* i fältet **Enhet**. I fältet **Slut** anger du ett slutdatum som sträcker sig ett år in i framtiden. I detta fall skapas en prognosrad för respektive månad under det kommande året, baserat på den artikel och kvantitet som anges i rubrikraden.</p> |
| Enhet | Välj enhet för tidsintervallet: *dagar*, *månader* eller *år*. Allokeringen motsvarar därefter antalet dagar, månader eller år som du anger i fältet **Per**.|
| Periodnyckel | Ange periodallokeringsnyckeln. |
| End | Ange slutdatumet när du använder fälten **Per** och **Enhet**. |

### <a name="the-item-tab-on-the-supply-forecast-page"></a>Fliken Artikel på sidan Inflödesprognos

Fliken **Artikel** visar mer artikelinformation om den rad som för tillfället valts på fliken **Översikt**.

Rutnätet högst upp på fliken **Artikel** upprepar artikelinformation som också visas på fliken **Översikt**. Dessutom innehåller det fältet **Enhetspris** som anger inköpspriset för det antal enheter som har angetts i fältet **Enhet**. Enhetspriset hämtas automatiskt från artikelinställningen, men du kan ändra det.

Fälten under rutnätet innehåller fler artikeldetaljer. En del av informationen upprepas från fliken **Översikt**. I tabellen nedan beskrivs de fält som är unika för fliken **Artikel**.

| Fält | beskrivning |
|---|---|
| Prisenhet | Det antal enheter som inköpspriset gäller för. Värdet hämtas automatiskt från artikelregistret, men du kan ändra det. |
| Avgifter på inköp | Fasta avgifter på inköpspriset. Avgifterna är oberoende av kvantiteten. |
| Rabattprocent | Rabatten i procent. |
| Rabattbelopp | Rabatten som ett belopp per försäljningsenhet. |
| Bruttobelopp | Beloppet när inga rabatter används. |
| Antal | Transaktionskvantiteten i artikelns lagerenhet. |
| Understrukturlista | Strukturlistenumret för en viss understrukturlista. |
| Delrutt | Flödesnumret för ett visst delflöde. |

### <a name="the-financial-dimensions-tab-on-the-supply-forecast-page"></a>Fliken Ekonomisk dimension på sidan Inflödesprognos

Fliken **Ekonomiska dimensioner** visar all ekonomiska dimensionsvärden för raden som är markerad på fliken **Översikt**.

### <a name="the-inventory-dimensions-tab-on-the-supply-forecast-page"></a>Fliken Lagerdimensioner på sidan Inflödesprognos

Fliken **lagerdimensioner** visar alla lagerdimensionsvärden för raden som för tillfället är markerad på fliken **Översikt**.

### <a name="the-allocation-grid-on-the-supply-forecast-page"></a>Allokeringsrutnätet på sidan Inflödesprognos

Om du använder en artikelallokeringsnyckel eller om du har angett en artikelprognos för en eller flera framtida perioder, kan du allokera prognosen genom att välja **Allokera prognos** i verktygsfältet på fliken **Översikt**. Kvantiteten fördelas sedan på det sätt som indikeras av raderna i rutnätet **Allokering**.

## <a name="demand-forecast-lines"></a>Rader i efterfrågeprognos

Med hjälp av efterfrågeprognosen kan du ange eller generera efterfrågan för en kund. Detta hjälper försäljnings- och marknadsföringspersonal att informera huvudplaneringskontoren om den förväntade efterfrågan under den kommande prognosperioden.

Du kan ange en efterfrågeprognos per artikel, artikelgrupp, artikelallokeringsnyckel, kund samt kundgrupp. Information om alla sätt att öppna sidan **Efterfrågeprognos** för olika entiteter och poster finns i avsnittet [Visa och ange prognosrader manuellt](#manual-entry) tidigare i detta ämne.

Den övre delen av sidan **Efterfråge prognos** innehåller ett rutnät med rader för efterfrågeprognos samt en uppsättning flikar som du kan använda för att visa och ange mer information om en vald prognosrad. Den nedre delen av sidan innehåller ett rutnät för **allokering**.

I följande delavsnitt beskrivs alla fält som är tillgängliga på respektive flik samt alla kommandon som är tillgängliga i sidans åtgärdsfönster och i verktygsfältet på fliken **Översikt**.

### <a name="action-pane-commands-on-the-demand-forecast-page"></a>Kommandon i åtgärdsfönstret på sidan Efterfrågeprognos

I följande tabell beskrivs de kommandon som är tillgängliga i åtgärdsfönstret på sidan **Efterfrågeprognos**.

| Kommando | beskrivning |
|---|---|
| Spara | Spara de aktuella inställningarna. |
| Redigera | Aktivera de inställningar på sidan som ska redigeras. |
| Nytt | Lägg till en prognosrad i det övre rutnätet. |
| Delete | Ta bort den valda prognosraden från det övre rutnätet. |
| Prognossaldon | Visa prognossaldon som har beräknats för den valda radens modell-ID för aktuellt räkenskapsår. Saldona delas in per period (månad). |
| Kassaflödesprognos | Visa prognostransaktioner som måste allokeras till redovisningen. Mer information finns i [Kassaflödesprognoser](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Visa dimensioner | Välj de produkt-, lager och spårningsdimensioner som ska visas i rutnätet på fliken **Översikt**. |
| Förhandsgranskning av huvudbok | Visa redovisningsposterna för den valda transaktionen. |
| Överför offertrader | Överför offertrader till det valda projektet. |

### <a name="toolbar-commands-on-the-overview-tab-of-the-demand-forecast-page"></a>Verktygsfältskommandon på fliken Översikt på sidan Efterfrågeprognos

I följande tabell beskrivs de kommandon som är tillgängliga i verktygsfältet på fliken **Översikt** på sidan **Efterfrågeprognos**.

| Kommando | beskrivning |
|---|---|
| Allokera prognos | Om du använder en allokeringsmetod genererar du de enskilda tidsplaneringsraderna för prognostransaktionen. Radens kvantitet fördelas därefter per datum (enligt valda tidsintervall), kvantitet och belopp för hela tidshorisonten. |
| Massuppdatering | Öppna sidan **Redigera prognostransaktioner**. (Se avsnittet [Massuppdatering av prognostransaktioner](#bulk-update) längre fram i detta avsnitt.) |
| Lagerprognos | Öppna en vy på sidan **Lagerprognos** som har filtrerats för den valda artikel-/modellkombinationen. (Se avsnittet [Lagerprognos](#inventory-forecast) längre fram i detta avsnitt.) |
| Skapa artikelbehov | Öppna en dialogruta där du kan skapa artikelbehov och försäljningsorder- eller artikeljournalrader för projektrelaterade prognostransaktioner. |

### <a name="the-overview-tab-on-the-demand-forecast-page"></a>Fliken Översikt på sidan Efterfrågeprognos

I följande tabell beskrivs fälten på fliken **Översikt** på sidan **Efterfrågeprognos**.

| Fält | beskrivning |
|---|---|
| **Uppgiftsnamn** | Namnet på den batch-uppgift som användes för att skapa prognosraden. |
| **Modell** | Den prognosmodell som transaktionen är kopplad till. |
| **Datum** | Startdatumet för transaktionen. |
| **Kund-ID** | Det kundkonto som transaktionen är associerad med. |
| **Kundgrupp** | Det kundkonto som transaktionen är associerad med. |
| **Artikelnummer** | Identifieraren för artikeln. |
| **Produktnamn** | Beskrivningen av artikeln. |
| **Artikelallokeringsnyckel** | Artikelallokeringsnyckel som används vid lagerprognosallokering. |
| **Försäljningskvantitet** | Transaktionskvantiteten i den angivna försäljningsenheten. |
| **Enhet** | Enhet i vilken artikeln säljs. |
| **Belopp** | Det bruttobelopp – exklusive rabatter – som prognostransaktionen bidrar med till prognosen. |
| **Försäljningspris** | Försäljningspriset för det antal enheter som har angetts i fältet **Prisenhet**. Värdet hämtas från artikelinställningen, men du kan ändra det. |
| **Försäljningsvaluta** | Den valutakod som används för prognostransaktionen. Standardvalutan anges automatiskt, men du kan också välja en annan valuta. |
| **FV-kvantitet** | Prognoskvantiteten i den angivna nominella viktenheten. |
| **FV-enhet** | Den nominella viktenhet som artikeln säljs i. Värdet hämtas automatiskt från artikelinställningarna. |
| (Övriga dimensioner) | Ytterligare produkt, lagrings- och spårningsdimensioner kan visas som kolumner i rutnätet. Välj **Visa dimensioner** i åtgärdsfönstret om du vill välja de ytterligare dimensioner som visas. |

### <a name="the-general-tab-on-the-demand-forecast-page"></a>Fliken Allmänt på sidan Efterfrågeprognos

På fliken **Allmänt** visas mer information om raden som för närvarande är markerad på fliken **Översikt**. En del av informationen upprepas från fliken **Översikt**. I tabellen nedan beskrivs de fält som är unika för fliken **Allmänt**.

| Fält | beskrivning |
|---|---|
| Löpnummer för efterfrågeprognos | Det unika numret på efterfrågeprognosraden. Numret genereras med hjälp av den nummerserie som väljs för efterfrågeprognoser på sidan för **Huvudplaneringsparametrar**. |
| Artikelgrupp | Den artikelgrupp som transaktionen är kopplad till. |
| Rapport | Ange detta alternativ som *Ja* om du vill inkludera transaktionen i rapporten. |
| Kommentarer | Ange exentuella kommentarer som du har gällande prognostransaktionen. |
| Aktiva | Markera denna kryssruta för att inkludera transaktionen i budgetrapporten. Inställningen för den här kryssrutan kan inte ändras för rapportering av transaktioner. |
| Inkludera i kassaflödesprognoser | Välj denna kryssruta om du vill allokera prognostransaktionen till redovisningen. Inställningen för den här kryssrutan kan inte ändras för rapportering av transaktioner. Mer information finns i [Kassaflödesprognoser](../../finance/cash-bank-management/cash-flow-forecasting.md). |
| Momsgrupp | Den momsgrupp som används för att ange momsen för prognostransaktionen. |
| Artikelmomsgrupp | Den artikelmomsgrupp som används för att ange momsen för prognostransaktionen. |
| Metod | <p>Välj den metod som används för att allokera prognostransaktionen:</p><ul><li>**Ingen** – Ingen allokering sker.</li><li>**Period** – Prognosticera samma kvantitet för respektive period. Om du väljer det här värdet anger du en kvantitet i fältet **Per** samt en tidsenhet i fältet **Enhet**.</li><li>**Nyckel** – Allokera prognosen i enlighet med den periodallokeringsnyckel som du anger i fältet **Periodnyckel**. Den här metoden kan användas när hänsyn ska tas till säsongsvariationer.</li><ul>|
| Per | <p>Ange antalet framtida tidsintervaller som prognosen sträcker sig över. Detta fältet blir bara tillgängligt när du väljer *Period* i fältet **Metod**.</p><p>Du väljer exempelvis *Period* i fältet **Metod**, anger *1* i fältet **Per** och väljer *Månader* i fältet **Enhet**. I fältet **Slut** anger du ett slutdatum som sträcker sig ett år in i framtiden. I detta fall skapas en prognosrad för respektive månad under det kommande året, baserat på den artikel och kvantitet som anges i rubrikraden. |
| Enhet | Välj enhet för tidsintervallet: *dagar*, *månader* eller *år*. Allokeringen motsvarar därefter antalet dagar, månader eller år som du anger i fältet **Per**.|
| Periodnyckel | Ange den periodallokeringsnyckel som används för att allokera prognosen. Mer information finns i [Datallokering för budgetplanering](../../finance/budgeting/budget-planning-data-allocation.md). |
| End | Ange slutdatumet när du använder fälten **Per** och **Enhet**. |

### <a name="the-item-tab-on-the-demand-forecast-page"></a>Fliken Artikel på sidan Efterfrågeprognos

På fliken **Artikel** visas mer artikelinformation om raden som för närvarande är markerad på fliken **Översikt**. En del av informationen upprepas från fliken **Översikt**. I tabellen nedan beskrivs de fält som är unika för fliken **Artikel**.

| Fält | beskrivning |
|---|---|
| Prisenhet | Antalet försäljningsenheter som försäljningspriset gäller för. Värdet hämtas automatiskt från artikelregistret, men du kan ändra det. |
| Försäljningsavgifter | Fasta avgifter på försäljningspriset. Avgifterna är oberoende av kvantiteten. |
| Självkostnad | Kostnaden för den aktuella prognostransaktionen per lagerenhet. Värdet hämtas automatiskt från artikelregistret, men du kan ändra det. |
| Rabattprocent | Rabatten i procent. |
| Rabattbelopp | Rabatten som ett belopp per försäljningsenhet. |
| Bruttobelopp | Beloppet när inga rabatter används. |
| Lagerkvantitet | Transaktionskvantiteten i artikelns lagerenhet. |
| Använd specifik strukturlista | Strukturlistenumret för en viss understrukturlista. |
| Använd specifikt flöde | Flödesnumret för ett visst delflöde. |

### <a name="the-project-tab-on-the-demand-forecast-page"></a>Fliken Projekt på sidan Efterfrågeprognos

På fliken **Projekt** visas mer projektinformation om den rad som för tillfället är vald i fliken **Översikt**. En del av denna information upprepas från flikarna **Översikt**, **Allmänt** eller **Artikel**. Följande tabell beskriver de fält som är unika för fliken **Projekt**.

| Fält | beskrivning |
|---|---|
| Projektdatum | Transaktionsdatumet för efterfrågeprognosen. |
| Projekt-ID | ID för det projekt som den aktuella transaktionen refererar till. |
| Finansieringskälla | Den finansieringskälla som har associerats med efterfrågeprognosen. |
| Aktivitetsnummer | Den aktivitet som har associerats med efterfrågeprognostransaktionen. |
| Kategori | Kostnadskategorin för den aktuella transaktionen. |
| Radegenskap | Den status som transaktionen är kopplad till. |
| Transaktions-ID | System-ID för efterfrågeprognostransaktionen. |
| Kostnadsbelopp | Beloppet för efterfrågeprognosen. |
| Enhetspris | Priset per enhet. |
| Ändrades av | ID:t för den medarbetare som senast ändrade den valda transaktionen. |
| Fakturadatum | Ange det förväntade faktureringsdatumet. |
| Elimineringsdatum | Visa eller ändra elimineringsdatumet. När prognosen skapas ställs elimineringsdatumet in till projektets slutdatum. Om projektet inte har något slutdatum används projektdatumet. Detta fält gäller endast fastpris- och investeringsprojekt. |
| Betalningsdatum för kostnad | Ange förväntat datum för betalning av inköp. |
| Försäljningsbetalningsdatum | Ange förväntat datum för betalning av försäljning. |

### <a name="the-financial-dimensions-tab-on-the-demand-forecast-page"></a>Fliken Ekonomisk dimension på sidan Efterfrågeprognos

Fliken **Ekonomiska dimensioner** visar all ekonomiska dimensionsvärden för raden som är markerad på fliken **Översikt**.

### <a name="the-inventory-dimensions-tab-on-the-demand-forecast-page"></a>Fliken Lagerdimension på sidan Efterfrågeprognos

Fliken **lagerdimensioner** visar alla lagerdimensionsvärden för raden som för tillfället är markerad på fliken **Översikt**.

### <a name="the-allocation-grid-on-the-demand-forecast-page"></a>Allokeringsrutnätet på sidan Efterfrågeprognos

Om du använder en artikelallokeringsnyckel eller om du har angett en artikelprognos för en eller flera framtida perioder, kan du allokera prognosen genom att välja **Allokera prognos** i verktygsfältet på fliken **Översikt**. Kvantiteten fördelas sedan på det sätt som indikeras av raderna i rutnätet **Allokering**.

## <a name="inventory-forecast"></a><a name="inventory-forecast"></a>Lagerprognos

På sidorna för tillgångs- och efterfrågeprognosrader finns knappen **Lagerprognos** som öppnar en vy över sidan **Lagerprognos** som filtreras för samma artikel/modell-kombination. Lagerprognosen representerar ett saldo mellan den tillgång och efterfrågan som angetts för samma artikel. Den kan inte ändras. Lagerprognosen gör det lättare för lagerhanteringsteamet att granska förväntade ändringar av lagerbehållningen för en artikel under den kommande period som har prognosticerats.

### <a name="the-action-pane-on-the-inventory-forecast-page"></a>Åtgärdsfönstret på sidan lagerprognos

I följande tabell beskrivs de kommandon som är tillgängliga i åtgärdsfönstret på sidan **Lagerprognos**.

| Åtgärd | beskrivning |
|---|---|
| Leveransprognos | Öppna en vy på sidan **Inflödesprognos** som har filtrerats för samma artikel-/modell-/datumkombination. |
| Efterfrågeprognos | Öppna en vy på sidan **Efterfrågeprognos** som har filtrerats för samma artikel-/modell-/datumkombination. |
| Lager \> Visa dimensioner | Välj de produkt-, lagrings- och spårningsdimensioner som ska visas i rutnätet på fliken **Översikt**. |

### <a name="the-grid-on-the-inventory-forecast-page"></a>Rutnätet på sidan Lagerprognos

I följande tabell beskrivs fälten i rutnätet på sidan **Lagerprognos**.

| Fält | beskrivning |
|---|---|
| **Modell** | Den prognosmodell som transaktionen är kopplad till. |
| **Artikelnummer** | Identifieraren för artikeln. |
| **Budgetdatum** | Prognosens transaktionsdatum. |
| **Prognostyp** | Transaktionskällan (*Efterfrågeprognos* eller *Inflödesprognos*). |
| **FV-kvantitet** | Prognoskvantiteten i den nominella viktenheten. |
| **Antal** | Den prognosticerade kvantiteten i lagerenheten. |
| **Ackumulerad kvantitet (FV)** | Den ackumulerade prognoskvantiteten i den nominella viktenheten när flera prognosrader har ackumulerats för samma artikel. |
| **Understrukturlista** | Strukturlistenumret för en viss understrukturlista. |
| **Delrutt** | Flödesnumret för ett visst delflöde. |
| (Övriga dimensioner) | Ytterligare dimensioner kan visas som kolumner i rutnätet. Välj **Lagher \> Visa dimensioner** i åtgärdsfönstret om du vill välja de ytterligare dimensioner som visas. |

## <a name="bulk-update-forecast-transactions"></a><a name="bulk-update"></a>Massuppdatera prognostransaktioner

Använd denna procedur när du vill bearbeta befintliga prognostransaktionsrader. Du kan kopiera, redigera och ta bort prognostransaktionsrader.

1. På sidan Rader för tillgångs- eller efterfrågeprognoser väljer du **Bulkuppdatering**.
1. I dialogrutan väljer du **Filter**.
1. PÅ fliken **Område** väljer du de kriterier som identifierar den data för källprognos som du vill kopiera, redigera eller ta bort. Denna data kan prognosmodellen, artikelnumret och kundkontot.
1. Välj **OK** för att bekräfta valet.

    När du har valt önskad data kan du använda dialogrutan **Redigera prognostransaktiner** för att definiera hur länge du vill kopiera, redigera eller ta bort datan.

    > [!NOTE]
    > Filtreringssteget är en förutsättning för att kunna använda funktionen **Massredigering**. Om du hoppar över detta markerar och uppdaterar programmet **alla** prognosrader. Du kan därför oavsiktligt komma att orsaka duplicering eller borttagning av transaktioner.

1. I avsnittet **Hantering** väljer du om du vill kopiera, uppdatera eller ta bort de valda prognostransaktionerna.
1. Använd avsnittet **Ändringar i fält** för att ändra parametrarna i prognosen. Markera kryssrutan för en parameter och välj sedan bland de tillgängliga alternativen. Markera till exempel kryssrutan **Modell** och välj sedan ett prognosmodellnummer. Befintliga prognosrader kopieras till den valda prognosmodellen.
1. Använd avsnittet **Ändring av period** om du vill flytta start- och slutdatum för prognosen framåt eller bakåt. Markera kryssrutan och använd sedan fälten för kvantitet och period för att definiera hur prognosdatumen ska flyttas. Du kan ange en negativ kvantitet för att flytta startdatumet framåt (d.v.s. få det att infalla idigare).

    Om du till exempel vill försena startdatumet för prognostransaktionen med sex månader markerar du kryssrutan, anger *6* som kvantitet och anger sedan *Månader* som period.

1. Använd avsnittet **Rätt fält** för att uppdatera den faktiska prognosdatan. I fältet **Fält** väljer du det kriterium som du vill ändra. I fältet **Faktor** anger du en multiplikationsfaktro som ska tillämpas på valt kriterium, eller också anger du en konstant att lägga till eller dra ifrån. Välj till exempel *Kvantitet* som kriterium, och ange sedan faktorn *1,5* för att multiplicera artikelkvantiteten med 1,5. Du kan också ange konstanten *-25* för att öka artikelkvantiteten med 25 enheter.
1. Använd avsnittet **Ekonomiska dimensioner** om du vill uppdatera prognosradernas ekonomiska dimensioner. Välj de ekonomiska dimensioner som du vill ändra och ange sedan ett värde som ska användas för de valda dimensionerna.
1. Välj **OK** om du vill applicera dina ändringar.

## <a name="run-forecast-planning"></a>Kör prognosplanering

När du har angett dina efterfråge- och/eller inflödesprognos kan du köra en prognosplanering för att beräkna bruttobehov för material och kapacitet, samt för att generera planerade order.

1. Gå till **Huvudplanering \> Prognosticering \> Prognosplanering**.
1. I fältet **Prognosplan** väljer du en prognosplan.
1. Aktivera **Spåra bearbetningstid** för att registrera bearbetningstiden för respektive planeringsuppgift.
1. Ange ett värde i fältet **Antal trådar.** (Mer information finns i [Förbättra prestandan för huvudplanering](master-planning-performance.md).)
1. I fältet **Kommentar** anger du en text för att registrera ytterligare information som krävs.
1. På snabbfliken **Poster som ska inkluderas** väljer du **Filter** för att begränsa artikelurvalet.
1. På snabbfliken **Kör i bakgrunden** anger du parametrar för batchen.
1. Välj **OK**.

Du visar de behov som beräknas genom att öppna sidan **Bruttobehov**. På sidan **Frisläppta produkter**, på fliken **Plan**, i avsnittet **Krav**, väljer du **Bruttobehov**.

Om du vill visa planerade order som genereras går du till **Huvudplanering \> Common \> Planerade order** och väljer sedan lämplig prognosplan.

## <a name="additional-resources"></a>Ytterligare resurser

- [Efterfrågeprognosticering – översikt](introduction-demand-forecasting.md)
- [Inställning av efterfrågeprognosticering](demand-forecasting-setup.md)
- [Generera en statistisk baslinjeprognos](generate-statistical-baseline-forecast.md)
- [Gör manuella justeringar på baslinjeprognosen](manual-adjustments-baseline-forecast.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
