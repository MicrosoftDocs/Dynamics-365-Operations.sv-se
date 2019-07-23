---
title: (ER) Importera konfigurationer från RCS
description: I det här avsnittet finns information om hur en användare kan importera en ny version av en återställningskonfiguration från RCS.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c458cf815837fb7e4688c4c0443b7962cac403a5
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/04/2019
ms.locfileid: "1727016"
---
# <a name="er-import-configurations-from-rcs"></a><span data-ttu-id="0d701-103">(ER) Importera konfigurationer från RCS</span><span class="sxs-lookup"><span data-stu-id="0d701-103">(ER) Import configurations from RCS</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0d701-104">I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan importera en ny version av en konfiguration för elektronisk rapportering (ER) från Microsoft Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="0d701-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Regulatory Configuration Services (RCS).</span></span> <span data-ttu-id="0d701-105">I det här exemplet ska du välja den version av ER-konfiguration som har konfigurerats i en RCS-instans och importera den till den aktuella Finance and Operations-instansen för exempelföretaget Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigurationer delas mellan företag.</span><span class="sxs-lookup"><span data-stu-id="0d701-105">In this example, you will select the version of the ER configuration that has been configured in an RCS instance and import it into the current Finance and Operations instance for sample company, Litware, Inc. These steps can be performed in any company because ER configurations are shared among companies.</span></span> <span data-ttu-id="0d701-106">För att slutföra dessa steg måste du först slutföra stegen i ämnet [Skapa en konfigurationsleverantör och välj den som aktiv](er-configuration-provider-mark-it-active-2016-11.md)</span><span class="sxs-lookup"><span data-stu-id="0d701-106">To complete these steps, you must first complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="0d701-107">För att kunna utföra de här stegen måste du också ha till gång till en RCS-instans som innehåller minst en ER-konfiguration med antingen status **slutförd** eller **delad**.</span><span class="sxs-lookup"><span data-stu-id="0d701-107">To complete these steps, you must also have access to an RCS instance containing at least one ER configuration in either **Completed** or **Shared** status.</span></span>

1. <span data-ttu-id="0d701-108">Gå till **Organisationsadministration** > **Arbetsytor** > **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="0d701-108">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="0d701-109">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0d701-109">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="0d701-110">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i avsnittet [Skapa en konfigurationsleverantör och välj den som aktiv](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="0d701-110">If you don’t see this configuration provider, complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3. <span data-ttu-id="0d701-111">Om du inte har någon RCS-miljö etablerad till ditt företag klickar du på den externa länken **Regulatory services - konfiguration** och följer instruktionerna för att etablera en RCS-miljö.</span><span class="sxs-lookup"><span data-stu-id="0d701-111">If you have no RCS environment provisioned to your company, click **Regulatory services – Configuration** external link and follow the instructions to provision an RCS environment.</span></span> 
4. <span data-ttu-id="0d701-112">Klicka på **parametrar för elektronisk rapportering**</span><span class="sxs-lookup"><span data-stu-id="0d701-112">Click **Electronic reporting parameters**.</span></span> 
5. <span data-ttu-id="0d701-113">Klicka på fliken **RCS**.</span><span class="sxs-lookup"><span data-stu-id="0d701-113">Click the **RCS** tab.</span></span> 
6. <span data-ttu-id="0d701-114">Om RCS-miljön redan har etablerats till ditt företag, använder du sidans URL:er för att komma åt den.</span><span class="sxs-lookup"><span data-stu-id="0d701-114">If RCS environment has been already provisioned to your company, use presented on the page URLs to access it.</span></span> 
7. <span data-ttu-id="0d701-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0d701-115">Close the page.</span></span> 

## <a name="register-a-new-er-repository"></a><span data-ttu-id="0d701-116">Registrera en ny ER-databas.</span><span class="sxs-lookup"><span data-stu-id="0d701-116">Register a new ER repository.</span></span> 
1. <span data-ttu-id="0d701-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="0d701-117">In the list, mark the selected row.</span></span> 
2. <span data-ttu-id="0d701-118">Välj leverantören Litware, inc.</span><span class="sxs-lookup"><span data-stu-id="0d701-118">Select Litware, Inc. provider.</span></span> 
3. <span data-ttu-id="0d701-119">Klicka på Databaser.</span><span class="sxs-lookup"><span data-stu-id="0d701-119">Click Repositories.</span></span> 
4. <span data-ttu-id="0d701-120">Klicka på Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="0d701-120">Click Add to open the drop dialog.</span></span> 
5. <span data-ttu-id="0d701-121">Skriv "RCS" i fältet Typ av konfigurationsdatabas.</span><span class="sxs-lookup"><span data-stu-id="0d701-121">In the Configuration repository type field, enter 'RCS'.</span></span> 
6. <span data-ttu-id="0d701-122">Klicka på Skapa en databas.</span><span class="sxs-lookup"><span data-stu-id="0d701-122">Click Create repository.</span></span> 
7. <span data-ttu-id="0d701-123">Ange eller välj ett värde i namnfältet RCS-miljö.</span><span class="sxs-lookup"><span data-stu-id="0d701-123">In the RCS environment display name field, enter or select a value.</span></span> 
8. <span data-ttu-id="0d701-124">Välj önskat RCS-instans.</span><span class="sxs-lookup"><span data-stu-id="0d701-124">Select the desired RCS instance.</span></span> <span data-ttu-id="0d701-125">Observera att du kan använda flera av dem.</span><span class="sxs-lookup"><span data-stu-id="0d701-125">Note that you can have several of them.</span></span> 
9. <span data-ttu-id="0d701-126">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="0d701-126">Click OK.</span></span> 

## <a name="import-er-configurations-from-rcs-based-repository"></a><span data-ttu-id="0d701-127">Importera ER-konfigurationer från RCS-baserad databas</span><span class="sxs-lookup"><span data-stu-id="0d701-127">Import ER configurations from RCS based repository</span></span>
1. <span data-ttu-id="0d701-128">Klicka på **Visa filter**</span><span class="sxs-lookup"><span data-stu-id="0d701-128">Click **Show filters**.</span></span> 
2. <span data-ttu-id="0d701-129">Ange filtervärdet "RCS" i fältet **Namn** med filteroperatorn **börjar med**.</span><span class="sxs-lookup"><span data-stu-id="0d701-129">Enter a filter value of "RCS" on the **Name** field using the **begins with** filter operator.</span></span> 
3. <span data-ttu-id="0d701-130">När du öppnar den markerade databasen, på sidan **Anslut till Regulatory Configuration Services**, klicka på länken **Klicka här för att ansluta till Regulatory Configuration Services**.</span><span class="sxs-lookup"><span data-stu-id="0d701-130">When you open the selected repository, on the **Connect to Regulatory Configuration Services** page, click **Click here to connect to Regulatory Configuration Services** link.</span></span> 
4. <span data-ttu-id="0d701-131">Klicka på **Öppna.**</span><span class="sxs-lookup"><span data-stu-id="0d701-131">Click **Open**.</span></span> 
5. <span data-ttu-id="0d701-132">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="0d701-132">Click **Close**.</span></span> 
6. <span data-ttu-id="0d701-133">Markera önskad version av ER-konfigurationen och klicka på **importera** för att ta med den aktuella Finance and Operations-instansen.</span><span class="sxs-lookup"><span data-stu-id="0d701-133">Select the desired version of ER configuration and click **Import** to bring it in the current Finance and Operations instance.</span></span>

