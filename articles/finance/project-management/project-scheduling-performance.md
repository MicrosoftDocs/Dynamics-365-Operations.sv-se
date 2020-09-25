---
title: Prestanda för tidsplanering av projektresurser
description: Det här avsnittet innehåller information om hur du förbättrar prestanda vid resursplanering för ett stort antal projekt.
author: Yowelle
manager: AnnBe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 10.0.14
ms.search.validFrom: 2020-09-01
ms.openlocfilehash: 988fc83230f08a6534caa7c37784757d73c1cc12
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760669"
---
# <a name="project-resource-scheduling-performance"></a><span data-ttu-id="b4632-103">Prestanda för tidsplanering av projektresurser</span><span class="sxs-lookup"><span data-stu-id="b4632-103">Project resource scheduling performance</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


<span data-ttu-id="b4632-104">Prestandafrågor som rör resursplanering kan inträffa när antalet projekt når tusental.</span><span class="sxs-lookup"><span data-stu-id="b4632-104">Performance issues related to resource scheduling can occur when the number of projects reaches into the thousands.</span></span> <span data-ttu-id="b4632-105">För att förbättra resursens schemaläggningsprestanda finns det en funktion som gör att användarna kan förkorta den tid det tar att starta formuläret för resurstillgänglighet.</span><span class="sxs-lookup"><span data-stu-id="b4632-105">To improve resource scheduling performance, a feature is available that allows users to reduce the time that it takes to launch the resource availability form.</span></span> <span data-ttu-id="b4632-106">Specifikt tar detta bort synkroniseringsprocessen för resurskapacitetsuppbyggnad och använder tabellen **ResProjectResource** för att påskynda resursökningen.</span><span class="sxs-lookup"><span data-stu-id="b4632-106">Specifically, this removes the resource capacity roll-up synchronization process and uses the **ResProjectResource** table to speed up the resource lookup.</span></span> <span data-ttu-id="b4632-107">Observera att tabellen **ResRollup** inte längre används.</span><span class="sxs-lookup"><span data-stu-id="b4632-107">Note that the **ResRollup** table will no longer be used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4632-108">Om det finns ett beroende av antingen resurskapacitetssynkroniseringsprocessen eller tabellen **ResProjectResource** inte använder den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="b4632-108">If there is a dependency on either the resource capacity roll-up synchronization process or the **ResProjectResource** table, do not use this feature.</span></span>

## <a name="enable-resource-scheduling-performance-enhancement"></a><span data-ttu-id="b4632-109">Aktivera prestandaförbättring för resursplanering</span><span class="sxs-lookup"><span data-stu-id="b4632-109">Enable resource scheduling performance enhancement</span></span>
<span data-ttu-id="b4632-110">Gör på följande sätt om du vill aktivera prestandaförbättring för resursplanering.</span><span class="sxs-lookup"><span data-stu-id="b4632-110">To enable resource scheduling performance enhancement, complete the following steps.</span></span>

1. <span data-ttu-id="b4632-111">Gå till **funktionenshantera** > **Alla** och i listan funktioner letar du upp **Aktivera funktionen för prestandaförbättring för resursplanering** .</span><span class="sxs-lookup"><span data-stu-id="b4632-111">Go to **Feature management** > **All**, and in the feature list, locate **Enable project resource scheduling performance enhancement feature**.</span></span>
2. <span data-ttu-id="b4632-112">Välj **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="b4632-112">Select **Enable now**.</span></span>

> [!NOTE]
> <span data-ttu-id="b4632-113">Om du inte hittar funktionen i listan väljer du **Sök efter uppdateringar** för att uppdatera listan.</span><span class="sxs-lookup"><span data-stu-id="b4632-113">If you can't find the feature in the list, select **Check for updates** to refresh the list.</span></span>

