---
title: Parametrar som inte används av Planeringsoptimeringen
description: Denna artikel visar en lista över de parametrar som Planeringsoptimeringen just nu inte tar hänsyn till under drift.
author: t-benebo
ms.date: 09/02/2021
ms.topic: article
ms.search.form: ReqParameters, ReqGroup, ReqItemTable, ReqPlanSched, EcoResProductDetailsExtended, InventItemOrderSetup, WorkCalendarTable, PdsDispositionMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-06-29
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: db8a8e929bf75c4d1dac0c1b0a7cbc848ff291a9
ms.sourcegitcommit: b3579ac62e1ea15664a114abcc2409cad76d4f19
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/14/2022
ms.locfileid: "9682679"
---
# <a name="parameters-not-used-by-planning-optimization"></a>Parametrar som inte används av Planeringsoptimeringen

[!include [banner](../../includes/banner.md)]

Denna artikel visar en lista över de parametrar som Planeringsoptimeringen just nu inte tar hänsyn till under drift. Planeringstjänsten kan hoppa över en parameter eftersom till exempel relaterade funktioner ännu inte stöds. Alternativt kan parametern ha blivit föråldrad på grund av funktionella ändringar.

I de följande avsnitten anges de parametrar som Planeringsoptimeringen inte använder på vissa sidor. De förklarar också varför respektive parameter inte används.

## <a name="master-planning-parameters-page"></a>Sidan Huvudplaneringsparametrar

Planeringsoptimeringen använder inte följande parametrar eller alternativ på sidan **Parametrar för huvudplanering**:

- Fliken **Allmänt**:

  - **Aktuell prognosplan** – Inväntar stöd för *Prognos*.
  - **Aktuell statisk huvudplan** – Inväntar stöd för *Kopiera statisk till dynamisk plan*.
  - **Aktuell dynamisk huvudplan** – Inväntar stöd för *Kopiera statisk till dynamisk plan*.
  - **Kopiera den fullständiga och uppdaterade statiska huvudplanen till den dynamiska huvudplanen** – Inväntar stöd för *Kopiera statisk till dynamisk plan*.
  - **Starttid för beräknade förseningar** – Inväntar stöd för *Beräknade förseningar*.
  - **Använd dynamiska negativa dagar** – I Planeringsoptimeringen används alltid metoden *Dynamiskt negativa dagar*.
  - **Dagens datumkalender** – Inväntar stöd för *Tidsplanering*.
  - **Användning av cacheminne** – Konfigurationen av Microsoft Azure-prenumerationen hanterar prestandapunkter.
  - **Antalet uppgifter i hjälpens uppgiftsbunt** – Azure-prenumerationskonfigurationen hanterar prestandapunkter.
  - **Förbearbetning: Filtrera automatiskt efter artiklar med direkt efterfrågan** – Azure-prenumerationskonfigurationen hanterar prestandapunkter.
  - **Efterbearbetning: Filtrera automatiskt efter artiklar med direkt efterfrågan** – Azure-prenumerationskonfigurationen hanterar prestandapunkter.
  - **Antalet order i uppgiftsbunt** – Azure-prenumerationskonfigurationen hanterar prestandapunkter.
  - **Antalet trådar** – Azure-prenumerationskonfigurationen hanterar prestandapunkter.
  - **Tidsgräns för planeringsprocess i minuter** – Azure-prenumerationskonfigurationen hanterar prestandapunkter.
  - **Starttid för planering** – Inväntar stöd för *Tidsplanering*.

- Fliken **Planerade order**:

  - **Inleveranstid** – Inväntar stöd för *Tidsplanering*.
  - **Produktion** – Inväntar stöd för *Tidsplanering*.
  - Fält i avsnittet **Projekt** – Inväntar stöd för *Tidsplanering*.

## <a name="coverage-groups-page"></a>Sida för disponeringsgrupper

Planeringsoptimeringen använder inte följande parametrar eller alternativ på sidan **Disponeringsgrupper**:

