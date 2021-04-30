---
title: Skatteberäkning (förhandsversion)
description: Detta ämne innehåller information om skatteberäkningsfunktionens övergripande omfattning och funktioner.
author: wangchen
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 3df952e0632807e55f176e63dc2047be5e622ec2
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892359"
---
# <a name="tax-calculation-preview"></a><span data-ttu-id="97c13-103">Skatteberäkning (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="97c13-103">Tax Calculation (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="97c13-104">Skatteberäkningen är en hyperskalbar tjänst för flera innehavare som gör det möjligt för den globala skattemotorn (Global Tax Engine) att automatisera och förenkla bestämmandet och beräkningsprocessen för skatt.</span><span class="sxs-lookup"><span data-stu-id="97c13-104">Tax Calculation is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="97c13-105">Skattemotorn är helt konfigurerbar.</span><span class="sxs-lookup"><span data-stu-id="97c13-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="97c13-106">Elementen som kan konfigureras är inklusive, men inte begränsat till, den beskattningsbara datamodellen, skattekoden, tillämplighetsmatrisen för skatt och beräkningsformeln för skatt.</span><span class="sxs-lookup"><span data-stu-id="97c13-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="97c13-107">Skattemotorn körs på Microsoft Azure kärntjänsters plattform och erbjuder modern teknik och exponentiell skalbarhet.</span><span class="sxs-lookup"><span data-stu-id="97c13-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="97c13-108">Beräkningstjänsten för skatt går att integrera med Dynamics 365 Finance och Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="97c13-108">Tax Calculation integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="97c13-109">Så småningom kommer den också att integreras Dynamics 365 Project Operations, Dynamics 365 Commerce och andra applikationer från första och tredje part.</span><span class="sxs-lookup"><span data-stu-id="97c13-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="97c13-110">Skatteberäkningstjänsten är en mikrotjänstbaserad skattemotor som erbjuder exponentiell skalbarhet.</span><span class="sxs-lookup"><span data-stu-id="97c13-110">Tax Calculation is a microservice-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="97c13-111">Det kan hjälpa dig att utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="97c13-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="97c13-112">Konfigurera beräkningstjänsten för skatt via Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="97c13-112">Configure Tax Calculation through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="97c13-113">RCS är en förbättrad version av designern Elektronisk rapportering (ER) och är tillgänglig som en fristående tjänst.</span><span class="sxs-lookup"><span data-stu-id="97c13-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="97c13-114">Konfigurera skattematrisen om du automatiskt vill bestämma skattekoder och skattesatser.</span><span class="sxs-lookup"><span data-stu-id="97c13-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="97c13-115">Konfigurera skattematrisen om du automatiskt vill bestämma skatteregistreringsnummer.</span><span class="sxs-lookup"><span data-stu-id="97c13-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="97c13-116">Konfigurera designern för skatteberäkning om du vill definiera formler och villkor.</span><span class="sxs-lookup"><span data-stu-id="97c13-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="97c13-117">Dela lösningen för skattebestämning och beräkning mellan juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="97c13-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="97c13-118">Om du vill använda beräkningstjänsten för skatte ska du installera tillägget för skatteberäkningstjänsten från projektet i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="97c13-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="97c13-119">Slutför sedan inställningarna i RCS och aktivera skatteberäkningstjänsten i Finance och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="97c13-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="97c13-120">För mer information, se [Kom igång med skattetjänsten](./global-get-started-with-tax-calculation-service.md).</span><span class="sxs-lookup"><span data-stu-id="97c13-120">For more information, see [Get started with tax service](./global-get-started-with-tax-calculation-service.md).</span></span>

## <a name="availability"></a><span data-ttu-id="97c13-121">Tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="97c13-121">Availability</span></span>

