---
title: Villkorsutvärdering
description: Det här avsnittet beskriver hur du skapar en mall för villkorsutvärdering och registrering på en tillgång i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e2694b3ee51e2619a94e7ea2f4039fb52adddbbc
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208925"
---
# <a name="condition-assessment"></a><span data-ttu-id="34e3b-103">Villkorsutvärdering</span><span class="sxs-lookup"><span data-stu-id="34e3b-103">Condition assessment</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="34e3b-104">Det här avsnittet beskriver hur du skapar en mall för villkorsutvärdering och registrering på en tillgång i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="34e3b-104">This topic explains how to create a condition assessment template and registration on an asset in Asset Management.</span></span> <span data-ttu-id="34e3b-105">Villkorsutvärdering utförs med jämna mellanrum och det primära målet är att skapa och underhålla villkorsdata för tillgångar.</span><span class="sxs-lookup"><span data-stu-id="34e3b-105">Condition assessment is performed at regular intervals, and the primary objective is to create and maintain condition data on assets.</span></span> <span data-ttu-id="34e3b-106">Sett ur ett förebyggande underhållsperspektiv är det viktigt att övervaka viktig information som aktuellt tillstånd och återstående livslängd.</span><span class="sxs-lookup"><span data-stu-id="34e3b-106">Seen from a preventive maintenance perspective, it is important to monitor key information such as current condition, and remaining life span.</span></span> <span data-ttu-id="34e3b-107">Dessutom, om du utför villkorsutvärdering med jämna mellanrum, kommer du att kunna övervaka och jämföra förhållandena på maskinen i din fabrik.</span><span class="sxs-lookup"><span data-stu-id="34e3b-107">Furthermore, if you carry out condition assessment at regular intervals, you will be able to monitor and compare conditions on the machinery in your factory.</span></span>

<span data-ttu-id="34e3b-108">Tillståndsbedömning kan användas för att mäta och övervaka många förhållanden på din utrustning.</span><span class="sxs-lookup"><span data-stu-id="34e3b-108">Condition assessment can be used to measure and monitor many conditions on your equipment.</span></span> <span data-ttu-id="34e3b-109">Exempel: du kan mäta vibrationer på din maskin.</span><span class="sxs-lookup"><span data-stu-id="34e3b-109">Example: You could measure vibrations on your machinery.</span></span> <span data-ttu-id="34e3b-110">När du har registrerat vibrationsmätningar i tillståndshantering på olika typer av utrustning kan du söka efter den senaste registrerade utvärderingen och se vibrationsmätningar.</span><span class="sxs-lookup"><span data-stu-id="34e3b-110">After you have registered vibration measurements in Asset Management on various types of equipment, you can search for the latest registered assessment and view vibration measurements.</span></span>

<span data-ttu-id="34e3b-111">Villkorsutvärdering skapas på tillgångar.</span><span class="sxs-lookup"><span data-stu-id="34e3b-111">Condition assessment is created on assets.</span></span> <span data-ttu-id="34e3b-112">Du ställer in en mall för villkorsutvärdering på en tillgångstyp innan du utför villkors utvärderingsproceduren.</span><span class="sxs-lookup"><span data-stu-id="34e3b-112">You set up a condition assessment template on an asset type before you carry out the condition assessment procedure.</span></span> <span data-ttu-id="34e3b-113">Anledningen till att använda mallar för villkorsutvärdering är att undvika variation av villkorsdata på liknande tillgångar.</span><span class="sxs-lookup"><span data-stu-id="34e3b-113">The reason for using templates for condition assessment is to avoid variation of condition data on similar assets.</span></span> <span data-ttu-id="34e3b-114">Sekvensen för att ställa in och använda villkorsutvärdering i tillgångshantering är: först ställer du in de nödvändiga villkorsutvärderingsmallarna.</span><span class="sxs-lookup"><span data-stu-id="34e3b-114">The sequence for setting up and using condition assessment in Asset Management is: First you set up the required condition assessment templates.</span></span> <span data-ttu-id="34e3b-115">Därefter kopplar du mallar med tillgångstyper i formuläret **tillgångstyper**.</span><span class="sxs-lookup"><span data-stu-id="34e3b-115">Next, you associate templates with asset types in the **Asset types** form.</span></span> <span data-ttu-id="34e3b-116">Slutligen kan du skapa villkorsutvärderingsregistreringar på en tillgång i formuläret **tillgång**.</span><span class="sxs-lookup"><span data-stu-id="34e3b-116">Finally, you can create condition assessment registrations on an asset in the **Asset** form.</span></span>

