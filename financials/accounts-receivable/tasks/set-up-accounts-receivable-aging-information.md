--- 
title: "Ställ in och generera åldersfördelningsinformation för kundreskontra"
description: "I den här handboken får du hjälp med att ställa in en åldersfördelningsperioddefinition, ålderkundsaldon och vysaldon i ålderssaldolistan och samlingssidan."
author: mikefalkner
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ed23bcfed4e256ecc16264a181161c7119cd9bb3
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a>Ställ in och generera åldersfördelningsinformation för kundreskontra

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här handboken får du hjälp med att ställa in en åldersfördelningsperioddefinition, ålderkundsaldon och vysaldon i ålderssaldolistan och samlingssidan. I den här registreringen används demonstrationsföretaget USMF.


## <a name="create-an-aging-period-definition"></a>Skapa en åldersfördelningsperioddefinition
1. Gå till Kredit och inkasso > Inställningar > Definitioner för åldersfördelningsperiod.
2. Klicka på Ny.
3. Skriv ett värde i åldersfördelningsperioddefinitionsfältet.
4. Skriv ett värde i fältet Beskrivning.
5. Infoga en ny åldersfördelningsperiod genom att klicka på Lägg till nedan.
6. Ange beskrivningen som ska visas på åldersrapporter i periodfältet.
7. Välj ett tal i fältet Enhet.
8. Markera ett alternativ i fältet Intervall.
    * Redovisningsperioden matchar perioden mot din redovisningskalender. Dag, vecka, månad, kvartal och år definierar storleken på intervallet efter datumtyp. Obegränsat väljer Alla transaktioner, före eller efter den föregående perioden, beroende på om det är den första eller sista perioden.  
9. Markera ett alternativ i fältet Åldersfördelningsindikator.
10. Välj perioden högst upp i rutnätet. Uppdatera beskrivningen för att beskriva den äldsta perioden i åldersfördelningsperioddefinitionen
11. Ange den nya beskrivningen som ska visas på åldersfördelningsperioden i periodfältet.
12. Stäng sidan.

## <a name="age-the-balances"></a>Åldersfördela saldon
1. Gå till Kredit och inkasso > Periodiska uppgifter > Åldersfördelade kundsaldon.
2. Välj åldersfördelningsperioddefinitionen som du skapade i åldersfördelningsperioddefinitionfältet.
    * Du kan ha en ögonblicksbild aktiv för varje åldersfördelningsperioddefinition.  
    * Alla kunder bearbetas som standard. Du kan använda det här valet för att beräkna en enskild samlingspool av kunder.  
    * Välj det datum från den transaktion som du ska använda för åldersfördelningen.  
    * Välj ”från och med”-datum för ålder. Standardinställningen är Idag, men om du ändrar detta fält till det valda datumet, ska du kunna plocka datum som du vill ha. Använd dagens datum för batchbearbetning.  
3. Expandera företagsintervallet. Du kan välja företaget som ska inkluderas i ögonblicksbilden. Som standard är det aktuella företaget valt.
4. Börja bearbeta ögonblicksbilden genom att klicka på OK. Den kan dröja en tid, så vänta tills skjutreglaget försvinner och kontrollera meddelandecenter om det finns ett meddelande.

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a>Visa saldo på åldersfördelningssaldolistan och på samlingssidan
1. Gå till Kredit och inkasso > Inkasso > Åldersfördelade saldon.
    * Listsidan innehåller saldon för kunden. Åldersfördelningsikonen visas åldersfördelningsperioden för den äldsta transaktionen.  
2. Välj en kund med ett saldo.
3. Expandera åldersfördelningsfaktarutan om du vill visa åldersfördelningssaldon.
    * Åldersfördelningsperioddefinitionen för faktarutan hämtas från standardåldersfördelningsperioddefinitionen som anges i parametrarna. Du kan ändra detta med menyn Inkasso.  

