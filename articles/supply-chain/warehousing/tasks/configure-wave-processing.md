---
title: Konfigurera påfyllnadsbearbetning, exempel
description: Det här ämnet ger ett exempel på hur du ställer in villkoren som avgör vilket arbete som genereras för ett lagerställe när en påfyllnad bearbetas och om påfyllnad bearbetas manuellt eller automatiskt.
author: Mirzaab
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, InventLocationIdLookup, WHSParameters, ProdParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 39c3fecf9250ee89c22003d5dff4ea662c3042e3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7572995"
---
# <a name="configure-wave-processing-example"></a>Konfigurera påfyllnadsbearbetning, exempel

[!include [banner](../../includes/banner.md)]

Det här ämnet ger ett exempel på hur du ställer in villkoren som avgör vilket arbete som genereras för ett lagerställe när en påfyllnad bearbetas och om påfyllnad bearbetas manuellt eller automatiskt. Du anger villkor genom att ställa in påfyllnadsmallar och frågor som matchar en påfyllnad mot frisläppta rader i försäljningsorder, tillverkningsorder eller kanban-ordrar.

## <a name="enable-sample-data"></a>Aktivera exempeldata

Om du vill arbeta genom detta scenario med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard demodata har installerats. Du måste också välja den **USMF** juridiska personen innan du börjar.

## <a name="example-scenario-configure-wave-processing"></a>Exempelscenario: Konfigurera påfyllnadsbearbetning

I det här exemplet går du igenom många av de olika inställningarna som påverkar hur påfyllnad skapas, fylls i, bearbetas och frisläpps.

1. Gå till **navigeringsfönstret > moduler > lagerstyrning > inställningar > påfyllnader > påfyllnadsmallar**.
1. Välj **Ny**.
1. I fältet **Påfyllnadsmallnamn**, skriv ett värde. När du ställer in en påfyllnadsmall, anger du sekvensen i vilken mallar ska matchas för att frisläppa rader på försäljningsorder, tillverkningsorder eller kanban. När en rad frisläppts till lagerställe eller till produktion, används den första påfyllnadsmallen som den uppfyller villkoren för. Vi rekommenderar därför att du sätter mallar med det mest specifika kriteriet längst upp i listan. Ju bredare villkoren är, desto mer rimligt är det att en rad ska uppfylla kriterierna, vilket kan leda till att rader tilldelas fel påfyllnad.  
1. Skriv ett värde i fältet **Beskrivning av påfyllnadsmall**.
1. i fältet **Plats** anger eller väljer du ett värde. Om du använder USMF kan du välja site 2.  
1. Ange eller välj ett värde i fältet **Lagerställe**. Om du använder USMF kan du välja lager 24.  
1. Ange fältet **Automatisera skapande av påfyllnad** till **Ja**. Välj det här alternativet om du vill skapa en påfyllnad automatiskt när en försäljningsorder, produktionsorder eller kanban frisläpps till lagerstället.  
1. Ange alternativet **Bearbeta påfyllnaden vid släpp till lager** till **Ja**. Välj det här alternativet om du vill bearbeta påfyllnaden automatiskt och skapa arbete när en rad frisläpps till lagerstället.  
1. Ange alternativet **Automatisera släpp av påfyllnad** till **Ja**. Välj det här alternativet om du vill att påfyllnaden ska frisläppas automatiskt. Plockningsarbetet skapas och görs tillgängligt på mobila enheter.  
1. Ange alternativet **Automatisera släpp av påfyllnad** till **Ja**. Rader tilldelas påfyllnader baserat på frågefiltret för påfyllnadsmallen.  
1. Ange alternativet **Bearbeta påfyllnad automatiskt vid tröskel** till **Ja**. Välj det här alternativet om du vill bearbeta påfyllnaden automatiskt när dess värden når trösklarna för vikt, leverans och rader som anges i fältgruppen **Påfyllnadströsklar**. Detta alternativ är endast tillgängligt om **Leverans** har valts i fältet **Påfyllnadsmalltyp**.  
1. Ange alternativet **Automatisera frisläppning av lagerpåfyllnadsarbete** till **Ja**. Välj det här alternativet om du vill skapa efterfrågebaserat återanskaffningsarbete och frisläppa det automatiskt. Du måste lägga till påfyllnadsmetoden i påfyllnadsmallen och skapa en återanskaffningsmall av typen **Påfyllnadsefterfrågan**.  
1. Använd inställningar i gruppen **Standardvärden** om du vill tilldela påfyllnadsattribut. Vågattribut fungerar som filter, för att begränsa vilken typ av artiklar som kan använda vågen. Du kan till exempel ange en artikelgrupp.  
1. Expandera avsnittet **Metoder** och ställ in de åtgärder som ska vidtas av påfyllnadsmallen. Påfyllnadsmallmetoder låter dig kontrollera sekvensen av aktiviteter som varje påfyllnad genomgår, när den har bearbetats. Du kanske till exempel har en metod för lagerpåfyllnad. När du lägger till en metod, anges den automatiskt på rätt plats i sekvensen för steg. Om du har angett alternativet **Automatisera frisläppning av lagerpåfyllnadsarbete** till **Ja**, måste du lägga till påfyllningsmetoden här.  
1. Välj **Spara**.
1. Stäng sidan.
1. Gå till **Lagerstyrning > Inställningar > Parametrar för lagerstyrning**.
1. Expandera **Visa avsnittet Påfyllnadsbearbetning**.
1. Ange eller välj ett värde i fältet **Batchgrupp för påfyllnadsbearbetning**.
1. Ange alternativet **Behandla påfyllnader i batch** till **Ja**.
1. Ange ett nummer fältet **Vänta på lås (ms)**. Ange tiden, i millisekunder, som ett allokeringssteg ska vänta på en systemresurs som har låsts av ett annat allokeringssteg. När denna tid överskrids, bearbetas påfyllnaden inte, och ett meddelande visas.  
1. Välj **Spara**.
1. Stäng sidan.
1. Gå till **Navigeringsfönster > Moduler > Produktionskontroll > Inställningar > Produktionskontrollparametrar**.
1. I fältet **Släpp till lagerställe**, markera ett alternativ.

    För försäljnings - och kanbanorder måste lager reserveras om ordern har frisläppts till lagerstället. Annars kan artiklarna eller allokeringsraderna inte bearbetas i en våg. För tillverkningsorder har du även alternativet att välja **Tillåt viss reservation**. Detta är till exempel praktiskt om du har material som behövs för att starta en produktion, och kan vänta tills ytterligare material är tillgängligt för att avsluta processen. Om du markerar det här alternativet måste du upprepa frisläppningen till lagerprocess när ytterligare material blir tillgängliga.
1. Stäng sidan.

## <a name="additional-resources"></a>Ytterligare resurser

- [Skapa och bearbeta påfyllnad](../wave-processing.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
