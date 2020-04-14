---
title: Skapa en inköpsfrisläppningsorder när inköpsordern skapas
description: I den här proceduren visas hur du använder en inköpsavtal när du skapar en inköpsorder.
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41d857dbe7c5f7af8ef7a50ee60784a53e5c6823
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147421"
---
# <a name="create-a-purchase-release-order-when-creating-the-purchase-order"></a>Skapa en inköpsfrisläppningsorder när inköpsordern skapas

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du använder en inköpsavtal när du skapar en inköpsorder. Inköpsavtalet måste tillämpas när du skapar inköpsordern eftersom det finns allmänna villkor som ska kopieras till inköpsorderhuvudet. Uppgiften utförs vanligtvis av en inköpsagent. Som en förutsättning för den här guiden måste du ha ett giltigt inköpsavtal med en produktkvantitetsutfästelse för en leverantör och artiklar. Samma procedur kan användas om du har en inköpsavtal med andra typer av utfästelser. Du kan köra den här handboken i demonstrationsdataföretaget USMF. Om du använder USMF kan du köra guiden "Skapa ett inköpsavtal" först när du vill ställa in de nödvändiga förutsättningarna för den här guiden.


## <a name="create-a-purchase-order"></a>Skapa en inköpsorder
1. Öppna arbetsyta för inköpsorderförberedelse.
2. Klicka på Ny inköpsorder.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Växla utökningen av avsnittet Allmänt.
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Inköpsavtal.
    * Alla tillgängliga avtal för leverantören anges här. Sök efter det giltiga avtal som du vill använda.  
8. Klicka på länken på den valda raden i listan.
9. Klicka på Ja.
10. Klicka på OK.

## <a name="add-a-line"></a>Lägga till en rad
1. Skriv ett värde i fältet Artikelnummer.
    * Om det finns specifika lager- eller platsdimensioner på utfästelsen måste du ange samma värden på inköpsorderraden för att underlätta användningen av avtalet.  
2. Öppna sökningen genom att klicka på listruteknappen i fältet Plats.
    * Webbplatsen kan redan ha fyllts i med standardvärdet från ordern eller från leverantören. Om så är fallet hoppar du över detta steg.  
3. Hitta och markera önskad post i listan.
4. Klicka på länken på den valda raden i listan.
5. Ange ett tal i fältet Kvantitet.
    * Validera att priset kopieras från utfästelsen.  

## <a name="look-up-the-commitment"></a>Slå upp utfästelsen
1. Klicka på Uppdatera rad.
2. Klicka på Kopplat.
    * Här kan du få information om inköpsavtalet. Du kan till exempel se priset och om priset och rabatten är fasta, vilket innebär att om du ändrar priset eller rabatten på inköpsordern till ett annat värde än på utfästelsen, så tas länken bort så att inköpsorderraden inte uppfyller utfästelsen. Du kan även se om alternativet Max framtvingas, vilket innebär att kvantiteten på utfästelsen inte kan överskridas genom att summera alla inköp som uppfyller utfästelsen.  
3. Stäng sidan.

## <a name="look-up-the-purchase-agreement"></a>Slå upp inköpsavtalet
1. Klicka på Allmänt i åtgärdsfönstret.
2. Klicka på Inköpsavtal.
3. Stäng sidan.
4. Stäng sidan.

