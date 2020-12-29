---
title: Installera, ställ in och uppdatera kundportalen
description: Det här avsnittet innehåller licensieringsinformation och installationsinstruktioner för kundportalen.
author: dasani-madipalli
manager: tfehr
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: e61fc5f7151a0bb61d496d47f4ad4e727a2a1d65
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529540"
---
# <a name="install-set-up-and-update-the-customer-portal"></a>Installera, ställ in och uppdatera kundportalen

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="licensing-requirements"></a>Licensieringskrav

Om du vill implementera kundportalen måste du ha följande licenser:

- **Power Apps-portaler** – den här licensen krävs för att vara värd för kundportalen. Portaler är licensierade utifrån användning. Mer information finns i avsnittet om [Power Apps licenskrav för portaler](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).
- **Dubbelriktad skrivning** – du måste ha de licenser som krävs för att möjliggöra dubbelriktad skrivning för enheter för Supply Chain Management. För mer information, se [systemkrav för dubbelriktad skrivning](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a>Beroenden på dubbelriktad skrivning och Power Apps-portaler

Kundportalen beror på Power Apps-portaler och dubbelskrivning, vilket visas i bilden nedan.

![Kundportalberoenden](media/customer-portal-elements.png "Kundportalberoenden")

Till skillnad från andra funktioner från Supply Chain Management, kundportalmallen finns i Power Apps-portaler. Därför begränsas kundportalen av de funktioner som tillhandahålls av Power Apps-portaler och enheterna i dubbelriktad skrivning.

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a>Obligatorisk inställning för att aktivera kundportalen

När du har installerat de nödvändiga licenserna kan du ställa in dubbelriktad skrivning enligt beskrivningen i [inledande synkroniseringsinställningarna för dubbelriktad skrivning](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).

Se till att aktivera följande enhetsmappningar i dubbelriktad skrivning:

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

- [Power Apps-portaldokumentation](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [Dokumentation för dubbelriktad skrivning](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

Om du vill hantera portalerna effektivt måste du känna till Power Apps-portalerna och Common Data Service livscykeln. Mer information finns i följande resurser:

- [Om portalens livscykel](https://docs.microsoft.com/powerapps/maker/portals/admin/portal-lifecycle)
- [Uppgradera en portal](https://docs.microsoft.com/powerapps/maker/portals/admin/upgrade-portal)
- [Migrera portalkonfiguration](https://docs.microsoft.com/powerapps/maker/portals/admin/migrate-portal-configuration)
- [Hantering av lösningens livscykel: Dynamics 365 for Customer Engagement-appar](https://www.microsoft.com/download/details.aspx?id=57777)
