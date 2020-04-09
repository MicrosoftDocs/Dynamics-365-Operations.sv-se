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
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 460e41d69a78cda664e0d3af828fdc482169ac52
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145085"
---
# <a name="set-up-sales-tax-reporting-codes"></a><span data-ttu-id="97c22-103">Ställ in momsrapporteringskoder</span><span class="sxs-lookup"><span data-stu-id="97c22-103">Set up sales tax reporting codes</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="97c22-104">Momsrapportkoderna refererar till ett fältnummer i momsrapporten.</span><span class="sxs-lookup"><span data-stu-id="97c22-104">The Sales tax reporting codes refer to a field number on a sales tax report.</span></span> <span data-ttu-id="97c22-105">Dessa används för landsspecifika rapportlayouter och rapporten Momsbetalning per kod om du vill skriva ut momsbelopp för en kvittningsperiod som summeras per rapporteringskod.</span><span class="sxs-lookup"><span data-stu-id="97c22-105">They are used on country specific report layouts and the Sales tax payment by code report to print sales tax amounts for a settlement period summarized per reporting code.</span></span> <span data-ttu-id="97c22-106">När du har skapat momsrapporteringskoder kan du referera till dem på rapportinställningssnabbflikarna på momskodsidan.</span><span class="sxs-lookup"><span data-stu-id="97c22-106">After you create Sales tax reporting codes, you can refer to them on the Report setup FastTabs in the Sales tax code page.</span></span> 

<span data-ttu-id="97c22-107">I den här registreringen används demonstrationsföretaget DEMF.</span><span class="sxs-lookup"><span data-stu-id="97c22-107">This recording uses the DEMF demo company.</span></span>

1. <span data-ttu-id="97c22-108">I **Navigeringsfönster**, gå till **Skatt > Inställningar > Moms > Momsrapporteringskoder**.</span><span class="sxs-lookup"><span data-stu-id="97c22-108">In the **Navigation pane**, go to **Tax > Setup > Sales tax > Sales tax reporting codes**.</span></span>
2. <span data-ttu-id="97c22-109">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="97c22-109">Click **New**.</span></span>
3. <span data-ttu-id="97c22-110">Välj den rapportlayout som rapporteringskoden tillhör.</span><span class="sxs-lookup"><span data-stu-id="97c22-110">Select the report layout that the reporting code belongs to.</span></span> <span data-ttu-id="97c22-111">Denna layout används för att filtrera de tillgängliga rapportkoderna för en momskod.</span><span class="sxs-lookup"><span data-stu-id="97c22-111">This layout is used to filter the available reporting codes for a Sales tax code.</span></span> <span data-ttu-id="97c22-112">Varje momskod tillhör en kvittningsperiod som tillhör en skattemyndighet, som använder en rapportlayout.</span><span class="sxs-lookup"><span data-stu-id="97c22-112">Each Sales tax code belongs to a settlement period which belongs to a Sales tax authority which uses a Report layout.</span></span>  
4. <span data-ttu-id="97c22-113">Ange ett nummer i fältet **Rapporteringskod**.</span><span class="sxs-lookup"><span data-stu-id="97c22-113">In the **Reporting code** field, enter a number.</span></span>
5. <span data-ttu-id="97c22-114">Ange en beskrivning som ska visas på rapporter i fältet **Rapporttext**.</span><span class="sxs-lookup"><span data-stu-id="97c22-114">In the **Report text** field, enter a description to display on reports.</span></span>
6. <span data-ttu-id="97c22-115">Ange en beskrivning för internt bruk i fältet **Kort beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="97c22-115">In the **Brief description** field, enter a description for internal purposes.</span></span>
7. <span data-ttu-id="97c22-116">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="97c22-116">Click **Save**.</span></span>

