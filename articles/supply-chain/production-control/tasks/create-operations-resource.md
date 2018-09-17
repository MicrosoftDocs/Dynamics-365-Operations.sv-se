--- 
title: Skapa en verksamhetsresurs
description: "En verksamhetsresurs utför aktiviteter för ett projekt eller en produktionsprocess."
author: sorenva
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WrkCtrTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e05eb5df2d29e90ed24fb13ed16543ad470dfe6b
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-an-operations-resource"></a>Skapa en verksamhetsresurs

[!include [task guide banner](../../includes/task-guide-banner.md)]

En verksamhetsresurs utför aktiviteter för ett projekt eller en produktionsprocess. Proceduren visar hur du definierar en verksamhetsresurs. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller använda dina egna data.

1. Gå till Resurser.
2. Klicka på Ny.
3. Ange ett värde i fältet Resurs.
4. Ange ett värde i fältet Beskrivning.

## <a name="define-capacity-and-consumption-parameters"></a>Definiera kapacitet och förbrukningparametrar
1. Expandera avsnittet Operation.
2. Ange ett nummer i fältet Kassationsprocent.
3. I fältet Inställningskategori, ange eller välj ett värde.
    * Ange kostnadskategorin som definierar hur du ska beräkna kostnaden för inställningstid.  
4. I fältet Kategori för körtid, ange eller välj ett värde.
    * Ange kostnadskategorin som definierar hur du ska beräkna kostnaden för körtid.  
5. Ange eller välj ett värde i fältet Kvantitetskategori.
    * Ange kostnadskategorin som definierar hur du ska beräkna resurskostnaden baserat på utleveranskvantitet.  
6. Markera ett alternativ i fältet Kapacitetsenhet.
    * Ange enheten för uttryck av kapacitet för verksamhetsresursen.  
7. Välj ett tal i fältet Kapacitet.
8. Ange ett nummer i fältet Effektivitet i procent.
    * Ange effektiviteten som du förväntar dig från verksamhetsresursen. Effektivitetsprocentsatsen justerar genomflödet från verksamhetsresursen och påverkar den tid som reserverats för resursen.  
9. Ange ett tal i fältet Grovplaneringsprocent.
    * Ange högsta procentandelen av kapaciteten för verksamhetsresursen som du vill använda i grovplaneringen.  
10. Välj Ja i fältet Begränsad kapacitet.
    * Ange det här alternativet som Ja om verksamhetsresursen ska planeras utifrån verklig kapacitet som är tillgänglig och om befintliga kapacitetsreservationer ska inkluderas. Om det här alternativet är Nej antas verksamhetsresursen ha obegränsad kapacitet och resursen kan överbokas.  
11. Välj Ja i fältet Flaskhalsresurs.

## <a name="define-working-times"></a>Definiera arbetstider
1. Expandera avsnittet Kalendrar.
2. Klicka på Lägg till.
3. Ange eller välj ett värde i fältet Kalender.
    * Ange arbetstidskalendrar som definierar kapaciteten (i timmar) för resursen.  
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.

## <a name="define-resource-capabilities"></a>Definiera resurskunskaper
1. Expandera avsnittet Funktioner.
2. Klicka på Lägg till.
    * En kapacitet är möjligheten hos en verksamhetsresurs att utföra en viss aktivitet. Planeringsmotorn allokerar resurser genom att matcha resurskrav för varje aktivitet mot kapaciteter hos de tillgängliga verksamhetsresurserna.  
3. Ange eller välj ett värde i fältet Funktion.
4. Välj ett tal i fältet Nivå.
    * Ange kompetensnivån som används av resursen för att bearbeta kapaciteten.  
5. Välj ett tal i fältet Prioritet.
    * Ange prioriteten för verksamhetsresursen med avseende på kapaciteten. När du planerar med prioritet väljs verksamhetsresursen med högst prioritet (lägst numeriskt värde) först.  

## <a name="assign-resource-to-resource-group"></a>Tilldela resurs till resursgrupp
1. Expandera avsnittet Resursgrupper.
2. Klicka på Lägg till.
    * Resursgruppen definierar plats, produktionsenhet och lagerställeskontext för verksamhetsresurser. Verksamhetsresursen kan bara planeras när den har tilldelats till en resursgrupp och endast på den plats där resursgruppen finns.  
3. I fältet Resursgrupp, ange eller välj ett värde.
4. Ange eller välj ett värde i fältet Plats för inleverans.
    * Ange lagerställesplatsen från vilken verksamhetsresursen förbrukar material.  