## <a name="create-a-condition-assessment-template"></a><span data-ttu-id="34e3b-117">Skapa en mall för villkorsutvärdering</span><span class="sxs-lookup"><span data-stu-id="34e3b-117">Create a condition assessment template</span></span>

1. <span data-ttu-id="34e3b-118">Välj **tillgångshantering** > **inställningar** > **tillgångstyper** > **villkorsutvärdering**.</span><span class="sxs-lookup"><span data-stu-id="34e3b-118">Select **Asset management** > **Setup** > **Asset types** > **Condition assessment**.</span></span>
2. <span data-ttu-id="34e3b-119">Skapa en ny mall genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="34e3b-119">Select **New** to create a new template.</span></span>
3. <span data-ttu-id="34e3b-120">Infoga ID för mallen i fältet **Mall** field.</span><span class="sxs-lookup"><span data-stu-id="34e3b-120">Insert and ID for the template in the **Template** field.</span></span>
4. <span data-ttu-id="34e3b-121">Infoga ett namn för mallen i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="34e3b-121">Insert a name for the template in the **Name** field.</span></span>
5. <span data-ttu-id="34e3b-122">På snabbfliken **Villkorsutvärderingsrader** lägger du till de rader som krävs för villkorsutvärderingen, inklusive val av lämplig villkorstyp och måttenhet.</span><span class="sxs-lookup"><span data-stu-id="34e3b-122">On the **Condition assessment lines** FastFab, add the lines required for the condition assessment, including selection of the appropriate condition type and measurement unit.</span></span>
6. <span data-ttu-id="34e3b-123">På snabbfliken **tillgångstyper** lägger du till de tillgångstyper som ska använda mallen för villkorsutvärdering.</span><span class="sxs-lookup"><span data-stu-id="34e3b-123">On the **Asset types** FastTab, add the asset types that should use the condition assessment template.</span></span>
7. <span data-ttu-id="34e3b-124">I fälten **rader** och **tillgångstyper** i gruppen i **detaljgruppen** överst på skärmen ser du antalet utvärderingsrader och tillgångstyper som är relaterade till den valda villkorsutvärderingsmallen.</span><span class="sxs-lookup"><span data-stu-id="34e3b-124">In the **Lines** and **Asset types** fields in the **Details** group at the top of the screen, you will see the number of assessment lines and asset types related to the selected condition assessment template.</span></span>


## <a name="create-condition-assessment-registration-on-an-asset"></a><span data-ttu-id="34e3b-125">Skapa villkorsutvärderingsregistrering på en tillgång</span><span class="sxs-lookup"><span data-stu-id="34e3b-125">Create condition assessment registration on an asset</span></span>