- Snabbfliken **Allmänt**:

  - **Positiva dagar** – Värdet för *Positiva dagar* används inte. Med Planeringsoptimering betraktas positiva dagar som obegränsade.
  - **Förbruka lagerbehållning** – Inväntar stöd för *Förbrukning av lagerhållning*.
  - **Använd angiven strukturlista eller formelversion** – Inväntar stöd för *Formelversioner med sam-/biprodukt*.
  - **Använd angiven flödesversion** – Inväntar stöd för *Krav med definierade strukturliste- eller flödeskrav*.


- Snabbfliken **Annan**:

  - **Frys tidsgräns (dagar)** – Stöd för *Frys tidsgräns* planeras inte i Planeringsoptimeringen.
  - **Tidsgräns för strukturlistenedbrytning (dagar)** – Inväntar stöd för *Tidsplanering*.
  - **Tidsgräns för kapacitetsplanering (dagar)** – Inväntar stöd för *Tidsplanering*.
  - **Godkänd tidsgräns för rekvisition (dagar)** – Inväntar stöd för *Rekvisition*.
  - **Tidsgräns för prognosplan** – Inväntar stöd för *Prognos*.

- Snabbfliken **Förseningar**:

  - **Beräknade förseningar** – Inväntar stöd för *Beräknade förseningar*.
  - **Tidsgräns för beräknade förseningar (dagar)** – Inväntar stöd för *Beräknade förseningar*.

## <a name="item-coverage-page"></a>Sidan Artikeldisponering

Planeringsoptimeringen använder inte följande parametrar eller alternativ på sidan **Artikeldisponering**:

- Fliken **Allmänt**:

  - **Planerad ordertyp** – Planeringsoptimeringen stöder inte alternativet *Kanban* i väntan på stöd för *kanban*.
  - **Frys tidsgräns (dagar)** – Stöd för *Frys tidsgräns* planeras inte i Planeringsoptimeringen.
  - **Tidsgräns för strukturlistenedbrytning (dagar)** – Inväntar stöd för *Tidsplanering*.
  - **Tidsgräns för kapacitetsplanering (dagar)** – Inväntar stöd för *Tidsplanering*.
  - **Godkänd tidsgräns för rekvisition (dagar)** – Inväntar stöd för *Rekvisition*.
  - **Uppfyll minimum** – Planeringsoptimeringen stöder inte alternativen *Dagens datum*, *Första utleverans* eller *Tidsgräns för disponering*. Den använder alltid alternativet *Dagens datum + anskaffningstid*.
  - **Minimiperioder** – Inväntar på stöd *Lägsta lagernivå*.
  - **Planeringsformel** – Inväntar stöd för *Formelversioner med sam-/biprodukter*.
  - **Standardprioritet** – Inväntar stöd för *Formelversioner med sam-/biprodukter*.
  - **Aktuelle prioritet** – Inväntar stöd för *Formelversioner med sam-/biprodukter*.
  - **Datum för ändring** – Inväntar stöd för *Formelversioner med sam-/biprodukter*.
  - **Förbruka lagerbehållning** – Inväntar stöd för *Förbrukning av lagerhållning*.

