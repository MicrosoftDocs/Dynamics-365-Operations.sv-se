---
title: Regulatory Configuration Service
description: Detta ämne innehåller en översikt över funktionerna i Regulatory Configuration Service (OMS) och förklarar hur du öppnar tjänsten.
author: JaneA07
ms.date: 06/04/2021
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
ms.openlocfilehash: 7f946988f124c814452e1774c700d5c7354f39b0
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216572"
---
# <a name="regulatory-configuration-service"></a><span data-ttu-id="17edb-103">Regulatory Configuration Service</span><span class="sxs-lookup"><span data-stu-id="17edb-103">Regulatory Configuration Service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="17edb-104">Regulatory Configuration Service (RCS) är en fristående tjänst för design- och livscykelhantering för globaliseringsfunktioner utan kod/lite kod ("low-code").</span><span class="sxs-lookup"><span data-stu-id="17edb-104">Regulatory Configuration Service (RCS) is a standalone designer and lifecycle management service for no-code/low-code globalization functionality.</span></span> <span data-ttu-id="17edb-105">Med RCS kan globaliseringsintressenter utöka och anpassa viktiga globaliseringsområden för skatt, e-fakturering, lagstadgad rapportering, bank- och affärsdokument utan att behöva involvera utvecklare.</span><span class="sxs-lookup"><span data-stu-id="17edb-105">RCS lets globalization stakeholders extend and customize key globalization areas of tax, e-invoicing, regulatory reporting, banking, and business documents without having to involve developers.</span></span> <span data-ttu-id="17edb-106">Denna globaliseringsmetod utan kod/med lite kod ("low-code") gör globaliseringen enklare, snabbare och kostnadseffektivare att skapa eller utöka.</span><span class="sxs-lookup"><span data-stu-id="17edb-106">This no-code/low-code globalization approach makes globalization easier, faster, and more cost effective to create or extend.</span></span>

<span data-ttu-id="17edb-107">RCS tillhandahåller följande funktioner:</span><span class="sxs-lookup"><span data-stu-id="17edb-107">RCS provides the following capabilities:</span></span>

- <span data-ttu-id="17edb-108">Stöd för alla funktioner som tillhandahålls av Elektronisk rapportering (ER).</span><span class="sxs-lookup"><span data-stu-id="17edb-108">Support for all functionality that is provided by Electronic reporting (ER).</span></span>
- <span data-ttu-id="17edb-109">En förutsättning för att nya mikrotjänster för globalisering ska kunna konfigureras.</span><span class="sxs-lookup"><span data-stu-id="17edb-109">A prerequisite to configure new globalization microservices.</span></span>
- <span data-ttu-id="17edb-110">Stöd för elektronisk fakturering.</span><span class="sxs-lookup"><span data-stu-id="17edb-110">Support for Electronic Invoicing.</span></span> <span data-ttu-id="17edb-111">Mer information finns i [E-fakturering](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).</span><span class="sxs-lookup"><span data-stu-id="17edb-111">For more information, see [Electronic Invoicing](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/electronic-invoicing-add-on-dynamics-365-ga).</span></span>
- <span data-ttu-id="17edb-112">Stöd för skatteberäkning.</span><span class="sxs-lookup"><span data-stu-id="17edb-112">Supports for Tax Calculation.</span></span> <span data-ttu-id="17edb-113">Mer information finns i [Skattetjänst](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).</span><span class="sxs-lookup"><span data-stu-id="17edb-113">For more information, see [Tax service](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/tax-service-preview).</span></span>
- <span data-ttu-id="17edb-114">Stöd för nya globaliseringsfunktioner som förenklar livscykelhanteringen av flerkomponentfunktioner och ger extra kapacitet att konfigurera åtgärder och ställa in funktionsparametrar.</span><span class="sxs-lookup"><span data-stu-id="17edb-114">Support for new globalization feature functionality that simplifies the lifecycle management of multi-component features and provides extra capability to configure actions and set up feature parameters.</span></span> <span data-ttu-id="17edb-115">Mer information finns i [Regulatory Configuration Service – förenklad hantering av globaliseringsfunktioner för globaliseringstjänster](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).</span><span class="sxs-lookup"><span data-stu-id="17edb-115">For more information, see [Regulatory Configuration Service – simplified globalization feature management for globalization services](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services).</span></span>
- <span data-ttu-id="17edb-116">Stöd för centraliserad publicering, lagring och delning av anpassade konfigurationer i den globala databasen för att förenkla konfigurationshanteringen utan att Microsoft Dynamics Lifecycle Services (LCS) behöver användas.</span><span class="sxs-lookup"><span data-stu-id="17edb-116">Support for centralized publication, storage, and sharing of custom configurations in the Global repository to simplify configuration management without requiring the use of Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="access-rcs"></a><span data-ttu-id="17edb-117">Åtkomst till RCS</span><span class="sxs-lookup"><span data-stu-id="17edb-117">Access RCS</span></span>