<span data-ttu-id="97c13-122">Skatteberäkningstjänsten är bara tillgänglig i sandbox-miljöer och för utvalda kunder, detta via en allmänt tillgänglig förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="97c13-122">Tax Calculation is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="97c13-123">Så småningom blir den allmänt tillgänglig för alla kunder och i produktionsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="97c13-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="97c13-124">Nya funktioner kommer att tillkomma - kontrollera därför den senaste dokumentationen ofta för att ta reda på omfattningen av de funktioner som stöds.</span><span class="sxs-lookup"><span data-stu-id="97c13-124">New features will continue to be delivered, so be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="97c13-125">Skatteberäkningstjänsten distribueras på följande Azure-områden:</span><span class="sxs-lookup"><span data-stu-id="97c13-125">Tax Calculation is deployed in the following Azure geographies.</span></span> <span data-ttu-id="97c13-126">Den kommer även att distribueras till fler Azure-geologer, baserat på kundernas behov:</span><span class="sxs-lookup"><span data-stu-id="97c13-126">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="97c13-127">USA</span><span class="sxs-lookup"><span data-stu-id="97c13-127">United States</span></span>
- <span data-ttu-id="97c13-128">Europa</span><span class="sxs-lookup"><span data-stu-id="97c13-128">Europe</span></span>

> [!NOTE]
> <span data-ttu-id="97c13-129">Skatteberäkningstjänsten har inte stöd för lokala distributioner av Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="97c13-129">Tax Calculation doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="97c13-130">Den stöder inte heller tidigare versioner, till exempel Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="97c13-130">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="97c13-131">Funktionens höjdpunkter</span><span class="sxs-lookup"><span data-stu-id="97c13-131">Feature highlights</span></span>

- <span data-ttu-id="97c13-132">Konfigurera skattematrisen om du automatiskt vill bestämma och beräkna skatt</span><span class="sxs-lookup"><span data-stu-id="97c13-132">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="97c13-133">Stöd för flera skatteregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="97c13-133">Support for multiple tax registration numbers</span></span>
- <span data-ttu-id="97c13-134">Överföringsorderstöd för bestämning och beräkning av skatter</span><span class="sxs-lookup"><span data-stu-id="97c13-134">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="97c13-135">Stöd för överföringsorder med syfte att bestämma flera skatteregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="97c13-135">Transfer order support for determination of multiple tax registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="97c13-136">Transaktioner som stöds</span><span class="sxs-lookup"><span data-stu-id="97c13-136">Supported transactions</span></span>

<span data-ttu-id="97c13-137">Skatteberäkningstjänsten kan aktiveras av juridisk person och transaktion.</span><span class="sxs-lookup"><span data-stu-id="97c13-137">Tax Calculation can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="97c13-138">Följande transaktioner stöds:</span><span class="sxs-lookup"><span data-stu-id="97c13-138">The following transactions are supported:</span></span>

- <span data-ttu-id="97c13-139">Försäljningsprocess</span><span class="sxs-lookup"><span data-stu-id="97c13-139">Sales process</span></span>

    - <span data-ttu-id="97c13-140">Försäljningsoffert</span><span class="sxs-lookup"><span data-stu-id="97c13-140">Sales quotation</span></span>
    - <span data-ttu-id="97c13-141">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="97c13-141">Sales order</span></span>
    - <span data-ttu-id="97c13-142">Bekräftelse</span><span class="sxs-lookup"><span data-stu-id="97c13-142">Confirmation</span></span>
    - <span data-ttu-id="97c13-143">Plocklista</span><span class="sxs-lookup"><span data-stu-id="97c13-143">Picking list</span></span>
    - <span data-ttu-id="97c13-144">Följesedel</span><span class="sxs-lookup"><span data-stu-id="97c13-144">Packing slip</span></span>
    - <span data-ttu-id="97c13-145">Försäljningsfaktura</span><span class="sxs-lookup"><span data-stu-id="97c13-145">Sales invoice</span></span>
    - <span data-ttu-id="97c13-146">Kreditfaktura</span><span class="sxs-lookup"><span data-stu-id="97c13-146">Credit note</span></span>
    - <span data-ttu-id="97c13-147">Returorder</span><span class="sxs-lookup"><span data-stu-id="97c13-147">Return order</span></span>
    - <span data-ttu-id="97c13-148">Övriga avgifter för rubrik</span><span class="sxs-lookup"><span data-stu-id="97c13-148">Header miscellaneous charge</span></span>
    - <span data-ttu-id="97c13-149">Övriga avgifter för rad</span><span class="sxs-lookup"><span data-stu-id="97c13-149">Line miscellaneous charge</span></span>