- Fliken **Produktionstid**:

  - **Inköpstid** – I versioner av tjänsten Planeringsoptimering som är äldre än den 6 augusti 2021-versionen använder Planeringsoptimering den här parametern för att beräkna korrekta order- och leveransdatum, men den sparar inte själva den beräknade produktionstiden i den planerade ordern. I senare versioner använder tjänsten också den beräknade ledtiden för att konfigurera fältet **Produktionstid** och **Arbetsdagar** efter behov för den relevanta planerade ordern.
  - **Produktionstid** – I versioner av tjänsten Planeringsoptimering som är äldre än den 6 augusti 2021-versionen använder Planeringsoptimering den här parametern för att beräkna korrekta order- och leveransdatum, men den sparar inte själva den beräknade produktionstiden i den planerade ordern. I senare versioner använder tjänsten också den beräknade ledtiden för att konfigurera fältet **Produktionstid** och **Arbetsdagar** efter behov för den relevanta planerade ordern.
  - **Överföringstid** – I versioner av tjänsten Planeringsoptimering som är äldre än den 6 augusti 2021-versionen använder Planeringsoptimering den här parametern för att beräkna korrekta order- och leveransdatum, men den sparar inte själva den beräknade produktionstiden i den planerade ordern. I senare versioner använder tjänsten också den beräknade ledtiden för att konfigurera fältet **Produktionstid** och **Arbetsdagar** efter behov för den relevanta planerade ordern.
  - **Arbetsdagar** – I versioner av tjänsten Planeringsoptimering som är äldre än den 6 augusti 2021-versionen använder Planeringsoptimering den här parametern för att beräkna korrekta order- och leveransdatum, men den sparar inte själva den beräknade produktionstiden i den planerade ordern. I senare versioner använder tjänsten också den beräknade ledtiden för att konfigurera fältet **Produktionstid** och **Arbetsdagar** efter behov för den relevanta planerade ordern.

## <a name="master-plans-page"></a>Sidan Huvudplaner

Planeringsoptimeringen använder inte följande parametrar eller alternativ på sidan **Huvudplaner**:

- Snabbfliken **Allmänt**:

  - **Åsidosätt behållning** – Inväntar stöd för *Förbrukning av lagerhållning*.
  - **Förbruka lagerbehållning** – Inväntar stöd för *Förbrukning av lagerhållning*.
  - **Inkludera försäljningsofferter** – Inväntar stöd för *försäljningsofferter*.
  - **Inkludera anbudsförfrågningar** – Inväntar stöd för *Anbudsförfrågningar*.
  - **Använd datum för hållbarhetstid** – Inväntar stöd för *Hållbarhetstid*.
  - **Inkludera kontinuitetsplan** – Inväntar stöd för *Kontinuitetstidsplanering*.
  - **Planeringsmetod** – Inväntar stöd för *Tidsplanering*.
  - **Begränsad egenskap** – Inväntar stöd för *Tidsplanering*.
  - **Tidsgräns för planeringskapacitet bakåt** – Inväntar stöd för *Tidsplanering*.
  - **Begränsad kapacitet** – Inväntar stöd för *Tidsplanering*.
  - **Tidsgräns för begränsad kapacitet** – Inväntar stöd för *Tidsplanering*.
  - **Begränsad kapacitet för flaskhalsresurser** – Inväntar stöd för *Tidsplanering*.
  - **Kapacitetstidsgräns för flaskhalsresurser** – Inväntar stöd för *Tidsplanering*.
  - **Planerade order** – I Planeringsoptimering används fasta nummerserier.
  - **Session** – I Planeringsoptimering används fasta nummerserier.
  - **Kontinuitetsplan** – I Planeringsoptimering används fasta nummerserier.

- Snabbfliken **Tidsgräns i dagar**:

  - **Frys** – Stöd för *Frys tidsgräns* planeras inte i Planeringsoptimeringen.
  - **Nedbrytning** – Inväntar stöd för *Tidsplanering*.
  - **Prognosplan** – Inväntar ytterligare stöd för *Prognos*.
  - **Kapacitet** – Inväntar stöd för *Tidsplanering*.
  - **Kontinuitetsplan** – Inväntar stöd för *Kontinuitetsplanering*.
  - **Beräknade förseningar** – Inväntar ytterligare stöd för *Beräknade förseningar*.
  - **Ordningsföljd** – Inväntar stöd för *Produktion*.

- Snabbfliken **Beräknade förseningar**:

  - **Kontrollera att planerade order inte skapas före körningsdatumet för huvudplaneringen** – Inväntar stöd för *beräknade förseningar*.
  - **Lägg till den beräknade förseningen till kravdatum** (i avsnittet **Planerade inköpsorder**) – Inväntar stöd för *Beräknade fördröjningar*.
  - **Lägg till den beräknade förseningen till kravdatum** (i avsnittet **Planerade inköpsorder**) – Inväntar stöd för *Beräknade fördröjningar*.
  - **Lägg till den beräknade förseningen till kravdatum** (i avsnittet **Planerad överföring**) – Inväntar stöd för *Beräknade fördröjningar*.
  - **Lägg till den beräknade förseningen till kravdatum** (i avsnittet **Planerad kanban**) – Inväntar stöd för *Beräknade fördröjningar*.

