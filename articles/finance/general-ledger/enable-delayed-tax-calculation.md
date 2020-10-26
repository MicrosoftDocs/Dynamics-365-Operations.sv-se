---
title: Aktivera fördröjd momsberäkning i journal
description: Det här ämnet förklarar hur du aktiverar funktionen Fördröjd momsberäkning för att förbättra resultat för momsberäkningar när antalet journalrader är mycket stort.
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
ms.author: roschlom
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: d4ce0343ac766b30d532be0866a381dc520fd462
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3977153"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a><span data-ttu-id="af5e0-103">Aktivera fördröjd momsberäkning i journal</span><span class="sxs-lookup"><span data-stu-id="af5e0-103">Enable delayed tax calculation on journals</span></span>
[!include [banner](../includes/banner.md)]


<span data-ttu-id="af5e0-104">I det här avsnittet beskrivs hur du kan fördröja momsberäkning för journaler.</span><span class="sxs-lookup"><span data-stu-id="af5e0-104">This topic explains how you can delay sales tax calculation on journals.</span></span> <span data-ttu-id="af5e0-105">Den här funktionen ger bättre prestanda vid momsberäkningar när det finns många journalrader.</span><span class="sxs-lookup"><span data-stu-id="af5e0-105">This capability helps improve the performance of tax calculations when there are many journal lines.</span></span>

<span data-ttu-id="af5e0-106">Som standard beräknas momsbelopp på journalrader när momsrelaterade fält uppdateras.</span><span class="sxs-lookup"><span data-stu-id="af5e0-106">By default, sales tax amounts on journal lines are calculated whenever tax-related fields are updated.</span></span> <span data-ttu-id="af5e0-107">Dessa fält inkluderar fält för momsgrupper och artikelmomsgrupper.</span><span class="sxs-lookup"><span data-stu-id="af5e0-107">These fields include the fields for sales tax groups and item sales tax groups.</span></span> <span data-ttu-id="af5e0-108">Alla uppdateringar av en journalrad gör att momsbeloppen räknas om för alla journalrader.</span><span class="sxs-lookup"><span data-stu-id="af5e0-108">Any update to a journal line causes tax amounts to be recalculated for all journal lines.</span></span> <span data-ttu-id="af5e0-109">Även om beteendet hjälper användare att se momsbelopp som beräknats i realtid, kan det också påverka prestandan om antalet journalrader är mycket stort.</span><span class="sxs-lookup"><span data-stu-id="af5e0-109">Although this behavior helps user see tax amounts calculated in real time, it can also affect performance if the number of journal lines is very large.</span></span>

<span data-ttu-id="af5e0-110">Med funktionen för fördröjd momsberäkning kan du fördröja momsberäkningen för journaler och därmed lösa prestandaproblem.</span><span class="sxs-lookup"><span data-stu-id="af5e0-110">The Delayed tax calculation feature lets you delay tax calculation on journals and therefore helps fix performance issues.</span></span> <span data-ttu-id="af5e0-111">Om den här funktionen är aktiverad kommer beloppen endast att beräknas när användaren klickar på **Moms** eller bokför journalen.</span><span class="sxs-lookup"><span data-stu-id="af5e0-111">When this feature is turned on, tax amounts are calculated only when a user selects **Sales Tax** or posts the journal.</span></span>

<span data-ttu-id="af5e0-112">Du kan fördröja beräkningen av moms på tre nivåer:</span><span class="sxs-lookup"><span data-stu-id="af5e0-112">You can delay the calculation of sales taxes at three levels:</span></span>

- <span data-ttu-id="af5e0-113">Juridisk person</span><span class="sxs-lookup"><span data-stu-id="af5e0-113">Legal entity</span></span>
- <span data-ttu-id="af5e0-114">Journalnamn</span><span class="sxs-lookup"><span data-stu-id="af5e0-114">Journal name</span></span>
- <span data-ttu-id="af5e0-115">Journalrubrik</span><span class="sxs-lookup"><span data-stu-id="af5e0-115">Journal header</span></span>

<span data-ttu-id="af5e0-116">Systemet ger företräde åt inställningen för journalrubriken.</span><span class="sxs-lookup"><span data-stu-id="af5e0-116">The system gives priority to the setting for the journal header.</span></span> <span data-ttu-id="af5e0-117">Som standard hämtas den här inställningen från journalnamnet.</span><span class="sxs-lookup"><span data-stu-id="af5e0-117">By default, this setting is taken from the journal name.</span></span> <span data-ttu-id="af5e0-118">Som standard hämtas inställningen för journalnamn från inställningen på sidan **redovisningsparametrar** när journalnamnet skapas.</span><span class="sxs-lookup"><span data-stu-id="af5e0-118">By default, the setting for the journal name is taken from the setting on the **General ledger parameters** page when the journal name is created.</span></span> <span data-ttu-id="af5e0-119">I följande avsnitt beskrivs hur du aktiverar fördröjd momsberäkning för juridiska personer, journalnamn och journalrubriker.</span><span class="sxs-lookup"><span data-stu-id="af5e0-119">The following sections explain how to turn on delayed tax calculation for legal entities, journal names, and journal headers.</span></span>

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a><span data-ttu-id="af5e0-120">Aktivera fördröjd momsberäkning på nivån juridisk person</span><span class="sxs-lookup"><span data-stu-id="af5e0-120">Turn on delayed tax calculation at the legal entity level</span></span>

1. <span data-ttu-id="af5e0-121">Gå till **Redovisning \> Redovisningsinställning \> Allmänna redovisningsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="af5e0-121">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="af5e0-122">På fliken **Moms** på snabbfliken **Allmänt**, ange alternativet **"fördröjd momsberäkning** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="af5e0-122">On the **Sales tax** tab, on the **General** FastTab, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Bild på allmänna huvudboksparametrar](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a><span data-ttu-id="af5e0-124">Aktivera fördröjd momsberäkning på nivån journalnamn</span><span class="sxs-lookup"><span data-stu-id="af5e0-124">Turn on delayed tax calculation at the journal name level</span></span>

1. <span data-ttu-id="af5e0-125">Gå till **Redovisning \> Journalkonfiguration \> Journalnamn**.</span><span class="sxs-lookup"><span data-stu-id="af5e0-125">Go to **General ledger \> Journal setup \> Journal names**.</span></span>
2. <span data-ttu-id="af5e0-126">På snabbfliken **Allmänt** i avsnittet **Moms** anger du alternativet **fördröjd momsberäkning** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="af5e0-126">On the **General** FastTab, in the **Sales tax** section, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Bild på journalnamn](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a><span data-ttu-id="af5e0-128">Aktivera fördröjd momsberäkning på nivån journalrubrik</span><span class="sxs-lookup"><span data-stu-id="af5e0-128">Turn on delayed tax calculation at the journal header level</span></span>

1. <span data-ttu-id="af5e0-129">Gå till **Redovisning \> Journalposter \> Allmänna journaler**.</span><span class="sxs-lookup"><span data-stu-id="af5e0-129">Go to **General ledger \> Journal entries \> General journals**.</span></span>
2. <span data-ttu-id="af5e0-130">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="af5e0-130">Select **New**.</span></span>
3. <span data-ttu-id="af5e0-131">Välj ett journalnamn.</span><span class="sxs-lookup"><span data-stu-id="af5e0-131">Select a journal name.</span></span>
4. <span data-ttu-id="af5e0-132">På fliken **inställningar** ställer du in alternativet **fördröjd momsberäkning** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="af5e0-132">On the **Setup** tab, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Bild på allmän journalsida](media/delayed-tax-calculation-journal-header.png)
