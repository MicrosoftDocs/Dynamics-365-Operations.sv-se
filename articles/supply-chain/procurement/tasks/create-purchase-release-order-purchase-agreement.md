---
title: Skapa en inköpsfrisläppningsorder från ett inköpsavtal
description: I den här proceduren visas hur du använder en inköpsavtal när du skapar en inköpsorder.
author: kamaybac
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cd3f837590cd7fe09ad385d0baac6c16fcf145d0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812286"
---
# <a name="create-a-purchase-release-order-from-a-purchase-agreement"></a>Skapa en inköpsfrisläppningsorder från ett inköpsavtal

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du använder en inköpsavtal när du skapar en inköpsorder. Inköpsavtalet måste tillämpas när du skapar inköpsordern eftersom det finns allmänna villkor som ska kopieras till inköpsorderhuvudet. Uppgiften utförs vanligtvis av en inköpsagent. Som en förutsättning för den här guiden måste du ha ett giltigt inköpsavtal med en produktkvantitetsutfästelse för en leverantör och artiklar. Samma procedur kan användas om du har en inköpsavtal med andra typer av utfästelser. Du kan köra den här handboken i demonstrationsdataföretaget USMF. Om du använder USMF kan du köra guiden "Skapa ett inköpsavtal" först när du vill ställa in de nödvändiga förutsättningarna för den här guiden.


## <a name="create-a-purchase-order"></a>Skapa en inköpsorder
1. I **Navigeringsfönster**, gå till **Arbetsytor > Inköpsorderförberedelse**. 
2. Klicka på **Ny inköpsorder.**
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Leverantörskonto**.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Expandera **Allmänt** snabbflik.
7. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Inköpsavtal**. Alla tillgängliga avtal för leverantören anges här. Sök efter det giltiga avtal som du vill använda.  
8. Klicka på länken på den valda raden i listan.
9. Klicka på **Ja**.
10. Klicka på **OK**.

## <a name="add-a-line"></a>Lägga till en rad
1. I fältet **Artikelnummer**, skriv ett värde. Om det finns specifika lager- eller platsdimensioner på utfästelsen måste du ange samma värden på inköpsorderraden för att underlätta användningen av avtalet.  
2. I fältet **Plats**, klicka på listruteknappen för att öppna sökningen. Webbplatsen kan redan ha fyllts i med standardvärdet från ordern eller från leverantören. Om så är fallet hoppar du över detta steg.  
3. Hitta och markera önskad post i listan.
4. Klicka på länken på den valda raden i listan.
5. Ange ett nummer i fältet **Kvantitet**. Validera att priset kopieras från utfästelsen.  

## <a name="look-up-the-commitment"></a>Slå upp utfästelsen
1. Klicka på **Uppdatera rad.**
2. Klicka på **Kopplat**. Här kan du få information om inköpsavtalet. Du kan till exempel se priset och om priset och rabatten är fasta, vilket innebär att om du ändrar priset eller rabatten på inköpsordern till ett annat värde än på utfästelsen, så tas länken bort så att inköpsorderraden inte uppfyller utfästelsen. Du kan även se om alternativet Max framtvingas, vilket innebär att kvantiteten på utfästelsen inte kan överskridas genom att summera alla inköp som uppfyller utfästelsen.  
3. Stäng sidan.

## <a name="look-up-the-purchase-agreement"></a>Slå upp inköpsavtalet
1. I **åtgärdsrutan** klickar du på **Allmänt**.
2. Klicka på **Inköpsavtal.**
3. Stäng sidan.
4. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]