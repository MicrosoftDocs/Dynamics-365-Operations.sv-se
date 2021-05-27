---
title: Regulatory Configuration Service
description: Detta ämne innehåller en översikt över funktionerna i Regulatory Configuration Service (OMS) och förklarar hur du öppnar tjänsten.
author: JaneA07
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
ms.openlocfilehash: 1eeac7217290e0583fcecdf5b4b5b9153d266240
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019404"
---
# <a name="regulatory-configuration-service"></a><span data-ttu-id="a0663-103">Regulatory Configuration Service</span><span class="sxs-lookup"><span data-stu-id="a0663-103">Regulatory Configuration Service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a0663-104">Regulatory Configuration Service (RCS) är en fristående tjänst för design- och livscykelhantering för globaliseringsfunktioner utan kod/lite kod ("low-code").</span><span class="sxs-lookup"><span data-stu-id="a0663-104">Regulatory Configuration Service (RCS) is a standalone designer and lifecycle management service for no-code/low-code globalization functionality.</span></span> <span data-ttu-id="a0663-105">Med RCS kan globaliseringsintressenter utöka och anpassa viktiga globaliseringsområden för skatt, e-fakturering, lagstadgad rapportering, bank- och affärsdokument utan att behöva involvera utvecklare.</span><span class="sxs-lookup"><span data-stu-id="a0663-105">RCS lets globalization stakeholders extend and customize key globalization areas of tax, e-invoicing, regulatory reporting, banking, and business documents without having to involve developers.</span></span> <span data-ttu-id="a0663-106">Denna globaliseringsmetod utan kod/med lite kod ("low-code") gör globaliseringen enklare, snabbare och kostnadseffektivare att skapa eller utöka.</span><span class="sxs-lookup"><span data-stu-id="a0663-106">This no-code/low-code globalization approach makes globalization easier, faster, and more cost effective to create or extend.</span></span>

<span data-ttu-id="a0663-107">RCS tillhandahåller följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="a0663-107">RCS provides the following capabilities:</span></span>

- <span data-ttu-id="a0663-108">Stöd för alla funktioner som tillhandahålls av Elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="a0663-108">Support for all functionality that is provided by Electronic reporting (ER).</span></span>
- <span data-ttu-id="a0663-109">En förutsättning för att nya mikrotjänster för globalisering ska kunna konfigureras.</span><span class="sxs-lookup"><span data-stu-id="a0663-109">A prerequisite to configure new globalization microservices.</span></span>
- <span data-ttu-id="a0663-110">Stöd för elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="a0663-110">Support for Electronic Invoicing.</span></span> <span data-ttu-id="a0663-111">Mer information finns i [E-fakturering](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).</span><span class="sxs-lookup"><span data-stu-id="a0663-111">For more information, see [Electronic Invoicing](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).</span></span>
- <span data-ttu-id="a0663-112">Stöd för skatteberäkning.</span><span class="sxs-lookup"><span data-stu-id="a0663-112">Supports for Tax Calculation.</span></span> <span data-ttu-id="a0663-113">Mer information finns i [Skattetjänst](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).</span><span class="sxs-lookup"><span data-stu-id="a0663-113">For more information, see [Tax service](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).</span></span>
- <span data-ttu-id="a0663-114">Stöd för nya globaliseringsfunktioner som förenklar livscykelhanteringen av flerkomponentfunktioner och ger extra kapacitet att konfigurera åtgärder och ställa in funktionsparametrar.</span><span class="sxs-lookup"><span data-stu-id="a0663-114">Support for new globalization feature functionality that simplifies the lifecycle management of multi-component features and provides extra capability to configure actions and set up feature parameters.</span></span> <span data-ttu-id="a0663-115">Mer information finns i [Regulatory Configuration Service – förenklad hantering av globaliseringsfunktioner för globaliseringstjänster](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).</span><span class="sxs-lookup"><span data-stu-id="a0663-115">For more information, see [Regulatory Configuration Service – simplified globalization feature management for globalization services](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).</span></span>
- <span data-ttu-id="a0663-116">Stöd för centraliserad publicering, lagring och delning av anpassade konfigurationer i den globala databasen för att förenkla konfigurationshanteringen utan att Microsoft Dynamics Lifecycle Services (LCS) behöver användas.</span><span class="sxs-lookup"><span data-stu-id="a0663-116">Support for centralized publication, storage, and sharing of custom configurations in the Global repository to simplify configuration management without requiring the use of Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="access-rcs"></a><span data-ttu-id="a0663-117">Åtkomst till RCS</span><span class="sxs-lookup"><span data-stu-id="a0663-117">Access RCS</span></span>

