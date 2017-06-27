---
title: "Standardkostnadskonvertering – översikt"
description: "Den här artikeln ger en översikt över processen för att ställa in och köra en standardkostnadskonvertering. Den angivna stegen är avsett att utföras efter att du slutfört förberedelserna för en standardkostnadskonvertering."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 78212
ms.assetid: d601d9d5-1de3-4868-aff4-534dca01d624
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 6e223c2d9a683d7b92b73d3fe3d3c8b22684d22c
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="standard-cost-conversion-overview"></a>Standardkostnadskonvertering – översikt

[!include[banner](../includes/banner.md)]


Den här artikeln ger en översikt över processen för att ställa in och köra en standardkostnadskonvertering. Den angivna stegen är avsett att utföras efter att du slutfört förberedelserna för en standardkostnadskonvertering. 

Använd formuläret **Konverteringar av standardkostnad** när du vill konvertera lagermodellen för en batch med valda artiklar från en faktisk kostnadsredovisning till en standardkostnadsredovisning. Konverteringsprocessen omfattar en obligatorisk lagerstängning, flera steg under en övergångsperiod, som definieras av ett övergångsstartdatum och ett planerat konverteringsdatum, samt själva konverteringen med tillhörande lagerstängning.

-   Lagerstängning före övergångperioden – en lagerstängning representerar ett nödvändigt steg eftersom det kvittar en artikels öppna transaktioner med den gamla värderingsmetoden. Under övergångperioden kan du ange och bokföra bakåtdaterade transaktioner, till exempel fakturor, så att du kan stänga den föregående perioden. Lagerstängningsdatumet måste vara en dag före övergångstartdatumet så att det blir en tydlig avgränsning mot den gamla värderingsmetoden.
-   Konverteringssteg under övergångsperioden − använd formuläret **Konverteringar av standardkostnad** när du vill skapa en konverteringspost som även innehåller en användardefinierad identifierare för en ny kostnadsredovisningsversion. Du identifierar artiklarna som måste konverteras och registrerar sedan artikelns väntande standardkostnader inom den nya kostnadsredovisningsversionen. Du utför en kontroll av de valda artiklarna för att identifiera problem som kan förhindra konverteringen, löser problemen och utför sedan en andra kontroll. När artiklarna är kontrollerade och redo ändrar du statusen för konverteringsposten till **Klar**. På det planerade konverteringsdatumet genomför du konverteringen och inkluderar eventuellt en lagerstängning. En artikels lagerrörelser under övergångperioden bokförs och värderas enligt den gamla lagermodellen. Därefter, efter konverteringen har slutförts, omvärderas lagerrörelser till standardkostnad.
-   Lagerstängning före konverteringen − lagerstängningen kan inkluderas som en del av konverteringen på det planerade konverteringsdatumet eller kan utföras som ett separat steg innan konverteringen.

När konverteringsprocessen har slutförts baseras lagermodellen för varje artiklar på standardkostnaden och artikelns standardkostnader aktiveras. Efterföljande lagertransaktioner värderas till artikelns standardkostnad. Dessutom konverterar systemet artikelns fysiska lagertransaktioner för in- och utleveranser till standardkostnader baserade på konverteringsdatumet. Systemet konverterar också artikelns ekonomiska lagerbehållning till standardkostnad och bokför differensen i värde som en lageromvärdering. Transaktioner som uppstår efter att konverteringen har värderats till artikelns standardkostnad. Du kan inte ange bakåtdaterade transaktioner före konverteringsdatumet eftersom en lagerstängning måste genomföras en dag före konverteringsdatumet. En konvertering kan endast utföras om en lagerstängning har genomförts en dag tidigare. Den här lagerstängningen kan inte annulleras.

## <a name="1-define-a-standard-cost-conversion-record-and-the-associated-costing-version"></a>1. Definiera en konverteringspost för standardkostnad och den associerade kostnadsredovisningsversionen
Använd **Konverteringar av standardkostnad**-sidan för att skapa en konverteringspost. Du kan bara skapa en ny konverteringspost om du har slutfört befintliga konverteringsposter. Tidslängden för den planerade övergångsperioden definieras av övergångsstartdatumet och det planerade konverteringsdatumet. En planerad övergångsperiod kan vara så kort som en enda dag. En planerad övergångsperiod garanterar att konverteringsprocessen har tillräcklig tid att slutföra dess samtliga steg. En lagerstängning måste genomföras på ett datum som är en dag före övergångsstartdatumet, för att se till att alla kvittningar slutförs innan konverteringsprocessen startas. För att se till att övergångsstartdatumet och lagerstängningsdatumen är korrekta kan du antingen ändra övergångsstartdatumet till en dag efter en befintlig lagerstängning, eller genomföra en lagerstängning. När du anger en konverteringspost anger du också ett användardefinierat ID för en ny kostnadsredovisningsversion som ska innehålla standardkostnaderna för konverterade artiklar. När du sparar konverteringsposten skapas kostnadsredovisningsversionen automatiskt.