<span data-ttu-id="17edb-118">Du kan registrera dig för eller logga in på RCS från [sidan Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="17edb-118">You can sign up for or sign in to RCS from the [Regulatory Configuration Service page](https://marketing.configure.global.dynamics.com/).</span></span>

![Registrering för/inloggning i RCS](media/202103_RCS%20Marketing%20page_updated_1.jpg)

<span data-ttu-id="17edb-120">På sidan **Regulatory Configuration Service** läser du igenom och godkänner tilläggsvillkoren för användningen av tjänster innan du väljer en av följande knappar:</span><span class="sxs-lookup"><span data-stu-id="17edb-120">On the **Regulatory Configuration Service** page, review and accept the supplemental terms and conditions for use of the service, and then select one of the following buttons:</span></span>

- <span data-ttu-id="17edb-121">**Registrera dig** om du använder tjänsten för första gången och använder en företags-e-postadress för att tillhandahålla en tjänstemiljö till din organisation</span><span class="sxs-lookup"><span data-stu-id="17edb-121">**Sign up** if you're a first-time user of the service, and you're using a business email address to provision your organization a service environment</span></span>
- <span data-ttu-id="17edb-122">**Logga in** om du redan tidigare har registrerat dig för tjänsten och vill komma åt organisationsmiljön</span><span class="sxs-lookup"><span data-stu-id="17edb-122">**Sign in** if you've previously signed up for the service, and you want to access your organization environment</span></span>

## <a name="regional-availability"></a><span data-ttu-id="17edb-123">Regional tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="17edb-123">Regional availability</span></span>

<span data-ttu-id="17edb-124">RCS är i allmänhet tillgängligt i följande regioner:</span><span class="sxs-lookup"><span data-stu-id="17edb-124">RCS is generally available in the following regions:</span></span>

- <span data-ttu-id="17edb-125">USA</span><span class="sxs-lookup"><span data-stu-id="17edb-125">United States</span></span>
- <span data-ttu-id="17edb-126">Indien</span><span class="sxs-lookup"><span data-stu-id="17edb-126">India</span></span>
- <span data-ttu-id="17edb-127">Frankrike</span><span class="sxs-lookup"><span data-stu-id="17edb-127">France</span></span>
- <span data-ttu-id="17edb-128">Europa</span><span class="sxs-lookup"><span data-stu-id="17edb-128">Europe</span></span>

<span data-ttu-id="17edb-129">En fullständig lista över regioner finns i [Dynamics 365 och Power Platform: Tillgänglighet, dataplats, språk och lokalisering](https://aka.ms/dynamics_365_international_availability_deck).</span><span class="sxs-lookup"><span data-stu-id="17edb-129">For a complete list of regions, see [Dynamics 365 and Power Platform: Availability, data location, language, and localization](https://aka.ms/dynamics_365_international_availability_deck).</span></span>

## <a name="rcs-default-company"></a><span data-ttu-id="17edb-130">RCS-standardföretag</span><span class="sxs-lookup"><span data-stu-id="17edb-130">RCS default company</span></span>

<span data-ttu-id="17edb-131">Designtidsfunktionen som används i RCS delas av alla företag.</span><span class="sxs-lookup"><span data-stu-id="17edb-131">Design time functionality that is used in RCS is shared across all companies.</span></span> <span data-ttu-id="17edb-132">Det finns inte någon företagsspecifik funktion.</span><span class="sxs-lookup"><span data-stu-id="17edb-132">There is no company-specific functionality.</span></span> <span data-ttu-id="17edb-133">Därför rekommenderar vi att du använder ett företag, **DAT**, med din RCS-miljö.</span><span class="sxs-lookup"><span data-stu-id="17edb-133">Therefore, we recommend that you use one company, **DAT**, with your RCS environment.</span></span>

<span data-ttu-id="17edb-134">I vissa situationer kanske du vill göra så att ER-format använder parametrar som hör till en specifik juridisk person.</span><span class="sxs-lookup"><span data-stu-id="17edb-134">However, in some scenarios, you might want to make ER formats use parameters that are related to a specific legal entity.</span></span> <span data-ttu-id="17edb-135">I dessa scenarier ska du bara använda standardföretagsväxlaren.</span><span class="sxs-lookup"><span data-stu-id="17edb-135">In these scenarios only, you should use the default company switcher.</span></span> <span data-ttu-id="17edb-136">Se exemplet [Konfigurera ER-format att använda parametrar som angetts per juridisk person](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-configure-format.md).</span><span class="sxs-lookup"><span data-stu-id="17edb-136">For an example, see [Configure ER format to use parameters that are specified per legal entity](../../fin-ops-core/dev-itpro/analytics/er-app-specific-parameters-configure-format.md).</span></span>

## <a name="related-rcs-documentation"></a><span data-ttu-id="17edb-137">Relaterad RCS-dokumentation</span><span class="sxs-lookup"><span data-stu-id="17edb-137">Related RCS documentation</span></span>

<span data-ttu-id="17edb-138">Mer information om relaterade komponenter finns i följande ämnen:</span><span class="sxs-lookup"><span data-stu-id="17edb-138">For more information about related components, see the following topics:</span></span>

- <span data-ttu-id="17edb-139">**RCS:**</span><span class="sxs-lookup"><span data-stu-id="17edb-139">**RCS:**</span></span>

    - [<span data-ttu-id="17edb-140">Skapa ER-konfigurationer i RCS och överföra dem till den globala databasen</span><span class="sxs-lookup"><span data-stu-id="17edb-140">Create ER configurations in RCS and upload them to the Global repository</span></span>](rcs-global-repo-upload.md)

- <span data-ttu-id="17edb-141">**Global databas:**</span><span class="sxs-lookup"><span data-stu-id="17edb-141">**Global repository:**</span></span>

    - [<span data-ttu-id="17edb-142">Skapa ER-konfiguration & överföring till Global lagringsplats</span><span class="sxs-lookup"><span data-stu-id="17edb-142">Create ER configuration & upload to Global repo</span></span>](rcs-global-repo-upload.md)
    - [<span data-ttu-id="17edb-143">Dela konfiguration i Global lagringsplats</span><span class="sxs-lookup"><span data-stu-id="17edb-143">Share configuration in Global repo</span></span>](rcs-global-repo-share-configuration.md)
    - [<span data-ttu-id="17edb-144">Utökad filtrering i global lagringsplats</span><span class="sxs-lookup"><span data-stu-id="17edb-144">Enhanced filtering in Global repo</span></span>](enhanced-filtering-global-repo.md)
    - [<span data-ttu-id="17edb-145">Hämta ER-konfigurationer från den globala lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="17edb-145">Download ER configurations from the Global repository</span></span>](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md)
    - [<span data-ttu-id="17edb-146">Avbryta konfigurationer i den globala lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="17edb-146">Discontinuing configurations in Global repo</span></span>](discontinuing-configurations-rcs-global-repo.md)
    - [<span data-ttu-id="17edb-147">Regulatory Configuration Service (RCS) – Lagringsavskrivning för Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="17edb-147">Regulatory Configuration Service (RCS) – Lifecycle Services (LCS) storage deprecation</span></span>](rcs-lcs-repo-dep-faq.md)

- <span data-ttu-id="17edb-148">**Globaliseringsfunktion:**</span><span class="sxs-lookup"><span data-stu-id="17edb-148">**Globalization feature:**</span></span>

    - [<span data-ttu-id="17edb-149">Regulatory Configuration Service (RCS) - Globalizseringsfunktion</span><span class="sxs-lookup"><span data-stu-id="17edb-149">Regulatory Configuration Service (RCS) - Globalization feature</span></span>](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-finance/regulatory-configuration-service-simplified-globalization-feature-management-globalization-services)


## <a name="troubleshooting-rcs-sign-up"></a><span data-ttu-id="17edb-150">Registrering för RCS-felsökning</span><span class="sxs-lookup"><span data-stu-id="17edb-150">Troubleshooting RCS sign-up</span></span>

<span data-ttu-id="17edb-151">När du registrerar dig för RCS från servicesidan kan du komma att stöta på ett problem som är relaterat till Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="17edb-151">When you sign up for RCS from the service page, you might encounter an issue that is related to Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="17edb-152">Det felmeddelande som du får visar att registreringen för RCS för tillfället är inaktiverad och måste aktiveras innan du kan slutföra registreringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="17edb-152">The error message that you receive indicates that sign-up for RCS is currently turned off and must be turned on before you can complete the sign-up process.</span></span>

![Felmeddelande om RCS-inloggning](media/01_RCSSignUpError.jpg)

<span data-ttu-id="17edb-154">Problemet beror på att du har blockerats från att registrera dig för ad-hoc-abonnemang, och `AllowAdHocSubscriptions`-egenskapen måste vara aktiverad i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="17edb-154">The issue occurs because you're blocked from signing up for ad-hoc subscriptions, and the `AllowAdHocSubscriptions` property must be enabled in your tenant.</span></span> 

- <span data-ttu-id="17edb-155">Om din IT-avdelning hanterar organisationens Azure-klientorganisationer kontaktar du den avdelningen och rapporterar problemet.</span><span class="sxs-lookup"><span data-stu-id="17edb-155">If your IT department manages your organization's Azure tenants, contact that department to report the issue.</span></span>
- <span data-ttu-id="17edb-156">Om du ansvarar för hanteringen av dina Azure-klientorganisationer kan du åtgärda problemen genom att följa stegen i [Vad är registrering för självbetjäning för Azure Active Directory](/azure/active-directory/enterprise-users/directory-self-service-signup#how-do-i-control-self-service-settings).</span><span class="sxs-lookup"><span data-stu-id="17edb-156">If you're responsible for managing your Azure tenants, you can fix the issues by following the steps in [What is self-service sign-up for Azure Active Directory](/azure/active-directory/enterprise-users/directory-self-service-signup#how-do-i-control-self-service-settings).</span></span>