- <span data-ttu-id="97c13-150">Inköpsprocess</span><span class="sxs-lookup"><span data-stu-id="97c13-150">Purchase process</span></span>

    - <span data-ttu-id="97c13-151">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="97c13-151">Purchase order</span></span>
    - <span data-ttu-id="97c13-152">Bekräftelse</span><span class="sxs-lookup"><span data-stu-id="97c13-152">Confirmation</span></span>
    - <span data-ttu-id="97c13-153">Inleveranslista</span><span class="sxs-lookup"><span data-stu-id="97c13-153">Receipts list</span></span>
    - <span data-ttu-id="97c13-154">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="97c13-154">Product receipt</span></span>
    - <span data-ttu-id="97c13-155">Inköpsfaktura</span><span class="sxs-lookup"><span data-stu-id="97c13-155">Purchase invoice</span></span>
    - <span data-ttu-id="97c13-156">Övriga avgifter för rubrik</span><span class="sxs-lookup"><span data-stu-id="97c13-156">Header miscellaneous charge</span></span>
    - <span data-ttu-id="97c13-157">Övriga avgifter för rad</span><span class="sxs-lookup"><span data-stu-id="97c13-157">Line miscellaneous charge</span></span>
    - <span data-ttu-id="97c13-158">Kreditfaktura</span><span class="sxs-lookup"><span data-stu-id="97c13-158">Credit note</span></span>
    - <span data-ttu-id="97c13-159">Returorder</span><span class="sxs-lookup"><span data-stu-id="97c13-159">Return order</span></span>
    - <span data-ttu-id="97c13-160">Inköpsrekvisition</span><span class="sxs-lookup"><span data-stu-id="97c13-160">Purchase requisition</span></span>
    - <span data-ttu-id="97c13-161">Övriga avgifter för inköpsrekvisitionsrad</span><span class="sxs-lookup"><span data-stu-id="97c13-161">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="97c13-162">Anbudsförfrågan</span><span class="sxs-lookup"><span data-stu-id="97c13-162">Request for quotation</span></span>
    - <span data-ttu-id="97c13-163">Övriga avgifter för anbudsförfråganrubriken</span><span class="sxs-lookup"><span data-stu-id="97c13-163">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="97c13-164">Övriga avgifter för anbudsförfråganraden</span><span class="sxs-lookup"><span data-stu-id="97c13-164">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="97c13-165">Lagerprocess</span><span class="sxs-lookup"><span data-stu-id="97c13-165">Inventory process</span></span>

    - <span data-ttu-id="97c13-166">Överföringsorder - leverera</span><span class="sxs-lookup"><span data-stu-id="97c13-166">Transfer order – ship</span></span>
    - <span data-ttu-id="97c13-167">Överföringsorder - ta emot</span><span class="sxs-lookup"><span data-stu-id="97c13-167">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="97c13-168">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="97c13-168">Related resources</span></span>

[<span data-ttu-id="97c13-169">Kom i gång med skattetjänst</span><span class="sxs-lookup"><span data-stu-id="97c13-169">Get started with tax service</span></span>](./global-get-started-with-tax-calculation-service.md)

[<span data-ttu-id="97c13-170">Flera momsregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="97c13-170">Multiple VAT registration number</span></span>](./emea-multiple-vat-registration-numbers.md)

[<span data-ttu-id="97c13-171">Skattefunktionsstöd för överföringsorder</span><span class="sxs-lookup"><span data-stu-id="97c13-171">Tax feature support for transfer order</span></span>](./tasks/tax-feature-support-for-transfer-order.md)

[<span data-ttu-id="97c13-172">Så här skapar du tillägg i skattetjänst</span><span class="sxs-lookup"><span data-stu-id="97c13-172">How to build extension in tax service</span></span>](./tax-service-add-data-fields-tax-integration-by-extension.md)