---
title: Ställ in och generera åldersfördelningsinformation för kundreskontra
description: I den här handboken får du hjälp med att ställa in en åldersfördelningsperioddefinition, ålderkundsaldon och vysaldon i ålderssaldolistan och samlingssidan.
author: mikefalkner
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2468beea898de6367c655b54d89c1faab1e4435506bd21019c970af32d215729
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713292"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a>Ställ in och generera åldersfördelningsinformation för kundreskontra

[!include [banner](../../includes/banner.md)]

I den här handboken får du hjälp med att ställa in en åldersfördelningsperioddefinition, ålderkundsaldon och vysaldon i ålderssaldolistan och samlingssidan. I den här registreringen används demonstrationsföretaget USMF.


## <a name="create-an-aging-period-definition"></a>Skapa en åldersfördelningsperioddefinition
1. Gå till **Navigeringsfönster > Moduler > Kredit och inkasso > Inställningar > Definitioner för åldersfördelningsperiod**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **åldersfördelningsperiod**.
4. I fältet **Beskrivning** anger du ett värde.
5. Infoga en ny åldersfördelningsperiod genom att klicka på **Lägg till nedan**.
6. Ange beskrivningen som ska visas på åldersrapporter i fältet **Period**.
7. Välj ett tal i fältet **Enhet**.
8. Markera ett alternativ i fältet **Intervall**. Redovisningsperioden matchar perioden mot din redovisningskalender. Dag, vecka, månad, kvartal och år definierar storleken på intervallet efter datumtyp. Obegränsat väljer Alla transaktioner, före eller efter den föregående perioden, beroende på om det är den första eller sista perioden.  
9. Markera ett alternativ i fältet **Åldersfördelningsindikator**.
10. Välj perioden högst upp i rutnätet. Uppdatera beskrivningen för att beskriva den äldsta perioden i åldersfördelningsperioddefinitionen
11. Ange den nya beskrivningen som ska visas på åldersfördelningsperioden i fältet **period**.
12. Stäng sidan.

## <a name="age-the-balances"></a>Åldersfördela saldon
1. Gå till **Kredit och inkasso > Periodiska uppgifter > Åldersfördelade kundsaldon**.
2. Välj **åldersfördelningsperioddefinitionen** som du skapade i fältet åldersfördelningsperioddefinition.
    + Du kan ha en ögonblicksbild aktiv för varje åldersfördelningsperioddefinition.  
    + Alla kunder bearbetas som standard. Du kan använda det här valet för att beräkna en enskild samlingspool av kunder.  
    + Välj det datum från den transaktion som du ska använda för åldersfördelningen.  
    + Välj ”från och med”-datum för ålder. Standardinställningen är Idag, men om du ändrar detta fält till det valda datumet, ska du kunna plocka datum som du vill ha. Använd dagens datum för batchbearbetning.  
3. Expandera intervallet **företag**. Du kan välja företaget som ska inkluderas i ögonblicksbilden. Som standard är det aktuella företaget valt.
4. Börja bearbeta ögonblicksbilden genom att klicka på **OK**. Den kan dröja en tid, så vänta tills skjutreglaget försvinner och kontrollera meddelandecenter om det finns ett meddelande.

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a>Visa saldo på åldersfördelningssaldolistan och på samlingssidan
1. Gå till **Kredit och inkasso > Inkasso > Åldersfördelade saldon**. Listsidan innehåller saldon för kunden. Åldersfördelningsikonen visas åldersfördelningsperioden för den äldsta transaktionen.  
2. Välj en kund med ett saldo.
3. Expandera faktarutan **åldersfördelning** om du vill visa åldersfördelningssaldon. Åldersfördelningsperioddefinitionen för faktarutan hämtas från standardåldersfördelningsperioddefinitionen som anges i parametrarna. Du kan ändra detta med menyn Inkasso.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]