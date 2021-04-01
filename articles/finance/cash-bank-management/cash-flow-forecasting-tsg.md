---
title: Felsöka inställningar för kassaflödesprognoser
description: Detta ämne innehåller svar på frågor som du kan ha när du konfigurerar kassaflödesprognoser. Det avhandlar vanliga frågor och svar (FAQ) om hur du ställer in kassaflöde, uppdateringar av kassaflöde och Power BI-kassaflöde.
author: panolte
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d1cde9321259753bd0cacab3706c7f8455598ff3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232499"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a><span data-ttu-id="dc308-104">Felsöka inställningar för kassaflödesprognoser</span><span class="sxs-lookup"><span data-stu-id="dc308-104">Troubleshoot cash flow forecasting setup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dc308-105">Detta ämne innehåller svar på frågor som du kan ha när du konfigurerar kassaflödesprognoser.</span><span class="sxs-lookup"><span data-stu-id="dc308-105">This topic provides answers to questions that you might have when you configure cash flow forecasting.</span></span> <span data-ttu-id="dc308-106">Det avhandlar vanliga frågor och svar (FAQ) om hur du ställer in kassaflöde, uppdateringar av kassaflöde och Power BI-kassaflöde.</span><span class="sxs-lookup"><span data-stu-id="dc308-106">It addresses frequently asked questions (FAQ) about the setup for cash flow, updates to cash flow, and cash flow Power BI.</span></span>

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a><span data-ttu-id="dc308-107">Varför visas kassaflöde endast för en enda juridisk person?</span><span class="sxs-lookup"><span data-stu-id="dc308-107">Why is cash flow shown for only one legal entity?</span></span>

<span data-ttu-id="dc308-108">Kassaflödesprognoser konfigureras och beräknas per juridisk person.</span><span class="sxs-lookup"><span data-stu-id="dc308-108">Cash flow forecasting is configured and calculated per legal entity.</span></span> <span data-ttu-id="dc308-109">Power BI-rapporter och funktionen för kassaflödesprognoser i Finance Insights visar resultaten.</span><span class="sxs-lookup"><span data-stu-id="dc308-109">Power BI reports and the cash flow forecasts capability in Finance insights show the results.</span></span>

<span data-ttu-id="dc308-110">Kassaflödesprognoser måste ställas in för varje enskild juridisk person som du vill visa en prognos för.</span><span class="sxs-lookup"><span data-stu-id="dc308-110">Cash flow forecasting must be set up for each legal entity that you want to see a forecast for.</span></span> <span data-ttu-id="dc308-111">Granska konfigurationen för kassaflödesprognoser i alla dina juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="dc308-111">Review the configuration of cash flow forecasting in all your legal entities.</span></span> <span data-ttu-id="dc308-112">Du kan också granska konfigurationen för alla juridiska personer för kassaflödesprognos och kontrollera att dessa är inställda på det sätt som du har tänkt dig.</span><span class="sxs-lookup"><span data-stu-id="dc308-112">Alternatively, review the configuration of all the legal entities for cash flow forecasting, and make sure that they are set as you intended.</span></span>

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a><span data-ttu-id="dc308-113">Varför visar Power BI inte alla kassaflödesdata?</span><span class="sxs-lookup"><span data-stu-id="dc308-113">Why doesn't Power BI show all the cash flow data?</span></span>

<span data-ttu-id="dc308-114">Flera steg måste utföras innan kassaflödesprognoser kan visas i Power BI-vyer.</span><span class="sxs-lookup"><span data-stu-id="dc308-114">Several steps must be completed before cash flow forecasts can appear in Power BI views.</span></span> <span data-ttu-id="dc308-115">Granska följande checklista och se till att varje steg har slutförts:</span><span class="sxs-lookup"><span data-stu-id="dc308-115">Review the following checklist, and make sure that every step has been completed:</span></span>

