---
title: Skapa ett projekt för dataintegrerare (förhandsversion)
description: I det här ämnet beskrivs hur du skapar ett projekt för dataintegrerare.
author: ShivamPandey-msft
ms.date: 07/24/2020
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
ms.openlocfilehash: 2335721cfe8fd7ff3f76e3c7ca2560a56d45d583
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818690"
---
# <a name="create-a-data-integrator-project-preview"></a><span data-ttu-id="bde8a-103">Skapa ett projekt för dataintegrerare (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="bde8a-103">Create a data integrator project (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="bde8a-104">I det här ämnet beskrivs hur du skapar ett projekt för dataintegrerare.</span><span class="sxs-lookup"><span data-stu-id="bde8a-104">This topic explains how to create a data integrator project.</span></span>

1. <span data-ttu-id="bde8a-105">Logga in på Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="bde8a-105">Sign in to Microsoft Dynamics 365 Finance.</span></span>
2. <span data-ttu-id="bde8a-106">Gå till **Arbetsytor \> Datahantering** och välj **Dataentiteter**.</span><span class="sxs-lookup"><span data-stu-id="bde8a-106">Go to **Workspaces \> Data management**, and select **Data entities**.</span></span> <span data-ttu-id="bde8a-107">Vänta tills alla dataentiteter har uppdaterats innan du går vidare till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="bde8a-107">Wait until all the data entities have been refreshed before you move on to the next step.</span></span>
3. <span data-ttu-id="bde8a-108">Öppna [Power Apps-portalen](https://make.powerapps.com/) och gör följande:</span><span class="sxs-lookup"><span data-stu-id="bde8a-108">Open the [Power Apps portal](https://make.powerapps.com/), and follow these steps:</span></span>

    1. <span data-ttu-id="bde8a-109">Välj lämplig miljö.</span><span class="sxs-lookup"><span data-stu-id="bde8a-109">Select the appropriate environment.</span></span>
    2. <span data-ttu-id="bde8a-110">I det vänstra navigeringsfönstret väljer du **Data \> Anslutningar**.</span><span class="sxs-lookup"><span data-stu-id="bde8a-110">In the left navigation pane, select **Data \> Connections**.</span></span>
    3. <span data-ttu-id="bde8a-111">Anslut till lämpliga instanser av följande objekt:</span><span class="sxs-lookup"><span data-stu-id="bde8a-111">Connect to appropriate instances of the following items:</span></span>

        - <span data-ttu-id="bde8a-112">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="bde8a-112">Dynamics 365</span></span>
        - <span data-ttu-id="bde8a-113">Dynamics 365 för Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="bde8a-113">Dynamics 365 for Fin & Ops</span></span>

4. <span data-ttu-id="bde8a-114">Öppna [Power Apps-miljöerna](https://admin.powerapps.com/environments) och gör följande:</span><span class="sxs-lookup"><span data-stu-id="bde8a-114">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>

    1. <span data-ttu-id="bde8a-115">Välj **Dataintegrerare**.</span><span class="sxs-lookup"><span data-stu-id="bde8a-115">Select **Data Integrator**.</span></span>
    2. <span data-ttu-id="bde8a-116">Välj **Anslutningsuppsättningar**.</span><span class="sxs-lookup"><span data-stu-id="bde8a-116">Select **Connection sets**.</span></span>
    3. <span data-ttu-id="bde8a-117">Välj **Ny anslutningsuppsättning**.</span><span class="sxs-lookup"><span data-stu-id="bde8a-117">Select **New connection set**.</span></span>
    4. <span data-ttu-id="bde8a-118">Ange ett namn på anslutningen.</span><span class="sxs-lookup"><span data-stu-id="bde8a-118">Enter a name for the connection.</span></span>
    5. <span data-ttu-id="bde8a-119">Välj lämpliga anslutningar för följande objekt:</span><span class="sxs-lookup"><span data-stu-id="bde8a-119">Select the appropriate connections for the following items:</span></span>

        - <span data-ttu-id="bde8a-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="bde8a-120">Dynamics 365</span></span>
        - <span data-ttu-id="bde8a-121">Dynamics 365 för Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="bde8a-121">Dynamics 365 for Fin & Ops</span></span>

    6. <span data-ttu-id="bde8a-122">Välj lämplig organisationsmappning.</span><span class="sxs-lookup"><span data-stu-id="bde8a-122">Select the appropriate organization mapping.</span></span>
    7. <span data-ttu-id="bde8a-123">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="bde8a-123">Select **Create**.</span></span>

5. <span data-ttu-id="bde8a-124">Öppna [Power Apps-miljöerna](https://admin.powerapps.com/environments) och gör följande:</span><span class="sxs-lookup"><span data-stu-id="bde8a-124">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>  

    1. <span data-ttu-id="bde8a-125">Skapa dataintegreringsprojekt för följande mallar med hjälp av den anslutningsuppsättning du just skapat:</span><span class="sxs-lookup"><span data-stu-id="bde8a-125">Create data integration projects for the following templates by using the connection set that you just created:</span></span>

        - <span data-ttu-id="bde8a-126">Resultat av kundbetalningsinsikter (CDS till Fin och Ops)</span><span class="sxs-lookup"><span data-stu-id="bde8a-126">Customer payment insights results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="bde8a-127">Resultat av kassaflödes tidsserier (CDS till Fin och Ops)</span><span class="sxs-lookup"><span data-stu-id="bde8a-127">Cash flow time series results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="bde8a-128">Resultat av budgettidsserier (CDS till Fin och Ops)</span><span class="sxs-lookup"><span data-stu-id="bde8a-128">Budget time series results (CDS to Fin and Ops)</span></span>

    2. <span data-ttu-id="bde8a-129">Ställ in lämplig tidsplanering för varje projekt.</span><span class="sxs-lookup"><span data-stu-id="bde8a-129">Set the appropriate scheduling for each project.</span></span>

> [!NOTE]
> <span data-ttu-id="bde8a-130">Om du inte ser de obligatoriska entiteterna i CDS går du till **Kredit och inkasso > Konfigurera > Finance-insikter > Parametrar för ekonomiinsikter**, aktiverar funktionen Prediktioner av kundbetalning och klickar på knappen **Skapa förutsägelsemodell**.</span><span class="sxs-lookup"><span data-stu-id="bde8a-130">If you do not see the required entities in CDS, please go to **Credit and collections > Setup > Finance Insights > Finance insights parameters**, enable Customer payment predictions feature and click on **Create prediction model** button.</span></span> <span data-ttu-id="bde8a-131">När AI-modellens distribution är slutförd (lyckad eller misslyckad), distribueras de CDS-entiteter som behövs för att skapa integrationen i CDS.</span><span class="sxs-lookup"><span data-stu-id="bde8a-131">When the deployment of AI model is completed (successful or failed), the CDS entities needed to create integration will be deployed in CDS.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="bde8a-132">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="bde8a-132">Privacy notice</span></span>

<span data-ttu-id="bde8a-133">Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="bde8a-133">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]