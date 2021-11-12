---
title: Installera, ställ in och uppdatera kundportalen
description: Det här avsnittet innehåller licensieringsinformation och installationsinstruktioner för kundportalen.
author: Henrikan
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: b24aa8c342a3de647acc9cf0b4ec175ca24cef43
ms.sourcegitcommit: e891a6cc0674d27b7e218fdf22ca5ba8ac3310d0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648388"
---
# <a name="install-set-up-and-update-the-customer-portal"></a>Installera, ställ in och uppdatera kundportalen

[!include [banner](../includes/banner.md)]
[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="licensing-requirements"></a>Licensieringskrav

Om du vill implementera kundportalen måste du ha följande licenser:

- **Power Apps-portaler** – den här licensen krävs för att vara värd för kundportalen. Portaler är licensierade utifrån användning. Mer information finns i avsnittet om [Power Apps licenskrav för portaler](/power-platform/admin/powerapps-flow-licensing-faq#portals).
- **Dubbelriktad skrivning** – du måste ha de licenser som krävs för att möjliggöra dubbelriktad skrivning för tabeller för Supply Chain Management. För mer information, se [systemkrav för dubbelriktad skrivning](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a>Beroenden på dubbelriktad skrivning och Power Apps-portaler

Kundportalen beror på Power Apps-portaler och dubbelskrivning, vilket visas i bilden nedan.

![Kundportalberoenden.](media/customer-portal-elements.png "Kundportalberoenden")

Till skillnad från andra funktioner från Supply Chain Management, kundportalmallen finns i Power Apps-portaler. Därför begränsas kundportalen av de funktioner som tillhandahålls av Power Apps-portaler och tabellerna i dubbelriktad skrivning.

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a>Obligatorisk inställning för att aktivera kundportalen

När du har installerat de nödvändiga licenserna kan du ställa in dubbelriktad skrivning enligt beskrivningen i [inledande synkroniseringsinställningarna för dubbelriktad skrivning](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-entity-map.md).

Se till att aktivera följande tabellmappningar i dubbelriktad skrivning:

- Försäljningsorderhuvud
- Försäljningsorderinformation
- Konton
- Kontakter
- Produkter

När den här inställningen har slutförts kan du etablera kundportalmallen.

## <a name="provision-the-customer-portal"></a>Etablera kundportalen

Innan du börjar ska du kontrollera att du redan har slutfört de [nödvändiga inställningarna](#required-setup). Följ sedan dessa steg för att etablera kundportalen.

1. Gå till [make.powerapps.com](https://make.powerapps.com/).
2. Kontrollera att du använder den miljö där du har aktiverat dubbelriktad skrivning.
3. På fliken **Skapa** bläddra ned till avsnittet **Starta från mall** och välj den mall som har fått kunden för hantering av **Kundportal**.
4. Följ instruktionerna på skärmen.

När etableringen har slutförts kan du få tillgång till kundportalen i avsnittet **Dina appar** på sidan **Start**-sidan.

> [!NOTE]
> Om den dubbelriktad lösningen inte är installerad i den miljö som du arbetar i får du ett felmeddelande och kundportalen etableras inte.

## <a name="update-the-customer-portal"></a>Uppdatera kundportalen

Fler funktioner kan läggas till kundportalen senare. Alla ändringar som Microsoft gör i de underliggande lösningskomponenterna visas automatiskt i din miljö. Den webbplats som är etablerad i miljön återspeglar dock inte automatiskt ändringar som görs i konfigurationsdata. Du måste manuellt tillämpa ändringarna genom att hämta koden från den nya mallen och koppla den till den etablerade webbplatsen.

## <a name="additional-resources"></a>Ytterligare resurser

Om du vill veta hur du kan ställa in och anpassa kundportalen bör du börja med att granska följande dokumentation för den underliggande tekniken:

- [Power Apps-portaldokumentation](/powerapps/maker/portals/overview)
- [Dokumentation för dubbelriktad skrivning](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

Om du vill hantera portalerna effektivt måste du känna till Power Apps-portalerna och Microsoft Dataverse livscykeln. Mer information finns i följande resurser:

- [Om portalens livscykel](/powerapps/maker/portals/admin/portal-lifecycle)
- [Uppgradera en portal](/powerapps/maker/portals/admin/upgrade-portal)
- [Migrera portalkonfiguration](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Hantering av lösningens livscykel: Dynamics 365 for Customer Engagement-appar](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]