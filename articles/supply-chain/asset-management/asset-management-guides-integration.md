---
title: Integrera Dynamics 365 Supply Chain Management (tillgångshantering) med Dynamics 365 Guides
description: Det här avsnittet innehåller information om hur du integrerar modulen för tillgångshantering i Microsoft Dynamics 365 Supply Chain Management med Dynamics 365 Guides och drar nytta av guiderna för dagligt service- och underhållsarbete.
author: kamaybac
ms.date: 04/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-28
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 50cfea6656e1f13532b018784fa64b2aac10fc7f
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908577"
---
# <a name="integrate-dynamics-365-supply-chain-management-asset-management-with-dynamics-365-guides"></a>Integrera Dynamics 365 Supply Chain Management (tillgångshantering) med Dynamics 365 Guides

Du kan integrera modulen för **tillgångshantering** i Microsoft Dynamics 365 Supply Chain Management med Dynamics 365 Guides och dra nytta av guiderna för dagligt service- och underhållsarbete. Om en guide är associerad till en arbetsorder för tillgångshantering kan en arbetare som öppnar arbetsorderns underhållschecklista i mobilappen Supply Chain Management (Dynamics 365) se att en guide är tillgänglig. Arbetaren kan sedan hitta och öppna guiden i appen Dynamics 365 Guides HoloLens.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan koppla guider till arbetsorder för tillgångshantering måste följande förutsättningar föreligga:

- [Ställ in Dynamics 365 Supply Chain Management](../../fin-ops-core/fin-ops/index.md) version 10.0.9 eller senare.
- [Aktivera dubbelriktad skrivning för Supply Chain Management-appar](../../fin-ops-core/dev-itpro/data-entities/dual-write/enable-dual-write.md).
- [Aktivera flight](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#features-flighted-in-data-management-and-enabling-flighted-features) för funktionen **MRGuidesFeature**. (För produktionsmiljöer måste du först skicka in ett supportärende så att din klientorganisation läggs till i flightgruppen.)
- [Aktivera följande konfigurationsnycklar](/dynamicsax-2012/appuser-itpro/license-code-and-configuration-key-reference) på sidan **Licenskonfiguration**:

    - Tillgångshantering \> Tillgångshantering mixed reality
    - Mixed reality \> Mixed reality-guide

- [Ställ in Dynamics 365 Guides](/dynamics365/mixed-reality/guides/setup#step-2-create-a-common-data-service-environment-and-install-the-dynamics-365-guides-solution) version 200.0.0.96 eller senare.

## <a name="use-dynamics-365-guides-with-asset-management"></a>Använd Dynamics 365 Guides med tillgångshantering

Om du vill associera en guide använder du en underhållschecklistrad i tillgångshantering. Du kan skapa associeringen via en mall för checklista för underhåll, en underhållsjobbtyp eller en arbetsorder, eftersom alla tre innehåller underhållschecklistrader. Du kan spara tid genom att använda en mall, eftersom en mall kan associeras till alla typer av underhållsjobb som använder den. En guide som är associerad med en underhållsjobbtyp kopplas till exempel automatiskt till alla arbetsorder som anger den jobbtypen. Å andra sidan finns en guide som är associerad direkt till en arbetsorder enbart för den aktuella arbetsordern.

### <a name="associate-a-guide-with-a-maintenance-checklist-template"></a>Associera en guide med en mall för underhållschecklista

För att associera en guide med en mall för underhållschecklista ska du följa dessa steg.

1. Skapa en guide med Dynamics 365 Guides för dator och HoloLens-apparna. För information om hur du skapar en guide, se följande ämnen:

    - [Skapa guiden med hjälp av datorappen](/dynamics365/mixed-reality/guides/pc-app-overview)
    - [Använd HoloLens-appen för att placera dina hologram](/dynamics365/mixed-reality/guides/hololens-app-overview)

1. I Supply Chain Management [skapar du en mall för underhållschecklista](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-checklist-template).
1. Associera guiden som du skapade med en underhållschecklistrad i den nya mallen för underhållschecklista:

    1. På snabbfliken **Underhållschecklistrader** markerar du raden som du vill associera guiden till.
    1. På snabbfliken **Associerade guider** väljer du **Lägg till guide**.

        ![Associera en guide med en mall för underhållschecklistrad](media/am-guides-integration-add-guide.png "Associera en guide med en mall för underhållschecklistrad")

    1. I fältet **Namn** väljer du en guide och sedan **Spara**.

        ![Välj guide i fältet Namn](media/am-guides-integration-select-guide.png "Välj guide i fältet Namn")

1. Associera en mall för underhållschecklista med en jobbtyp:

    1. [Skapa en underhållsjobbtyp](setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md#create-a-maintenance-job-type) eller välj en befintlig underhållsjobbtyp.
    1. I åtgärdsfönstret väljer du **Standardinställningar för underhållsjobbtyp**.

        ![Knappen standardinställningar för underhållsjobbtyp](media/am-guides-integration-job-defaults.png "Knappen standardinställningar för underhållsjobbtyp")

    1. Skapa en rad och välj sedan **Spara**.

        ![Skapa en rad](media/am-guides-integration-add-line.png "Skapa en rad")

    1. I åtgärdsfönstret klickar du på **Underhållschecklista**.

        ![Knapp för underhållschecklista](media/am-guides-integration-maintenance-checklist.png "Knapp för underhållschecklista")

    1. På snabbfliken **Underhållschecklistrader** lägger du till en rad och ändrar sedan värdet i fältet **Typ** till **Mall**.

        ![Ändra värdet Typ](media/am-guides-integration-checklist-lines.png "Ändra värdet Typ")

    1. På snabbfliken **Raddetaljer** i fältet **Mall** väljer du den mall som du associerade guiden till och väljer **Spara**.

        ![Välj mall](media/am-guides-integration-checklist-line-details.png "Välj mall")

1. [Skapa en arbetsorder](work-orders/manually-created-workorders.md#create-work-order) och välj sedan underhållsjobbtyp som använder den mall för underhållschecklista som du associerade guiden till. Guiden associeras automatiskt till arbetsordern.

    ![Välj underhållsjobbtyp](media/am-guides-integration-create-work-order.png "Välj underhållsjobbtyp")

1. Visa den guide som är associerad till arbetsordern och arbetarna:

    1. Öppna [Arbetsytan för tillgångshantering](asset-management-mobile-workspace.md) för att komma åt arbetsordern.
    1. [Öppna underhållschecklistan](asset-management-mobile-workspace.md#view-maintenance-checklist-on-a-work-order-job) för arbetsordern.
    1. Välj en checklistrad för att se associerad guide.

        ![Guide associerad till checklistarad](media/am-guides-integration-show-guide.png "Guide associerad till checklistrad")

    1. Öppna guiden i HoloLens.

        ![Öppna guiden i HoloLens](media/am-guides-integration-hololens-select.png "Öppna guiden i HoloLens")

> [!NOTE]
> Du kan även associera en guide direkt i underhållschecklistan för en arbetsorder eller jobbtyp.

> [!IMPORTANT]
> Det finns ett känt problem när du associerar en mall för underhållschecklista med en standard underhållsjobbtyp. Då visas inte guiden som är associerad till mallen på snabbfliken **Associerade guider** på sidan **Standardinställningar för underhållsjobbtyp**. Guiden visas dock när jobbtypen har tillämpats på en arbetsorder på snabbfliken **Associerade guider**.

## <a name="see-also"></a>Se även

- [Översikt över dubbelriktad skrivning](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview.md)
- [Översikt av tillgångshantering](index.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]