---
title: (ER) Importera konfigurationer från RCS
description: I det här avsnittet finns information om hur en användare kan importera en ny version av en återställningskonfiguration från RCS.
author: NickSelin
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 77d637b2ec1deeabc04a6796644363b330f5756e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744901"
---
# <a name="er-import-configurations-from-rcs"></a><span data-ttu-id="0174f-103">(ER) Importera konfigurationer från RCS</span><span class="sxs-lookup"><span data-stu-id="0174f-103">(ER) Import configurations from RCS</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0174f-104">I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan importera en ny version av en konfiguration för elektronisk rapportering (ER) från Microsoft Regulatory Configuration Services (RCS).</span><span class="sxs-lookup"><span data-stu-id="0174f-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Regulatory Configuration Services (RCS).</span></span> <span data-ttu-id="0174f-105">I det här exemplet ska du välja den version av ER-konfiguration som har konfigurerats i en RCS-instans och importera den till den aktuella instansen för exempelföretaget Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigurationer delas mellan företag.</span><span class="sxs-lookup"><span data-stu-id="0174f-105">In this example, you will select the version of the ER configuration that has been configured in an RCS instance and import it into the current instance for sample company, Litware, Inc. These steps can be performed in any company because ER configurations are shared among companies.</span></span> <span data-ttu-id="0174f-106">För att slutföra dessa steg måste du först slutföra stegen i ämnet [Skapa en konfigurationsleverantörer och välj de som aktiva](er-configuration-provider-mark-it-active-2016-11.md)</span><span class="sxs-lookup"><span data-stu-id="0174f-106">To complete these steps, you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="0174f-107">För att kunna utföra de här stegen måste du också ha till gång till en RCS-instans som innehåller minst en ER-konfiguration med antingen status **slutförd** eller **delad**.</span><span class="sxs-lookup"><span data-stu-id="0174f-107">To complete these steps, you must also have access to an RCS instance containing at least one ER configuration in either **Completed** or **Shared** status.</span></span>

1. <span data-ttu-id="0174f-108">Gå till **Organisationsadministration** > **Arbetsytor** > **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="0174f-108">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="0174f-109">Kontrollera att konfigurationsleverantören för exempelföretaget "Litware, Inc." är markerad som **aktiv** och är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="0174f-109">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="0174f-110">Om du inte ser den här konfigurationsleverantören ska du först slutföra stegen i ämnet [Skapa konfigurationsleverantörer och välj dem som aktiva](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="0174f-110">If you don't see this configuration provider, complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3. <span data-ttu-id="0174f-111">Om du inte har någon RCS-miljö etablerad till ditt företag kan du välja den externa länken **Regulatory services - konfiguration** och följa instruktionerna för att etablera en RCS-miljö.</span><span class="sxs-lookup"><span data-stu-id="0174f-111">If you have no RCS environment provisioned to your company, select **Regulatory services – Configuration** external link and follow the instructions to provision an RCS environment.</span></span> 
4. <span data-ttu-id="0174f-112">Välj **Parametrar för elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="0174f-112">Select **Electronic reporting parameters**.</span></span> 
5. <span data-ttu-id="0174f-113">Välj fliken **RCS**.</span><span class="sxs-lookup"><span data-stu-id="0174f-113">Select the **RCS** tab.</span></span> 
6. <span data-ttu-id="0174f-114">Om RCS-miljön redan har etablerats till ditt företag, använder du sidans URL:er för att komma åt den.</span><span class="sxs-lookup"><span data-stu-id="0174f-114">If RCS environment has been already provisioned to your company, use presented on the page URLs to access it.</span></span> 
7. <span data-ttu-id="0174f-115">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="0174f-115">Close the page.</span></span> 

## <a name="register-a-new-er-repository"></a><span data-ttu-id="0174f-116">Registrera en ny ER-databas.</span><span class="sxs-lookup"><span data-stu-id="0174f-116">Register a new ER repository.</span></span> 
1. <span data-ttu-id="0174f-117">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="0174f-117">In the list, mark the selected row.</span></span> 
2. <span data-ttu-id="0174f-118">Välj leverantören Litware, inc.</span><span class="sxs-lookup"><span data-stu-id="0174f-118">Select Litware, Inc. provider.</span></span> 
3. <span data-ttu-id="0174f-119">Välj Databaser.</span><span class="sxs-lookup"><span data-stu-id="0174f-119">Select Repositories.</span></span> 
4. <span data-ttu-id="0174f-120">Välj Lägg till för att öppna dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="0174f-120">Select Add to open the drop dialog.</span></span> 
5. <span data-ttu-id="0174f-121">Skriv "RCS" i fältet Typ av konfigurationsdatabas.</span><span class="sxs-lookup"><span data-stu-id="0174f-121">In the Configuration repository type field, enter 'RCS'.</span></span> 
6. <span data-ttu-id="0174f-122">Välj Skapa databas.</span><span class="sxs-lookup"><span data-stu-id="0174f-122">Select Create repository.</span></span> 
7. <span data-ttu-id="0174f-123">Ange eller välj ett värde i namnfältet RCS-miljö.</span><span class="sxs-lookup"><span data-stu-id="0174f-123">In the RCS environment display name field, enter or select a value.</span></span> 
8. <span data-ttu-id="0174f-124">Välj önskat RCS-instans.</span><span class="sxs-lookup"><span data-stu-id="0174f-124">Select the desired RCS instance.</span></span> <span data-ttu-id="0174f-125">Du kan använda flera av dem.</span><span class="sxs-lookup"><span data-stu-id="0174f-125">You can have several of them.</span></span> 
9. <span data-ttu-id="0174f-126">Välj OK.</span><span class="sxs-lookup"><span data-stu-id="0174f-126">Select OK.</span></span> 

## <a name="import-er-configurations-from-rcs-based-repository"></a><span data-ttu-id="0174f-127">Importera ER-konfigurationer från RCS-baserad databas</span><span class="sxs-lookup"><span data-stu-id="0174f-127">Import ER configurations from RCS-based repository</span></span>
1. <span data-ttu-id="0174f-128">Välj **Visa filter**.</span><span class="sxs-lookup"><span data-stu-id="0174f-128">Select **Show filters**.</span></span> 
2. <span data-ttu-id="0174f-129">Ange filtervärdet "RCS" i fältet **Namn** med filteroperatorn **börjar med**.</span><span class="sxs-lookup"><span data-stu-id="0174f-129">Enter a filter value of "RCS" on the **Name** field using the **begins with** filter operator.</span></span> 
3. <span data-ttu-id="0174f-130">När du öppnar den markerade databasen, på sidan **Anslut till Regulatory Configuration Services**, väljer du länken **Markera här för att ansluta till Regulatory Configuration Services**.</span><span class="sxs-lookup"><span data-stu-id="0174f-130">When you open the selected repository, on the **Connect to Regulatory Configuration Services** page, select **Select here to connect to Regulatory Configuration Services** link.</span></span> 
4. <span data-ttu-id="0174f-131">Välj **Öppen**.</span><span class="sxs-lookup"><span data-stu-id="0174f-131">Select **Open**.</span></span> 
5. <span data-ttu-id="0174f-132">Välj **Nära**.</span><span class="sxs-lookup"><span data-stu-id="0174f-132">Select **Close**.</span></span> 
6. <span data-ttu-id="0174f-133">Markera önskad version av ER-konfigurationen och välj **importera** för att ta med den aktuella instansen.</span><span class="sxs-lookup"><span data-stu-id="0174f-133">Select the desired version of ER configuration and select **Import** to bring it in the current instance.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]