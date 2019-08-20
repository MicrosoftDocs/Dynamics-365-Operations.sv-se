---
title: Definiera lagerberäkningsprocesser
description: I den här proceduren om du vill gå du hjälp med konfigurationen för ifyllda processer för det grundläggande lager, genom att skapa en beräkningsgrupp och en inventeringsjournal.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountGroup, InventJournalName, InventParameters, EcoResProductDetailsExtended, InventItemLocation, InventLocationIdLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4128023ba9fded23b994579f0ab54a75f72fc15a
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845472"
---
# <a name="define-inventory-counting-processes"></a>Definiera lagerberäkningsprocesser

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren om du vill gå du hjälp med konfigurationen för ifyllda processer för det grundläggande lager, genom att skapa en beräkningsgrupp och en inventeringsjournal. Det visar också om hur du aktiverar du vill beräkna principer för ett lagerställe och artikelnivå. Dessa uppgifter utförs vanligtvis av en lagerchef. Det är en förutsättning som har några befintliga frisläppning produkter och lagerställen. Om du använder ett demonstrationsdataföretag kan du köra denna procedur i USMF-företaget med en valfri lagerförd artikel.


## <a name="create-a-counting-group"></a>Skapa en inventeringsgrupp
1. Gå till Lagerhantering > Inställningar > Lagerindelning > Inventeringsgrupper.
2. Klicka på Ny.
3. Skriv ett värde i fältet Inventeringsgrupp.
4. Skriv ett värde i fältet Namn.
5. I fältet Inventeringskod, välj ett alternativ.
    * Manuell – Inkluderar rader varje gång du kör jobbet. Det innebär att du bestämmer inventeringsintervallet för inventeringsgruppen.  Period – Inkluderar rader för perioden i inventeringsjournalen när periodintervallet har gått ut.   Noll i lager – Om lagerbehållningen når noll (0), genereras rader i inventeringsjournalen när jobbet körs. Om lagerbehållningen når 0 efter en inventering, genereras rader nästa gång du startar inventeringen.   Minimum – Infogar rader i inventeringsjournalen om lagerbehållningen är lika med eller mindre än den angivna minsta gränsen.  
    * Valfritt: Om du har angett Period i inventeringskodsfältet måste du skriva in intervallen för perioden i inventeringsperiodfältet. Enheten för intervall är dagar.  
    * När du kör jobbet för att skapa nya rader i inventeringsjournalen, skapas nya rader i intervallet som anges i det här fältet, oavsett hur ofta du kör det samma jobb. Om till exempel att beräkna period ställs in på 7, och journalrader genererades senast för en strukturlista i januari, 1, om ett annat jobb som fanns på 5 månader, har sju dagar och inte gått, så att inga rader skapas i journalen för det periodintervallet. Om du startar jobbet igen den 8 januari genereras rader för perioden i inventeringsjournalen eftersom 7 dagar har gått.  
6. Klicka på Spara.

## <a name="create-a-counting-journal-name"></a>Skapa ett lagerinventeringsjournal
1. Gå till Lagerhantering > Inställningar > Journalnamn > Lager.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Ange ett värde i fältet Beskrivning.
5. Välj Inventering i fältet Journaltyp.
    * Valfritt: Du kan välja olika verifikationsserie-ID, om du vill generera en specifik nummerserie för verifikations-ID:n, när du skapar inventeringsjournaler. Verifikationsserier skapas på sidan Nummerserier.  
6. Markera ett alternativ i fältet Detaljnivå.
    * Detta är detaljnivån som används, när journalen bokförs.  
    * Valfritt: Du kan visa eller ändra värdet i fältet Reservation. Detta är metoden för att reservera artiklarna under inventering.   
    * Manuell – artiklarna reserveras manuellt i reservationformuläret.   Automatisk –Orderkvantiteten har reserverats i den tillgängliga lagerbehållningen för artikeln.   Nedbrytning – Reservationen är en del av huvudplaneringen för transaktionen.  
7. Klicka på Spara.

## <a name="set-standard-counting-journal-name"></a>Ange standardinventeringsjournalnamn
1. Gå till Lagerhantering > Inställningar > Parametrar för hantering av lager och lagerstyrning.
2. Klicka på fliken Journaler.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Inventering.
4. Välj den journaltyp som du skapat tidigare.
    * Journalen används sedan som standardjournalnamn för lagerjournaler av typen Inventering.  
5. Klicka på fliken Allmänt.
    * Valfritt: Välj det här alternativet för att låsa en artikel under räkningsprocessen för att hindra uppdateringar vid följesedlar, plocklistor eller registreringar av plocklista.  

## <a name="set-the-counting-policy-for-an-item"></a>Ange inventeringsprincip för en artikel
1. Gå till Produktinformationshantering > Produkter > Frisläppta produkter.
2. Klicka på länken för artikelnumret av produkten att du vill ange att beräkna på policyer i listan.
    * Observera att du behöver välja en artikel som har spårats i lagret. En produkt som inte finns i lager räknas inte. Om du använder USMF-deodata kan du välja artikel A0001.  
3. Klicka på Redigera.
4. Växla utökningen av avsnittet Hantera lager.
5. I fältet Inventeringsgrupp, öppna sökningen genom att klicka på den nedrullningsbara knappen.
6. Klicka på den beräkningsgrupp som du skapade tidigare i listan.
    * Den produkt ska inkluderas när lagerinventeringsjournalrader nu, skapas med hjälp av denna beräkningsgrupp.  
7. Klicka på Spara.

## <a name="set-the-counting-policy-for-an-item-in-a-specific-warehouse"></a>Ange inventeringsprincip för en artikel i ett specifikt lagerställe
1. Klicka på Hantera inventering i åtgärdsfönstret.
2. Klicka på Lagerställeartiklar.
3. Klicka på Ny.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.
5. Välj det lagerställe som du vill ställa in specifika av principer för i listan.
6. I fältet Inventeringsgrupp, öppna sökningen genom att klicka på den nedrullningsbara knappen.
7. Välj inventeringsgrupp i listan.
    * Här kan du välja en viss beräkningsgrupp som ska användas för artikeln i den angivna lagerstället, som du har valt. När du vill beräkna är den utförs i lagerstället, kommer denna av policy åsidosätta den allmänna principen för av artikeln.  
8. Klicka på Spara.

