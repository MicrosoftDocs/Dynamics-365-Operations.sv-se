---
title: Felsöka inställningar för kassaflödesprognoser
description: Detta ämne innehåller svar på frågor som du kan ha när du konfigurerar kassaflödesprognoser. Det avhandlar vanliga frågor och svar (FAQ) om hur du ställer in kassaflöde, uppdateringar av kassaflöde och Power BI-kassaflöde.
author: panolte
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7b4760d7a0d0c14e2df8df20c2f81ec41e077cc0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827324"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a><span data-ttu-id="fa09b-104">Felsöka inställningar för kassaflödesprognoser</span><span class="sxs-lookup"><span data-stu-id="fa09b-104">Troubleshoot cash flow forecasting setup</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fa09b-105">Detta ämne innehåller svar på frågor som du kan ha när du konfigurerar kassaflödesprognoser.</span><span class="sxs-lookup"><span data-stu-id="fa09b-105">This topic provides answers to questions that you might have when you configure cash flow forecasting.</span></span> <span data-ttu-id="fa09b-106">Det avhandlar vanliga frågor och svar (FAQ) om hur du ställer in kassaflöde, uppdateringar av kassaflöde och Power BI-kassaflöde.</span><span class="sxs-lookup"><span data-stu-id="fa09b-106">It addresses frequently asked questions (FAQ) about the setup for cash flow, updates to cash flow, and cash flow Power BI.</span></span>

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a><span data-ttu-id="fa09b-107">Varför visas kassaflöde endast för en enda juridisk person?</span><span class="sxs-lookup"><span data-stu-id="fa09b-107">Why is cash flow shown for only one legal entity?</span></span>

<span data-ttu-id="fa09b-108">Kassaflödesprognoser konfigureras och beräknas per juridisk person.</span><span class="sxs-lookup"><span data-stu-id="fa09b-108">Cash flow forecasting is configured and calculated per legal entity.</span></span> <span data-ttu-id="fa09b-109">Power BI-rapporter och funktionen för kassaflödesprognoser i Finance Insights visar resultaten.</span><span class="sxs-lookup"><span data-stu-id="fa09b-109">Power BI reports and the cash flow forecasts capability in Finance insights show the results.</span></span>

<span data-ttu-id="fa09b-110">Kassaflödesprognoser måste ställas in för varje enskild juridisk person som du vill visa en prognos för.</span><span class="sxs-lookup"><span data-stu-id="fa09b-110">Cash flow forecasting must be set up for each legal entity that you want to see a forecast for.</span></span> <span data-ttu-id="fa09b-111">Granska konfigurationen för kassaflödesprognoser i alla dina juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="fa09b-111">Review the configuration of cash flow forecasting in all your legal entities.</span></span> <span data-ttu-id="fa09b-112">Du kan också granska konfigurationen för alla juridiska personer för kassaflödesprognos och kontrollera att dessa är inställda på det sätt som du har tänkt dig.</span><span class="sxs-lookup"><span data-stu-id="fa09b-112">Alternatively, review the configuration of all the legal entities for cash flow forecasting, and make sure that they are set as you intended.</span></span>

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a><span data-ttu-id="fa09b-113">Varför visar Power BI inte alla kassaflödesdata?</span><span class="sxs-lookup"><span data-stu-id="fa09b-113">Why doesn't Power BI show all the cash flow data?</span></span>

<span data-ttu-id="fa09b-114">Flera steg måste utföras innan kassaflödesprognoser kan visas i Power BI-vyer.</span><span class="sxs-lookup"><span data-stu-id="fa09b-114">Several steps must be completed before cash flow forecasts can appear in Power BI views.</span></span> <span data-ttu-id="fa09b-115">Granska följande checklista och se till att varje steg har slutförts:</span><span class="sxs-lookup"><span data-stu-id="fa09b-115">Review the following checklist, and make sure that every step has been completed:</span></span>

- <span data-ttu-id="fa09b-116">Ställ in kassaflödet för varje juridisk person.</span><span class="sxs-lookup"><span data-stu-id="fa09b-116">Set up cash flow for each legal entity.</span></span>
- <span data-ttu-id="fa09b-117">Ange systemets valuta och systemets valutakurstyp i redovisningsparametrarna.</span><span class="sxs-lookup"><span data-stu-id="fa09b-117">In General ledger parameters, set the system currency and the system exchange rate type.</span></span>
- <span data-ttu-id="fa09b-118">Ställ in redovisningsvalutan och valutakurstypen.</span><span class="sxs-lookup"><span data-stu-id="fa09b-118">Set the ledger accounting currency and the exchange rate type.</span></span>
- <span data-ttu-id="fa09b-119">Ange valutakurserna mellan transaktionsvalutan och redovisningsvalutan.</span><span class="sxs-lookup"><span data-stu-id="fa09b-119">Enter exchange rates between the transaction currency and the accounting currency.</span></span>
- <span data-ttu-id="fa09b-120">Ange valutakurserna mellan redovisningsvalutan och systemvalutan.</span><span class="sxs-lookup"><span data-stu-id="fa09b-120">Enter exchange rates between the accounting currency and the system currency.</span></span>
- <span data-ttu-id="fa09b-121">Ange valutakurserna mellan redovisningsvalutan och respektive bankvaluta.</span><span class="sxs-lookup"><span data-stu-id="fa09b-121">Enter exchange rates between the accounting currency and each bank currency.</span></span>

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a><span data-ttu-id="fa09b-122">Varför fungerade kassaflödet i Power BI i tidigare versioner men är nu tomt?</span><span class="sxs-lookup"><span data-stu-id="fa09b-122">Why did cash flow Power BI work in previous versions but is now blank?</span></span>

