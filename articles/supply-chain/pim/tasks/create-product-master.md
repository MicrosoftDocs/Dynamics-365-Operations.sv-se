---
title: Skapa en produktmall
description: Skapa en produktmall för de fördefinierade varianterna.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fdb30b46a0e5a6d4fac997588dd47148f2664c03
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437666"
---
# <a name="create-a-product-master"></a>Skapa en produktmall

[!include [banner](../../includes/banner.md)]

Skapa en produktmall för de fördefinierade varianterna. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren är avsedd för produktplaneraren.


## <a name="create-a-new-product-master"></a>Skapa en ny produktmall
1. Gå till **Navigeringsfönstret > Moduler > Produktinformationshantering > Produkter > Produktmallar**.
2. Klicka på **Ny**.
3. Skriv ett värde i fältet **Produktnummer**. Numret måste vara unikt. En nummerserie kan ställas in för fältet **Produktnummer**. I det här fallet måste användaren inte ange något värde.
4. Skriv ett värde i fältet **Produktnamn**. Ange ett beskrivande namn på produkten. Värdet hämtas som standard i söknamnet, men det kan ändras av användaren.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Produktdimensionsgrupp**. Produktdimensionsgruppen bestämmer vilken av de 4 produktdimensionerna som kan användas för att skapa produktvarianter. I det här exemplet används en grupp med färg och storlek.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan. Standardinställda **konfigurationsteknik** är den fördefinierade varianten. Denna används för det här exemplet.
8. Klicka på **OK**.

## <a name="select-product-dimension-groups"></a>Välj produktdimensionsgrupper
1. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Färggrupp**.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Storleksgrupp**.
5. Hitta och markera önskad post i listan.
6. Klicka på länken på den valda raden i listan.

## <a name="add-dimension-groups"></a>Lägg till dimensionsgrupper
1. I **Åtgärdsfönstret**, klicka på **Produkt**.
2. Klicka på **Dimensionsgrupper** för att öppna dialogrutan.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Lagringsdimensionsgrupp**. Lagringsdimensioner bestämmer hur artiklar lagras och tas från lagret. Till exempel kan en lagringsdimension omfatta webbplats och lagerställe.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Spårningsdimensionsgrupp**. Spårningsdimensionsgruppen avgör vilka spårningsdimensioner du kan lägga till för en produkt. Batchnummer och serienummer används till exempel för att spåra lagerartiklar.
7. Hitta och markera önskad post i listan.
8. Klicka på länken på den valda raden i listan.
9. Klicka på **OK**.
10. Klicka på **Spara**.
11. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]