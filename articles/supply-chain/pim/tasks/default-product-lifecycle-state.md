---
title: Skapa ett standardproduktlivscykeltillstånd
description: Den här proceduren visar hur du skapar produktlivscykelns standardtillstånd och hur du kopplar standardtillståndet till frisläppta produkter.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6e7e637157ee06a3d07a1a9c5da71295eb75b424
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564188"
---
# <a name="create-a-default-product-lifecycle-state"></a>Skapa ett standardproduktlivscykeltillstånd

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du skapar produktlivscykelns standardtillstånd och hur du kopplar standardtillståndet till frisläppta produkter.


## <a name="create-a-default-lifecycle-state"></a>Skapa ett standardlivscykeltillstånd
1. Gå till Produktinformationshantering > Inställningar > produktlivscykeltillstånd.
2. Klicka på Ny.
3. Ange ett värde i fältet Tillstånd.
4. Välj Ja i standard när de frisläpps till fältet juridisk person.
5. Ange ett värde i fältet Beskrivning.
6. Välj Nej i fältet Är aktiv för planering.

> [!NOTE]
> Om en ny frisläppt produkt inte ska ingå i Huvudplanering väljer du Nej. Om den ska tas med i huvudplaneringen lämna kontrollen till standardvärdet Ja.  

## <a name="create-a-new-released-product"></a>Skapa en ny frisläppt produkt
1. Stäng sidan.
2. Gå till Produktinformationshantering > Produkter > Frisläppta produkter.
3. Klicka på Ny.
4. Skriv ett värde i fältet Produktnummer.
5. Skriv ett värde i fältet Produktnamn.
6. Ange ett värde i fältet Söknamn.
7. Ange eller välj ett värde i fältet Artikelmodellgrupp.
8. Ange eller välj ett värde i fältet Artikelgrupp.
9. Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.
10. Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.
11. Klicka på OK.

> [!NOTE]
> Produktlivscykelns standardläge är en global definition.  

## <a name="change-the-product-to-an-active-state"></a>Ändra produkten till ett aktivt tillstånd.
1. Ange eller välj ett värde i fältet produktlivscykeltillstånd.

> [!NOTE]
> Anta att du har ställt in ett aktivt tillstånd, kan du nu välja det aktiva tillståndet så att produkten används i huvudplanering och beräkning av strukturlistenivå. Självklart lönar det sig bara om produkten har allt som krävs för konsekvent planering.  

