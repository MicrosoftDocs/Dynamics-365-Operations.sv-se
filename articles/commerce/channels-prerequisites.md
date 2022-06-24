---
title: Förutsättningar för kanalinställningar
description: Denna artikel innehåller en översikt över förutsättningar för att konfigurera kanaler i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 02/21/2020
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
ms.openlocfilehash: 84b176ed07de8dd0828ba02cdbefd7a3795d984b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884943"
---
# <a name="channel-setup-prerequisites"></a>Förutsättningar för kanalinställningar

[!include [banner](includes/banner.md)]

Denna artikel innehåller en översikt över förutsättningar för att konfigurera kanaler i Microsoft Dynamics 365 Commerce.

Innan du kan skapa en Dynamics 365 Commerce-kanal måste flera nödvändiga uppgifter slutföras. Följande lista över nödvändiga uppgifter är ordnade efter kanaltyp.

> [!NOTE]
> En del dokumentation håller fortfarande på att skrivas och länkar uppdateras när nytt innehåll publiceras.

## <a name="initialization"></a>Initialisering

- [Initiera startdata](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a>Globala förutsättningar krävs för alla kanaltyper

- [Definiera och konfigurera din juridiska organisationens struktur](channels-legal-entities.md) 
- [Konfigurera din organisationshierarki](channels-org-hierarchies.md)
- [Ställ in ett lagerställen](channels-setup-warehouse.md)
- [Konfigurera moms](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [Ange en meddelandeprofil för e-post](email-notification-profiles.md)
- [Ställa in nummerserier](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [Ställa in en standardkund och adressbok](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a>Förutsättningar för butikskanaler

- [Infokoder och infokodgrupper](info-codes-retail.md)
- [Konfigurera en butiksfunktionsprofil](retail-functionality-profile.md)
- [Konfigurera en medarbetaradressbok](new-address-book.md)
- [Ställ in en skärmlayout](pos-screen-layouts.md)
- [Konfigurera en maskinvarustation](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a>Förutsättningar för kundtjänstkanal

- Parametrar för kundtjänst
- [Kundtjänstorder och återbetalsätt](work-with-payments.md)
- [Leveranssätt och avgifter för kundtjänst](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a>Förutsättningar för onlinekanal

- [Skapa en onlinefunktionsprofil](online-functionality-profile.md)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över kanaler](channels-overview.md)

[Organisationer och organisationshierarkier – översikt](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Ange organisationshierarkier](channels-org-hierarchies.md)

[Skapa juridiska personer](channels-legal-entities.md)

[Ställa in en butikskanal](channel-setup-retail.md)
    
[Ställ in en onlinekanal](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
