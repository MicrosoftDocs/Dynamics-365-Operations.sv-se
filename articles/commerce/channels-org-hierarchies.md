---
title: Ställa in organisationshierarkier
description: I det här avsnittet beskrivs hur du ställer in organisationshierarkier i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 4238d1aa277bf2f1df30825ef20dbf3095d13ebc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800577"
---
# <a name="set-up-organization-hierarchies"></a>Ställa in organisationshierarkier

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in organisationshierarkier i Microsoft Dynamics 365 Commerce.

Innan du skapar kanaler måste du se till att du har ställt in dina organisationshierarkier.

Du kan använda organisationshierarkier för att visa och skapa en rapport från olika perspektiv av din verksamhet. Du kan till exempel skapa en hierarki för momsrapportering, juridisk rapportering eller lagstadgad rapportering. Du kan ställa in en annan hierarki om du vill rapportera ekonomisk information som inte krävs lagligen, men som används för intern rapportering.

Innan du skapar en organisationshierarki måste du skapa organisationer. Mer information finns i [Skapa juridisk personer](channels-legal-entities.md) eller [Skapa driftenheter](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).


Mer information finns i följande avsnitt.
- [Organisationer och organisationshierarkier – översikt](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [Planera en organisationshierarki](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [Skapa en organisationshierarki](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a>Skapa en organisationshierarki

Följ stegen nedan om du vill skapa en organisationshierarki för kanaler.

1. I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Organisationshierarkier**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Namn** anger du ett värde.
1. I avsnittet **Syfte**, klicka på **Tilldela syfte**.
1. Hitta och markera önskad post i listan. Välj ett syfte att tilldela till din organisationshierarki.
1. Klicka på **Lägg till** i avsnittet **Tilldelade hierarkier**.
1. Markera vald rad i listan. Hitta hierarki som du just skapat.
1. Välj **OK**.

Följande bild visar ett exempel på en organisationshierarki som skapats för en fiktiv "Adventure Works"-uppsättning butiker.

![Exempel på organisationshierarki](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a>Lägg till organisationer i hierarkin

Om du vill lägga till organisationer till en hierarki gör du följande.

1. Hitta och markera önskad post i listan. Välj hierarki.
1. Klicka på **Visa** i åtgärdsfönstret.
1. Lägg till fler organisationer efter behov.
1. Om du vill lägga till en organisation, välj **redigera** och sedan **infoga**. När du är klar med ändringar, kan du spara ett utkast och publicera ändringarna.

Följande bild visar en juridisk person som lagts till i hierarkistrukturen med fyra kostnadsställen som har lagts till för kanalerna "köpcentrum", "outlet", "online" och "kundtjänst". Olika butiks-, kundtjänst- och onlinekanaler kan sedan läggas till i var och en.

![Exempel på hierarkidesigner](media/hierarchy-designer.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Organisationer och organisationshierarkier – översikt](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planera en organisationshierarki](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Skapa juridiska personer](channels-legal-entities.md)

[Skapa driftenheter](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[Översikt över kanaler](channels-overview.md)

[Förutsättningar för att ställa in kanaler](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
