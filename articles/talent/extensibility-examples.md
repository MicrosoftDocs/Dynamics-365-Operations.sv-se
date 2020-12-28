---
title: Utöka Talent med Power Apps och Power Automate
description: Den här artikeln beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 Talent - Attract som använder Microsoft Power Apps och Microsoft Power Automate.
author: negudava
manager: Annbe
ms.date: 02/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent;Core;Experience Apps
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: negudava
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: cfdf36e9486aa4853d3bf674afa73ec3a4d1c161
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529644"
---
# <a name="extend-talent-with-power-apps-and-power-automate"></a><span data-ttu-id="ef9c9-103">Utöka Talent med Power Apps och Power Automate</span><span class="sxs-lookup"><span data-stu-id="ef9c9-103">Extend Talent with Power Apps and Power Automate</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="ef9c9-104">Den här artikeln beskriver några exempel på tilläggsscenarier för Microsoft Dynamics 365 Talent: Attract som använder Microsoft Power Apps och Microsoft Power Automate.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-104">This article describes some examples of extensibility scenarios for Microsoft Dynamics 365 Talent: Attract that use Microsoft Power Apps and Microsoft Power Automate.</span></span> <span data-ttu-id="ef9c9-105">Du kan importera lösningspaketet som associeras med varje exempel i din Power Apps-miljö.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-105">You can import the solution package that is associated with each example into your Power Apps environment.</span></span> <span data-ttu-id="ef9c9-106">Du kan sedan använda paketen antingen som vägledning eller som utgångspunkt för att implementera scenarier som gäller för din organisation.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-106">You can then use the packages either as guidance or as starting points to implement scenarios that are applicable to your organization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef9c9-107">Om du vill använda de mallar och program som beskrivs i den här artikeln ”i befintligt skick” bör du testa dem och se till att de täcker alla de scenarier som avser implementeringen.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-107">If you want to use the templates and app that are described in this article "as is," be sure to test them to make sure that they cover all the scenarios that are specific to your implementation.</span></span>


## <a name="prerequisites"></a><span data-ttu-id="ef9c9-108">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="ef9c9-108">Prerequisites</span></span>

- <span data-ttu-id="ef9c9-109">Om du vill importera paket måste användarna ha behörighet **Environment Maker**.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-109">To import packages, users must have the **Environment Maker** permission.</span></span>
- <span data-ttu-id="ef9c9-110">Användare måste ha en Power Apps Plan 2-licens eller en Power Apps Plan 2 utvärderingslicens för att exportera eller importera appar.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-110">To export or import apps, users must have a Power Apps Plan 2 license or a Power Apps Plan 2 trial license.</span></span>

## <a name="power-automate--form-connect"></a><span data-ttu-id="ef9c9-111">Power Automate – formuläret Ansluta</span><span class="sxs-lookup"><span data-stu-id="ef9c9-111">Power Automate – Form Connect</span></span>

<span data-ttu-id="ef9c9-112">Mallen **Power Automate – formuläret Ansluta** kan användas för att läsa data från Microsoft Forms och lagra det i en Common Data Service-enhet.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-112">The **Power Automate – Form Connect** template can be used to read data from Microsoft Forms and store it in a Common Data Service entity.</span></span>

<span data-ttu-id="ef9c9-113">Den här mallen kan utökas så att den kan användas för andra scenarier.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-113">This template can be extended so that it can be used for other scenarios.</span></span> <span data-ttu-id="ef9c9-114">Nedan följer några exempel:</span><span class="sxs-lookup"><span data-stu-id="ef9c9-114">Here are some examples:</span></span>

- <span data-ttu-id="ef9c9-115">Hämta kandidatens bedömningar.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-115">Capture candidate assessments.</span></span>
- <span data-ttu-id="ef9c9-116">Hämta resultaten från kursens enkäter.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-116">Capture results from course questionnaires.</span></span>
- <span data-ttu-id="ef9c9-117">Kompilera ett bibliotek med intervjufrågor för personaladministratörer (HR).</span><span class="sxs-lookup"><span data-stu-id="ef9c9-117">Compile a library of interview questions for Human resources (HR) administrators.</span></span>
- <span data-ttu-id="ef9c9-118">Hämta kandidatens utvärdering av intervjuprocessen</span><span class="sxs-lookup"><span data-stu-id="ef9c9-118">Capture a candidate's evaluation of the interview process</span></span>

<span data-ttu-id="ef9c9-119">I Microsoft Dynamics 365: Attract, kan du använda formulär i kandidatportalen och kandidater kan fylla i information.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-119">In Microsoft Dynamics 365: Attract, you can use forms in the candidate portal, where candidates fill in details.</span></span> <span data-ttu-id="ef9c9-120">Du kan också bädda in formulär som aktiviteter i en jobbmall.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-120">You can also embed forms as activities in a job template.</span></span>

<span data-ttu-id="ef9c9-121">När en kandidat skickar ett formulär, hämtar Microsoft Power Automate formuläröverföringen, läser in data och lagrar den Common Data Service-enhet.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-121">When a candidate submits a form, Microsoft Power Automate captures the form submission, reads the data, and stores it in the Common Data Service entity.</span></span>

