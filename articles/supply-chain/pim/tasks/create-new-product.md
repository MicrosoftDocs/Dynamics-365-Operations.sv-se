---
title: Skapa en ny produkt
description: I det här avsnittet beskrivs hur du skapar en ny delad produkt.
author: ShylaThompson
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bab383e4e1b33cbeeb0bbd7712e4907301057fd293c8334b45888be8f3d97277
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6761816"
---
# <a name="create-a-new-product"></a>Skapa en ny produkt

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en ny delad produkt. Den utförs vanligtvis av en produktdesigner. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF.


## <a name="create-a-product"></a>Skapa en produkt
1. I navigeringsfönstret, gå till **Moduler > Produktinformationshantering > Produkter > Produkter**.
2. Välj **Ny**.
3. Skriv ett värde i fältet **Produktnummer**. Om en nummerserie inte har ställts in för den produktnumret, måste den anges manuellt.  
4. Skriv ett värde i fältet **Produktnamn**. Produktnamnet anges som standard till söknamnet. Du kan ändra detta om det behövs.  
5. Välj **OK**.

## <a name="set-up-dimension-groups"></a>Ställ in dimensionsgrupper
1. Välj **Dimensionsgrupper** för att öppna dialogrutan.
2. Ange eller välj ett värde i fältet **Lagringsdimensionsgrupp**. Lagringsdimensiongruppen avgör vilka lagringsdimensioner du måste ange för varje transaktion för produkten och hur den ska spåras i lagret.  
3. Ange eller välj ett värde i fältet **Spårningsdimensionsgrupp**. Spårningsdimensiongruppen avgör vilka spårningsdimensioner du måste ange för varje transaktion för produkten och hur den ska hanteras i lagret.  
4. Välj **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]