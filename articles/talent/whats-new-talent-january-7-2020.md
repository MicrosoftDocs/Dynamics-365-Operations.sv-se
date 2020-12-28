---
title: Nyheter och ändringar i Dynamics 365 Talent (7 januari 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/07/2020
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
ms.search.validFrom: 2020-01-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e227c614fdbfe6f3dd410f1a533c593979abf1ec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462597"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-january-7-2020"></a><span data-ttu-id="f342f-103">Nyheter och ändringar i Dynamics 365 Talent (7 januari 2020)</span><span class="sxs-lookup"><span data-stu-id="f342f-103">What's new or changed in Dynamics 365 Talent (January 7, 2020)</span></span>

<span data-ttu-id="f342f-104">Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="f342f-104">This article describes features that are either new or changed in Dynamics 365 Talent.</span></span>

## <a name="changes-in-attract"></a><span data-ttu-id="f342f-105">Ändringar i Attract</span><span class="sxs-lookup"><span data-stu-id="f342f-105">Changes in Attract</span></span>

<span data-ttu-id="f342f-106">Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="f342f-106">This release includes minor bug fixes for Dynamics 365 Talent: Attract.</span></span>

## <a name="changes-in-onboard"></a><span data-ttu-id="f342f-107">Ändringar i Onboard</span><span class="sxs-lookup"><span data-stu-id="f342f-107">Changes in Onboard</span></span>

<span data-ttu-id="f342f-108">Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="f342f-108">This release includes minor bug fixes for Dynamics 365 Talent: Onboard.</span></span>

## <a name="changes-in-core-hr"></a><span data-ttu-id="f342f-109">Ändringar i Core HR</span><span class="sxs-lookup"><span data-stu-id="f342f-109">Changes in Core HR</span></span>

<span data-ttu-id="f342f-110">Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2697.</span><span class="sxs-lookup"><span data-stu-id="f342f-110">Changes described in this section apply to build number 8.1.2697.</span></span> <span data-ttu-id="f342f-111">Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="f342f-111">The numbers in parentheses in some headings refer to support numbers in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

 
### <a name="cant-delete-workers-that-dont-have-employment-records---386157"></a><span data-ttu-id="f342f-112">Det går inte att radera arbetare som inte har anställningsposter - (386157)</span><span class="sxs-lookup"><span data-stu-id="f342f-112">Can't delete workers that don't have employment records - (386157)</span></span>

<span data-ttu-id="f342f-113">Denna ändring lägger till ett borttagningsalternativ i formuläret **arbetare utan anställning**.</span><span class="sxs-lookup"><span data-stu-id="f342f-113">This change adds a delete option in the **Workers without employment** form.</span></span> <span data-ttu-id="f342f-114">Arbetare visas i det här formuläret när det inte finns några framtida, aktiva eller historiska anställningar för arbetaren.</span><span class="sxs-lookup"><span data-stu-id="f342f-114">Workers appear in this form when no future, active, or historical employments exist for the worker.</span></span> <span data-ttu-id="f342f-115">I den här versionen är ta bort endast aktiverad för systemadministratörer.</span><span class="sxs-lookup"><span data-stu-id="f342f-115">In this release, delete is only enabled for System Administrators.</span></span> <span data-ttu-id="f342f-116">Under nästa veckas utgivning kommer dock säkerhet att uppdateras så att alla användare med rollen personalassistent kan ta bort medarbetare utan anställning.</span><span class="sxs-lookup"><span data-stu-id="f342f-116">However, in next week's release, security will be updated to allow all users with the HR assistant role to remove employees without employments.</span></span> <span data-ttu-id="f342f-117">Du kan även göra dessa ändringar manuellt genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="f342f-117">You can also make these changes manually by following the following steps.</span></span>

1. <span data-ttu-id="f342f-118">Gå till **Säkerhetskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f342f-118">Go to **Security configuration**.</span></span>
2. <span data-ttu-id="f342f-119">På fliken **behörigheter** filtrera listan **behörigheter** till **Underhåll arbetare**.</span><span class="sxs-lookup"><span data-stu-id="f342f-119">In the **Privileges** tab, filter the **Privileges** list to **Maintain workers**.</span></span>
3. <span data-ttu-id="f342f-120">I kolumnen **Referenser**, välj **Visa menyobjekt**.</span><span class="sxs-lookup"><span data-stu-id="f342f-120">In the **References** column, select **Display menu items**.</span></span>
4. <span data-ttu-id="f342f-121">I kolumnen **Visa menyobjekt**, välj **HcmWOrkersWithoutEmployment**.</span><span class="sxs-lookup"><span data-stu-id="f342f-121">In **Display menu items**, select **HcmWOrkersWithoutEmployment**.</span></span>
5. <span data-ttu-id="f342f-122">Ange behörigheten **Ta bort** till Bevilja.</span><span class="sxs-lookup"><span data-stu-id="f342f-122">Set the **Delete** permission to Grant.</span></span>
6. <span data-ttu-id="f342f-123">Välj fliken **Opublicerade objekt**.</span><span class="sxs-lookup"><span data-stu-id="f342f-123">Select the **Unpublished objects** tab.</span></span>
7. <span data-ttu-id="f342f-124">Markera **Publicera alla**.</span><span class="sxs-lookup"><span data-stu-id="f342f-124">Select **Publish all**.</span></span>