3. <span data-ttu-id="b4632-114">Uppdatera din webbläsare och gå till **Projekthantering och redovisning** > **Periodisk** > **Projektresurser** > **Synkronisera resurskalendrarnas kapacitet i alla företag**.</span><span class="sxs-lookup"><span data-stu-id="b4632-114">Refresh your browser, and then go to **Project management and accounting** > **Periodic** > **Project resources** > **Synchronize resource calendars capacity across all companies**.</span></span>
4. <span data-ttu-id="b4632-115">Ange **Ta bort befintliga kapacitetsposter** till **Ja** om du vill ta bort tidigare data.</span><span class="sxs-lookup"><span data-stu-id="b4632-115">Set **Remove existing capacity records** to **Yes** to remove previous data.</span></span> <span data-ttu-id="b4632-116">Om du vill generera stegvisa data ställer du in den på **Nej** .</span><span class="sxs-lookup"><span data-stu-id="b4632-116">If you want generate incremental data, set it to **No**.</span></span>
5. <span data-ttu-id="b4632-117">I fältet **Periodkod** väljer du den period då data ska genereras.</span><span class="sxs-lookup"><span data-stu-id="b4632-117">In the **Period code** field, select the period in which data should be generated.</span></span> <span data-ttu-id="b4632-118">Om du väljer en periodkod behöver du inte ange start- och slutdatum.</span><span class="sxs-lookup"><span data-stu-id="b4632-118">If you select a period code, a start and end date do not need to be defined.</span></span>
6. <span data-ttu-id="b4632-119">Om du lämnar fältet **periodkod** tomt, ska du välja specifika start- och slutdatum för att generera data.</span><span class="sxs-lookup"><span data-stu-id="b4632-119">If you leave the **Period code** field blank, select specific start and end dates to generate data.</span></span>
7. <span data-ttu-id="b4632-120">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4632-120">Select **OK**.</span></span>

 > [!NOTE]
 > <span data-ttu-id="b4632-121">Detta innebär att allmänna data distribueras till tabellen **ResCalendarCapacity** i alla företag i din miljö, så att batch-jobbet bara behöver köras i en juridisk person.</span><span class="sxs-lookup"><span data-stu-id="b4632-121">This will distribute general data to the **ResCalendarCapacity** table across all companies in your environment, so the batch job only needs to be run in one legal entity.</span></span> <span data-ttu-id="b4632-122">Data i det här batchjobbet behövs för att beräkna resurskapacitet genom den associerade kalendern.</span><span class="sxs-lookup"><span data-stu-id="b4632-122">The data in this batch job is needed to calculate resource capacity through the associated calendar.</span></span>

8. <span data-ttu-id="b4632-123">Gå till **Projekthantering och redovisning** > **Periodisk** > **Projektresurser** > **Fyll i projektresurser i alla företag** och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4632-123">Go to **Project management and accounting** > **Periodic** > **Project resources** > **Populate project resources across all companies** and then select **OK**.</span></span> <span data-ttu-id="b4632-124">Det här är datauppgraderingsskriptet för allmänna data i tabellerna **ResProjectResource**, **ResCalendarDateTimeRange** och **ResEffectiveDateTimeRange**.</span><span class="sxs-lookup"><span data-stu-id="b4632-124">This is the data upgrade script for general data in the **ResProjectResource**, **ResCalendarDateTimeRange**, and **ResEffectiveDateTimeRange** tables.</span></span> <span data-ttu-id="b4632-125">Värden för fältet **PSAPRojSchedRole.RootActivity** uppdateras också.</span><span class="sxs-lookup"><span data-stu-id="b4632-125">Values for the **PSAPRojSchedRole.RootActivity** field are also updated.</span></span> <span data-ttu-id="b4632-126">Om det inte körs visas en varning när du försöker köra resursplaneringsåtgärder.</span><span class="sxs-lookup"><span data-stu-id="b4632-126">If this is not run, you will receive a warning when you try to execute resource scheduling operations.</span></span>
 
