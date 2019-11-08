---
title: Nyheter och ändringar i Dynamics 365 Talent - Core HR (augusti 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 08/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-08-27
ms.dyn365.ops.version: Talent August 2018 update
ms.openlocfilehash: 14dc4d2a1b69f58d6d9c2466b2bcaf4f9185931e
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550284"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-august-2018"></a><span data-ttu-id="6c6cd-103">Nyheter och ändringar i Dynamics 365 Talent - Core HR (augusti 2018)</span><span class="sxs-lookup"><span data-stu-id="6c6cd-103">What's new or changed in Dynamics 365 Talent - Core HR (August 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6c6cd-104">**Skapa 8.1.104**</span><span class="sxs-lookup"><span data-stu-id="6c6cd-104">**Build 8.1.104**</span></span>

<span data-ttu-id="6c6cd-105">Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-105">This topic describes features that are either new or changed in Dynamics 365 Talent: Core HR.</span></span>

## <a name="view-expiring-records-in-manager-self-service"></a><span data-ttu-id="6c6cd-106">Visa utgående poster i självbetjäning för chef</span><span class="sxs-lookup"><span data-stu-id="6c6cd-106">View expiring records in Manager self service</span></span>

<span data-ttu-id="6c6cd-107">Du kan nu visa utgående poster i självbetjäning för chef.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-107">You can now view expiring records in Manager self-service.</span></span> <span data-ttu-id="6c6cd-108">Nya alternativ låter dig konfigurera vilken information som ska vara tillgängliga för chefer att visa.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-108">New options are allow you to configure what information will be available for managers to view.</span></span> <span data-ttu-id="6c6cd-109">Dessa omfattar:</span><span class="sxs-lookup"><span data-stu-id="6c6cd-109">These include:</span></span>

-   <span data-ttu-id="6c6cd-110">Intyg</span><span class="sxs-lookup"><span data-stu-id="6c6cd-110">Certificates</span></span>

-   <span data-ttu-id="6c6cd-111">Identifieringsnummer</span><span class="sxs-lookup"><span data-stu-id="6c6cd-111">Identification numbers</span></span>

-   <span data-ttu-id="6c6cd-112">Provanställningsperioder</span><span class="sxs-lookup"><span data-stu-id="6c6cd-112">Probation periods</span></span>

-   <span data-ttu-id="6c6cd-113">Kontroller</span><span class="sxs-lookup"><span data-stu-id="6c6cd-113">Screenings</span></span>

-   <span data-ttu-id="6c6cd-114">Tester</span><span class="sxs-lookup"><span data-stu-id="6c6cd-114">Tests</span></span>

<span data-ttu-id="6c6cd-115">Den här funktionen ger även möjlighet att ange det antal dagar som ska sökas efter poster som upphör att gälla.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-115">This feature also gives you the ability to specify the range of days in which to look for expiring records.</span></span>

## <a name="configurable-transfer-actions"></a><span data-ttu-id="6c6cd-116">Konfigurerbara överföringsåtgärder</span><span class="sxs-lookup"><span data-stu-id="6c6cd-116">Configurable transfer actions</span></span>

<span data-ttu-id="6c6cd-117">Du kan konfigurera efter roll de alternativ som är tillgängliga vid registrering av en överföringsbegäran.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-117">You can configure by role the options that will be available during the entry of a transfer request.</span></span> <span data-ttu-id="6c6cd-118">Denna funktion ger ytterligare flexibilitet mellan roller i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-118">This feature provides additional flexibility across the roles in an organization.</span></span>

<span data-ttu-id="6c6cd-119">T.ex. chefer som begär överföring av medarbetare kanske inte har åtkomst till att föreslå eller ange kompensationsbelopp eller välja uppgiftslistor som kommer att vara associerade till överföringsbegäran.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-119">For example, managers requesting employee transfers may not have access to suggest or enter compensation amounts or select the task lists that will be associated with the transfer request.</span></span> <span data-ttu-id="6c6cd-120">I detta fall kan chefer skapa och skicka överföringsbegäranden men de får inte ange kompensation eller lista aktivitetstilldelningar.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-120">In this case, managers can create and submit transfer requests but are not allowed to enter compensation or task list assignments.</span></span> <span data-ttu-id="6c6cd-121">I samma konfiguration kommer personalavdelningen att kunna tilldela nya kompensationsvärden och även tilldela eventuella ytterligare checklistor som ska slutföras som ett resultat av att överföringen slutförs.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-121">In this same configuration, HR will be able to assign the new compensation values as well as assign any additional checklists to be completed as a result of the transfer completing.</span></span>

<span data-ttu-id="6c6cd-122">Som standard ställs nya konfigurationsalternativ in för att inte ändra funktionerna före uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-122">By default, the new configuration options are set to not change the capabilities prior to this update.</span></span>

## <a name="leave-and-absence"></a><span data-ttu-id="6c6cd-123">Tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="6c6cd-123">Leave and absence</span></span>

<span data-ttu-id="6c6cd-124">Det finns nu fler datumfält i Ledighet och frånvaro.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-124">There are now additional Date fields available in Leave and Absence.</span></span>

<span data-ttu-id="6c6cd-125">Du kan ange underlag för periodiseringsperiod på plannivå för att använda specifika medarbetardatum.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-125">With this feature you can set the accrual period basis at the plan level to use specific employee dates.</span></span> <span data-ttu-id="6c6cd-126">Detta inkluderar andra datum än startdatum för planen som ska användas under periodiseringsprocessen för ledigheten.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-126">This allows for dates other than the plan start date to be used during the leave accrual process.</span></span> <span data-ttu-id="6c6cd-127">Alternativen för specifika medarbetardatum omfattar följande värden:</span><span class="sxs-lookup"><span data-stu-id="6c6cd-127">Options for employee specific dates include the following values:</span></span>

-   <span data-ttu-id="6c6cd-128">Anpassad (tillgänglig innan denna uppdatering)</span><span class="sxs-lookup"><span data-stu-id="6c6cd-128">Custom (available prior to this update)</span></span>

-   <span data-ttu-id="6c6cd-129">Årsdag</span><span class="sxs-lookup"><span data-stu-id="6c6cd-129">Anniversary date</span></span>

-   <span data-ttu-id="6c6cd-130">Ursprungligt anställningsdatum</span><span class="sxs-lookup"><span data-stu-id="6c6cd-130">Original hire date</span></span>

-   <span data-ttu-id="6c6cd-131">Datum för tjänsteålder</span><span class="sxs-lookup"><span data-stu-id="6c6cd-131">Seniority date</span></span>

-   <span data-ttu-id="6c6cd-132">Arbetarens justerade startdatum</span><span class="sxs-lookup"><span data-stu-id="6c6cd-132">Worker’s adjusted start date</span></span>

-   <span data-ttu-id="6c6cd-133">Arbetarens startdatum</span><span class="sxs-lookup"><span data-stu-id="6c6cd-133">Worker’s start date</span></span>

<span data-ttu-id="6c6cd-134">När de är konfigurerade för att använda ett av de medarbetarspecifika datumen kommer registreringsprocessen att använda detta datum för beräkning av periodiseringsperioderna.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-134">When configured to use one of the employee specific dates, the enrollment process will use the specified date to calculate the accrual periods.</span></span> <span data-ttu-id="6c6cd-135">Periodiseringsperiodens grund visas också på medarbetarens planregistrering för att hjälpa dig att förstå vad som används under periodiseringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-135">The accrual period basis is also displayed on the employee’s plan enrollment to help you understand what’s being used during the accrual process.</span></span>

## <a name="microsoft-word-integration"></a><span data-ttu-id="6c6cd-136">Microsoft Word-integrering</span><span class="sxs-lookup"><span data-stu-id="6c6cd-136">Microsoft Word integration</span></span>

<span data-ttu-id="6c6cd-137">Dokumentmallar har aktiverats i Core HR.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-137">Document templates have been enabled throughout Core HR.</span></span> <span data-ttu-id="6c6cd-138">Den här funktionen låter dig skapa brev och rapporter baserat på Word-mallar som du skapar.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-138">This feature allows you to create letters and reports based on Word templates that you create.</span></span>

<span data-ttu-id="6c6cd-139">Mer information om den här funktionen finns i [Office integration självstudier](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-tutorial?toc=/dynamics365/unified-operations/talent/toc.json).</span><span class="sxs-lookup"><span data-stu-id="6c6cd-139">Additional information about this feature is available in the [Office integration tutorial](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/office-integration/office-integration-tutorial?toc=/dynamics365/unified-operations/talent/toc.json).</span></span>


## <a name="other-fixes"></a><span data-ttu-id="6c6cd-140">Andra korrigeringar</span><span class="sxs-lookup"><span data-stu-id="6c6cd-140">Other fixes</span></span>

<span data-ttu-id="6c6cd-141">Den här versionen innehåller ett antal olika felkorrigeringar, tillägg av nya entiteter, korrigeringar för befintliga entiteter och lokaliserade etikettändringar.</span><span class="sxs-lookup"><span data-stu-id="6c6cd-141">This release also includes a number of bug fixes, the addition of new entities, fixes to existing entities, and localized label changes.</span></span>
