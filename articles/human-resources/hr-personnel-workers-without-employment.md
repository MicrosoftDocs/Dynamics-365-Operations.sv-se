---
title: Arbetare utan anställning
description: Medarbetare utan framtida, aktiva eller historiska anställningar i organisationen visas i formuläret Medarbetare utan anställning.
author: andreabichsel
ms.date: 04/06/2021
ms.topic: ''
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorkerV2, HRMMassHireProject, HRMMassHireLine, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-04-06
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f6fbada6feb55b8627b1aa1ddfe367177edb7a0a
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6051723"
---
# <a name="workers-without-employment"></a><span data-ttu-id="e3490-103">Arbetare utan anställning</span><span class="sxs-lookup"><span data-stu-id="e3490-103">Workers without employment</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e3490-104">Medarbetare utan framtida, aktiva eller historiska anställningar i organisationen visas i formuläret **Medarbetare utan anställning**.</span><span class="sxs-lookup"><span data-stu-id="e3490-104">Workers with no future, active, or historical employment with your organization appear in the **Workers without employment** form.</span></span> <span data-ttu-id="e3490-105">Arbetare med den här statusen kan visas när du importerar medarbetare utan en anställningspost, eller när du tar bort en medarbetares anställning via **Medarbetare > Anställningshistorik**.</span><span class="sxs-lookup"><span data-stu-id="e3490-105">Workers with this status can appear when you import workers without an employment record, or when you delete a worker's employment via **Workers > Employment history**.</span></span>

<span data-ttu-id="e3490-106">Som standard är formuläret **Medarbetare utan anställning** tillgängligt för följande roller:</span><span class="sxs-lookup"><span data-stu-id="e3490-106">By default, the **Workers without employment** form is available to the following roles:</span></span>

- <span data-ttu-id="e3490-107">Personalassistent</span><span class="sxs-lookup"><span data-stu-id="e3490-107">Human Resources Assistant</span></span>
- <span data-ttu-id="e3490-108">Personalchef</span><span class="sxs-lookup"><span data-stu-id="e3490-108">Human Resources Manager</span></span>
- <span data-ttu-id="e3490-109">Rekryterare</span><span class="sxs-lookup"><span data-stu-id="e3490-109">Recruiter</span></span>
- <span data-ttu-id="e3490-110">Kompensations- och förmånsansvarig</span><span class="sxs-lookup"><span data-stu-id="e3490-110">Comp and Benefits Manager</span></span>
- <span data-ttu-id="e3490-111">Löneadministratör</span><span class="sxs-lookup"><span data-stu-id="e3490-111">Payroll Administrator</span></span>
- <span data-ttu-id="e3490-112">Löneansvarig</span><span class="sxs-lookup"><span data-stu-id="e3490-112">Payroll Manager</span></span>
- <span data-ttu-id="e3490-113">Utbildningsansvarig</span><span class="sxs-lookup"><span data-stu-id="e3490-113">Training Manager</span></span>

<span data-ttu-id="e3490-114">I listan **Medarbetare utan anställning** kan du ta bort listade individer.</span><span class="sxs-lookup"><span data-stu-id="e3490-114">In the **Workers without employment** list, you can delete the individuals listed.</span></span> <span data-ttu-id="e3490-115">Som standard ges denna behörighet till rollen Personalassistent.</span><span class="sxs-lookup"><span data-stu-id="e3490-115">By default, this privilege is given to the Human Resources Assistant role.</span></span> <span data-ttu-id="e3490-116">Du kan ge den här behörigheten till andra roller med hjälp av följande steg:</span><span class="sxs-lookup"><span data-stu-id="e3490-116">You can give this privilege to other roles with the following steps:</span></span>

1. <span data-ttu-id="e3490-117">Välj **Systemadministration** och välj sedan fliken **Säkerhetskonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e3490-117">Select **System administration**, and then select **Security configuration**.</span></span>

2. <span data-ttu-id="e3490-118">På fliken **behörigheter** filtrera listan **behörigheter** till **Underhåll arbetare**.</span><span class="sxs-lookup"><span data-stu-id="e3490-118">In the **Privileges** tab, filter the **Privileges** list to **Maintain workers**.</span></span>

   <span data-ttu-id="e3490-119">[![Lista över filterbehörigheter](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)</span><span class="sxs-lookup"><span data-stu-id="e3490-119">[![Filter Privileges list](./media/hr-personnel-workers-without-employment-filter.png)](./media/hr-personnel-workers-without-employment-filter.png)</span></span>

3. <span data-ttu-id="e3490-120">I kolumnen **Referenser**, välj **Visa menyobjekt**.</span><span class="sxs-lookup"><span data-stu-id="e3490-120">In the **References** column, select **Display menu items**.</span></span>

4. <span data-ttu-id="e3490-121">I kolumnen **Visa menyobjekt** väljer du **HcmWOrkersWithoutEmployment**.</span><span class="sxs-lookup"><span data-stu-id="e3490-121">In **Display menu items**, select **HcmWorkersWithoutEmployment**.</span></span>

   <span data-ttu-id="e3490-122">[![Välj formulär](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)</span><span class="sxs-lookup"><span data-stu-id="e3490-122">[![Select form](./media/hr-personnel-workers-without-employment-select.png)](./media/hr-personnel-workers-without-employment-select.png)</span></span>

5. <span data-ttu-id="e3490-123">Ange behörigheten **Ta bort** som **Beviljande**.</span><span class="sxs-lookup"><span data-stu-id="e3490-123">Set the **Delete** permission to **Grant**.</span></span>

6. <span data-ttu-id="e3490-124">Välj fliken **Opublicerade objekt**.</span><span class="sxs-lookup"><span data-stu-id="e3490-124">Select the **Unpublished objects** tab.</span></span>

7. <span data-ttu-id="e3490-125">Markera **Publicera alla**.</span><span class="sxs-lookup"><span data-stu-id="e3490-125">Select **Publish all**.</span></span>

   <span data-ttu-id="e3490-126">[![Publicera ändringar](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)</span><span class="sxs-lookup"><span data-stu-id="e3490-126">[![Publish changes](./media/hr-personnel-workers-without-employment-publish.png)](./media/hr-personnel-workers-without-employment-publish.png)</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]