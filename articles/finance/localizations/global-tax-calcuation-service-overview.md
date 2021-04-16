---
title: Skatteberäkningstjänst (förhandsversion)
description: Det här ämnet innehåller information om beräkningstjänstens övergripande omfattning och funktioner.
author: wangchen
ms.date: 03/02/2021
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
ms.openlocfilehash: 518d3fda7b97e55d23beea6a1ba0e50b44a7aa0e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818234"
---
# <a name="tax-calculation-service-preview"></a><span data-ttu-id="825ea-103">Skatteberäkningstjänst (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="825ea-103">Tax calculation service (Preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="825ea-104">Momsberäkningstjänsten är en hyperskalbar tjänst för flera innehavare som gör det möjligt för global tax engine att automatisera och förenkla bestämmandet av skatt och beräkningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="825ea-104">The tax calculation service is a hyper-scalable multitenant service that enables the global tax engine to automate and simplify the tax determination and calculation process.</span></span> <span data-ttu-id="825ea-105">Skattemotorn är helt konfigurerbar.</span><span class="sxs-lookup"><span data-stu-id="825ea-105">The tax engine is fully configurable.</span></span> <span data-ttu-id="825ea-106">Elementen som kan konfigureras är inklusive, men inte begränsat till, den momsbara datamodellen, momskoden, tillämplighetsmatrisen för moms och beräkningsformeln för skatt.</span><span class="sxs-lookup"><span data-stu-id="825ea-106">The elements that can be configured include, but aren't limited to, the taxable data model, tax code, tax applicability matrix, and tax calculation formula.</span></span> <span data-ttu-id="825ea-107">Momsmotorn körs på Microsoft Azure kärntjänsters plattform och erbjuder modern teknik och exponentiell skalbarhet.</span><span class="sxs-lookup"><span data-stu-id="825ea-107">The tax engine runs on the Microsoft Azure core services platform, and offers modern technology and exponential scalability.</span></span>

<span data-ttu-id="825ea-108">Beräkningstjänsten för moms går att integrera med Dynamics 365 Finance och Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="825ea-108">The tax calculation service integrates with Dynamics 365 Finance and Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="825ea-109">Så småningom kommer den också att integreras Dynamics 365 Project Operations, Dynamics 365 Commerce och andra applikationer från första och tredje part.</span><span class="sxs-lookup"><span data-stu-id="825ea-109">Eventually, it will also integrate with Dynamics 365 Project Operations, Dynamics 365 Commerce, and other first-party and third-party applications.</span></span>

<span data-ttu-id="825ea-110">Momsberäkningstjänsten är en Microsoft-baserad momsmotor som erbjuder exponentiell skalbarhet.</span><span class="sxs-lookup"><span data-stu-id="825ea-110">The tax calculation service is a Microsoft-based tax engine that offers exponential scalability.</span></span> <span data-ttu-id="825ea-111">Det kan hjälpa dig att utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="825ea-111">It can help you perform the following tasks:</span></span>

- <span data-ttu-id="825ea-112">Konfigurera beräkningstjänsten för skatt via Regulatory Configuration Service (RCS).</span><span class="sxs-lookup"><span data-stu-id="825ea-112">Configure the tax calculation service through Regulatory Configuration Service (RCS).</span></span> <span data-ttu-id="825ea-113">RCS är en förbättrad version av designern Elektronisk rapportering (ER) och är tillgänglig som en fristående tjänst.</span><span class="sxs-lookup"><span data-stu-id="825ea-113">RCS is an enhanced version of the Electronic reporting (ER) designer and is available as a standalone service.</span></span>
- <span data-ttu-id="825ea-114">Konfigurera momsmatrisen om du automatiskt vill bestämma momskoder och momssatser.</span><span class="sxs-lookup"><span data-stu-id="825ea-114">Configure the tax matrix to automatically determine tax codes and rates.</span></span>
- <span data-ttu-id="825ea-115">Konfigurera momsmatrisen om du automatiskt vill bestämma momsregistreringsnummer.</span><span class="sxs-lookup"><span data-stu-id="825ea-115">Configure the tax matrix to automatically determine the tax registration number.</span></span>
- <span data-ttu-id="825ea-116">Konfigurera designern för momsberäkning om du vill definiera formler och villkor.</span><span class="sxs-lookup"><span data-stu-id="825ea-116">Configure the tax calculation designer to define formulas and conditions.</span></span>
- <span data-ttu-id="825ea-117">Dela lösningen för skattebestämning och beräkning mellan juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="825ea-117">Share the tax determination and calculation solution across legal entities.</span></span>

