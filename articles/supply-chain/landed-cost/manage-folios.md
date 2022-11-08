---
title: Hantera folio
description: I denna artikel beskrivs hur du arbetar med folio. En folio består normalt av en leverantörs varor för en enhet eller ett företag per leverans. Varorna i en folio kan läggas i en behållare eller spridas bland flera behållare.
author: Weijiesa
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMFolioTable, ITMFolioTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ab5729cd441246a6c04ac060d5a69f949bfe47c5
ms.sourcegitcommit: eb9a53d5cf10f1ada68757536d6a94b2cb00929d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725505"
---
# <a name="manage-folios"></a>Hantera folio

[!include [banner](../../includes/banner.md)]

En folio avgörs ofta av tullregleringar. Den består av en leverantörs varor för en enhet eller ett företag per leverans. Varorna i en folio hanteras i en och samma behållare.

Om du vill öppna sidan **Alla folio** går du till **Hemtagningskostnad \> folio \> Alla folio**. På den här sidan visas en lista över alla aktuella folio. Med knapparna i åtgärdsfönstret kan du skapa, ta bort och arbeta med folio. Välj folio i listan om du vill visa mer information om detta på sidan **folio**.

## <a name="action-pane"></a>Åtgärdsfönster

Åtgärdsfönstret på sidan **Alla folio** och **Folio** ger knappar som gör att du kan arbeta med en vald folio. Varje knapp utför en enskild åtgärd. I åtgärdsfönstret finns även flikar, och varje flik, som i sin tur innehåller en uppsättning relaterade knappar. Utom i de fall där detta anges finns alla knappar och flikar som beskrivs i följande delgrupper tillgängliga både i listvyn (det vill säga på sidan **Alla folio**) och i den detaljerade vyn (d.v.s. på sidan **Folio**).

### <a name="buttons-that-appear-directly-on-the-action-pane"></a>Knappar som visas direkt i åtgärdsfönstret

I följande tabell beskrivs de knappar som finns tillgängliga direkt i åtgärdsfönstret.

| Knapp | beskrivning |
|---|---|
| Nytt | Skapa en folio. |
| Radera | Ta bort den öppna eller valda folio. |
| Kostnader för sjötransport | Öppna sidan **Färdkostnader**, där du kan visa och lägga till kostnader på folio-nivå för alla varor i färden. När foliokostnader läggs till manuellt i resan läggs de automatiskt till Kostnadsförfrågan och fördelas på varje vara enligt metoden som anges på sidan **Färdkostnader**. |

### <a name="buttons-on-the-manage-tab"></a>Knappar på fliken Hantera

I följande tabell beskrivs de knappar som finns tillgängliga på fliken **Hantera** i åtgärdsfönstret.

| Knapp | beskrivning |
|---|---|
| Bokför inleveranslista | Bokför en inleveranslista för alla inköpsorderrader i folio.  |
| Bokför produktinleverans | Bokför en produktinleverans för alla inköpsorderrader i folio. |
| Bokför faktura | Bokför en faktura för alla inköpsorderrader i folio.  |
| Leverera överföringsorder | Bokför en överföringsorder för alla överföringsorderrader som är relaterade till aktuell leverans. |
| Inleverera överföringsorder | Bokför en inleverans av överföringsorder för alla överföringsorderrader som är relaterade till aktuell leverans. |
| Inleverera varor på väg | Ta emot alla orderrader som är på väg i folio. |
| Mottagna dokument | Uppdatera inställningar för alternativet **Dokument som mottagits** till *Ja*. Du kan använda den här knappen om du vill låsa artikeln och/eller inköpsraden så att den inte kan uppdateras ytterligare. |
| Sök efter automatiska kostnader | Hitta relevanta färdkostnader. Om dessa kostnader redan har hittats eller uppdaterats visas följande meddelande: "Ej fakturerade kostnadsrader finns. Vill du skriva över dem? Observera att färdkostnader som är kopplade till en folio och som har fakturerats kommer inte att skrivas över. |
| Skapa införseljournal | Generera en införseljournal för organisationer med hjälp av avancerade lagerställefunktioner. Du kan välja **Initiera kvantitet** (rekommenderas), **Skapa från varor under transport** och/eller **Skapa från inköpsorder**. Det sista alternativet beror på om bearbetning av varor på väg används. |
| Periodisera kostnader | Periodisera kostnader där en kostnadstyp har ett redovisningskonto angivet för debet. Den här knappen används normalt när lagret är under transport eller när varor har tagits emot och fakturerats. |