<span data-ttu-id="a0663-118">Du kan registrera dig för eller logga in på RCS från [sidan Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="a0663-118">You can sign up for or sign in to RCS from the [Regulatory Configuration Service page](https://marketing.configure.global.dynamics.com/).</span></span>

![Registrering för/inloggning i RCS](media/202103_RCS%20Marketing%20page_updated_1.jpg)

<span data-ttu-id="a0663-120">På sidan **Regulatory Configuration Service** läser du igenom och godkänner tilläggsvillkoren för användningen av tjänster innan du väljer en av följande knappar:</span><span class="sxs-lookup"><span data-stu-id="a0663-120">On the **Regulatory Configuration Service** page, review and accept the supplemental terms and conditions for use of the service, and then select one of the following buttons:</span></span>

- <span data-ttu-id="a0663-121">**Registrera dig** om du använder tjänsten för första gången och använder en företags-e-postadress för att tillhandahålla en tjänstemiljö till din organisation</span><span class="sxs-lookup"><span data-stu-id="a0663-121">**Sign up** if you're a first-time user of the service, and you're using a business email address to provision your organization a service environment</span></span>
- <span data-ttu-id="a0663-122">**Logga in** om du redan tidigare har registrerat dig för tjänsten och vill komma åt organisationsmiljön</span><span class="sxs-lookup"><span data-stu-id="a0663-122">**Sign in** if you've previously signed up for the service, and you want to access your organization environment</span></span>

## <a name="regional-availability"></a><span data-ttu-id="a0663-123">Regional tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="a0663-123">Regional availability</span></span>

<span data-ttu-id="a0663-124">RCS är i allmänhet tillgängligt i följande regioner:</span><span class="sxs-lookup"><span data-stu-id="a0663-124">RCS is generally available in the following regions:</span></span>

- <span data-ttu-id="a0663-125">USA</span><span class="sxs-lookup"><span data-stu-id="a0663-125">United States</span></span>
- <span data-ttu-id="a0663-126">Indien</span><span class="sxs-lookup"><span data-stu-id="a0663-126">India</span></span>
- <span data-ttu-id="a0663-127">Frankrike</span><span class="sxs-lookup"><span data-stu-id="a0663-127">France</span></span>
- <span data-ttu-id="a0663-128">Europa</span><span class="sxs-lookup"><span data-stu-id="a0663-128">Europe</span></span>

<span data-ttu-id="a0663-129">En fullständig lista över regioner finns i [Dynamics 365 och Power Platform: Tillgänglighet, dataplats, språk och lokalisering](https://aka.ms/dynamics_365_international_availability_deck).</span><span class="sxs-lookup"><span data-stu-id="a0663-129">For a complete list of regions, see [Dynamics 365 and Power Platform: Availability, data location, language, and localization](https://aka.ms/dynamics_365_international_availability_deck).</span></span>

## <a name="related-rcs-documentation"></a><span data-ttu-id="a0663-130">Relaterad RCS-dokumentation</span><span class="sxs-lookup"><span data-stu-id="a0663-130">Related RCS documentation</span></span>

<span data-ttu-id="a0663-131">Mer information om att relaterade komponenter finns i följande dokumentation:</span><span class="sxs-lookup"><span data-stu-id="a0663-131">For more information about related components, see the following documentation:</span></span>

- <span data-ttu-id="a0663-132">**Global databas:**</span><span class="sxs-lookup"><span data-stu-id="a0663-132">**Global repository:**</span></span>

    - [<span data-ttu-id="a0663-133">Skapa ER-konfiguration & överföring till Global lagringsplats</span><span class="sxs-lookup"><span data-stu-id="a0663-133">Create ER configuration & upload to Global repo</span></span>](rcs-global-repo-upload.md)
    - [<span data-ttu-id="a0663-134">Dela konfiguration i Global lagringsplats</span><span class="sxs-lookup"><span data-stu-id="a0663-134">Share configuration in Global repo</span></span>](rcs-global-repo-share-configuration.md)
    - [<span data-ttu-id="a0663-135">Utökad filtrering i global lagringsplats</span><span class="sxs-lookup"><span data-stu-id="a0663-135">Enhanced filtering in Global repo</span></span>](enhanced-filtering-global-repo.md)
    - [<span data-ttu-id="a0663-136">Hämta ER-konfigurationer från den globala lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="a0663-136">Download ER configurations from the Global repository</span></span>](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [<span data-ttu-id="a0663-137">Avbryta konfigurationer i den globala lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="a0663-137">Discontinuing configurations in Global repo</span></span>](discontinuing-configurations-rcs-global-repo.md)

- <span data-ttu-id="a0663-138">**Globaliseringsfunktion:**</span><span class="sxs-lookup"><span data-stu-id="a0663-138">**Globalization feature:**</span></span>

    - [<span data-ttu-id="a0663-139">Regulatory Configuration Service (RCS) - Globalizseringsfunktion</span><span class="sxs-lookup"><span data-stu-id="a0663-139">Regulatory Configuration Service (RCS) - Globalization feature</span></span>](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)