<span data-ttu-id="825ea-118">Om du vill använda beräkningstjänsten för moms ska du installera tillägget för skatteberäkningstjänsten från projektet i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="825ea-118">To use the tax calculation service, install the tax calculation service add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="825ea-119">Slutför sedan inställningarna i RCS och aktivera skatteberäkningstjänsten i Finance och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="825ea-119">Then complete the setup in RCS, and enable the tax calculation service in Finance and Supply Chain Management.</span></span> <span data-ttu-id="825ea-120">För mer information, se [Kom igång med momstjänsten](https://go.microsoft.com/fwlink/?linkid=2138482).</span><span class="sxs-lookup"><span data-stu-id="825ea-120">For more information, see [Get started with tax service](https://go.microsoft.com/fwlink/?linkid=2138482).</span></span>

## <a name="availability"></a><span data-ttu-id="825ea-121">Tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="825ea-121">Availability</span></span>

<span data-ttu-id="825ea-122">Skatteberäkningstjänsten är bara tillgänglig i arbetsmiljöer och för valda kunder, via ett public preview-program.</span><span class="sxs-lookup"><span data-stu-id="825ea-122">The tax calculation service is available only in sandbox environments and to selected customers, through a public preview program.</span></span> <span data-ttu-id="825ea-123">Så småningom blir den allmänt tillgänglig för alla kunder och i produktionsmiljöer.</span><span class="sxs-lookup"><span data-stu-id="825ea-123">Eventually, it will become generally available to all customers and in production environments.</span></span>

<span data-ttu-id="825ea-124">Nya funktioner kommer även fortsättningsvis att levereras i skatteberäkningstjänsten.</span><span class="sxs-lookup"><span data-stu-id="825ea-124">New features will continue to be delivered in the tax calculation service.</span></span> <span data-ttu-id="825ea-125">Kontrollera därför den senaste dokumentationen ofta för att ta reda på disponering och område som stöds av funktionerna.</span><span class="sxs-lookup"><span data-stu-id="825ea-125">Therefore, be sure to check the most up-to-date documentation often to learn about the coverage and scope of supported features.</span></span>

<span data-ttu-id="825ea-126">Momsberäkningstjänsten distribueras i följande geologier för Azure.</span><span class="sxs-lookup"><span data-stu-id="825ea-126">The tax calculation service is deployed in the following Azure geographies.</span></span> <span data-ttu-id="825ea-127">Den kommer även att distribueras till fler Azure-geologer, baserat på kundernas behov:</span><span class="sxs-lookup"><span data-stu-id="825ea-127">It will also be deployed to more Azure geographies, based on customer needs:</span></span>

- <span data-ttu-id="825ea-128">USA</span><span class="sxs-lookup"><span data-stu-id="825ea-128">United States</span></span>
- <span data-ttu-id="825ea-129">Europa</span><span class="sxs-lookup"><span data-stu-id="825ea-129">Europe</span></span>
- <span data-ttu-id="825ea-130">Frankrike</span><span class="sxs-lookup"><span data-stu-id="825ea-130">France</span></span>
- <span data-ttu-id="825ea-131">Storbritannien</span><span class="sxs-lookup"><span data-stu-id="825ea-131">United Kingdom</span></span>

> [!NOTE]
> <span data-ttu-id="825ea-132">Beräkningstjänsten för moms har inte stöd för lokala distributioner av Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="825ea-132">The tax calculation service doesn't support on-premises deployments of Dynamics 365.</span></span> <span data-ttu-id="825ea-133">Den stöder inte heller tidigare versioner, till exempel Dynamics AX 2012.</span><span class="sxs-lookup"><span data-stu-id="825ea-133">It also doesn't support earlier versions, such as Dynamics AX 2012.</span></span>

## <a name="feature-highlights"></a><span data-ttu-id="825ea-134">Funktionens höjdpunkter</span><span class="sxs-lookup"><span data-stu-id="825ea-134">Feature highlights</span></span>

- <span data-ttu-id="825ea-135">Konfigurera momsmatrisen om du automatiskt vill bestämma och beräkna skatt</span><span class="sxs-lookup"><span data-stu-id="825ea-135">A configurable tax matrix to automatically determine and calculate tax</span></span>
- <span data-ttu-id="825ea-136">Stöd för flera momsregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="825ea-136">Support for multiple value-added tax (VAT) registration numbers</span></span>
- <span data-ttu-id="825ea-137">Överföringsorderstöd för bestämning och beräkning av skatter</span><span class="sxs-lookup"><span data-stu-id="825ea-137">Transfer order support for tax determination and calculation</span></span>
- <span data-ttu-id="825ea-138">Överföringsorder för att bestämma flera momsregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="825ea-138">Transfer order support for determination of multiple VAT registration numbers</span></span>

## <a name="supported-transactions"></a><span data-ttu-id="825ea-139">Transaktioner som stöds</span><span class="sxs-lookup"><span data-stu-id="825ea-139">Supported transactions</span></span>

<span data-ttu-id="825ea-140">Beräkningstjänsten för moms kan aktiveras av juridisk person och transaktion.</span><span class="sxs-lookup"><span data-stu-id="825ea-140">The tax calculation service can be enabled by legal entity and transaction.</span></span> <span data-ttu-id="825ea-141">Följande transaktioner stöds:</span><span class="sxs-lookup"><span data-stu-id="825ea-141">The following transactions are supported:</span></span>

- <span data-ttu-id="825ea-142">Försäljningsprocess</span><span class="sxs-lookup"><span data-stu-id="825ea-142">Sales process</span></span>

    - <span data-ttu-id="825ea-143">Försäljningsoffert</span><span class="sxs-lookup"><span data-stu-id="825ea-143">Sales quotation</span></span>
    - <span data-ttu-id="825ea-144">Försäljningsorder</span><span class="sxs-lookup"><span data-stu-id="825ea-144">Sales order</span></span>
    - <span data-ttu-id="825ea-145">Bekräftelse</span><span class="sxs-lookup"><span data-stu-id="825ea-145">Confirmation</span></span>
    - <span data-ttu-id="825ea-146">Plocklista</span><span class="sxs-lookup"><span data-stu-id="825ea-146">Picking list</span></span>
    - <span data-ttu-id="825ea-147">Följesedel</span><span class="sxs-lookup"><span data-stu-id="825ea-147">Packing slip</span></span>
    - <span data-ttu-id="825ea-148">Försäljningsfaktura</span><span class="sxs-lookup"><span data-stu-id="825ea-148">Sales invoice</span></span>
    - <span data-ttu-id="825ea-149">Kreditfaktura</span><span class="sxs-lookup"><span data-stu-id="825ea-149">Credit note</span></span>
    - <span data-ttu-id="825ea-150">Returorder</span><span class="sxs-lookup"><span data-stu-id="825ea-150">Return order</span></span>
    - <span data-ttu-id="825ea-151">Övriga avgifter för rubrik</span><span class="sxs-lookup"><span data-stu-id="825ea-151">Header miscellaneous charge</span></span>
    - <span data-ttu-id="825ea-152">Övriga avgifter för rad</span><span class="sxs-lookup"><span data-stu-id="825ea-152">Line miscellaneous charge</span></span>

- <span data-ttu-id="825ea-153">Inköpsprocess</span><span class="sxs-lookup"><span data-stu-id="825ea-153">Purchase process</span></span>

    - <span data-ttu-id="825ea-154">Inköpsorder</span><span class="sxs-lookup"><span data-stu-id="825ea-154">Purchase order</span></span>
    - <span data-ttu-id="825ea-155">Bekräftelse</span><span class="sxs-lookup"><span data-stu-id="825ea-155">Confirmation</span></span>
    - <span data-ttu-id="825ea-156">Inleveranslista</span><span class="sxs-lookup"><span data-stu-id="825ea-156">Receipts list</span></span>
    - <span data-ttu-id="825ea-157">Produktinleverans</span><span class="sxs-lookup"><span data-stu-id="825ea-157">Product receipt</span></span>
    - <span data-ttu-id="825ea-158">Inköpsfaktura</span><span class="sxs-lookup"><span data-stu-id="825ea-158">Purchase invoice</span></span>
    - <span data-ttu-id="825ea-159">Övriga avgifter för rubrik</span><span class="sxs-lookup"><span data-stu-id="825ea-159">Header miscellaneous charge</span></span>
    - <span data-ttu-id="825ea-160">Övriga avgifter för rad</span><span class="sxs-lookup"><span data-stu-id="825ea-160">Line miscellaneous charge</span></span>
    - <span data-ttu-id="825ea-161">Kreditfaktura</span><span class="sxs-lookup"><span data-stu-id="825ea-161">Credit note</span></span>
    - <span data-ttu-id="825ea-162">Returorder</span><span class="sxs-lookup"><span data-stu-id="825ea-162">Return order</span></span>
    - <span data-ttu-id="825ea-163">Inköpsrekvisition</span><span class="sxs-lookup"><span data-stu-id="825ea-163">Purchase requisition</span></span>
    - <span data-ttu-id="825ea-164">Övriga avgifter för inköpsrekvisitionsrad</span><span class="sxs-lookup"><span data-stu-id="825ea-164">Purchase requisition line miscellaneous charge</span></span>
    - <span data-ttu-id="825ea-165">Anbudsförfrågan</span><span class="sxs-lookup"><span data-stu-id="825ea-165">Request for quotation</span></span>
    - <span data-ttu-id="825ea-166">Övriga avgifter för anbudsförfråganrubriken</span><span class="sxs-lookup"><span data-stu-id="825ea-166">Request for quotation header miscellaneous charge</span></span>
    - <span data-ttu-id="825ea-167">Övriga avgifter för anbudsförfråganraden</span><span class="sxs-lookup"><span data-stu-id="825ea-167">Request for quotation line miscellaneous charge</span></span>

- <span data-ttu-id="825ea-168">Lagerprocess</span><span class="sxs-lookup"><span data-stu-id="825ea-168">Inventory process</span></span>

    - <span data-ttu-id="825ea-169">Överföringsorder - leverera</span><span class="sxs-lookup"><span data-stu-id="825ea-169">Transfer order – ship</span></span>
    - <span data-ttu-id="825ea-170">Överföringsorder - ta emot</span><span class="sxs-lookup"><span data-stu-id="825ea-170">Transfer order – receive</span></span>

## <a name="related-resources"></a><span data-ttu-id="825ea-171">Relaterade resurser</span><span class="sxs-lookup"><span data-stu-id="825ea-171">Related resources</span></span>

[<span data-ttu-id="825ea-172">Kom i gång med momstjänst</span><span class="sxs-lookup"><span data-stu-id="825ea-172">Get started with tax service</span></span>](https://go.microsoft.com/fwlink/?linkid=2138482)

[<span data-ttu-id="825ea-173">Flera momsregistreringsnummer</span><span class="sxs-lookup"><span data-stu-id="825ea-173">Multiple VAT registration number</span></span>](https://go.microsoft.com/fwlink/?linkid=2153387)

[<span data-ttu-id="825ea-174">Momsfunktionens stöd för överföringsorder</span><span class="sxs-lookup"><span data-stu-id="825ea-174">Tax feature support for transfer order</span></span>](https://go.microsoft.com/fwlink/?linkid=2153388)

[<span data-ttu-id="825ea-175">Så här bygger du anknytning i momstjänst</span><span class="sxs-lookup"><span data-stu-id="825ea-175">How to build extension in tax service</span></span>](https://go.microsoft.com/fwlink/?linkid=2138483)