### <a name="buttons-on-the-general-tab"></a>Knappar på fliken Allmän

I följande tabell beskrivs de knappar som finns tillgängliga på fliken **Allmän** i åtgärdsfönstret.

| Knapp | beskrivning |
|---|---|
| Inleveranslista | Bokför en inleveranslista för alla inköpsorderrader i folio.  |
| Produktinleverans | Visa produktinleveransposten, om den används. |
| Artikelinförsel | Visa artikelinförseljournalen om den används. |
| Kostnadsförfrågan | Öppna sidan kostnadsförfrågan om du vill visa alla kostnader för en sådan, inklusive leveransbehållare, vy eller inköpsorder. Du kan justera den exakta vyn av sidan med åtgärden visa. På sidan kostnadsförfrågan kan du visa alla områden, samt artikel- och kostnadstypkoden. Genom att ta bort dessa artiklar kan du justera sidan genom att gruppera kostnader tillsammans. Den här kapaciteten kan vara användbar om du använder storlekar och färger. Du kan ändra dimensionerna som visas på sidan. Sidan **Kostnader** visar bara kostnadstypskoder där fältet **Dr** på fliken **Bokföring** är inställt på *Artikel*. |

## <a name="header-view"></a>Huvudvy

Öppna vyn **Huvud** genom att öppna en folio och sedan välja fliken **Huvud** i den övre högra delen av folio rubrik.

### <a name="settings-on-the-general-fasttab"></a>Inställningar på snabbfliken Redovisning

I tabellen nedan beskrivs fälten som är tillgängliga på snabbfliken **Allmänt** i vyn **Huvud** för en folio.