## <a name="2-review-and-change-the-new-costing-version-for-the-conversion-record"></a>2. Granska och ändra den nya kostnadsredovisningsversion som skapats för konverteringsposten.
Den nya kostnadsredovisningsversionen dedikeras till konverteringsposten, vilket visas med kostnadsredovisningsversionen **Konvertering**. Den dedikerade kostnadsredovisningsversionen liknar en kostnadsredovisningsversion för standardkostnader och innehåller artikelkostnadsposter för artiklar som är associerade med konverteringsposten. Den dedikerade kostnadsredovisningsversionen för en konverteringspost har följande inställningar, som bör granskas och redigeras på de olika flikarna efter behov:

-   **Kostnadsredovisningstyp:** Detta fält ska anges för **Standardkostnad**.
-   **Version:** ID:t motsvarar den information som anges på konverteringsposten för kostnadsredovisningsversions-ID:t.
-   **Namn:** Namnet är tomt som standard. Du kan även ange ett namn.
-   **Spärra:** Detta fält ska anges för **Nej**. Du kan ange kostnadsposter i kostnadsredovisningsversionen tills du ändrar statusen för konverteringsposten till **Klar**. Statusvärdet **Klar** innebär att de valda artiklarna har kontrollerats och att kostnadsposterna inte bör få ändras.
-   **Spärraktivering:** Detta fält ska anges för **Ja**. Du kan inte aktivera en pågående kostnadspost i den dedikerade kostnadsredovisningsversionen manuellt. Aktivering sker när du genomför konverteringen.
-   **Från datum:** Det här datumet motsvarar det planerade konverteringsdatum som har angetts för konverteringsposten.
-   **Plats:** Lämna det här fältet tomt så att kostnadsposter kan anges för alla platser.
-   **Fältgruppen Tillåt pristyp:** Ange detta fält till **Ja** så att bara självkostnadsposter kan anges.
-   **Reservprincip:** Detta fält har satts till **Ingen**. Ändra reservprincipen till **Aktiv** om du behöver kostnadsinformation som har aktiverats i andra kostnadsredovisningsversioner. Du kan till exempel behöva kostnadsinformation om komponenter, kostnadskategorier och indirekta kostnader för att beräkna kostnaderna för tillverkade artiklar.
-   **Version av reservkostnadsredovisning:** Lämna det här fältet tomt.

Artikelkostnadsinformation i den dedikerade kostnadsredovisningsversionen kan bara underhållas från sidan **Konverteringar av standardkostnad**. Du kan inte använda **Inställningar för kostnadsredovisningsversion**-sidan eller **Underhåll av kostnadsredovisningsversion**-sidan för att beräkna kostnader för kostnadsredovisningsversionen under konverteringen. De här formulären kan dock användas för att underhålla den dedikerade kostnadsredovisningsversionen efter att konverteringen har genomförts.

## <a name="3-identify-the-items-to-convert-to-standard-cost"></a>3. Identifiera de artiklar som ska konverteras till standardkostnad.
Använd **Konverteringar av standardkostnad**-sidan för att identifiera de enskilda artiklar som ska konverteras till standardkostnad. Du kan lägga till flera objekt genom att använda sidan **Lägg till artiklar för standardkostnadskonvertering**. En allmän riktlinje är att du bör inkludera alla tillverkade artiklar i en enda konverteringspost för att se till att kostnaderna beräknas korrekt.

## <a name="4-enter-or-calculate-the-pending-standard-cost-for-each-item-that-is-being-converted"></a>4. Ange eller beräkna pågående standardkostnad för varje artikel som konverteras
Använd sidan **Artikelpris** för att ange pågående standardkostnader i den dedikerade kostnadsredovisningsversionen för inköpta artiklar och överföringsartiklar. Kostnadsposter är sitespecifika och de pågående kostnaderna för en artikel måste anges för varje site. Använd sidan **Artikelpris** för att beräkna pågående standardkostnader för tillverkade artiklar. Pågående kostnader för en tillverkad artikel ska beräknas för varje tillverkningsplats förutom när platsen motsvarar en överföringsplats. I detta fall bör de väntande kostnaderna anges manuellt. Vissa artiklar kan ha artikeldimensioner för färg, storlek eller konfiguration. På **Konverteringar av standardkostnad**-sidan, kryssrutan **Använd självkostnad per variant** visar standardkostnaden för varje kombination av produktdimensioner. Om den här kryssrutan är avmarkerad behöver du bara ange en pågående kostnad för artikeln.

## <a name="5-check-and-resolve-any-issues-for-the-items-that-are-being-converted"></a>5. Sök efter och korrigera alla eventuella problem för de artiklar som konverteras
Använd **Kontroller för standardkostnadskonvertering**-rapporten när du vill identifiera problem för de artiklar som konverteras. Om det inte finns några problem med en artikel ändras dess statusvärde i konverteringsposten till **Kontrollerad**. Om det finns problem med en artikel måste du korrigera problemen och sedan köra rapporten igen tills artikelns statusvärde ändras till **Kontrollerad**. Om det inte går att lösa ett artikelproblem inom rimlig tid kan du välja att ta bort artikeln från konverteringsposten och konvertera artikeln senare.

