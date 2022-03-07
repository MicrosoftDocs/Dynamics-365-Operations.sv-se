---
title: Underhåll av attributtyper
description: Det här avsnittet beskriver hur du skapar attributtyper i tillgångshantering.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationTypeCopy, EntAssetAttributeType, EntAssetAttributeTypeValue, EntAssetFunctionalLocationType
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec5552d96473403931bbd513ae68ef0fe3069209f52e813963914417ad41b88a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739141"
---
# <a name="maintenance-attribute-types"></a>Underhåll av attributtyper

[!include [banner](../../includes/banner.md)]

 

Det här avsnittet beskriver hur du skapar attributtyper i tillgångshantering. Attribut används för att beskriva egenskaperna för olika element. Du kan ställa in attribut på följande element:

- [Funktionsplatstyper](../setup-for-functional-locations/functional-location-types.md)
- [Skapa funktionsplatser](../functional-locations/create-functional-locations.md)
- [Tillgångstyper](../setup-for-objects/object-types.md)
- Tillgångar

Attributen som du kan ställa in varierar beroende på elementet. För en funktionsplats kan du till exempel ställa in attribut för konfigurationen och den fysiska storleken på platsen. För en tillgångstyp eller en tillgång kan du ställa in attribut för motorvolym, energiförbrukning och maximal lastkapacitet under olika förhållanden.

## <a name="create-attribute-types"></a>Skapa attributstyper

Du kan skapa egna attributtyper. Dessutom kan du överföra produktdimensioner till sidan **attributtyper**.

1. Välj **attributtyper** \> **inställningar** \> **attributtyper**.
2. Första gången du ställer in attributtyper väljer du **Skapa produktdimensioner** för att automatiskt överföra standardproduktdimensioner.
3. Skapa en ny attributtyp genom att välja **Nytt**.
4. I fältet **Attributtyp** anger du ett namn på attributtypen.
5. Ange en beskrivning i fältet **beskrivning**.
6. I fältet **enhet** väljer du relevant attributenhet efter behov.
7. I fältet **Datatyp** väljer du en datatyp för enheten.
8. Om du har valt **sträng** som datatyp, så här om du vill skapa värden för attributtypen:

    1. Välj attributtyp och välj sedan **Värden**.
    2. I fältet **Attributvärden** väljer du **Ny**.
    3. I fältet **Attributtyp** väljer du en attributtyp (dimension).
    4. I fältet **värde** anger du ett relaterat värde.
    5. Ange en beskrivning i fältet **beskrivning**.
    6. Spara posten.
    7. Gå tillbaka till sidan **attributtyper**.

9. Spara posten.

    I fältet **funktionsplatstyper** visas antalet funktionsplatser som använder attributtypen. Fältet **tillgångstyper** visar antalet tillgångstyper som använder den.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]