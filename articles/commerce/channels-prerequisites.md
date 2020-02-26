---
title: Förutsättningar för att ställa in kanaler
description: Det här ämnet innehåller en översikt över förutsättningar för att ställa in kanaler i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b861d90f1333c8f6e61a83602ed74e30b65f3dc1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002299"
---
# <a name="channel-setup-prerequisites"></a>Förutsättningar för att ställa in kanaler


[!include [banner](includes/banner.md)]

Det här ämnet innehåller en översikt över förutsättningar för att ställa in kanaler i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Innan du kan skapa en Dynamics 365 Commerce-kanal måste flera nödvändiga uppgifter slutföras. Följande lista över nödvändiga uppgifter är ordnade efter kanaltyp.

> [!NOTE]
> En del dokumentation håller fortfarande på att skrivas och länkar uppdateras när nytt innehåll publiceras.

## <a name="initialization"></a>Initialisering

- [Initiera startdata](../retail/enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a>Globala förutsättningar krävs för alla kanaltyper

- [Definiera och konfigurera din juridiska organisationens struktur](channels-legal-entities.md) 
- [Konfigurera din organisationshierarki](channels-org-hierarchies.md)
- [Ställ in ett lagerställen](channels-setup-warehouse.md)
- [Konfigurera moms](https://docs.microsoft.com/en-us/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json)
- [Ange en meddelandeprofil för e-post](email-notification-profiles.md)
- [Ställa in nummerserier](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/commerce/toc.json)
- [Ställa in en standardkund och adressbok](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a>Förutsättningar för butikskanaler

- [Infokoder och infokodgrupper](https://docs.microsoft.com/en-us/dynamics365/retail/info-codes-retail?toc=/dynamics365/commerce/toc.json)
- [Konfigurera en butiksfunktionsprofil](retail-functionality-profile.md)
- [Konfigurera en medarbetaradressbok](new-address-book.md)
- [Ställ in en skärmlayout](https://docs.microsoft.com/en-us/dynamics365/retail/pos-screen-layouts?toc=/dynamics365/commerce/toc.json)
- [Konfigurera en maskinvarustation](https://docs.microsoft.com/en-us/dynamics365/retail/retail-hardware-station-configuration-installation?toc=/dynamics365/commerce/toc.json)

## <a name="call-center-channel-prerequisites"></a>Förutsättningar för kundtjänstkanal

- Parametrar för kundtjänst
- Återbetalningsmetoder för kundtjänst
- Hyrestyper
- Betalningstjänster
- Koder för spärrad order

## <a name="online-channel-prerequisites"></a>Förutsättningar för onlinekanaler

- [Skapa en online funktionsprofil](online-functionality-profile.md)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över kanaler](channels-overview.md)

[Organisationer och organisationshierarkier – översikt](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Ange organisationshierarkier](channels-org-hierarchies.md)

[Skapa juridiska personer](channels-legal-entities.md)

[Ställa in en butikskanal](channel-setup-retail.md)
    
[Ställ in en onlinekanal](channel-setup-online.md)
