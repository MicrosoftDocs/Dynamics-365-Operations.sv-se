---
title: Skapa en ny produkt
description: Den här uppgiften visar hur du skapar en ny delad produkt.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7a603d89749242a4c6039ab83da286ec6ab727d8
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "328549"
---
# <a name="create-a-new-product"></a>Skapa en ny produkt

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiften visar hur du skapar en ny delad produkt. Den utförs vanligtvis av en produktdesigner. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.

1. Gå till Hantering av produktinformation > Produkter > Produkter.

## <a name="create-a-product"></a>Skapa en produkt
1. Klicka på Ny.
2. Skriv ett värde i fältet Produktnummer.
    * Om en nummerserie inte har ställts in för den produktnumret, måste den anges manuellt.  
3. Skriv ett värde i fältet Produktnamn.
    * Produktnamnet anges som standard till söknamnet. Du kan ändra detta om det behövs.  
4. Klicka på OK.

## <a name="set-up-dimension-groups"></a>Ställ in dimensionsgrupper
1. Klicka på Dimensionsgrupper för att öppna dialogrutan.
2. Ange eller välj ett värde i fältet Lagringsdimensionsgrupp.
    * Lagringsdimensiongruppen avgör vilka lagringsdimensioner du måste ange för varje transaktion för produkten och hur den ska spåras i lagret.  
3. Ange eller välj ett värde i fältet Spårningsdimensionsgrupp.
    * Spårningsdimensiongruppen avgör vilka spårningsdimensioner du måste ange för varje transaktion för produkten och hur den ska hanteras i lagret.  
4. Klicka på OK.

