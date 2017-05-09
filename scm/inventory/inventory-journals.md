---
title: Lagerjournaler.
description: "Det här avsnittet ger en beskrivning av hur du kan använda lagerjournaler för att bokföra olika typer av fysiska lagertransaktioner."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventJournalBOM, InventJournalCount, InventJournalCountTag, InventJournalLossProfit, InventJournalMovement, InventJournalTransfer, WMSJournalTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 51631
ms.assetid: 3fedeaaf-502f-483c-93d2-ab266828189e
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: c64ba9e081ab4224556af86ec855ebf508853454
ms.lasthandoff: 03/31/2017


---

# <a name="inventory-journals"></a>Lagerjournaler.

[!include[banner](../includes/banner.md)]


Det här avsnittet ger en beskrivning av hur du kan använda lagerjournaler för att bokföra olika typer av fysiska lagertransaktioner. 

Lagerjournalerna i Microsoft Dynamics 365 for Operations används för att bokföra fysiska lagertransaktioner av olika typer, till exempel bokföringen av problem och kvitton, lagerrörelser, genereringen av strukturlistor (BOM) och avstämningen av fysiskt lager. Alla dessa lagerjournaler används på liknande sätt, men de delas in i olika typer.

## <a name="types-of-inventory-journals"></a>Typer av lagerjournaler
Följande typer av lagerjournal finns:

-   Rörelse
-   Lagerjustering
-   Överför
-   Strukturlista
-   Artikelinförsel
-   Produktionsinleverans
-   Inventering
-   Märkesinventering

### <a name="movement"></a>Rörelse

När du använder en lagerflyttningsjournal kan du lägga till kostnad för en artikel när du lägger till lagret, men du måste manuellt allokera merkostnaden till ett visst redovisningskonto genom att ange ett redovisningsmotkonto när du skapar journalen. Den här lagerjournaltypen är användbar om du vill skapa en utgift för en artikel mot en annan avdelning, eller om du vill ta bort artiklar från lager för utgiftsändamål.

### <a name="inventory-adjustment"></a>Lagerjustering

När du använder en lagerjusteringsjournal kan du lägga till kostnaden för en artikel när du lägger till lagret. Merkostnaden bokförs automatiskt till ett visst redovisningskonto baserat på inställningarna för artikelgruppbokföringsprofilen. Använd den här lagerjournaltypen om du vill uppdatera vinster och förluster till lagerkvantiteter när artikeln ska behålla sitt förvalda redovisningsmotkonto. När du bokför en lagerjusteringsjournal bokförs en lagerinleverans eller -utleverans, lagervärdena ändras och redovisningstransaktioner skapas.

### <a name="transfer"></a>Överför

Du kan använda överföringsjournaler för att överföra artiklar mellan lagerplatser, batchar eller produktvarianter utan att associera några kostnadskonsekvenser. Du kan till exempel överföra artiklar från ett lagerställe till ett annat lagerställe inom samma företag. När du använder en överföringsjournal måste du ställa in både ”från”- och ”till”-lagerdimensioner (exempelvis för Plats och Lagerställe). Lagerbehållningen för de definierade lagerdimensionerna ändras efter detta. Lageröverföringar återspeglar den omedelbara flyttningen av material. Lagret spåras inte under transport. Om detta krävs bör du använda en överföringsorder i stället. När du bokför en överföringsjournal skapas två lagertransaktioner för varje journalrad:

-   En lagerutleverans vid ”från”-platsen
-   En lagerinleverans vid ”till”-platsen

### <a name="bom"></a>Strukturlista

När du rapporterar en strukturlista som färdig kan du skapa en strukturlistejournal. Genom att använda en strukturlistejournal kan du bokföra strukturlistan direkt. Denna bokföring genererar en lagerinleverans av produkten tillsammans med en associerad strukturlista och en lagerutleverans av produkterna som ingår i strukturlistan. Denna lagerjournaltyp är användbar i enkla produktionsscenarier eller produktionsscenarier med hög volym där flöden inte är obligatoriska.

### <a name="item-arrival"></a>Artikelinförsel

Du kan använda artikelinförseljournalen för att registrera inleveransen av artiklar (exempelvis från inköpsorder). En artikelinförseljournal kan skapas som en del av införselhanteringen från sidan **Införselöversikt** eller så kan du manuellt skapa en journalpost från sidan **Artikelinförsel**. Om du aktiverar journalnamnet för artikelinförsel för att söka efter plockplatser, söker Dynamics 365 for Operation efter en plats för mottagna artiklar och genererar, om det finns plats, platsdestinationer för de inkommande artiklarna.

### <a name="production-input"></a>Produktionsinleverans

Produktionsinförseljournaler fungerar som artikelinförseljournalerna men används för tillverkningsorder.

### <a name="counting"></a>Inventering

Med inventeringsjournaler kan du justera den aktuella lagerbehållningen som är registrerad för artiklar eller grupper av artiklar och sedan bokföra det verkliga fysiska antalet så att du kan göra justeringar som krävs för att stämma av skillnaderna. Du kan koppla inventeringspolicyer med inventeringsgrupper som hjälper dig att gruppera artiklar som har olika egenskaper, så att artiklarna kan inkluderas i en inventeringsjournal. Du kan till exempel ställa in inventeringsgrupper för att räkna artiklar som har en specifik frekvens, eller för att räkna artiklar när lagret faller till en viss nivå. För mer information om hur du definierar inventeringsgrupper, se [Definiera inventeringsprocesser (uppgiftsguide)](http://ax.help.dynamics.com/en/wiki/define-inventory-counting-processes/).

### <a name="tag-counting"></a>Märkesinventering

Märkesinventeringsjournaler används för att tilldela ett numrerat märke till ett inventeringsparti. Märket ska innehålla märkesnummer, artikelnummer och artikelkvantitet. För att garantera att ett märke bara används en gång, och att alla märken används, bör alla artikelnummer ha en unik uppsättning märken som har sin egen nummerserie. Tre statusvärden kan anges för varje märke:

-   **Används** – Artikelnumret räknas för detta märke.
-   **Annullerad** – Artikelnumret annulleras för detta märke.
-   **Saknas** – Artikelnumret saknas för detta märke.

När du bokför en märkesinventeringsjournal skapas en ny inventeringsjournal baserat på raderna i märkesinventeringsjournalen. Mer information om märkesinventering finns i [Lagermärkesinventering](inventory-tag-counting.md).

## <a name="working-with-journals"></a>Arbeta med journaler
En journal kan endast öppnas av en användare åt gången. Om flera användare måste ha åtkomst till journalerna samtidigt för att skapa journalrader måste användarna välja journaler som för närvarande inte används för att förhindra överskrivning av information. I situationer där flera avdelningar använder samma journaltyp är det praktiskt att skapa flera journalnamn (exempelvis ett per avdelning). Det kan också vara användbart att dela upp journaler så att varje bokföringsrutin anges i sin egen unika lagerjournal. För bokföringsrutiner som är förknippade med lagertransaktioner skapar du en journal för periodiska lagerjusteringar och en annan för lagerinventering.

## <a name="posting-journal-lines"></a>Bokföringsjournalrader
Du kan bokföra journalraderna som du skapar när som helst, tills du har låst en artikel från ytterligare transaktioner. Data som du anger i en journal finns kvar i journalen även om du stänger den utan att bokföra raderna.