<span data-ttu-id="ef9c9-122">För att hämta mallen **Power Automate – formuläret Ansluta** och anpassad entitetsstruktur, gå till [Power Automate – formuläret Ansluta](https://go.microsoft.com/fwlink/?linkid=2081988) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-122">To download the **Power Automate – Form Connect** template and Custom Entity Structure, go to [Power Automate – Form Connect](https://go.microsoft.com/fwlink/?linkid=2081988) on the Microsoft Download Center.</span></span>

## <a name="power-automate--sharepoint-integration"></a><span data-ttu-id="ef9c9-123">Power Automate – SharePoint-integration</span><span class="sxs-lookup"><span data-stu-id="ef9c9-123">Power Automate – SharePoint Integration</span></span>

<span data-ttu-id="ef9c9-124">Mallen **Power Automate – SharePoint-integration** kan användas för att läsa in data från en Microsoft SharePoint-lista, jämföra listan med fältvärden för någon Common Data Service entitet och skicka resultatet av jämförelsen som ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-124">The **Power Automate – SharePoint Integration** template can be used to read data from a Microsoft SharePoint list, compare the list with field values for any Common Data Service entity, and send the results of the comparison as a notification email.</span></span> 

<span data-ttu-id="ef9c9-125">En organisation kan ha en uppsättning med kunskaper som den kräver snarast.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-125">An organization might have a set of skills that it urgently requires.</span></span> <span data-ttu-id="ef9c9-126">Dessa kunskaper kan lagras i SharePoint som en SharePoint lista.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-126">These skills can be stored in SharePoint as a SharePoint list.</span></span> <span data-ttu-id="ef9c9-127">Då en kandidat ansöker om ett jobb som en uppsättning kunskaper anges för, om det finns en betydande matchning mellan kandidatens kunskaper och de kunskaper som är lagrade i SharePoint skickas ett e-postmeddelande.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-127">When a candidate applies for any job that a set of required skills is listed for, if there is a significant match between the candidate's skill and the skills that are stored in SharePoint, a notification email is sent.</span></span> <span data-ttu-id="ef9c9-128">På så sätt fylls befattningar som krävs snarast snabbare eftersom meddelanden hjälper rekryterare att anställa kandidater i hela organisationen.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-128">This helps fill positions that are urgently required faster, because the notifications help recruiters cross-hire candidates throughout the organization.</span></span>

<span data-ttu-id="ef9c9-129">Den här mallen kan utökas så att den kan användas för vissa situationer som omfattar SharePoint-integration.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-129">This template can be extended so that it can be used for any scenario that involves SharePoint integration.</span></span>

<span data-ttu-id="ef9c9-130">För att hämta mallen **Power Automate – SharePoint-integration** gå till [Power Automate – SharePoint-integration](https://go.microsoft.com/fwlink/?linkid=2082109) på Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-130">To download the **Power Automate – SharePoint Integration** template, go to [Power Automate – SharePoint Integration](https://go.microsoft.com/fwlink/?linkid=2082109) on the Microsoft Download Center.</span></span>

## <a name="referral-app"></a><span data-ttu-id="ef9c9-131">Appen Hänvisning</span><span class="sxs-lookup"><span data-stu-id="ef9c9-131">Referral App</span></span>

<span data-ttu-id="ef9c9-132">Du kan använda appen Hänvisning för att lägga till kandidater till en delad talangpool.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-132">You can use the Referral App to add candidates to a shared talent pool.</span></span> <span data-ttu-id="ef9c9-133">Hänvisaren kan ange **förnamn**, **efternamn**, **e-postadress** och **Linkedln-adress** när han eller hon skickar en kandidat.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-133">The referrer can enter **Firstname**, **Lastname**, **Email**, and **LinkedIn URL** when submitting a candidate.</span></span> <span data-ttu-id="ef9c9-134">Kandidatens metadata för källan fylls sedan i med hänvisarens information.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-134">The candidate source metadata is then populated with the referrer’s information.</span></span>

<span data-ttu-id="ef9c9-135">Du kan bädda in den här appen i Självbetjäning för medarbetare för att skicka referenser eller använda den som en hyperlänk i företagsportalen och köra den som en fristående app.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-135">You can embed this app in Employee self service for submitting referrals, or you can use it as a hyperlink in the corporate portal and run it as a stand-alone app.</span></span>

<span data-ttu-id="ef9c9-136">Hämta **Appen Hänvisning** genom att gå till [Dynamics 365 Talent utbyggbarhetslösning: appen Hänvisning](https://www.microsoft.com/download/details.aspx?id=58497) i Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-136">To download **Referral App**, go to [Dynamics 365 Talent extensibility solution: Referral App](https://www.microsoft.com/download/details.aspx?id=58497) on the Microsoft Download Center.</span></span> <span data-ttu-id="ef9c9-137">Du kan importera den här appen och anpassa den om du vill lägga till fler funktioner.</span><span class="sxs-lookup"><span data-stu-id="ef9c9-137">You can import this app and customize it to add additional functionality.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ef9c9-138">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ef9c9-138">Additional resources</span></span>

[<span data-ttu-id="ef9c9-139">Appen Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="ef9c9-139">The Microsoft Power Platform</span></span>](https://docs.microsoft.com/power-platform/admin/admin-documentation)</br>
[<span data-ttu-id="ef9c9-140">Migrera mellan innehavare och program</span><span class="sxs-lookup"><span data-stu-id="ef9c9-140">Migrate app between tenants and environments</span></span>](https://docs.microsoft.com/power-platform/admin/environment-and-tenant-migration)
