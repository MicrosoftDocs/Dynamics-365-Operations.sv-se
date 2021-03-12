---
title: Ställ in momsrapporteringskoder
description: Momsrapportkoderna refererar till ett fältnummer som anges i momsrapporten.
author: twheeloc
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxReportCollection
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 821d4abcffbca624382aa7709c02b857fcb6e349
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994525"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="37f4b-103">Ställ in momsrapporteringskoder</span><span class="sxs-lookup"><span data-stu-id="37f4b-103">Set up sales tax reporting codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="37f4b-104">Momsrapportkoderna refererar till ett fältnummer som anges i momsrapporten.</span><span class="sxs-lookup"><span data-stu-id="37f4b-104">The Sales tax reporting codes refer to a field number that's listed on a sales tax report.</span></span> <span data-ttu-id="37f4b-105">De används på landsspecifika rapportlayouter.</span><span class="sxs-lookup"><span data-stu-id="37f4b-105">They are used on country-specific report layouts.</span></span> <span data-ttu-id="37f4b-106">De används också på rapporten Momsbetalning per kod.</span><span class="sxs-lookup"><span data-stu-id="37f4b-106">They're also used on the Sales tax payment by code report.</span></span> <span data-ttu-id="37f4b-107">Rapporten visar momsbelopp för en kvittningsperiod som summeras för varje rapporteringskod.</span><span class="sxs-lookup"><span data-stu-id="37f4b-107">That report shows sales tax amounts for a settlement period summarized for each reporting code.</span></span> <span data-ttu-id="37f4b-108">När du har skapat momsrapporteringskoder kan du referera till koderna på rapportinställningssnabbflikarna, som du når från sidan **Momskod**.</span><span class="sxs-lookup"><span data-stu-id="37f4b-108">After you create Sales tax reporting codes, you can refer to those codes on the Report setup FastTabs, which you can access from the **Sales tax code** page.</span></span> 

<span data-ttu-id="37f4b-109">I den här registreringen används demonstrationsföretaget DEMF.</span><span class="sxs-lookup"><span data-stu-id="37f4b-109">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="37f4b-110">I **Navigeringsfönster**, gå till **Skatt > Inställningar > Moms > Momsrapporteringskoder**.</span><span class="sxs-lookup"><span data-stu-id="37f4b-110">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="37f4b-111">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="37f4b-111">Click **New**.</span></span>
3. <span data-ttu-id="37f4b-112">Välj den rapportlayout som rapporteringskoden tillhör.</span><span class="sxs-lookup"><span data-stu-id="37f4b-112">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="37f4b-113">Denna layout används för att filtrera de tillgängliga rapportkoderna för en momskod.</span><span class="sxs-lookup"><span data-stu-id="37f4b-113">This layout is used to filter the available reporting codes for a sales tax code.</span></span> <span data-ttu-id="37f4b-114">Varje momskod tillhör en kvittningsperiod som tillhör en skattemyndighet, som använder en rapportlayout.</span><span class="sxs-lookup"><span data-stu-id="37f4b-114">Each sales tax code belongs to a settlement period, which belongs to a Sales tax authority, which uses a report layout.</span></span>  
4. <span data-ttu-id="37f4b-115">Ange ett nummer i fältet **Rapporteringskod**.</span><span class="sxs-lookup"><span data-stu-id="37f4b-115">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="37f4b-116">Ange en beskrivning som ska visas på rapporter i fältet **Rapporttext**.</span><span class="sxs-lookup"><span data-stu-id="37f4b-116">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="37f4b-117">Ange en beskrivning för internt bruk i fältet **Kort beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="37f4b-117">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="37f4b-118">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="37f4b-118">Click **Save**.</span></span>

