---
title: Aktivera fördröjd momsberäkning i journal
description: Det här avsnittet innehåller information om hur du använder funktionen **Aktivera fördröjd momsberäkning i journal** för att förbättra momsberäkningsresultatet när volymen för journalrader är mycket stor.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 5a8ae30a007d3e2b8b7a9bc9eb7786f6e58246d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179928"
---
# <a name="enable-delayed-tax-calculation-on-journal"></a><span data-ttu-id="5b2b2-103">Aktivera fördröjd momsberäkning i journal</span><span class="sxs-lookup"><span data-stu-id="5b2b2-103">Enable delayed tax calculation on journal</span></span>
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="5b2b2-104">Det här avsnittet innehåller information om hur du använder funktionen **Aktivera fördröjd momsberäkning i journal** för att förbättra momsberäkningsresultatet när volymen för journalrader är mycket stor.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-104">This topic explains how to use the **Enable delayed tax calculation on journal** feature to improve tax calculation performance when the volume of journal lines is huge.</span></span>

<span data-ttu-id="5b2b2-105">Aktuellt momsberäkningsbeteende i journalen aktiveras realtid när en användare uppdaterar fält som är relaterade till moms, t.ex. momsgrupp eller artikelmomsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-105">Current sales tax calculation behavior on journal is real-time triggered when user updates tax related fields, e.g. sales tax group/item sales tax group.</span></span> <span data-ttu-id="5b2b2-106">Alla uppdateringar på journalradnivå kommer att omberäkna skattebelopp på alla journalrader.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-106">Any update at journal line level will re-calculate tax amount on all journal lines.</span></span> <span data-ttu-id="5b2b2-107">Den hjälper användaren att visa det beräknade momsbeloppet i realtid, men det kan också leda till prestandaproblem om volymen på journalraderna är mycket stor.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-107">It helps user to see real-time calculated tax amount but it could also bring performance issue if  the volume of journal lines is huge.</span></span>

<span data-ttu-id="5b2b2-108">Den här funktionen är ett alternativ till att fördröja momsberäkningen för att lösa prestandaproblem.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-108">This feature provides an option to delay tax calculation to solve performance issue.</span></span> <span data-ttu-id="5b2b2-109">Om den här funktionen är aktiverad kommer momsbeloppet endast att beräknas när användaren klickar på kommandot "moms" eller bokför journalen.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-109">If this feature is turned on, tax amount will only be calculated when user clicks "Sales Tax" command or posts the journal.</span></span>

<span data-ttu-id="5b2b2-110">Användaren kan aktivera/inaktivera parametern på tre nivåer:</span><span class="sxs-lookup"><span data-stu-id="5b2b2-110">User can turn on/off the parameter at three levels:</span></span>
- <span data-ttu-id="5b2b2-111">Efter juridisk person</span><span class="sxs-lookup"><span data-stu-id="5b2b2-111">By legal entity</span></span>
- <span data-ttu-id="5b2b2-112">Per journalnamn</span><span class="sxs-lookup"><span data-stu-id="5b2b2-112">By journal name</span></span>
- <span data-ttu-id="5b2b2-113">Per journalrubrik</span><span class="sxs-lookup"><span data-stu-id="5b2b2-113">By journal header</span></span>

<span data-ttu-id="5b2b2-114">Systemet kommer att ta parametervärdet för journalrubriken som slutgiltigt.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-114">System will take the parameter value on journal header as final.</span></span> <span data-ttu-id="5b2b2-115">Parametervärde i journalrubriken hämtas som standard från journalnamnet.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-115">Parameter value on journal header will be defaulted from journal name.</span></span> <span data-ttu-id="5b2b2-116">Journal namnets parametervärde visas som standard från redovisningsparametern när journalnamnet skapas.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-116">Parameter value on journal name will be defaulted from general ledger parameter when the journal name is created.</span></span>

<span data-ttu-id="5b2b2-117">Fälten "faktiskt momsbelopp" och "beräknat momsbelopp" för journalen döljs om den här parametern aktiveras.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-117">"Actual sales tax amount" and "Calculated sales tax amount" fields on journal will be hided if this parameter is turned on.</span></span> <span data-ttu-id="5b2b2-118">Syftet är inte att förväxla användaren eftersom värdet i dessa två fält alltid kommer att visa 0 innan en användare utlöser momsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-118">The purpose is not to confuse user because the value of these two fields will always show 0 before user trigger the tax calculation.</span></span>

## <a name="enable-delayed-tax-calculation-by-legal-entity"></a><span data-ttu-id="5b2b2-119">Aktivera fördröjd momsberäkning per juridisk person</span><span class="sxs-lookup"><span data-stu-id="5b2b2-119">Enable delayed tax calculation by legal entity</span></span>

1. <span data-ttu-id="5b2b2-120">Gå till **Redovisning > Redovisningsinställning > Redovisningsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-120">Go to **General ledger > Ledger setup > General ledger parameters**</span></span>
2. <span data-ttu-id="5b2b2-121">Klicka på **Moms**.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-121">Click **Sales tax** tab</span></span>
3. <span data-ttu-id="5b2b2-122">Under snabbfliken **allmän** hittar du parameter **fördröjd momsberäkning**, aktivera/inaktivera den</span><span class="sxs-lookup"><span data-stu-id="5b2b2-122">Under **General** fast tab, find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-gl.png)



## <a name="enable-delayed-tax-calculation-by-journal-name"></a><span data-ttu-id="5b2b2-123">Aktivera fördröjd momsberäkning per journalnamn</span><span class="sxs-lookup"><span data-stu-id="5b2b2-123">Enable delayed tax calculation by journal name</span></span>

1. <span data-ttu-id="5b2b2-124">Gå till **Redovisning > Journalkonfigurering > Journalnamn**.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-124">Go to **General ledger > Journal setup > Journal names**</span></span>
2. <span data-ttu-id="5b2b2-125">Under snabbfliken **allmän** hittar du parameter **fördröjd momsberäkning**, aktivera/inaktivera den</span><span class="sxs-lookup"><span data-stu-id="5b2b2-125">Under **General** fast tab, find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-journal-name.png)

## <a name="enable-delayed-tax-calculation-by-journal"></a><span data-ttu-id="5b2b2-126">Aktivera fördröjd momsberäkning per journal</span><span class="sxs-lookup"><span data-stu-id="5b2b2-126">Enable delayed tax calculation by journal</span></span>

1. <span data-ttu-id="5b2b2-127">Gå till **Redovisning > Journalposter > Allmänna journaler**.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-127">Go to **General ledger > Journal entries > General journals**</span></span>
2. <span data-ttu-id="5b2b2-128">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-128">Click **New**</span></span>
3. <span data-ttu-id="5b2b2-129">Välj ett journalnamn.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-129">Select a journal name</span></span>
4. <span data-ttu-id="5b2b2-130">Klicka på **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="5b2b2-130">Click **Setup**</span></span>
5. <span data-ttu-id="5b2b2-131">Hitta parameter **fördröjd momsberäkning**, aktivera/inaktivera den</span><span class="sxs-lookup"><span data-stu-id="5b2b2-131">Find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-journal-header.png)
