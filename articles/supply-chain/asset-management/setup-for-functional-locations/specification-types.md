---
title: Underhåll av attributtyper
description: Denna artikel beskriver hur du skapar attributtyper i Tillgångshantering.
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
ms.openlocfilehash: 5a0aca3ccf24505c064ad59f0adafb771056ba95
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887672"
---
# <a name="maintenance-attribute-types"></a>Underhåll av attributtyper

[!include [banner](../../includes/banner.md)]

 

Denna artikel beskriver hur du skapar attributtyper i Tillgångshantering. Attribut används för att beskriva egenskaperna för olika element. Du kan konfigurera attribut på följande element:

- [Funktionsplatstyper](../setup-for-functional-locations/functional-location-types.md)
- [Skapa funktionsplatser](../functional-locations/create-functional-locations.md)
- [Tillgångstyper](../setup-for-objects/object-types.md)
- Tillgångar

Attributen som du kan konfigurera varierar beroende på elementet. För en funktionsplats kan du till exempel konfigurera attribut för konfigurationen och den fysiska storleken på platsen. För en tillgångstyp eller en tillgång kan du konfigurera attribut för motorvolym, energiförbrukning och maximal lastkapacitet under olika förhållanden.

## <a name="create-attribute-types"></a>Skapa attributstyper

Du kan skapa egna attributtyper. Dessutom kan du överföra produktdimensioner till sidan **attributtyper**.

1. Välj **attributtyper** \> **inställningar** \> **attributtyper**.
2. Första gången du konfigurerar attributtyper väljer du **Skapa produktdimensioner** för att automatiskt överföra standardproduktdimensioner.
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