- Snabbfliken **Åtgärdsmeddelande**:

  - **Uppdatera senarelagt datum som behovsdatum** - Den här parametern upphör att använda Planeringsoptimering.

- Snabbfliken **Ordningsföljd**:

  - **Ordna planerade order efter huvudplanering** – Inväntar stöd för *Ordningsföljd*.
  - **Grupptyp** – Inväntar stöd för *Ordningsföljd*.
  - **Periodtyp** – Inväntar stöd för *Ordningsföljd*.
  - **Antal grupper i kampanjcykeln** – Inväntar stöd för *Ordningsföljd*.

## <a name="released-product-details-page"></a>Sidan Information om frisläppt produkt

Planeringsoptimeringen använder inte följande parameteralternativ på sidan **Frisläppta produktdetaljer**:

- Snabbfliken **Tekniker**:

  - **Produktionstyp** – Planeringsoptimering stöder inte alternativet *Planeringsartikel* i väntan på stöd för *Planeringsartiklar*.

## <a name="default-order-settings-page"></a>Sidan Standardorderinställningar

Planeringsoptimeringen använder inte följande parameteralternativ på sidan **Standardorderinställningar**:

- Snabbfliken **Inköpsorder**:

  - **Ledtid för inköp** – I versioner av tjänsten Planeringsoptimering som är äldre än den 6 augusti 2021-versionen använder Planeringsoptimering den här parametern för att beräkna korrekta order- och leveransdatum, men den sparar inte själva den beräknade produktionstiden i den planerade ordern. I senare versioner använder tjänsten också den beräknade ledtiden för att konfigurera fältet **Produktionstid** och **Arbetsdagar** efter behov för den relevanta planerade ordern.
  - **Arbetsdagar** – I versioner av tjänsten Planeringsoptimering som är äldre än den 6 augusti 2021-versionen använder Planeringsoptimering den här parametern för att beräkna korrekta order- och leveransdatum, men den sparar inte själva den beräknade produktionstiden i den planerade ordern. I senare versioner använder tjänsten också den beräknade ledtiden för att konfigurera fältet **Produktionstid** och **Arbetsdagar** efter behov för den relevanta planerade ordern.

- Snabbfliken **Lager**:

  - **Datumkontroll för leverans** – Planeringsoptimering stöder inte alternative *CTP* i väntan på stöd för *CTP*.
  - **Ledtid för lager** – I versioner av tjänsten Planeringsoptimering som är äldre än den 6 augusti 2021-versionen använder Planeringsoptimering den här parametern för att beräkna korrekta order- och leveransdatum, men den sparar inte själva den beräknade produktionstiden i den planerade ordern. I senare versioner använder tjänsten också den beräknade ledtiden för att konfigurera fältet **Produktionstid** och **Arbetsdagar** efter behov för den relevanta planerade ordern.
  - **Arbetsdagar** – I versioner av tjänsten Planeringsoptimering som är äldre än den 6 augusti 2021-versionen använder Planeringsoptimering den här parametern för att beräkna korrekta order- och leveransdatum, men den sparar inte själva den beräknade produktionstiden i den planerade ordern. I senare versioner använder tjänsten också den beräknade ledtiden för att konfigurera fältet **Produktionstid** och **Arbetsdagar** efter behov för den relevanta planerade ordern.

## <a name="batch-disposition-master-page"></a>Huvudsidan för batchdisposition

Planeringsoptimeringen använder inte följande parameter på sidan **Batch-dispositionshuvud**:

- Snabbfliken **Konfiguration**:

  - **Nettotabell** – Inväntar stöd för *batchdispositionskoder*.
 