1. <span data-ttu-id="34e3b-126">Välj **Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="34e3b-126">Select **Asset management** > **Common** > **Assets** > **All Assets**.</span></span>
2. <span data-ttu-id="34e3b-127">I listan väljer du den tillgång du vill skapa en villkorsutvärderingsregistrering för.</span><span class="sxs-lookup"><span data-stu-id="34e3b-127">In the list, select the asset for which you want to create a condition assessment registration.</span></span>
3. <span data-ttu-id="34e3b-128">Klicka på **villkorsutvärdering** på fliken **Allmänt**.</span><span class="sxs-lookup"><span data-stu-id="34e3b-128">On the **General** tab, click **Condition assessment**.</span></span>
4. <span data-ttu-id="34e3b-129">Klicka på **Ny** om du vill göra en ny registrering.</span><span class="sxs-lookup"><span data-stu-id="34e3b-129">Click **New** to make a new registration.</span></span>
5. <span data-ttu-id="34e3b-130">Välj datum för villkorsutvärderingen i fältet **datum**.</span><span class="sxs-lookup"><span data-stu-id="34e3b-130">Select the date for the condition assessment in the **Date** field.</span></span>
6. <span data-ttu-id="34e3b-131">Välj namnet på arbetare som utförde utvärderingsregistreringen i fältet **arbetare**.</span><span class="sxs-lookup"><span data-stu-id="34e3b-131">Select the name of the worker who carried out the assessment registration in the **Worker** field.</span></span>
7. <span data-ttu-id="34e3b-132">I fältet **rader** visas antalet utvärderingsrader som har ställts in för villkorsutvärderingen.</span><span class="sxs-lookup"><span data-stu-id="34e3b-132">In the **Lines** field, you see the number of assessment lines set up on the condition assessment.</span></span>
8. <span data-ttu-id="34e3b-133">Välj en mall för villkorsutvärderingen i fältet **mall**.</span><span class="sxs-lookup"><span data-stu-id="34e3b-133">Select a template for the condition assessment in the **Template** field.</span></span> <span data-ttu-id="34e3b-134">Namnet på mallen infogas automatiskt i fältet **namn** och de relaterade registreringsraderna infogas på snabbfliken **villkorsbedömningsrader**.</span><span class="sxs-lookup"><span data-stu-id="34e3b-134">The name of the template is automatically inserted in the **Name** field, and the related registration lines are inserted on the **Condition assessment lines** FastTab.</span></span>
9. <span data-ttu-id="34e3b-135">Du kan infoga anteckningar som rör den valda villkorsutvärderingen på snabbfliken **anteckningar**.</span><span class="sxs-lookup"><span data-stu-id="34e3b-135">You can insert notes relating to the selected condition assessment on the **Notes** FastTab.</span></span>
10. <span data-ttu-id="34e3b-136">För varje villkorsutvärderingsrad infogar du mätdata i fältet **värde**.</span><span class="sxs-lookup"><span data-stu-id="34e3b-136">For each condition assessment line, insert measurement data in the **Value** field.</span></span>
11. <span data-ttu-id="34e3b-137">Du kan infoga en kommentar som relaterar till den valda registreringsraden på snabbfliken **villkorsutvärderingsrader** > fältet **kommentarer**.</span><span class="sxs-lookup"><span data-stu-id="34e3b-137">You can insert a comment relating to the selected registration line on the **Condition assessment lines** FastTab > **Comments** field.</span></span> <span data-ttu-id="34e3b-138">Om du lägger till en kommentar på en rad markeras kryssrutan **Kommentar** automatiskt.</span><span class="sxs-lookup"><span data-stu-id="34e3b-138">If you add a comment on a line, the **Comment** check box is automatically selected.</span></span>

<span data-ttu-id="34e3b-139">När du har gjort en registrering av villkorsutvärdering på en tillgång kan du skriva ut en villkorsutvärderingsrapport.</span><span class="sxs-lookup"><span data-stu-id="34e3b-139">After you have made a condition assessment registration on an asset, you can print a condition assessment report.</span></span>

>[!NOTE]
><span data-ttu-id="34e3b-140">Du kan också registrera villkorsutvärdering på en arbetsorder (knappen **tillgångshantering** > **allmänt** > **arbetsorder** > **alla arbetsorder** > **villkorsutvärdering**.)</span><span class="sxs-lookup"><span data-stu-id="34e3b-140">You can also register condition assessment on a work order (**Asset management** > **Common** > **Work orders** > **All Work orders** > **Condition assessment** button.)</span></span>
