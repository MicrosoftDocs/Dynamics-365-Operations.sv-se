---
title: Ändra eller tilldela om en redovisningskalender
description: Den här artikeln förklarar hur du ändrar kalendern som för närvarande är tilldelad en redovisning och hur du tilldelar en ny kalender till redovisningen.
author: kweekley
ms.date: 05/07/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-07
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 751954e0dc5f682b99ab7fe349cd505dc9da7858
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848618"
---
# <a name="change-or-reassign-a-ledger-calendar"></a>Ändra eller tilldela om en redovisningskalender

[!include [banner](../includes/banner.md)]

Den här artikeln förklarar hur du ändrar kalendern som för närvarande är tilldelad en redovisning och hur du tilldelar en ny kalender till redovisningen.

## <a name="issue"></a>Problem

Ibland måste företag antingen ändra den befintliga kalendern som har tilldelats en redovisning eller tilldela en ny kalender.

## <a name="resolution"></a>Lösning

Det finns två scenarier för att ändra eller tilldela om en redovisningskalender. Det första scenariot ändrar en befintlig kalender som redan är tilldelad redovisningen. Det andra scenariot skapar en ny kalender och tilldelar den till redovisningen. Båda ändringarna kan utföras när som helst, även efter att transaktioner har bokförts i redovisningen.

### <a name="change-an-existing-fiscal-calendar"></a>Ändra en befintlig räkenskapskalender

Ändra en befintlig kalender som är tilldelad redovisningen genom att gå till **Redovisning \> Redovisningsinställningar \> Redovisning** och välj länken till räkenskapskalendern för att öppna sidan **Redovisningskalendrar**.

Det finns gränser för ändringarna som går att utföra i en kalender. Det går till exempel att ändra start- och slutdatum för *perioder* under ett år, men det går inte att ändra start- och slutdatum för ett *år* i kalendern.

Välj en lämplig kalender och ett lämpligt år om du vill ändra perioder under ett år. Använd först knappen **Ta bort period** för att ta bort vissa eller alla befintliga driftsperioder. Det går att ta bort alla driftsperioder utom den första. Använd sedan knappen **Dela period** för att dela upp återstående period eller perioder i nya perioder genom att ange ett lämpligt startdatum för nästa period.

När du ändrar perioderna i en kalender måste du köra processen **Beräkna om redovisningsperioder** i varje juridisk person (företag) som kalendern är tilldelad till. Även om inget varningsmeddelande påminner dig om att slutföra det här steget krävs omberäkningsprocessen för att uppdatera perioden som tilldelas varje bokförd transaktion i redovisningen. Kör omberäkningen genom att välja **Beräkna om redovisningsperioder** på sidan **Redovisningsinställningar** i varje företag.

Om omberäkningen inte körs är det möjligt att transaktionssaldon i en råbalans eller i bokslut felaktigt inkluderas i perioder. I det här fallet kan du korrigera saldon när som helst genom att köra omberäkningen.

### <a name="assign-a-new-fiscal-calendar"></a>Tilldela en ny räkenskapskalender

Tilldela en ny räkenskapskalender genom att öppna **Redovisning \> Redovisningsinställningar \> Redovisning** och välja **Redigera** för att ställa sidan **Redovisning** i redigeringsläge. Välj sedan en ny räkenskapskalender i fältet **Räkenskapskalender**.

När du har ändrat räkenskapskalendern för en redovisning måste du köra **Beräkna om redovisningsperioder**. När du tilldelar en ny räkenskapskalender till en redovisning påminner ett meddelande dig om att slutföra det här steget. Meddelande kan får omberäkningsprocessen att framstå som valfri, trots att den inte är det. Den krävs för att uppdatera perioden som tilldelas varje bokförd transaktion i redovisningen. Kör omberäkningen genom att välja **Beräkna om redovisningsperioder** på sidan **Redovisningsinställningar**.

Om omberäkningen inte körs är det möjligt att transaktionssaldon i en råbalans eller i bokslut felaktigt inkluderas i perioder. I det här fallet kan du korrigera saldon när som helst genom att köra omberäkningen.
