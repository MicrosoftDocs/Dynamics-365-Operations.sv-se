---
title: Definiera resurssnåla schemagrupper
description: Resurssnåla schemagrupper definieras för att kunna gruppera och skilja grupper åt i kanban-planering.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanScheduleGroup, GanttColorTableLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4187381b838825b21a354eeecdf48693d919975b07a881ba32d234135694ad06
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754594"
---
# <a name="define-lean-schedule-groups"></a>Definiera resurssnåla schemagrupper

[!include [banner](../../includes/banner.md)]

Resurssnåla schemagrupper definieras för att kunna gruppera och skilja grupper åt i kanban-planering. Grupperingen kan göras som en allmän association per företag eller specifik för en arbetsgrupp. Varje grupp har en färgkod för visuell indikation på kanban-planeringssidan. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="define-lean-scheduling-group"></a>Definiera resurssnål schemagrupp
1. Gå till Produktinformationshantering > Lean manufacturing > Resurssnåla schemagrupper.
2. Klicka på Ny.
3. Skriv ett värde i fältet Schemagrupp.
    * En schemagrupp kan definieras som global grupp eller specifik för en arbetsgrupp. I detta enkla exempel definierar vi en global grupp, och arbetsgruppen hålls tom. Inställningarna för den här gruppen gäller alla arbetsgrupper som inte har specifika schemagrupper.  
4. Välj en färg från färgvalet.
    * Färgerna används för att markera jobben på kanban-schemalistsidan eller kanban-processtavlan.  
5. Markera vald rad i listan.
6. Klicka på länken på den valda raden i listan.

## <a name="associate-product"></a>Associera produkt
1. Koppla en specifik produkt
    * Det går att associera produkter i resurssnåla schemagrupper på två sätt: antingen som en specifik produkt (artikelrelationtyp = artikel) eller som en del av en artikelallokeringsnyckel (artikelrelationtyp = grupp).    
2. Välj Artikel i fältet Artikelrelationstyp.
3. Skriv ett värde i fältet Artikelnummer.
4. Ange ett värde i fältet Genomflödestakt.
    * Standardgenomflödestakten är 1, vilket innebär att de relaterade produkterna förbrukar exakt den kapacitet som anges i processaktiviteterna i produktionsflödet. Genomflödestakt > 1 definierar en högre resursförbrukning och genomflödestakt > 1 en lägre förbrukning. Takten används i kostnadsberäkningen och i beräkningen av kanban-jobbförbrukningen.  

## <a name="associate-item-allocation-key"></a>Associera artikelallokeringsnyckel
1. Associera en artikelallokeringsnyckel
    * Lägg till en association i en artikelallokeringsnyckel genom att använda artikelrelationtypgruppen.   Observera att en artikelallokeringsnyckel för prognoser måste vara definierad i dina data för den här processen.  
2. Välj Grupp i fältet Artikelrelationstyp.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelallokeringsnyckel.
4. Klicka på länken på den valda raden i listan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]