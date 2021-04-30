---
title: Regulatory Configuration Service
description: Detta ämne innehåller en översikt över funktionerna i Regulatory Configuration Service (OMS) och förklarar hur du öppnar tjänsten.
author: JaneA07
manager: AnnBe
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: ec7e0fe07d979b85109605949b6ba33ab6d99b51
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890810"
---
# <a name="regulatory-configuration-service"></a>Regulatory Configuration Service

[!include [banner](../includes/banner.md)]

Regulatory Configuration Service (RCS) är en fristående tjänst för design- och livscykelhantering för globaliseringsfunktioner utan kod/lite kod ("low-code"). Med RCS kan globaliseringsintressenter utöka och anpassa viktiga globaliseringsområden för skatt, e-fakturering, lagstadgad rapportering, bank- och affärsdokument utan att behöva involvera utvecklare. Denna globaliseringsmetod utan kod/med lite kod ("low-code") gör globaliseringen enklare, snabbare och kostnadseffektivare att skapa eller utöka.

RCS tillhandahåller följande funktioner:

- Stöd för alla funktioner som tillhandahålls av Elektronisk rapportering (ER).
- En förutsättning för att nya mikrotjänster för globalisering ska kunna konfigureras.
- Stöd för elektronisk fakturering. Mer information finns i [E-fakturering](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).
- Stöd för skatteberäkning. Mer information finns i [Skattetjänst](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).
- Stöd för nya globaliseringsfunktioner som förenklar livscykelhanteringen av flerkomponentfunktioner och ger extra kapacitet att konfigurera åtgärder och ställa in funktionsparametrar. Mer information finns i [Regulatory Configuration Service – förenklad hantering av globaliseringsfunktioner för globaliseringstjänster](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).
- Stöd för centraliserad publicering, lagring och delning av anpassade konfigurationer i den globala databasen för att förenkla konfigurationshanteringen utan att Microsoft Dynamics Lifecycle Services (LCS) behöver användas.

## <a name="access-rcs"></a>Åtkomst till RCS

Du kan registrera dig för eller logga in på RCS från [sidan Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).

![Registrering för/inloggning i RCS](media/202103_RCS%20Marketing%20page_updated_1.jpg)

På sidan **Regulatory Configuration Service** läser du igenom och godkänner tilläggsvillkoren för användningen av tjänster innan du väljer en av följande knappar:

- **Registrera dig** om du använder tjänsten för första gången och använder en företags-e-postadress för att tillhandahålla en tjänstemiljö till din organisation
- **Logga in** om du redan tidigare har registrerat dig för tjänsten och vill komma åt organisationsmiljön

## <a name="regional-availability"></a>Regional tillgänglighet

RCS är i allmänhet tillgängligt i följande regioner:

- USA
- Indien
- Frankrike
- Europa

En fullständig lista över regioner finns i [Dynamics 365 och Power Platform: Tillgänglighet, dataplats, språk och lokalisering](https://aka.ms/dynamics_365_international_availability_deck).

## <a name="related-rcs-documentation"></a>Relaterad RCS-dokumentation

Mer information om att relaterade komponenter finns i följande dokumentation:

- **Global databas:**

    - [Skapa ER-konfiguration & överföring till Global lagringsplats](rcs-global-repo-upload.md)
    - [Dela konfiguration i Global lagringsplats](rcs-global-repo-share-configuration.md)
    - [Utökad filtrering i global lagringsplats](enhanced-filtering-global-repo.md)
    - [Hämta ER-konfigurationer från den globala lagringsplatsen](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [Avbryta konfigurationer i den globala lagringsplatsen](discontinuing-configurations-rcs-global-repo.md)

- **Globaliseringsfunktion:**

    - [Regulatory Configuration Service (RCS) - Globalizseringsfunktion](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)