---
title: Använd externa data i kassaflödesprognoser (förhandsversion)
description: I det här ämnes beskrivs de konfigurationssteg som du måste utföra så att externa data kan anges i eller importeras till kassaflödesprognoser.
author: rcarlson
manager: AnnBe
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 801327dc54f6d4cfef7a9f062395e29846783e8f
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644955"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a><span data-ttu-id="97a92-103">Använd externa data i kassaflödesprognoser (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="97a92-103">Use external data in cash flow forecasts (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="97a92-104">Externa data kan anges i eller importeras till kassaflödesprognoser.</span><span class="sxs-lookup"><span data-stu-id="97a92-104">External data can be entered or imported into cash flow forecasts.</span></span> <span data-ttu-id="97a92-105">I det här avsnittet beskrivs de konfigurationssteg som är specifika för användningen av externa data och som gör att externa data kan inkluderas i en kassaflödesprognos.</span><span class="sxs-lookup"><span data-stu-id="97a92-105">This topic describes the setup steps that are specific to the use of external data and that enable the external data to be included in a cash flow forecast.</span></span>

## <a name="external-data-setup"></a><span data-ttu-id="97a92-106">Konfigurera externa data</span><span class="sxs-lookup"><span data-stu-id="97a92-106">External data setup</span></span>

<span data-ttu-id="97a92-107">Använd fliken **Extern källa** på sidan **Kassaflödesprognosinställningar** (**Kassa- och bankhantering \> Kassaflödeprognoser**) om du vill ange inställningar som stöder användning av externa data i kassaflödesprognoser.</span><span class="sxs-lookup"><span data-stu-id="97a92-107">Use the **External source** tab on the **Cash flow forecast setup** page (**Cash and bank management \> Cash flow forecasting**) to enter settings that support the use of external data in cash flow forecasts.</span></span>

<span data-ttu-id="97a92-108">Mer information om konfigurationen finns i [Kassaflödesprognoser](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).</span><span class="sxs-lookup"><span data-stu-id="97a92-108">For more information about the setup, see [Cash flow forecasting](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).</span></span>

<span data-ttu-id="97a92-109">Om du vill ange externa data för kassaflödesprognoser kan du använda Öppna i Excel-upplevelsen för att ange och ändra externa data.</span><span class="sxs-lookup"><span data-stu-id="97a92-109">To enter external data for cash flow forecasts, you can use the Open in Excel experience for entering and modifying external data.</span></span> <span data-ttu-id="97a92-110">Välj knappen **Externa data** och välj sedan antingen **Lägg till externa data** eller **Redigera befintliga externa data**.</span><span class="sxs-lookup"><span data-stu-id="97a92-110">Select the **External data** button, and then select either **Add External Data** or **Edit existing external data**.</span></span> <span data-ttu-id="97a92-111">När Microsoft Excel-filen öppnas kan du ange information i följande fält:</span><span class="sxs-lookup"><span data-stu-id="97a92-111">When the Microsoft Excel file is opened, you can enter information in the following fields:</span></span>

- <span data-ttu-id="97a92-112">**Åtkomst-ID**</span><span class="sxs-lookup"><span data-stu-id="97a92-112">**Entry ID**</span></span>
- <span data-ttu-id="97a92-113">**Beskrivning** (valfritt)</span><span class="sxs-lookup"><span data-stu-id="97a92-113">**Description** (optional)</span></span>
- <span data-ttu-id="97a92-114">**Namn på extern källa** – Välj ett av de värden i listan som du definierade när du konfigurerade Ekonomiinsikter.</span><span class="sxs-lookup"><span data-stu-id="97a92-114">**External Source name** – Select one of the values in the list that you defined when you set up Finance Insights.</span></span>
- <span data-ttu-id="97a92-115">**Juridisk person**</span><span class="sxs-lookup"><span data-stu-id="97a92-115">**Legal Entity**</span></span>
- <span data-ttu-id="97a92-116">**Datum**</span><span class="sxs-lookup"><span data-stu-id="97a92-116">**Date**</span></span>
- <span data-ttu-id="97a92-117">**Belopp i transaktionsvaluta**</span><span class="sxs-lookup"><span data-stu-id="97a92-117">**Amount in transaction currency**</span></span>
- <span data-ttu-id="97a92-118">**Valutakod**</span><span class="sxs-lookup"><span data-stu-id="97a92-118">**Currency Code**</span></span>
- <span data-ttu-id="97a92-119">**Standarddimension** (valfritt)</span><span class="sxs-lookup"><span data-stu-id="97a92-119">**Default Dimension** (optional)</span></span>
- <span data-ttu-id="97a92-120">**Dokumentnummer** (valfritt)</span><span class="sxs-lookup"><span data-stu-id="97a92-120">**Document number** (optional)</span></span>
- <span data-ttu-id="97a92-121">**Kontonummer** (valfritt)</span><span class="sxs-lookup"><span data-stu-id="97a92-121">**Account number** (optional)</span></span>
- <span data-ttu-id="97a92-122">**Kontonamn** (valfritt)</span><span class="sxs-lookup"><span data-stu-id="97a92-122">**Account name** (optional)</span></span>

## <a name="importing-external-data-by-using-the-data-management-framework"></a><span data-ttu-id="97a92-123">Importera externa data med hjälp av datahanteringsramverket</span><span class="sxs-lookup"><span data-stu-id="97a92-123">Importing external data by using the Data Management framework</span></span>

<span data-ttu-id="97a92-124">Du kan importera externa data för kassaflödesprognoser genom att använda arbetsytan **Datahantering** och den entitet som har namnet **Extern källpost för kassaflödesprognos**.</span><span class="sxs-lookup"><span data-stu-id="97a92-124">You can import external data for cash flow forecasts by using the **Data Management** workspace and the entity that is named **Cash flow forecast external source entry**.</span></span>

<span data-ttu-id="97a92-125">Dessutom, om du måste flytta konfigurationsdata från en miljö till en annan, är följande entitetsområde tillgänglig för konfigurationstabellerna som krävs:</span><span class="sxs-lookup"><span data-stu-id="97a92-125">Additionally, if you must move setup data from one environment to another, the following entities area available for the setup tables that are required:</span></span>

- <span data-ttu-id="97a92-126">Konfiguration av extern kassaflödesprognoskälla</span><span class="sxs-lookup"><span data-stu-id="97a92-126">Cash flow forecast external source setup</span></span>
- <span data-ttu-id="97a92-127">Konfiguration av extern källa för kassaflödesprognos – juridisk person</span><span class="sxs-lookup"><span data-stu-id="97a92-127">Cash flow forecast external source legal entity setup</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="97a92-128">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="97a92-128">Privacy notice</span></span>
<span data-ttu-id="97a92-129">Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="97a92-129">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>