- <span data-ttu-id="dc308-116">Ställ in kassaflödet för varje juridisk person.</span><span class="sxs-lookup"><span data-stu-id="dc308-116">Set up cash flow for each legal entity.</span></span>
- <span data-ttu-id="dc308-117">Ange systemets valuta och systemets valutakurstyp i redovisningsparametrarna.</span><span class="sxs-lookup"><span data-stu-id="dc308-117">In General ledger parameters, set the system currency and the system exchange rate type.</span></span>
- <span data-ttu-id="dc308-118">Ställ in redovisningsvalutan och valutakurstypen.</span><span class="sxs-lookup"><span data-stu-id="dc308-118">Set the ledger accounting currency and the exchange rate type.</span></span>
- <span data-ttu-id="dc308-119">Ange valutakurserna mellan transaktionsvalutan och redovisningsvalutan.</span><span class="sxs-lookup"><span data-stu-id="dc308-119">Enter exchange rates between the transaction currency and the accounting currency.</span></span>
- <span data-ttu-id="dc308-120">Ange valutakurserna mellan redovisningsvalutan och systemvalutan.</span><span class="sxs-lookup"><span data-stu-id="dc308-120">Enter exchange rates between the accounting currency and the system currency.</span></span>
- <span data-ttu-id="dc308-121">Ange valutakurserna mellan redovisningsvalutan och respektive bankvaluta.</span><span class="sxs-lookup"><span data-stu-id="dc308-121">Enter exchange rates between the accounting currency and each bank currency.</span></span>

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a><span data-ttu-id="dc308-122">Varför fungerade kassaflödet i Power BI i tidigare versioner men är nu tomt?</span><span class="sxs-lookup"><span data-stu-id="dc308-122">Why did cash flow Power BI work in previous versions but is now blank?</span></span>

<span data-ttu-id="dc308-123">Kontrollera att mätningarna "Kassaflödesmått V2" och "LedgerCovLiquidityMeasurement" från Entitetsarkivet har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="dc308-123">Verify that the "Cash flow measure V2" and "LedgerCovLiquidityMeasurement" measurements from Entity store have been configured.</span></span> <span data-ttu-id="dc308-124">Mer information om hur du arbetar med data i Entitetsarkivet finns i [Power BI-integrering med Entitetsarkivet](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Kontrollera att alla steg som behövs för att visa Power BI-innehåll har slutförts.</span><span class="sxs-lookup"><span data-stu-id="dc308-124">For more information about how to work with data in Entity store, see [Power BI integration with Entity store](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Verify that all the steps that are required to view Power BI content have been completed.</span></span> <span data-ttu-id="dc308-125">Mer information finns i [Kassaöversikt Power BI-innehåll](Cash-Overview-Power-BI-content.md).</span><span class="sxs-lookup"><span data-stu-id="dc308-125">For more information, see [Cash overview Power BI content](Cash-Overview-Power-BI-content.md).</span></span>

## <a name="have-the-entity-store-entities-been-refreshed"></a><span data-ttu-id="dc308-126">Har Entitetsarkivets entiteter uppdaterats?</span><span class="sxs-lookup"><span data-stu-id="dc308-126">Have the Entity store entities been refreshed?</span></span>

<span data-ttu-id="dc308-127">Du måste uppdatera dina entiteter regelbundet för att se till att datan är aktuell och korrekt.</span><span class="sxs-lookup"><span data-stu-id="dc308-127">You must periodically refresh your entities to ensure that the data is current and accurate.</span></span> <span data-ttu-id="dc308-128">Du uppdaterar en specifik entitet manuellt genom att gå till **Systemadministration \> Inställningar \> Entitetsarkiv**, välja eniteten och sedan **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="dc308-128">To manually refresh a specific entity, go to **System administration \> Setup \> Entity store**, select the entity, and then select **Refresh**.</span></span> <span data-ttu-id="dc308-129">Det går också att uppdatera data automatiskt.</span><span class="sxs-lookup"><span data-stu-id="dc308-129">The data can also be updated automatically.</span></span> <span data-ttu-id="dc308-130">På sidan **Entitetsarkiv** anger du alternativet **Automatisk uppdatering aktiverad** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="dc308-130">On the **Entity store** page, set the **Automatic refresh enabled** option to **Yes**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]