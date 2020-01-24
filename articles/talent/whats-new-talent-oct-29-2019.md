---
title: Nyheter och ändringar i Dynamics 365 Talent (29 oktober 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/29/2019
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
ms.search.validFrom: 2019-10-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e2d79ee9e182df4a4efe65beb685567b1e7446ce
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2897452"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-29-2019"></a><span data-ttu-id="87fd1-103">Nyheter och ändringar i Dynamics 365 Talent (29 oktober 2019)</span><span class="sxs-lookup"><span data-stu-id="87fd1-103">What's new or changed in Dynamics 365 Talent (October 29, 2019)</span></span>

<span data-ttu-id="87fd1-104">Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="87fd1-104">This topic describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="87fd1-105">Ändringar i Attract</span><span class="sxs-lookup"><span data-stu-id="87fd1-105">Changes in Attract</span></span>

<span data-ttu-id="87fd1-106">Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="87fd1-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="87fd1-107">Ändringar i Onboard</span><span class="sxs-lookup"><span data-stu-id="87fd1-107">Changes in Onboard</span></span>

<span data-ttu-id="87fd1-108">Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="87fd1-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="87fd1-109">Ändringar i Core HR</span><span class="sxs-lookup"><span data-stu-id="87fd1-109">Changes in Core HR</span></span>

<span data-ttu-id="87fd1-110">Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2586.</span><span class="sxs-lookup"><span data-stu-id="87fd1-110">Changes described in this section apply to build number 8.1.2586.</span></span> <span data-ttu-id="87fd1-111">Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="87fd1-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

### <a name="delete-parties-with-no-roles-should-be-on-by-default-371233"></a><span data-ttu-id="87fd1-112">Ta bort parter utan roller ska som standard vara aktiverat (371233)</span><span class="sxs-lookup"><span data-stu-id="87fd1-112">Delete parties with no roles should be on by default (371233)</span></span>

<span data-ttu-id="87fd1-113">När du etablerar en ny miljö i Talent aktiveras **Ta bort parterna om ingen roll finns** som standard.</span><span class="sxs-lookup"><span data-stu-id="87fd1-113">When you provision a new environment in Talent, **Delete parties if no roles exist** is turned on by default.</span></span> <span data-ttu-id="87fd1-114">När du tar bort en arbetare tas inte den part som är kopplad till arbetaren bort om inte inställningen aktiveras.</span><span class="sxs-lookup"><span data-stu-id="87fd1-114">When you delete a worker, the party associated with the worker is not removed unless this setting is on.</span></span> <span data-ttu-id="87fd1-115">Den här ändringen begränsar dubblettposter i den globala adressboken när du behöver importera, ändra eller importera om arbetare.</span><span class="sxs-lookup"><span data-stu-id="87fd1-115">This change limits duplicate records in the global address book when you need to import, change, or reimport workers.</span></span>

### <a name="draft-and-cancelled-leave-requests-should-be-allowed-to-be-deleted-in-common-data-service-376999"></a><span data-ttu-id="87fd1-116">Utkast och avbrutna förfrågningar om tjänstledighet bör tillåtas att tas bort i Common Data Service (376999)</span><span class="sxs-lookup"><span data-stu-id="87fd1-116">Draft and cancelled leave requests should be allowed to be deleted in Common Data Service (376999)</span></span>

<span data-ttu-id="87fd1-117">Med den här ändringen kan du nu ta bort tjänstledighetsbegäranden med statusen **utkast** eller **avbruten** i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="87fd1-117">With this change, you can now delete leave requests with a status of **Draft** or **Cancelled** in Common Data Service.</span></span>

### <a name="additional-list-values-in-custom-fields-arent-reflected-in-common-data-service-after-clicking-apply-on-the-custom-fields-form-379599"></a><span data-ttu-id="87fd1-118">Ytterligare listvärden i anpassade fält visas inte i Common Data Service när du klickar på tillämpa på formuläret anpassade fält (379599)</span><span class="sxs-lookup"><span data-stu-id="87fd1-118">Additional list values in custom fields aren't reflected in Common Data Service after clicking Apply on the Custom fields form (379599)</span></span>

<span data-ttu-id="87fd1-119">När du lägger till nya listvärden i ett befintligt anpassat fält som redan har synkroniserats med Common Data Service, är de nu tillgängliga i Common Data Serivce när du har tillämpat ändringarna i formuläret **anpassade fält**.</span><span class="sxs-lookup"><span data-stu-id="87fd1-119">When you add new list values to an existing custom field that has already synchronized with Common Data Service, they're now available in Common Data Serivce after you apply your changes in the **Custom fields** form.</span></span>

### <a name="apply-onboarding-checklists-across-legal-entities-when-more-than-one-employment-exists-371270"></a><span data-ttu-id="87fd1-120">Använd checklistor för registrering över juridiska personer när det finns fler än en anställning (371270)</span><span class="sxs-lookup"><span data-stu-id="87fd1-120">Apply onboarding checklists across legal entities when more than one employment exists (371270)</span></span>

<span data-ttu-id="87fd1-121">Under den här veckans frisläppning kan du koppla checklistor till medarbetare med fler än en anställning i **formuläret arbetare > checklistor**.</span><span class="sxs-lookup"><span data-stu-id="87fd1-121">In this week's release, you can apply checklists to employees with more than one employment in **Worker form > Checklists**.</span></span>

### <a name="benefits-open-enrollment-preview-feature-has-been-removed"></a><span data-ttu-id="87fd1-122">Funktionen för Öppna anmälan i förhandsversionen har tagits bort</span><span class="sxs-lookup"><span data-stu-id="87fd1-122">Benefits open enrollment preview feature has been removed</span></span>

<span data-ttu-id="87fd1-123">I samverkan med vårt meddelande i blogginlägget [Strategiska investeringar i det Core HR-systemet för att effektivisera verksamheten](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence) tar Microsoft bort funktionen för öppna anmälan i den allmänna förhandsversionen.</span><span class="sxs-lookup"><span data-stu-id="87fd1-123">In conjunction with our announcement in the [Strategic investments in core HR drive operational excellence](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence) blog post, Microsoft has removed the benefits open enrollment feature from public preview.</span></span> <span data-ttu-id="87fd1-124">Nya funktioner att publiceras i framtiden.</span><span class="sxs-lookup"><span data-stu-id="87fd1-124">New functionality will be released in the future.</span></span> <span data-ttu-id="87fd1-125">Produktionsanvändning av funktionen för öppna anmälan stöds inte.</span><span class="sxs-lookup"><span data-stu-id="87fd1-125">Production use of the benefits open enrollment feature isn't be supported.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="87fd1-126">Kommer snart</span><span class="sxs-lookup"><span data-stu-id="87fd1-126">Coming soon</span></span>

### <a name="print-performance-reviews"></a><span data-ttu-id="87fd1-127">Skriv ut resultatöversyner</span><span class="sxs-lookup"><span data-stu-id="87fd1-127">Print performance reviews</span></span>

<span data-ttu-id="87fd1-128">Se [Skriv ut resultatöversyner](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) i Dynamics 365: 2019 släpp påfyllnad 2 plan.</span><span class="sxs-lookup"><span data-stu-id="87fd1-128">See [Print performance reviews](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) in the Dynamics 365: 2019 release wave 2 plan.</span></span>

### <a name="feature-management-workspace"></a><span data-ttu-id="87fd1-129">Arbetsytan Funktionshantering</span><span class="sxs-lookup"><span data-stu-id="87fd1-129">Feature management workspace</span></span>

<span data-ttu-id="87fd1-130">Funktioner läggs till och uppdateras i alla versioner.</span><span class="sxs-lookup"><span data-stu-id="87fd1-130">Features are added and updated in every release.</span></span> <span data-ttu-id="87fd1-131">Funktionshanteringen är en arbetsyta där du kan visa en lista med funktioner som har levererats i varje utgåva.</span><span class="sxs-lookup"><span data-stu-id="87fd1-131">The feature management experience provides a workspace where you can view a list of features that have been delivered in each release.</span></span> <span data-ttu-id="87fd1-132">Nya funktionen är avstängda som standard.</span><span class="sxs-lookup"><span data-stu-id="87fd1-132">By default, new features are turned off.</span></span> <span data-ttu-id="87fd1-133">Du kan använda arbetsytan för att aktivera dem och visa dokumentationen för dem.</span><span class="sxs-lookup"><span data-stu-id="87fd1-133">You can use the workspace to turn them on and view the documentation for them.</span></span>

<span data-ttu-id="87fd1-134">Mer information om de ändringar som kommer från funktionshantering finns i [översikt över funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="87fd1-134">To learn more about the changes coming with feature management, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>