## <a name="6-change-the-status-of-the-conversion-record-to-ready"></a>6. Ändra statusvärdet för konverteringsposten till Klar.
När statusvärdet för konverteringsposten ändras till **Klar** utförs en slutgiltig kontroll innan en standardkostnadskonvertering körs. Statusen ändras till **Klar** endast om följande villkor har uppfyllts:

-   Alla artiklar i konverteringsposten har statusvärdet **Kontrollerad**.
-   En lagerstängning genomfördes på ett datum en dag före övergångsstartdatumet. För att se till att övergångsstartdatumet och lagerstängningsdatumen är korrekta kan du antingen ändra övergångsstartdatumet till en dag efter en befintlig lagerstängning, eller genomföra en lagerstängning.

## <a name="7-back-up-the-database-before-conversion"></a>7. Säkerhetskopiera databasen före konverteringen
Om du har skapat en säkerhetskopia av databasen kan du återställa den om fel uppstår under konverteringsprocessen.

## <a name="8-perform-the-conversion-when-the-conversion-record-has-a-ready-status"></a>8. Genomför konverteringsprocessen när konverteringspostens statusvärde är Klar.
För att konverteringsprocessen ska kunna genomföras måste en lagerstängning ha genomförts på ett datum en dag före det planerade konverteringsdatumet. Det här kravet ser till att bakåtdaterade transaktioner inte ska kunna anges inom övergångsperioden. Om ingen lagerstängning har genomförts får du en fråga om du vill genomföra en lagerstängning som en del av konverteringsprocessen. Konverteringsprocessen hanterar en artikel åt gången. Den börjar med de lägsta artiklarna i en produktstruktur baserat på artikelns lågnivåkod. När en artikel har konverterats korrekt, ändras dess status till **Konverterad**i konverteringsposten. Om konverteringsprocessen avbryts används statusvärdet **Kontrollerad** för artiklar som inte har konverterats korrekt. En konverteringsprocess som genomförs utan problem har följande effekter:

-   Statusvärdet för konverteringsposten ändras från **Klar** till **Slutförd** och statusvärdet för alla valda artiklar ändras från **Kontrollerad** till **Konverterad**.
-   Artikelmodellgruppen för konverterade artiklar ändras så att den motsvarar en ny grupp med en lagermodell för standardkostnad.
-   Standardkostnaderna för de konverterade artiklarna har aktiverats i den dedikerade kostnadsredovisningsversionen.
-   Kostnadstypen för kostnadsredovisningsversionen ändras från **Konvertering** till **Standardkostnad** och kostnadsredovisningsversionen fungerar nu som alla andra kostnadsredovisningsversioner för standardkostnader.

## <a name="9-validate-and-reconcile-the-inventory-values-for-the-converted-items"></a>9. Validera och stäm av lagervärdena för de konverterade artiklarna
Rapporten **Utdrag för avvikelseanalys** kan analysera omvärderingsavvikelse och rapporten **Lagervärde** kan visa lagervärde på ett visst datum.

-   Analysera alla eventuella omvärderingsavvikelser. Använd rapporten **Utdrag för avvikelseanalys** för att visa avvikelser för lageromvärdering för de konverterade artiklarna. Du kan också använda sidan **Standardkostnadstransaktioner** för att visa transaktionerna för lageromvärdering för de konverterade artiklarna som har lager.
-   Analysera lagervärdet före övergångsstartdatumet. Använd rapporten **Lagervärde** för att visa avvikelsevärden för de konverterade artiklarna. Använd ett datum som infaller en dag före övergångstartdatumet som Till-värde för rapporten.
-   Analysera lagervärdet före konverteringsdatumet. Använd rapporten **Lagervärde** för att visa avvikelsevärden för de konverterade artiklarna. Använd ett datum som infaller en dag före konverteringsdatumet som Till-värde för rapporten.
-   Analysera lagervärdet på konverteringsdatumet. Använd rapporten **Lagervärde** för att visa lagervärden för konverteringsdatumet. Både Från- och Till-datumen för rapporten måste matcha konverteringsdatumet. Rapporturvalskriterierna ska motsvara de konverterade artiklarna.
-   Analysera bakåtdaterade lagerrörelser. Använd rapporten **Lagervärde** för att visa bakåtdaterade lagerrörelser som har angetts efter konverteringen. Från- och Till-datumen för rapporten måste motsvara övergångsstartdatumet och konverteringsdatumet, minus en dag. Rapporturvalskriterierna ska motsvara de konverterade artiklarna. I rapporten visas de lagerrörelser som har gjorts till standardkostnad under övergångsperioden.


<a name="see-also"></a>Se även
--------

[Förutsättningar för en standardkostnadskonvertering](prerequisites-standard-cost-conversion.md)




