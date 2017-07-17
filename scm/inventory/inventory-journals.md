---
title: Lagerjournaler.
description: "Det här avsnittet ger en beskrivning av hur du kan använda lagerjournaler för att bokföra olika typer av fysiska lagertransaktioner."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalBOM, InventJournalCount, InventJournalCountTag, InventJournalLossProfit, InventJournalMovement, InventJournalTransfer, WMSJournalTable
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 51631
ms.assetid: 3fedeaaf-502f-483c-93d2-ab266828189e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: fa629b4b8f7fcbd15ee89bc66cbc0bd7ca45215c
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Lagerjournaler.
<a id="inventory-journals" class="xliff"></a>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Det här avsnittet ger en beskrivning av hur du kan använda lagerjournaler för att bokföra olika typer av fysiska lagertransaktioner. 

Lagerjournalerna i Microsoft Dynamics 365 for Finance and Operations används för att bokföra fysiska lagertransaktioner av olika typer, till exempel bokföringen av problem och kvitton, lagerrörelser, genereringen av strukturlistor (BOM) och avstämningen av fysiskt lager. Alla dessa lagerjournaler används på liknande sätt, men de delas in i olika typer.

## Typer av lagerjournaler
<a id="types-of-inventory-journals" class="xliff"></a>
Följande typer av lagerjournal finns:

-   Rörelse
-   Lagerjustering
-   Överför
-   Strukturlista
-   Artikelinförsel
-   Produktionsinleverans
-   Inventering
-   Märkesinventering

### Rörelse
<a id="movement" class="xliff"></a>

När du använder en lagerflyttningsjournal kan du lägga till kostnad för en artikel när du lägger till lagret, men du måste manuellt allokera merkostnaden till ett visst redovisningskonto genom att ange ett redovisningsmotkonto när du skapar journalen. Den här lagerjournaltypen är användbar om du vill skapa en utgift för en artikel mot en annan avdelning, eller om du vill ta bort artiklar från lager för utgiftsändamål.

### Lagerjustering
<a id="inventory-adjustment" class="xliff"></a>

När du använder en lagerjusteringsjournal kan du lägga till kostnaden för en artikel när du lägger till lagret. Merkostnaden bokförs automatiskt till ett visst redovisningskonto baserat på inställningarna för artikelgruppbokföringsprofilen. Använd den här lagerjournaltypen om du vill uppdatera vinster och förluster till lagerkvantiteter när artikeln ska behålla sitt förvalda redovisningsmotkonto. När du bokför en lagerjusteringsjournal bokförs en lagerinleverans eller -utleverans, lagervärdena ändras och redovisningstransaktioner skapas.

### Överför
<a id="transfer" class="xliff"></a>

Du kan använda överföringsjournaler för att överföra artiklar mellan lagerplatser, batchar eller produktvarianter utan att associera några kostnadskonsekvenser. Du kan till exempel överföra artiklar från ett lagerställe till ett annat lagerställe inom samma företag. När du använder en överföringsjournal måste du ställa in både ”från”- och ”till”-lagerdimensioner (exempelvis för Plats och Lagerställe). Lagerbehållningen för de definierade lagerdimensionerna ändras efter detta. Lageröverföringar återspeglar den omedelbara flyttningen av material. Lagret spåras inte under transport. Om detta krävs bör du använda en överföringsorder i stället. När du bokför en överföringsjournal skapas två lagertransaktioner för varje journalrad:

-   En lagerutleverans vid ”från”-platsen
-   En lagerinleverans vid ”till”-platsen

### Strukturlista
<a id="bom" class="xliff"></a>

När du rapporterar en strukturlista som färdig kan du skapa en strukturlistejournal. Genom att använda en strukturlistejournal kan du bokföra strukturlistan direkt. Denna bokföring genererar en lagerinleverans av produkten tillsammans med en associerad strukturlista och en lagerutleverans av produkterna som ingår i strukturlistan. Denna lagerjournaltyp är användbar i enkla produktionsscenarier eller produktionsscenarier med hög volym där flöden inte är obligatoriska.

### Artikelinförsel
<a id="item-arrival" class="xliff"></a>

Du kan använda artikelinförseljournalen för att registrera inleveransen av artiklar (exempelvis från inköpsorder). En artikelinförseljournal kan skapas som en del av införselhanteringen från sidan **Införselöversikt** eller så kan du manuellt skapa en journalpost från sidan **Artikelinförsel**. Om du aktiverar journalnamnet för artikelinförsel för att söka efter plockplatser, söker Finance and Operations efter en plats för mottagna artiklar och genererar, om det finns plats, platsdestinationer för de inkommande artiklarna.

### Produktionsinleverans
<a id="production-input" class="xliff"></a>

Produktionsinförseljournaler fungerar som artikelinförseljournalerna men används för tillverkningsorder.

### Inventering
<a id="counting" class="xliff"></a>

Med inventeringsjournaler kan du justera den aktuella lagerbehållningen som är registrerad för artiklar eller grupper av artiklar och sedan bokföra det verkliga fysiska antalet så att du kan göra justeringar som krävs för att stämma av skillnaderna. Du kan koppla inventeringspolicyer med inventeringsgrupper som hjälper dig att gruppera artiklar som har olika egenskaper, så att artiklarna kan inkluderas i en inventeringsjournal. Du kan till exempel ställa in inventeringsgrupper för att räkna artiklar som har en specifik frekvens, eller för att räkna artiklar när lagret faller till en viss nivå. För mer information om hur du definierar inventeringsgrupper, se [Definiera inventeringsprocesser (uppgiftsguide)](http://ax.help.dynamics.com/en/wiki/define-inventory-counting-processes/).

### Märkesinventering
<a id="tag-counting" class="xliff"></a>

Märkesinventeringsjournaler används för att tilldela ett numrerat märke till ett inventeringsparti. Märket ska innehålla märkesnummer, artikelnummer och artikelkvantitet. För att garantera att ett märke bara används en gång, och att alla märken används, bör alla artikelnummer ha en unik uppsättning märken som har sin egen nummerserie. Tre statusvärden kan anges för varje märke:

-   **Används** – Artikelnumret räknas för detta märke.
-   **Annullerad** – Artikelnumret annulleras för detta märke.
-   **Saknas** – Artikelnumret saknas för detta märke.

När du bokför en märkesinventeringsjournal skapas en ny inventeringsjournal baserat på raderna i märkesinventeringsjournalen. Mer information om märkesinventering finns i [Lagermärkesinventering](inventory-tag-counting.md).

## Arbeta med journaler
<a id="working-with-journals" class="xliff"></a>
En journal kan endast öppnas av en användare åt gången. Om flera användare måste ha åtkomst till journalerna samtidigt för att skapa journalrader måste användarna välja journaler som för närvarande inte används för att förhindra överskrivning av information. I situationer där flera avdelningar använder samma journaltyp är det praktiskt att skapa flera journalnamn (exempelvis ett per avdelning). Det kan också vara användbart att dela upp journaler så att varje bokföringsrutin anges i sin egen unika lagerjournal. För bokföringsrutiner som är förknippade med lagertransaktioner skapar du en journal för periodiska lagerjusteringar och en annan för lagerinventering.

## Bokföringsjournalrader
<a id="posting-journal-lines" class="xliff"></a>
Du kan bokföra journalraderna som du skapar när som helst, tills du har låst en artikel från ytterligare transaktioner. Data som du anger i en journal finns kvar i journalen även om du stänger den utan att bokföra raderna.




