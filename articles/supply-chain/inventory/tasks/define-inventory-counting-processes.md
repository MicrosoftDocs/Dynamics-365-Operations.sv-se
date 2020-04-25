---
title: Definiera lagerberäkningsprocesser
description: I det här avsnittet beskrivs konfigurationen av grundläggande lagerinventeringsprocesser genom att skapa en inventeringsgrupp och en inventeringsjournal.
author: MarkusFogelberg
manager: tfehr
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountGroup, InventJournalName, InventParameters, EcoResProductDetailsExtended, InventItemLocation, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9df5db0e71f550e82820e15b1597d9e287071f83
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214008"
---
# <a name="define-inventory-counting-processes"></a>Definiera lagerberäkningsprocesser

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs konfigurationen av grundläggande lagerinventeringsprocesser genom att skapa en inventeringsgrupp och en inventeringsjournal. Det visar också om hur du aktiverar du vill beräkna principer för ett lagerställe och artikelnivå. Dessa uppgifter utförs vanligtvis av en lagerchef. Det är en förutsättning som har några befintliga frisläppning produkter och lagerställen. Om du använder ett demonstrationsdataföretag kan du köra denna procedur i USMF-företaget med en valfri lagerförd artikel.


## <a name="create-a-counting-group"></a>Skapa en inventeringsgrupp
1. I navigeringsfönstret, gå till **Moduler > Lagerhantering > Inställningar > Lager > Inventeringsgrupper**.
2. Välj **Ny**.
3. Ange ett värde i fältet **Inventeringsgrupp** för den nya raden.
4. Skriv ett värde i fältet **Namn**.
5. Välj ett alternativ i fältet **Inventeringskod**.

    - **Manuell** – inkluderar rader varje gång du kör jobbet. Det innebär att du bestämmer inventeringsintervallet för inventeringsgruppen.  
    - **Period** – inkluderar rader för perioden i inventeringsjournalen när periodintervallet har upphört.  
    - **Noll i lager** – Om lagerbehållningen når noll (0), genereras rader i inventeringsjournalen när jobbet körs. Om lagerbehållningen når 0 efter en inventering, genereras rader nästa gång du startar inventeringen.  
    - **Minimum** – Infogar rader i inventeringsjournalen om lagerbehållningen är lika med eller mindre än den angivna minsta gränsen.  
    - Valfritt: Om du har angett **Period** i fältet **Inventeringskod** måste du skriva in intervallen för perioden i fältet **Inventeringsperiod**. Enheten för intervall är dagar.  
    - När du kör jobbet för att skapa nya rader i inventeringsjournalen, skapas nya rader i intervallet som anges i det här fältet, oavsett hur ofta du kör det samma jobb. Om till exempel att **Inventeringsperiod** ställs in på 7, och journalrader genererades senast för en inventering den 1 januari, om ett annat jobb startades 5 januari, har sju dagar inte gått och att inga rader skapas i journalen för det periodintervallet. Om du startar jobbet igen den 8 januari genereras rader för perioden i inventeringsjournalen eftersom 7 dagar har gått.  

6. Välj **Spara**.

## <a name="create-a-counting-journal-name"></a>Skapa ett lagerinventeringsjournal
1. I navigeringsfönstret, gå till **Moduler > Lagerhantering > Inställningar > Journalnamn > Lager**.
2. Välj **Ny**.
3. Skriv ett värde i fältet **Namn**.
4. I fältet **Beskrivning** anger du ett värde.
5. I fältet **Journaltyp**, välj **Inventering**. Valfritt: Du kan välja olika verifikationsserie-ID, om du vill generera en specifik nummerserie för verifikations-ID:n, när du skapar inventeringsjournaler. Verifikationsserier skapas på sidan **Nummerserier**.  
6. Välj ett alternativ i fältet **Detaljnivå**.  

    - Detta är detaljnivån som används, när journalen bokförs.  
    - Valfritt: Du kan visa eller ändra värdet i fältet Reservation. Detta är metoden för att reservera artiklarna under inventering.   
    - **Manuell** – artiklarna reserveras manuellt i reservationsformuläret.  
    - **Automatisk** – Orderkvantiteten har reserverats i den tillgängliga lagerbehållningen för artikeln.   
    - **Nedbrytning** – Reservationen är en del av huvudplaneringen för transaktionen.  

7. Välj **Spara**.

## <a name="set-standard-counting-journal-name"></a>Ange standardinventeringsjournalnamn
1. I navigeringsfönstret, gå till **Moduler > Lagerhantering > Inställningar > Parametrar för hantering av lager och lagerstyrning**.
2. Välj fliken **Journaler**.
3. Välj den journal som du skapat tidigare i fältet **Inventering** på den nedrullningsbara menyn. Journalen används sedan som standardjournalnamn för lagerjournaler av typen **Inventering**.  
4. Välj fliken **Allmänt**. Valfritt: Välj det här alternativet för att låsa en artikel under inventeringsprocessen för att hindra uppdateringar för följesedlar, plocklistor eller registreringar av plocklista.  

## <a name="set-the-counting-policy-for-an-item"></a>Ange inventeringsprincip för en artikel
1. I navigeringsfönstret, gå till **Moduler > Produktinformationshantering > Produkter > Frisläppta produkter**.
2. I listan väljer du länken för artikelnumret för produkten som du vill ange för att ställa in inventeringspolicyer på. Du måste välja en artikel som har spårats i lagret. En produkt som inte finns i lager räknas inte. Om du använder USMF-deodata kan du välja artikel A0001.  
3. Välj **Redigera**.
4. Växla expansionen av avsnittet **Hantera lager**.
5. Välj den inventeringsgrupp som du skapat tidigare i fältet **Inventeringsgrupp** på den nedrullningsbara menyn. Den produkt ska inkluderas när lagerinventeringsjournalrader nu, skapas med hjälp av denna beräkningsgrupp.  
6. Välj **Spara**.

## <a name="set-the-counting-policy-for-an-item-in-a-specific-warehouse"></a>Ange inventeringsprincip för en artikel i ett specifikt lagerställe
1. I åtgärdsfönstret klicka på **Hantera inventering**.
2. Välj **Lagerställeartiklar**.
3. Välj **Ny**.
4. Välj det lagerställe som du vill ställa in särskilda inventeringspolicyer för på den nedrullningsbara menyn i fältet **Lagerställe**.
5. Välj en inventeringsgrupp på den nedrullningsbara menyn i fältet **Inventeringsgrupp**. Du kan välja en viss inventeringsgrupp som ska användas för artikeln i den angivna lagerstället, som du har valt. När du vill beräkna är den utförs i lagerstället, kommer denna av policy åsidosätta den allmänna principen för av artikeln.  
6. Välj **Spara**.

