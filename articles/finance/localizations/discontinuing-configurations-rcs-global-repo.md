---
title: Upphöra konfigurationer i den globala RCS-databasen
description: I det här avsnittet beskrivs hur du upphör att konfigurerar i globala RCS-databasen.
author: JaneA07
manager: AnnBe
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 35d0af91161d898b09557a83913019609c71e836
ms.sourcegitcommit: e9d19f25e64cf4d1c1d07c8031a7081454a6f79e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2021
ms.locfileid: "5474258"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a><span data-ttu-id="370a7-103">Upphöra konfigurationer i den globala RCS-databasen</span><span class="sxs-lookup"><span data-stu-id="370a7-103">Discontinue configurations in the RCS Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="370a7-104">I det här avsnittet beskrivs hur du upphör att konfigurerar i globala RCS-databasen.</span><span class="sxs-lookup"><span data-stu-id="370a7-104">This topic describes how to discontinue configuration in the RCS Global repository.</span></span> <span data-ttu-id="370a7-105">Tidigare var det bara möjligt att ta bort konfigurationer som inte längre behövs.</span><span class="sxs-lookup"><span data-stu-id="370a7-105">Previously, it was possible only to delete configurations that were no longer required.</span></span> <span data-ttu-id="370a7-106">Men nu kan du markera en släppt konfiguration som **Upphörd** i globala RCS-databasen.</span><span class="sxs-lookup"><span data-stu-id="370a7-106">However now you can mark a released configuration as **Discontinued** in the RCS Global repository.</span></span> <span data-ttu-id="370a7-107">Med den här funktionen kan du också göra följande:</span><span class="sxs-lookup"><span data-stu-id="370a7-107">With this functionality, you can also do the following:</span></span> 
 
 - <span data-ttu-id="370a7-108">Ange i förväg meddelanden när en konfiguration har planerats att upphöra.</span><span class="sxs-lookup"><span data-stu-id="370a7-108">Provide up front notifications when a configuration is planned to be discontinued.</span></span>
 - <span data-ttu-id="370a7-109">Inkludera tillämpliga uppgifter om ersättningskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="370a7-109">Include applicable details about the replacement configuration.</span></span>
 - <span data-ttu-id="370a7-110">Ange ett datum för **Stöds till** för att den specifika konfigurationen ska informera användaren när den kommer att avbrytas.</span><span class="sxs-lookup"><span data-stu-id="370a7-110">Set a **Supported until** date for the specific configuration to inform the user when it will be discontinued.</span></span>

<span data-ttu-id="370a7-111">När du upphör att använda en konfigurationsversion kan du ange följande valfria information:</span><span class="sxs-lookup"><span data-stu-id="370a7-111">When you discontinue a configuration version, you can specify the following optional information:</span></span>

  - <span data-ttu-id="370a7-112">**Ersättningskonfiguration**</span><span class="sxs-lookup"><span data-stu-id="370a7-112">**Replacement configuration**</span></span>
  - <span data-ttu-id="370a7-113">**Konfigurationsversion för ersättning**</span><span class="sxs-lookup"><span data-stu-id="370a7-113">**Replacement configuration version**</span></span>
  - <span data-ttu-id="370a7-114">**Fritextnotering**: Använd det här fältet för att tillhandahålla dokumentationslänkar eller referenser</span><span class="sxs-lookup"><span data-stu-id="370a7-114">**Free text note**: Use this field to provide documentation links or references</span></span>
  - <span data-ttu-id="370a7-115">**Stöds tills**: Det här fältet innehåller det föreslagna datum fram till vilket aktuell konfiguration/version kommer att stödjas.</span><span class="sxs-lookup"><span data-stu-id="370a7-115">**Supported until**: This field provides the proposed date up to which the current configuration/version will be supported.</span></span> <span data-ttu-id="370a7-116">Datumet måste uppdateras manuellt.</span><span class="sxs-lookup"><span data-stu-id="370a7-116">This date must be updated manually.</span></span>
  
<span data-ttu-id="370a7-117">Om du vill avbryta konfigurationen utför du följande steg.</span><span class="sxs-lookup"><span data-stu-id="370a7-117">To discontinue the configuration, complete the following steps.</span></span> 