<span data-ttu-id="fa09b-123">Kontrollera att mätningarna "Kassaflödesmått V2" och "LedgerCovLiquidityMeasurement" från Entitetsarkivet har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="fa09b-123">Verify that the "Cash flow measure V2" and "LedgerCovLiquidityMeasurement" measurements from Entity store have been configured.</span></span> <span data-ttu-id="fa09b-124">Mer information om hur du gör en arbeta med data i enhetslagring, se [Power BI-integrering med enhetslagring](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md).</span><span class="sxs-lookup"><span data-stu-id="fa09b-124">For more information about how to work with data in Entity store, see [Power BI integration with Entity store](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md).</span></span> <span data-ttu-id="fa09b-125">Kontrollera att alla steg som behövs för att visa Power BI innehåll har slutförts.</span><span class="sxs-lookup"><span data-stu-id="fa09b-125">Verify that all the steps that are required to view Power BI content have been completed.</span></span> <span data-ttu-id="fa09b-126">Mer information finns i [Kassaöversikt Power BI-innehåll](Cash-Overview-Power-BI-content.md).</span><span class="sxs-lookup"><span data-stu-id="fa09b-126">For more information, see [Cash overview Power BI content](Cash-Overview-Power-BI-content.md).</span></span>

## <a name="have-the-entity-store-entities-been-refreshed"></a><span data-ttu-id="fa09b-127">Har Entitetsarkivets entiteter uppdaterats?</span><span class="sxs-lookup"><span data-stu-id="fa09b-127">Have the Entity store entities been refreshed?</span></span>

<span data-ttu-id="fa09b-128">Du måste uppdatera dina entiteter regelbundet för att se till att datan är aktuell och korrekt.</span><span class="sxs-lookup"><span data-stu-id="fa09b-128">You must periodically refresh your entities to ensure that the data is current and accurate.</span></span> <span data-ttu-id="fa09b-129">Du uppdaterar en specifik entitet manuellt genom att gå till **Systemadministration \> Inställningar \> Entitetsarkiv**, välja eniteten och sedan **Uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="fa09b-129">To manually refresh a specific entity, go to **System administration \> Setup \> Entity store**, select the entity, and then select **Refresh**.</span></span> <span data-ttu-id="fa09b-130">Det går också att uppdatera data automatiskt.</span><span class="sxs-lookup"><span data-stu-id="fa09b-130">The data can also be updated automatically.</span></span> <span data-ttu-id="fa09b-131">På sidan **Entitetsarkiv** anger du alternativet **Automatisk uppdatering aktiverad** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="fa09b-131">On the **Entity store** page, set the **Automatic refresh enabled** option to **Yes**.</span></span>

## <a name="which-calculation-method-should-be-used-when-calculating-cash-flow-forecasts"></a><span data-ttu-id="fa09b-132">Vilken beräkningsmetod ska användas vid beräkning av kassaflödesprognoser?</span><span class="sxs-lookup"><span data-stu-id="fa09b-132">Which calculation method should be used when calculating cash flow forecasts?</span></span>

<span data-ttu-id="fa09b-133">Beräkningsmetod för kassaflödesprognos har två viktiga alternativ.</span><span class="sxs-lookup"><span data-stu-id="fa09b-133">The Cash flow forecast calculation method has two important selection options.</span></span> <span data-ttu-id="fa09b-134">Med alternativet **Nytt** beräknas kassaflödesprognoser för nya dokument och dokument som har ändrats sedan det senaste batchjobbet kördes.</span><span class="sxs-lookup"><span data-stu-id="fa09b-134">The **New** option will calculate cash flow forecasts for new documents and documents that have changed since the last batch job ran.</span></span> <span data-ttu-id="fa09b-135">Det här alternativet gör att processen blir snabbare eftersom den bearbetar en mindre delmängd av dokumenten.</span><span class="sxs-lookup"><span data-stu-id="fa09b-135">This option tends to run faster because it processes a smaller subset of documents.</span></span> <span data-ttu-id="fa09b-136">Alternativet **Summa** beräknar om kassaflödesprognoser för varje dokument i systemet.</span><span class="sxs-lookup"><span data-stu-id="fa09b-136">The **Total** option will recalculate cash flow forecasts for every document in the system.</span></span> <span data-ttu-id="fa09b-137">Det här alternativet tar längre tid eftersom det har mer arbete att slutföra.</span><span class="sxs-lookup"><span data-stu-id="fa09b-137">This option takes more time because it has more work to complete.</span></span>

### <a name="how-do-i-improve-the-performance-of-the-cash-flow-forecasting-recurring-batch-job"></a><span data-ttu-id="fa09b-138">Hur kan jag förbättra prestandan för kassaflödesprognoser för återkommande batchjobb?</span><span class="sxs-lookup"><span data-stu-id="fa09b-138">How do I improve the performance of the cash flow forecasting recurring batch job?</span></span>

<span data-ttu-id="fa09b-139">Vi rekommenderar att du kör kassaflödesprognosen en gång om dagen när belastningen är låg med den **Nytt** beräkningsmetoden.</span><span class="sxs-lookup"><span data-stu-id="fa09b-139">We recommend running your cash flow forecast once each day during the off-peak hours using the **New** calculation method.</span></span> <span data-ttu-id="fa09b-140">Vi rekommenderar att du använder den här metoden sex dagar per vecka.</span><span class="sxs-lookup"><span data-stu-id="fa09b-140">We recommend using this approach six days per week.</span></span> <span data-ttu-id="fa09b-141">Kör sedan en kassaflödesprognos en gång per vecka med hjälp av beräkningsmetoden **Summa** för dagen med den minsta aktivitetsmängden.</span><span class="sxs-lookup"><span data-stu-id="fa09b-141">Then run a cash flow forecast once each week using the **Total** calculation method on the day with the least amount of activity.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

