---
title: Regulatory Configuration Service
description: Detta ämne innehåller en översikt över funktionerna i Regulatory Configuration Service (OMS) och förklarar hur du öppnar tjänsten.
author: kfend
ms.date: 06/04/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization
ms.openlocfilehash: 01614aec0da097ee5c0c90bcbe9c7e0065f1d4fe
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277190"
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

![Registrering för/inloggning i RCS.](media/202103_RCS%20Marketing%20page_updated_1.jpg)

På sidan **Regulatory Configuration Service** läser du igenom och godkänner tilläggsvillkoren för användningen av tjänster innan du väljer en av följande knappar:

- **Registrera dig** om du använder tjänsten för första gången och använder en företags-e-postadress för att tillhandahålla en tjänstemiljö till din organisation
- **Logga in** om du redan tidigare har registrerat dig för tjänsten och vill komma åt organisationsmiljön

> [!NOTE] 
> När du har registrerat dig rekommenderar vi att du lägger till ytterligare en SysAdmin-användare till OMVS-miljön. Den här användaren får sin medadministratör för miljön. Detta kommer att göra det enkelt att få åtkomst till RCS-miljön, eftersom SysAdmin-rollen är att hantera användare för den miljön. Du kan lägga till användare med **RCS-arbetsyta > Systemadministration**.

## <a name="regional-availability"></a>Regional tillgänglighet

RCS är i allmänhet tillgängligt i följande regioner:

- USA
- Indien
- Frankrike
- Europa

En fullständig lista över regioner finns i [Dynamics 365 och Power Platform: Tillgänglighet, dataplats, språk och lokalisering](https://aka.ms/dynamics_365_international_availability_deck).

## <a name="rcs-default-company"></a>RCS-standardföretag

Designtidsfunktionen som används i RCS delas av alla företag. Det finns inte någon företagsspecifik funktion. Därför rekommenderar vi att du använder ett företag, **DAT**, med din RCS-miljö.

I vissa situationer kanske du vill göra så att ER-format använder parametrar som hör till en specifik juridisk person. I dessa scenarier ska du bara använda standardföretagsväxlaren. Se exemplet [Konfigurera ER-format att använda parametrar som angetts per juridisk person](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-configure-format.md).

## <a name="related-rcs-documentation"></a>Relaterad RCS-dokumentation

Mer information om relaterade komponenter finns i följande ämnen:

- **RCS:**

    - [Skapa ER-konfigurationer i RCS och överföra dem till den globala databasen](rcs-global-repo-upload.md)

- **Global databas:**

    - [Skapa ER-konfiguration & överföring till Global lagringsplats](rcs-global-repo-upload.md)
    - [Dela konfiguration i Global lagringsplats](rcs-global-repo-share-configuration.md)
    - [Utökad filtrering i global lagringsplats](enhanced-filtering-global-repo.md)
    - [Hämta ER-konfigurationer från den globala lagringsplatsen](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [Avbryta konfigurationer i den globala lagringsplatsen](discontinuing-configurations-rcs-global-repo.md)
    - [Regulatory Configuration Service (RCS) – Lagringsavskrivning för Lifecycle Services (LCS)](rcs-lcs-repo-dep-faq.md)

- **Globaliseringsfunktion:**

    - [Regulatory Configuration Service (RCS) - Globalizseringsfunktion](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)


## <a name="troubleshooting-rcs-sign-up"></a>Registrering för RCS-felsökning

När du registrerar dig för RCS från servicesidan kan du komma att stöta på ett problem som är relaterat till Azure Active Directory (Azure AD). Det felmeddelande som du får visar att registreringen för RCS för tillfället är inaktiverad och måste aktiveras innan du kan slutföra registreringsprocessen.

![Felmeddelande om RCS-inloggning.](media/01_RCSSignUpError.jpg)

Problemet beror på att du har blockerats från att registrera dig för ad-hoc-abonnemang, och `AllowAdHocSubscriptions`-egenskapen måste vara aktiverad i din klientorganisation. 

- Om din IT-avdelning hanterar organisationens Azure-klientorganisationer kontaktar du den avdelningen och rapporterar problemet.
- Om du ansvarar för hanteringen av dina Azure-klientorganisationer kan du åtgärda problemen genom att följa stegen i [Vad är registrering för självbetjäning för Azure Active Directory](/azure/active-directory/enterprise-users/directory-self-service-signup#how-do-i-control-self-service-settings).
