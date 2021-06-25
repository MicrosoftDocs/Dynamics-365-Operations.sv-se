---
title: Skatteberäkning (förhandsversion)
description: Detta ämne innehåller information om skatteberäkningsfunktionens övergripande omfattning och funktioner.
author: wangchen
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 9daa6e001200d03a2639974fb6de618d77ddf09d
ms.sourcegitcommit: cb282e8d2306ab71adf80a84346a6863d2d019e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2021
ms.locfileid: "6184111"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="c26de-103">Skatteberäkning (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="c26de-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="c26de-104">Skatteberäkningen är en hyperskalbar tjänst för flera innehavare som gör det möjligt för den globala skattemotorn (Global Tax Engine) att automatisera och förenkla bestämmandet och beräkningsprocessen för skatt.</span><span class="sxs-lookup"><span data-stu-id="c26de-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="c26de-105">Skattemotorn är helt konfigurerbar.</span><span class="sxs-lookup"><span data-stu-id="c26de-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="c26de-106">Elementen som kan konfigureras är inklusive, men inte begränsat till, den beskattningsbara datamodellen, skattekoden, tillämplighetsmatrisen för skatt och beräkningsformeln för skatt.</span><span class="sxs-lookup"><span data-stu-id="c26de-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="c26de-107">Skattemotorn körs på Microsoft Azure kärntjänsters plattform och erbjuder modern teknik och exponentiell skalbarhet.</span><span class="sxs-lookup"><span data-stu-id="c26de-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="c26de-108">Beräkningstjänsten för skatt går att integrera med Dynamics 365 Finance och Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c26de-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="c26de-109">Så småningom kommer den också att integreras Dynamics 365 Project Operations, Dynamics 365 Commerce och andra applikationer från första och tredje part.</span><span class="sxs-lookup"><span data-stu-id="c26de-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c26de-110">När du aktiverar tjänsten Skatteberäkning kan vissa operationer på relaterade data utföras i ett annat datacenter än det datacenter som underhåller dina servicedata.</span><span class="sxs-lookup"><span data-stu-id="c26de-110">When you enable the Tax Calculation service, some operations on related data might be performed in a data center other than the data center that maintains your service data.</span></span> <span data-ttu-id="c26de-111">Gå igenom [användarvillkoren](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) innan du aktiverar tjänsten för momsberäkning.</span><span class="sxs-lookup"><span data-stu-id="c26de-111">Review the [Terms and Conditions](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md) before you enable the Tax Calculation service.</span></span> <span data-ttu-id="c26de-112">Din sekretess är viktig för oss.</span><span class="sxs-lookup"><span data-stu-id="c26de-112">Your privacy is important to us.</span></span> <span data-ttu-id="c26de-113">Mer information finns i vår [sekretesspolicy](https://go.microsoft.com/fwlink/?LinkId=521839).</span><span class="sxs-lookup"><span data-stu-id="c26de-113">To learn more, read our [Privacy Statement](https://go.microsoft.com/fwlink/?LinkId=521839).</span></span>

<span data-ttu-id="c26de-114">Skatteberäkningstjänsten är en mikrotjänstbaserad skattemotor som erbjuder exponentiell skalbarhet.</span><span class="sxs-lookup"><span data-stu-id="c26de-114">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="c26de-115">Det kan hjälpa dig att utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="c26de-115">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="c26de-116">Konfigurera beräkningstjänsten för skatt via Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="c26de-116">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="c26de-117">RCS är en förbättrad version av designern Elektronisk rapportering (ER) och är tillgänglig som en fristående tjänst.</span><span class="sxs-lookup"><span data-stu-id="c26de-117">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="c26de-118">Konfigurera skattematrisen om du automatiskt vill bestämma skattekoder och skattesatser.</span><span class="sxs-lookup"><span data-stu-id="c26de-118">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="c26de-119">Konfigurera skattematrisen om du automatiskt vill bestämma skatteregistreringsnummer.</span><span class="sxs-lookup"><span data-stu-id="c26de-119">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="c26de-120">Konfigurera designern för skatteberäkning om du vill definiera formler och villkor.</span><span class="sxs-lookup"><span data-stu-id="c26de-120">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="c26de-121">Dela lösningen för skattebestämning och beräkning mellan juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="c26de-121">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="c26de-122">Om du vill använda beräkningstjänsten för skatte ska du installera tillägget för skatteberäkningstjänsten från projektet i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c26de-122">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="c26de-123">Slutför sedan inställningarna i RCS och aktivera skatteberäkningstjänsten i Finance och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c26de-123">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="c26de-124">För mer information, se [Kom igång med skattetjänsten](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="c26de-124">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="c26de-125">Tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="c26de-125">Availability</span></span>

<span data-ttu-id="c26de-126">Skatteberäkningstjänsten är bara tillgänglig i sandbox-miljöer och för utvalda kunder, detta via en allmänt tillgänglig förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="c26de-126">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="c26de-127">Så småningom blir den allmänt tillgänglig för alla kunder och i produktionsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="c26de-127">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="c26de-128">Nya funktioner kommer att tillkomma - kontrollera därför den senaste dokumentationen ofta för att ta reda på omfattningen av de funktioner som stöds.</span><span class="sxs-lookup"><span data-stu-id="c26de-128">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="c26de-129">Skatteberäkningstjänsten distribueras på följande Azure-områden:</span><span class="sxs-lookup"><span data-stu-id="c26de-129">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="c26de-130">Den kommer även att distribueras till fler Azure-geologer, baserat på kundernas behov:</span><span class="sxs-lookup"><span data-stu-id="c26de-130">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="c26de-131">USA</span><span class="sxs-lookup"><span data-stu-id="c26de-131">United States</span></span>
- <span data-ttu-id="c26de-132">Europa</span><span class="sxs-lookup"><span data-stu-id="c26de-132">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="c26de-133">Skatteberäkningstjänsten har inte stöd för lokala distributioner av Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c26de-133">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="c26de-134">Den stöder inte heller tidigare versioner, till exempel Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="c26de-134">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="c26de-135">Funktionens höjdpunkter</span><span class="sxs-lookup"><span data-stu-id="c26de-135">Feature highlights</span></span>

- <span data-ttu-id="c26de-136">Konfigurera skattematrisen om du automatiskt vill bestämma och beräkna skatt</span><span class="sxs-lookup"><span data-stu-id="c26de-136">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="c26de-137">Stöd för flera skatteregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="c26de-137">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="c26de-138">Överföringsorderstöd för bestämning och beräkning av skatter</span><span class="sxs-lookup"><span data-stu-id="c26de-138">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="c26de-139">Stöd för överföringsorder med syfte att bestämma flera skatteregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="c26de-139">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="c26de-140">Transaktioner som stöds</span><span class="sxs-lookup"><span data-stu-id="c26de-140">Supported transactions</span></span>

<span data-ttu-id="c26de-141">Skatteberäkningstjänsten kan aktiveras av juridisk person och transaktion.</span><span class="sxs-lookup"><span data-stu-id="c26de-141">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="c26de-142">Följande transaktioner stöds:</span><span class="sxs-lookup"><span data-stu-id="c26de-142">The following transactions are supported:</span></span>

- <span data-ttu-id="c26de-143">Försäljningsprocess</span><span class="sxs-lookup"><span data-stu-id="c26de-143">Sales process</span></span>

    - <span data-ttu-id="c26de-144">Försäljningsoffert</span><span class="sxs-lookup"><span data-stu-id="c26de-144">Sales quotation</span></span>
    - <span data-ttu-id="c26de-145">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="c26de-145">Sales order</span></span>
    - <span data-ttu-id="c26de-146">Bekräftelse</span><span class="sxs-lookup"><span data-stu-id="c26de-146">Confirmation</span></span>
    - <span data-ttu-id="c26de-147">Plocklista</span><span class="sxs-lookup"><span data-stu-id="c26de-147">Picking list</span></span>
    - <span data-ttu-id="c26de-148">Följesedel</span><span class="sxs-lookup"><span data-stu-id="c26de-148">Packing slip</span></span>
    - <span data-ttu-id="c26de-149">Försäljningsfaktura</span><span class="sxs-lookup"><span data-stu-id="c26de-149">Sales invoice</span></span>
    - <span data-ttu-id="c26de-150">Kreditfaktura</span><span class="sxs-lookup"><span data-stu-id="c26de-150">Credit note</span></span>
    - <span data-ttu-id="c26de-151">Returorder</span><span class="sxs-lookup"><span data-stu-id="c26de-151">Return order</span></span>
    - <span data-ttu-id="c26de-152">Övriga avgifter för rubrik</span><span class="sxs-lookup"><span data-stu-id="c26de-152">Header miscellaneous charge</span></span>
    - <span data-ttu-id="c26de-153">Övriga avgifter för rad</span><span class="sxs-lookup"><span data-stu-id="c26de-153">Line miscellaneous charge</span></span>

- <span data-ttu-id="c26de-154">Inköpsprocess</span><span class="sxs-lookup"><span data-stu-id="c26de-154">Purchase process</span></span>

    - <span data-ttu-id="c26de-155">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="c26de-155">Purchase order</span></span>
    - <span data-ttu-id="c26de-156">Bekräftelse</span><span class="sxs-lookup"><span data-stu-id="c26de-156">Confirmation</span></span>
    - <span data-ttu-id="c26de-157">Inleveranslista</span><span class="sxs-lookup"><span data-stu-id="c26de-157">Receipts list</span></span>
    - <span data-ttu-id="c26de-158">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="c26de-158">Product receipt</span></span>
    - <span data-ttu-id="c26de-159">Inköpsfaktura</span><span class="sxs-lookup"><span data-stu-id="c26de-159">Purchase invoice</span></span>
    - <span data-ttu-id="c26de-160">Övriga avgifter för rubrik</span><span class="sxs-lookup"><span data-stu-id="c26de-160">Header miscellaneous charge</span></span>
    - <span data-ttu-id="c26de-161">Övriga avgifter för rad</span><span class="sxs-lookup"><span data-stu-id="c26de-161">Line miscellaneous charge</span></span>
    - <span data-ttu-id="c26de-162">Kreditfaktura</span><span class="sxs-lookup"><span data-stu-id="c26de-162">Credit note</span></span>
    - <span data-ttu-id="c26de-163">Returorder</span><span class="sxs-lookup"><span data-stu-id="c26de-163">Return order</span></span>
    - <span data-ttu-id="c26de-164">Inköpsrekvisition</span><span class="sxs-lookup"><span data-stu-id="c26de-164">Purchase requisition</span></span>
    - <span data-ttu-id="c26de-165">Övriga avgifter för inköpsrekvisitionsrad</span><span class="sxs-lookup"><span data-stu-id="c26de-165">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="c26de-166">Anbudsförfrågan</span><span class="sxs-lookup"><span data-stu-id="c26de-166">Request for quotation</span></span>
    - <span data-ttu-id="c26de-167">Övriga avgifter för anbudsförfråganrubriken</span><span class="sxs-lookup"><span data-stu-id="c26de-167">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="c26de-168">Övriga avgifter för anbudsförfråganraden</span><span class="sxs-lookup"><span data-stu-id="c26de-168">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="c26de-169">Lagerprocess</span><span class="sxs-lookup"><span data-stu-id="c26de-169">Inventory process</span></span>

    - <span data-ttu-id="c26de-170">Överföringsorder - leverera</span><span class="sxs-lookup"><span data-stu-id="c26de-170">Transfer order – ship</span></span>
    - <span data-ttu-id="c26de-171">Överföringsorder - ta emot</span><span class="sxs-lookup"><span data-stu-id="c26de-171">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="c26de-172">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="c26de-172">Related resources</span></span>

[<span data-ttu-id="c26de-173">Kom i gång med skattetjänst</span><span class="sxs-lookup"><span data-stu-id="c26de-173">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="c26de-174">Flera momsregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="c26de-174">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="c26de-175">Skattefunktionsstöd för överföringsorder</span><span class="sxs-lookup"><span data-stu-id="c26de-175">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="c26de-176">Så här skapar du tillägg i skattetjänst</span><span class="sxs-lookup"><span data-stu-id="c26de-176">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)