## <a name="turn-off-resource-scheduling-performance-enhancement"></a><span data-ttu-id="b4632-127">Inaktivera prestandaförbättring för resursplanering</span><span class="sxs-lookup"><span data-stu-id="b4632-127">Turn off resource scheduling performance enhancement</span></span>

1. <span data-ttu-id="b4632-128">Gå till **funktionenshantera** > **Alla** och sök efter **Aktivera funktionen för prestandaförbättring för resursplanering** .</span><span class="sxs-lookup"><span data-stu-id="b4632-128">Go to **Feature management** > **All**  and search for **Enable project resource scheduling performance enhancement feature**.</span></span>
2. <span data-ttu-id="b4632-129">Markera funktionen och välj sedan knappen **Inaktivera**.</span><span class="sxs-lookup"><span data-stu-id="b4632-129">Select the feature, and then select the **Disable** button.</span></span>
3. <span data-ttu-id="b4632-130">Uppdatera webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="b4632-130">Refresh your browser.</span></span>
4. <span data-ttu-id="b4632-131">Gå till **Projekthantering och redovisning** > **Periodisk** > **Kapacitetssynkronisering** > **Synkronisera kapacitetsuppföljningar för resurs**.</span><span class="sxs-lookup"><span data-stu-id="b4632-131">Go to **Project management and accounting** > **Periodic** > **Capacity synchronization** > **Synchronize resource capacity roll-ups**.</span></span>
5. <span data-ttu-id="b4632-132">På sidan **Resurskapacitetsuppbyggnad** ange **Ta bort befintliga kapacitetsposter** till **Ja** för att ta bort tidigare data.</span><span class="sxs-lookup"><span data-stu-id="b4632-132">On the **Capacity roll-up synchronization** page, set **Remove existing capacity records** to **Yes** to remove previous data.</span></span> <span data-ttu-id="b4632-133">Om du vill generera stegvisa data ställer du in den på **Nej** .</span><span class="sxs-lookup"><span data-stu-id="b4632-133">If you want to generate incremental data, set it to **No**.</span></span>
6. <span data-ttu-id="b4632-134">I fältet **Periodkod** väljer du den period då data ska genereras.</span><span class="sxs-lookup"><span data-stu-id="b4632-134">In the **Period code** field, select the period in which data should be generated.</span></span> <span data-ttu-id="b4632-135">Om du väljer en periodkod behöver du inte ange start- och slutdatum.</span><span class="sxs-lookup"><span data-stu-id="b4632-135">If you select a period code, a start and end date do not need to be defined.</span></span>
7. <span data-ttu-id="b4632-136">Om du lämnar fältet **periodkod** tomt, ska du välja specifika start- och slutdatum för att generera data.</span><span class="sxs-lookup"><span data-stu-id="b4632-136">If you leave the **Period code** field blank, select specific start and end dates to generate data.</span></span>
8. <span data-ttu-id="b4632-137">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4632-137">Select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="b4632-138">Detta innebär att allmänna data distribueras till tabellen **ResRollup** i alla företag i din miljö, så att batch-jobbet bara behöver köras i en juridisk person.</span><span class="sxs-lookup"><span data-stu-id="b4632-138">This will distribute general data to the **ResRollup** table across all companies in your environment, so the batch job only needs to be run in one legal entity.</span></span> <span data-ttu-id="b4632-139">Det här batch-jobbet krävs för alla vyer **resurstillgänglighet**.</span><span class="sxs-lookup"><span data-stu-id="b4632-139">This batch job is needed for all **Resource Availability** views.</span></span> <span data-ttu-id="b4632-140">Om det här batchjobbet inte körs **ResRollup** data genereras i farten, vilket kan ta tid.</span><span class="sxs-lookup"><span data-stu-id="b4632-140">If this batch job is not run, the **ResRollup** data will be generated on the fly, which can take time.</span></span>
