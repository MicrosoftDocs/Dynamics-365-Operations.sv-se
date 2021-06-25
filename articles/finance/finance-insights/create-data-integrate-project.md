---
title: Skapa ett projekt för dataintegrerare (förhandsversion)
description: I det här ämnet beskrivs hur du skapar ett projekt för dataintegrerare.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 59f85c64ea7b1f539a245e08b76bd6a34797b0ca
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186478"
---
# <a name="create-a-data-integrator-project-preview"></a><span data-ttu-id="a3a99-103">Skapa ett projekt för dataintegrerare (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="a3a99-103">Create a data integrator project (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="a3a99-104">I det här ämnet beskrivs hur du skapar ett projekt för dataintegrerare.</span><span class="sxs-lookup"><span data-stu-id="a3a99-104">This topic explains how to create a data integrator project.</span></span>

1. <span data-ttu-id="a3a99-105">Logga in på Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="a3a99-105">Sign in to Microsoft Dynamics 365 Finance.</span></span>
2. <span data-ttu-id="a3a99-106">Gå till **Arbetsytor \> Datahantering** och välj **Dataentiteter**.</span><span class="sxs-lookup"><span data-stu-id="a3a99-106">Go to **Workspaces \> Data management**, and select **Data entities**.</span></span> <span data-ttu-id="a3a99-107">Vänta tills alla dataentiteter har uppdaterats innan du går vidare till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="a3a99-107">Wait until all the data entities have been refreshed before you move on to the next step.</span></span>
3. <span data-ttu-id="a3a99-108">Öppna [Power Apps-portalen](https://make.powerapps.com/) och gör följande:</span><span class="sxs-lookup"><span data-stu-id="a3a99-108">Open the [Power Apps portal](https://make.powerapps.com/), and follow these steps:</span></span>

    1. <span data-ttu-id="a3a99-109">Välj lämplig miljö.</span><span class="sxs-lookup"><span data-stu-id="a3a99-109">Select the appropriate environment.</span></span>
    2. <span data-ttu-id="a3a99-110">I det vänstra navigeringsfönstret väljer du **Data \> Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="a3a99-110">In the left navigation pane, select **Data \> Connections**.</span></span>
    3. <span data-ttu-id="a3a99-111">Anslut till lämpliga instanser av följande objekt:</span><span class="sxs-lookup"><span data-stu-id="a3a99-111">Connect to appropriate instances of the following items:</span></span>

        - <span data-ttu-id="a3a99-112">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a3a99-112">Dynamics 365</span></span>
        - <span data-ttu-id="a3a99-113">Dynamics 365 för Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="a3a99-113">Dynamics 365 for Fin & Ops</span></span>

4. <span data-ttu-id="a3a99-114">Öppna [Power Apps-miljöerna](https://admin.powerapps.com/environments) och gör följande:</span><span class="sxs-lookup"><span data-stu-id="a3a99-114">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>

    1. <span data-ttu-id="a3a99-115">Välj **Dataintegrerare**.</span><span class="sxs-lookup"><span data-stu-id="a3a99-115">Select **Data Integrator**.</span></span>
    2. <span data-ttu-id="a3a99-116">Välj **Anslutningsuppsättningar**.</span><span class="sxs-lookup"><span data-stu-id="a3a99-116">Select **Connection sets**.</span></span>
    3. <span data-ttu-id="a3a99-117">Välj **Ny anslutningsuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="a3a99-117">Select **New connection set**.</span></span>
    4. <span data-ttu-id="a3a99-118">Ange ett namn på anslutningen.</span><span class="sxs-lookup"><span data-stu-id="a3a99-118">Enter a name for the connection.</span></span>
    5. <span data-ttu-id="a3a99-119">Välj lämpliga anslutningar för följande objekt:</span><span class="sxs-lookup"><span data-stu-id="a3a99-119">Select the appropriate connections for the following items:</span></span>

        - <span data-ttu-id="a3a99-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="a3a99-120">Dynamics 365</span></span>
        - <span data-ttu-id="a3a99-121">Dynamics 365 för Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="a3a99-121">Dynamics 365 for Fin & Ops</span></span>

    6. <span data-ttu-id="a3a99-122">Välj lämplig organisationsmappning.</span><span class="sxs-lookup"><span data-stu-id="a3a99-122">Select the appropriate organization mapping.</span></span>
    7. <span data-ttu-id="a3a99-123">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="a3a99-123">Select **Create**.</span></span>

5. <span data-ttu-id="a3a99-124">Öppna [Power Apps-miljöerna](https://admin.powerapps.com/environments) och gör följande:</span><span class="sxs-lookup"><span data-stu-id="a3a99-124">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>  

    1. <span data-ttu-id="a3a99-125">Skapa dataintegreringsprojekt för följande mallar med hjälp av den anslutningsuppsättning du just skapat:</span><span class="sxs-lookup"><span data-stu-id="a3a99-125">Create data integration projects for the following templates by using the connection set that you just created:</span></span>

        - <span data-ttu-id="a3a99-126">Resultat av kundbetalningsinsikter (CDS till Fin och Ops)</span><span class="sxs-lookup"><span data-stu-id="a3a99-126">Customer payment insights results (CDS to Fin and Ops)</span></span>
            - <span data-ttu-id="a3a99-127">Om du använder version 10.0.17 eller senare måste du använda mallen med namnet "Insiktsresultat om kundbetalningar" (Customer payment insights result; CDS till Fin and Ops 10.0.17+).</span><span class="sxs-lookup"><span data-stu-id="a3a99-127">If you are using version 10.0.17 or later, you need to use the template named, Customer payment insights result (CDS to Fin and Ops 10.0.17+).</span></span>
        - <span data-ttu-id="a3a99-128">Resultat av kassaflödes tidsserier (CDS till Fin och Ops)</span><span class="sxs-lookup"><span data-stu-id="a3a99-128">Cash flow time series results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="a3a99-129">Resultat av budgettidsserier (CDS till Fin och Ops)</span><span class="sxs-lookup"><span data-stu-id="a3a99-129">Budget time series results (CDS to Fin and Ops)</span></span>

    2. <span data-ttu-id="a3a99-130">Ställ in lämplig tidsplanering för varje projekt.</span><span class="sxs-lookup"><span data-stu-id="a3a99-130">Set the appropriate scheduling for each project.</span></span>

> [!NOTE]
> <span data-ttu-id="a3a99-131">Om du inte ser de obligatoriska entiteterna i CDS går du till **Kredit och inkasso > Konfigurera > Finance-insikter > Parametrar för ekonomiinsikter**, aktiverar funktionen Prediktioner av kundbetalning och klickar på knappen **Skapa förutsägelsemodell**.</span><span class="sxs-lookup"><span data-stu-id="a3a99-131">If you do not see the required entities in CDS, please go to **Credit and collections > Setup > Finance Insights > Finance insights parameters**, enable Customer payment predictions feature and click on **Create prediction model** button.</span></span> <span data-ttu-id="a3a99-132">När AI-modellens distribution är slutförd (lyckad eller misslyckad), distribueras de CDS-entiteter som behövs för att skapa integrationen i CDS.</span><span class="sxs-lookup"><span data-stu-id="a3a99-132">When the deployment of AI model is completed (successful or failed), the CDS entities needed to create integration will be deployed in CDS.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