1. <span data-ttu-id="370a7-118">Välj om du vill upphöra att använda en enda version eller alla versioner med samma inställningar i en operation genom att ange **Alla versioner** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="370a7-118">Select whether you want to discontinue a single version or all versions with the same settings in one operation by setting **All versions** to **Yes**.</span></span> 
2. <span data-ttu-id="370a7-119">Ange parametern **Upphör** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="370a7-119">Set the **Discontinue** parameter to **Yes**.</span></span>
3. <span data-ttu-id="370a7-120">Välj **OK** om du vill upphöra konfigurationerna.</span><span class="sxs-lookup"><span data-stu-id="370a7-120">Select **OK** to discontinue the configurations.</span></span> <span data-ttu-id="370a7-121">Fältet **Utgångsdatum** fylls då i när du sparar ändringarna.</span><span class="sxs-lookup"><span data-stu-id="370a7-121">The **Discontinued date** field will be populated when you save the changes.</span></span>

![Upphöra med konfigurationsinformation](media/Discontinue-details-2.png)
  
<span data-ttu-id="370a7-123">Du kan när som helst återställa konfigurationen till **Delad** eller justera annulleringsinformation.</span><span class="sxs-lookup"><span data-stu-id="370a7-123">You can revert configuration back to **Shared** or adjust discontinuation information at any time.</span></span> <span data-ttu-id="370a7-124">Om du delar en konfiguration anger du datumet **Stöds till** och all annan information relaterad till avvecklingen för att ange dina planer för framtida avveckling.</span><span class="sxs-lookup"><span data-stu-id="370a7-124">If you share a configuration, specify the **Supported until** date and all other information related to the discontinuation to indicate your plans for future discontinuation.</span></span>

<span data-ttu-id="370a7-125">Om du vill dela information om en planerad avbrytning, innan konfigurationen faktiskt avbryts, kan användaren fylla i alla fält som är relaterade till ersättning men lämna parametern **Upphör** anges till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="370a7-125">If you want to share information about a planned discontinuation, prior to actually discontinuing the configuration, user is able to prefill all fields related to replacement but leave the **Discontinue** parameter set to **No**.</span></span>

> [!NOTE]
> <span data-ttu-id="370a7-126">När någon av dem avbryts begränsas inte operationer med konfigurationer.</span><span class="sxs-lookup"><span data-stu-id="370a7-126">Discontinuation doesn't limit operations with configurations.</span></span> <span data-ttu-id="370a7-127">De här fälten är information om du kan fortsätta att importera, köra eller härleda konfigurationerna.</span><span class="sxs-lookup"><span data-stu-id="370a7-127">You can continue to import, run, or derive the configurations, these fields are informational.</span></span>

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a><span data-ttu-id="370a7-128">Finance stöder visning av denna information från version 10.0.14</span><span class="sxs-lookup"><span data-stu-id="370a7-128">Finance supports displaying this information starting in version 10.0.14</span></span>

<span data-ttu-id="370a7-129">Startar i version 10.0.14, Dynamics 365 Finance stöder visa annulleringsinformation.</span><span class="sxs-lookup"><span data-stu-id="370a7-129">Starting in version 10.0.14, Dynamics 365 Finance supports displaying discontinuation information.</span></span> <span data-ttu-id="370a7-130">På sidan **globala databas** kan du visa aktuell information som är relaterad till annullering.</span><span class="sxs-lookup"><span data-stu-id="370a7-130">On the **Global repository** page, you can view up to date information related to discontinuation.</span></span> <span data-ttu-id="370a7-131">Som standard filtreras konfigurationer som upphör att vara utfilterade.</span><span class="sxs-lookup"><span data-stu-id="370a7-131">By default, configurations that are discontinued are filtered out.</span></span>
  
<span data-ttu-id="370a7-132">Sidan **Importerade konfigurationer** (ERSolutionTable) visar konfigurationer som redan upphörde när det importerades.</span><span class="sxs-lookup"><span data-stu-id="370a7-132">The **Imported configurations** (ERSolutionTable) page, shows configurations that were already discontinued when there were imported.</span></span> <span data-ttu-id="370a7-133">För de konfigurationer som upphör att köras efter importen kan information om förkonteringen synkroniseras genom att jobbet **Importkonfigurationer uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="370a7-133">For those configurations that were discontinued after import, the discontinuation information can be synchronized by running the **Import configurations updates** job.</span></span>


