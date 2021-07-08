---
title: Regulatory Configuration Service (RCS) - Ta bort en RCS-miljö
description: I det här avsnittet beskrivs hur Regulatory Configuration Service (RCS) systemadministratör kan ta bort en RCS-miljö och relaterad data.
author: JaneA07
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
audience: Application User, System Admin
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 637962cf63bfd8c2330726f33545f939ec91d58d
ms.sourcegitcommit: dbffde1944b9d037124415c28053036c9ef1ecb7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "6295828"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a><span data-ttu-id="12760-103">Regulatory Configuration Service (RCS) - Ta bort en RCS-miljö</span><span class="sxs-lookup"><span data-stu-id="12760-103">Regulatory Configuration Service (RCS) - Delete an RCS environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="12760-104">I det här avsnittet beskrivs hur Regulatory Configuration Service (RCS) systemadministratör kan ta bort en RCS-miljö och relaterad data.</span><span class="sxs-lookup"><span data-stu-id="12760-104">This topic explains how a Regulatory Configuration Service (RCS) system administrator can delete an RCS environment and related data.</span></span>

<span data-ttu-id="12760-105">Innan du kan slutföra procedurerna i detta ämne måste följande förutsättningar finnas på plats:</span><span class="sxs-lookup"><span data-stu-id="12760-105">Before you can complete the procedure in this topic, the following prerequisites must be met:</span></span>

- <span data-ttu-id="12760-106">Du måste ha tilldelats rollen **Systemadministratör** för RCS-miljön.</span><span class="sxs-lookup"><span data-stu-id="12760-106">You must have the **System Admin** role assigned to you for the RCS environment.</span></span>
- <span data-ttu-id="12760-107">Rollen **Systemadministratör** måste ha rollen **RCSDeleteEnvironmentDuty** tilldelad den.</span><span class="sxs-lookup"><span data-stu-id="12760-107">The **System Admin** role must have the **RCSDeleteEnvironmentDuty** role assigned to it.</span></span>

## <a name="delete-an-rcs-environment"></a><span data-ttu-id="12760-108">Ta bort en RCS-miljö</span><span class="sxs-lookup"><span data-stu-id="12760-108">Delete an RCS environment</span></span>

1. <span data-ttu-id="12760-109">Öppna RCS och välj arbetsytapanel **Elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="12760-109">Open RCS, and select the **Electronic reporting** workspace tile.</span></span>
2. <span data-ttu-id="12760-110">I avsnittet **Relaterade länkar**, välj **Ta bort RCS-miljö**.</span><span class="sxs-lookup"><span data-stu-id="12760-110">In the **Related links** section, select **Delete RCS environment**.</span></span>

    ![Ta bort RCS-miljölänk i avsnittet Relaterade länkar](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. <span data-ttu-id="12760-112">Granska meddelandena om omfattningen av borttagningen av miljön i dialogrutan som visas.</span><span class="sxs-lookup"><span data-stu-id="12760-112">In the dialog box that appears, review the messages about the scope of environment deletion.</span></span>

    ![Meddelanden i dialogrutan Ta bort RCS-miljö](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > <span data-ttu-id="12760-114">Radering av en RCS-miljö kan inte återföras.</span><span class="sxs-lookup"><span data-stu-id="12760-114">Deletion of an RCS environment can't be reversed.</span></span>
    >
    > <span data-ttu-id="12760-115">Operationen tar bort den valda RCS-miljön och alla relaterade data, inklusive funktioner och konfigurationer som är lagrade i den globala databasen.</span><span class="sxs-lookup"><span data-stu-id="12760-115">The operation deletes the selected RCS environment and any related data, including features and configurations that are stored in the Global repository.</span></span> <span data-ttu-id="12760-116">Funktioner och konfigurationer som delas med andra organisationer tas bort och tas bort om de inte har några beroenden.</span><span class="sxs-lookup"><span data-stu-id="12760-116">Features and configurations that are shared with other organizations will be unshared and deleted if they have no dependencies.</span></span> <span data-ttu-id="12760-117">Funktioner och konfigurationer som har beroenden markeras som utgått.</span><span class="sxs-lookup"><span data-stu-id="12760-117">Features and configurations that have dependencies will be marked as discontinued.</span></span>

4. <span data-ttu-id="12760-118">I fältet som finns anger du den globala unika identifieraren (GUID) för RCS-miljön för att bekräfta att du vill ta bort den.</span><span class="sxs-lookup"><span data-stu-id="12760-118">In the field that is provided, enter the globally unique identifier (GUID) of the RCS environment to confirm that you want to delete it.</span></span> <span data-ttu-id="12760-119">Miljöns GUID inkluderas i borttagningsmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="12760-119">The environment's GUID is included in the deletion message.</span></span>
5. <span data-ttu-id="12760-120">Välj **Ta bort miljö**.</span><span class="sxs-lookup"><span data-stu-id="12760-120">Select **Delete environment**.</span></span>
    
<span data-ttu-id="12760-121">Din RCS-miljö och alla relaterade data raderas nu.</span><span class="sxs-lookup"><span data-stu-id="12760-121">Your RCS environment and any related data are now deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="12760-122">När du har raderat en RCS-miljö går det inte att återställa data.</span><span class="sxs-lookup"><span data-stu-id="12760-122">After you delete an RCS environment, there is no way to recover the data.</span></span> <span data-ttu-id="12760-123">En ny RCS-miljö kan skapas i alla tillgängliga RCS-regioner.</span><span class="sxs-lookup"><span data-stu-id="12760-123">A new RCS environment can be created in any available RCS region.</span></span>
