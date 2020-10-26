---
title: Ställ in momsrapporteringskoder
description: Momsrapportkoderna refererar till ett fältnummer i momsrapporten.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6c18f4fb0db31a959647bb10d2b99d940646676e
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976803"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="e31e4-103">Ställ in momsrapporteringskoder</span><span class="sxs-lookup"><span data-stu-id="e31e4-103">Set up sales tax reporting codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e31e4-104">Momsrapportkoderna refererar till ett fältnummer i momsrapporten.</span><span class="sxs-lookup"><span data-stu-id="e31e4-104">The Sales tax reporting codes refer to a field number on a sales tax report.</span></span> <span data-ttu-id="e31e4-105">Dessa används för landsspecifika rapportlayouter och rapporten Momsbetalning per kod om du vill skriva ut momsbelopp för en kvittningsperiod som summeras per rapporteringskod.</span><span class="sxs-lookup"><span data-stu-id="e31e4-105">They are used on country specific report layouts and the Sales tax payment by code report to print sales tax amounts for a settlement period summarized per reporting code.</span></span> <span data-ttu-id="e31e4-106">När du har skapat momsrapporteringskoder kan du referera till dem på rapportinställningssnabbflikarna på momskodsidan.</span><span class="sxs-lookup"><span data-stu-id="e31e4-106">After you create Sales tax reporting codes, you can refer to them on the Report setup FastTabs in the Sales tax code page.</span></span> 

<span data-ttu-id="e31e4-107">I den här registreringen används demonstrationsföretaget DEMF.</span><span class="sxs-lookup"><span data-stu-id="e31e4-107">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="e31e4-108">I **Navigeringsfönster**, gå till **Skatt > Inställningar > Moms > Momsrapporteringskoder**.</span><span class="sxs-lookup"><span data-stu-id="e31e4-108">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="e31e4-109">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="e31e4-109">Click **New**.</span></span>
3. <span data-ttu-id="e31e4-110">Välj den rapportlayout som rapporteringskoden tillhör.</span><span class="sxs-lookup"><span data-stu-id="e31e4-110">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="e31e4-111">Denna layout används för att filtrera de tillgängliga rapportkoderna för en momskod.</span><span class="sxs-lookup"><span data-stu-id="e31e4-111">This layout is used to filter the available reporting codes for a Sales tax code.</span></span> <span data-ttu-id="e31e4-112">Varje momskod tillhör en kvittningsperiod som tillhör en skattemyndighet, som använder en rapportlayout.</span><span class="sxs-lookup"><span data-stu-id="e31e4-112">Each Sales tax code belongs to a settlement period which belongs to a Sales tax authority which uses a Report layout.</span></span>  
4. <span data-ttu-id="e31e4-113">Ange ett nummer i fältet **Rapporteringskod**.</span><span class="sxs-lookup"><span data-stu-id="e31e4-113">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="e31e4-114">Ange en beskrivning som ska visas på rapporter i fältet **Rapporttext**.</span><span class="sxs-lookup"><span data-stu-id="e31e4-114">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="e31e4-115">Ange en beskrivning för internt bruk i fältet **Kort beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="e31e4-115">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="e31e4-116">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e31e4-116">Click **Save**.</span></span>