| Fält | beskrivning |
|---|---|
| Folio | Namnet på folio. Det här namnet genereras automatiskt när folio skapas.|
| Sjötransport | Den färd som är associerad med folio. |
| Tullmäklare | Välj tullmäklare för folio. Tullmäklare definieras på leverantören. Med hjälp av dessa kan skapade kostnader bestämmas automatiskt. |
| HAWB/fraktsedel | Ange den underflygfraktsedel eller fraktsedel som ska tillämpas på folio. |
| Företag | Den juridiska enhet (företag) som är associerad med folio. |
| Lastens kontrollnummer | Detta fält används av tullmyndigheterna i vissa länder eller regioner. |
| Mått | Detta fält gör att en mätning kan anges i modulen **Hemtagningskostnad**. Mått används ofta av organisationer som inte känner till den individuella volymen eller vikten av varorna, men som kräver en mer korrekt fördelning än alternativen för belopp och kvantitet. Fraktspeditören ger med vikt- eller kubiska mått och du kan lägga den på antingen en artikel eller inköpsorder.. Den kan uppdateras automatiskt om parametern väljs eller anges manuellt. |
| Måttenhet | Enheten som gäller för det angivna måttet. |
| Antal kartonger | Antal kartonger i folio. Fältet kan uppdateras automatiskt beroende på parameterurvalet. |
| Leverantörskonto | Välj den leverantör som är associerad med folion. Detta fält är bara avsett för information. Den påverkar inte några funktioner. |
| Namn | Namnet på det valda leverantörskontot. |
| Kommentarer | Ange eventuell ytterligare information som är relaterad till folio. |
| Beskrivning av varor | Välj en varubeskrivning som identifierar folio. För mer information, se [Beskrivning av varor](shipping-information-setup.md#description-of-goods). |
| Värderingsdatum | Detta fält är relaterat till sidan för inmatning av skatt. Modulen **Hemtagningskostnad** kommer att använda tullväxelkursen för det datum som du anger här. Standardvärdet är datumet på inmatningssidan för skatt. |
| Tull-ID | Ange tull-ID. Det här ID:t kan tillhandahållas av tullavdelningarna i länder eller regioner. |
| Tariffkod | Ange en tariffkod som ska associeras med folio. Denna kod krävs normalt (och definieras) av landet eller regionen som du levererar till. |

### <a name="settings-on-the-delivery-fasttab"></a>Inställningar på snabbfliken Leverans

I tabellen nedan beskrivs inställningarna som är tillgängliga på snabbfliken **Leverans** i vyn **Huvud** för en folio.

| Fält | beskrivning |
|---|---|
| Foliodatum | Välj ett datum ska associeras med folio. Standardvärdet är datumet då färden skapades. |
| Beräknad ankomst vid leveranshamn | Uppskattat ankomstdatum (ETA) vid destinationsporten ("till"-porten). |
| Uppskattat leveransdatum | Vanligen det datum då varorna ska ankomma till lagerstället. Fältet används inte när det uppskattade leveransdatumet beräknas. (Det uppskattade leveransdatumet för spårningskontroll används istället.) Om du vill konfigurera detta fält så att värdet matchar spårningskontrollens uppskattade leveransdatum använder du [Spårningskontrollcentret](delivery-information-setup.md#tracking-control-center). |
| Mottagna originaldokument | Datumet när originaldokumenten togs emot. |
| Mäklaren har informerats | Datumet när mäklaren informerades. |
| Skickad ursprunglig fraktsedel | Datumet när den ursprungliga fraktsedeln skickades. |
| Varor som frisläppts | Det datum då varor frisläppdes. |
| Kundmöte | Datumet för kundbokningen. |
| Levererad vid distributionslager | Datumet när varorna levererades till lagerstället. |
| Verifieringsdatum | Verifieringsdatumet. |
| Leveransinstruktioner | Datum då leveransinstruktionerna togs emot. |
| Från hamn | Porten som färden avgår från. |
| Till hamn | Porten där färden anländer. Leveransbehållaren kan ha en annan port, eftersom den kan stoppas vid flera portar. |

### <a name="settings-on-the-export-fasttab"></a>Inställningar på snabbfliken Export

I tabellen nedan beskrivs inställningarna som är tillgängliga på snabbfliken **Export** i vyn **Huvud** för en folio.

| Fält | beskrivning |
|---|---|
| Exportör | Exportören kan lagras på folio. I den internationella handeln kan du skicka en inköpsorder till ett företag men ta emot varorna från ett annat företag. Spårning och dokumentation krävs av tullmyndigheten. Exportörens namn och adress kan lagras här. |
| Namn | Namn på vald exportör. |

## <a name="lines-view"></a>Radvy

Öppna vyn **Rader** genom att öppna en folio och sedan välja fliken **Rader** i den övre högra delen av folio rubrik.

### <a name="information-on-the-folio-fasttab"></a>Information om snabbfliken Folio

Snabbfliken **Folio** i vyn **Rader** visar information om folio. Större delen av den här informationen visas även i vyn **Rubrik**, på det sätt som beskrivs tidigare i denna artikel.

### <a name="information-and-buttons-on-the-lines-fasttab"></a>Information och knappar på snabbflikarna Rader

Snabbfliken **Rader** i vyn **Rader** visar information om alla fullständiga eller delvisa inköpsorderrader som ingår i den aktuella folio.

I följande tabell beskrivs de knappar som finns tillgängliga i verktygsfältet på snabbfliken **Rader** i vyn **Rader**.

| Knapp | beskrivning |
|---|---|
| Ta bort | Ta bort den valda inköpsorderraden från färden. |
| Lager \> Transaktioner | Visa lagertransaktioner för den valda inköpsordern. Observera att om du använder varor på väg visas även den ursprungliga ordern och ordern för varor som överförs under transport. |
| Lager \> Visa dimensioner | Öppna en dialogruta där du kan välja lagerdimensionerna som visas för de transaktioner som du visar. |
| Förnya | Uppdatera information som är relaterad till radbelopp, vikt eller volym för den valda inköpsorderraden. |

### <a name="information-on-the-lines-details-fasttab"></a>Information på snabbfliken raddetaljer

Snabbfliken **Raddetaljer** i vyn **Rader** visar information om inköpsorderraden som för närvarande är vald på snabbfliken **Rader**.
