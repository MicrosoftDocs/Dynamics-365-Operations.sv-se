---
title: Installera, ställ in och uppdatera kundportalen
description: Det här avsnittet innehåller licensieringsinformation och installationsinstruktioner för kundportalen.
author: dasani-madipalli
manager: tfehr
ms.date: 04/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: b9d1e742f78254d949dc49fda008d63b8bff4d65
ms.sourcegitcommit: 713b5dfc76a6875d0ba6d86c5cbd585ea502cf9d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/01/2020
ms.locfileid: "3414010"
---
# <a name="install-set-up-and-update-the-customer-portal"></a><span data-ttu-id="70a64-103">Installera, ställ in och uppdatera kundportalen</span><span class="sxs-lookup"><span data-stu-id="70a64-103">Install, set up, and update the Customer portal</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="70a64-104">Licensieringskrav</span><span class="sxs-lookup"><span data-stu-id="70a64-104">Licensing requirements</span></span>

<span data-ttu-id="70a64-105">Om du vill implementera kundportalen måste du ha följande licenser:</span><span class="sxs-lookup"><span data-stu-id="70a64-105">To implement the Customer portal, you must have the following licenses:</span></span>

- <span data-ttu-id="70a64-106">**Power Apps-portaler** – den här licensen krävs för att vara värd för kundportalen.</span><span class="sxs-lookup"><span data-stu-id="70a64-106">**Power Apps portals** – This license is required to host the Customer portal.</span></span> <span data-ttu-id="70a64-107">Portaler är licensierade utifrån användning.</span><span class="sxs-lookup"><span data-stu-id="70a64-107">Portals are licensed based on usage.</span></span> <span data-ttu-id="70a64-108">Mer information finns i avsnittet om [Power Apps licenskrav för portaler](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).</span><span class="sxs-lookup"><span data-stu-id="70a64-108">For more information, see the [Power Apps portals licensing requirements](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#portals).</span></span>
- <span data-ttu-id="70a64-109">**Dubbelriktad skrivning** – du måste ha de licenser som krävs för att möjliggöra dubbelriktad skrivning för enheter för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="70a64-109">**Dual-write** – You must have the necessary licenses to enable dual-write for Supply Chain Management entities.</span></span> <span data-ttu-id="70a64-110">För mer information, se [systemkrav för dubbelriktad skrivning](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span><span class="sxs-lookup"><span data-stu-id="70a64-110">For more information, see the [system requirements for dual-write](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span></span>

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a><span data-ttu-id="70a64-111">Beroenden på dubbelriktad skrivning och Power Apps-portaler</span><span class="sxs-lookup"><span data-stu-id="70a64-111">Dependencies on dual-write and Power Apps portals</span></span>

<span data-ttu-id="70a64-112">Kundportalen beror på Power Apps-portaler och dubbelskrivning, vilket visas i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="70a64-112">The Customer portal depends on Power Apps portals and dual-write, as shown in the following illustration.</span></span>

![![Kundportalberoenden](media/customer-portal-elements.png "Kundportalberoenden")](media/customer-portal-elements.png "Customer portal dependencies")

<span data-ttu-id="70a64-114">Till skillnad från andra funktioner från Supply Chain Management, kundportalmallen finns i Power Apps-portaler.</span><span class="sxs-lookup"><span data-stu-id="70a64-114">Unlike other features from Supply Chain Management, the Customer portal template resides in Power Apps portals.</span></span> <span data-ttu-id="70a64-115">Därför begränsas kundportalen av de funktioner som tillhandahålls av Power Apps-portaler och enheterna i dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="70a64-115">Therefore, the Customer portal is limited by the functionality and capabilities that are provided by Power Apps portals and the entities in dual-write.</span></span>

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a><span data-ttu-id="70a64-116">Obligatorisk inställning för att aktivera kundportalen</span><span class="sxs-lookup"><span data-stu-id="70a64-116">Required setup to enable the Customer portal</span></span>

<span data-ttu-id="70a64-117">När du har installerat de nödvändiga licenserna kan du ställa in dubbelriktad skrivning enligt beskrivningen i [inledande synkroniseringsinställningarna för dubbelriktad skrivning](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).</span><span class="sxs-lookup"><span data-stu-id="70a64-117">After you've made sure that you have the required licenses, you can set up dual-write as described in the [dual-write initial synchronization instructions](../../fin-ops-core/dev-itpro/data-entities/dual-write/initial-sync.md).</span></span>

<span data-ttu-id="70a64-118">Se till att aktivera följande enhetsmappningar i dubbelriktad skrivning:</span><span class="sxs-lookup"><span data-stu-id="70a64-118">Be sure to enable the following entity mappings in dual-write:</span></span>

- <span data-ttu-id="70a64-119">Försäljningsorderhuvud</span><span class="sxs-lookup"><span data-stu-id="70a64-119">Sales Order Header</span></span>
- <span data-ttu-id="70a64-120">Försäljningsorderinformation</span><span class="sxs-lookup"><span data-stu-id="70a64-120">Sales Order Details</span></span>
- <span data-ttu-id="70a64-121">Konton</span><span class="sxs-lookup"><span data-stu-id="70a64-121">Accounts</span></span>
- <span data-ttu-id="70a64-122">Kontakter</span><span class="sxs-lookup"><span data-stu-id="70a64-122">Contacts</span></span>
- <span data-ttu-id="70a64-123">Produkter</span><span class="sxs-lookup"><span data-stu-id="70a64-123">Products</span></span>

<span data-ttu-id="70a64-124">När den här inställningen har slutförts kan du etablera kundportalmallen.</span><span class="sxs-lookup"><span data-stu-id="70a64-124">After this setup is completed, you can provision the Customer portal template.</span></span>

## <a name="provision-the-customer-portal"></a><span data-ttu-id="70a64-125">Etablera kundportalen</span><span class="sxs-lookup"><span data-stu-id="70a64-125">Provision the Customer portal</span></span>

<span data-ttu-id="70a64-126">Innan du börjar ska du kontrollera att du redan har slutfört de [nödvändiga inställningarna](#required-setup).</span><span class="sxs-lookup"><span data-stu-id="70a64-126">Before you begin, make sure that you've already completed the [required setup](#required-setup).</span></span> <span data-ttu-id="70a64-127">Följ sedan dessa steg för att etablera kundportalen.</span><span class="sxs-lookup"><span data-stu-id="70a64-127">Then follow these steps to provision the Customer portal.</span></span>

1. <span data-ttu-id="70a64-128">Gå till [make.powerapps.com](https://make.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="70a64-128">Go to [make.powerapps.com](https://make.powerapps.com/).</span></span>
2. <span data-ttu-id="70a64-129">Kontrollera att du använder den miljö där du har aktiverat dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="70a64-129">Make sure that you're using the environment where you enabled dual-write.</span></span>
3. <span data-ttu-id="70a64-130">På fliken **Skapa** bläddra ned till avsnittet **Starta från mall** och välj den mall som har fått kunden för hantering av **Supply Chain Management-kund**.</span><span class="sxs-lookup"><span data-stu-id="70a64-130">On the **Create** tab, scroll down to the **Start from template** section, and select the template that is named **Supply Chain Management Customer**.</span></span>
4. <span data-ttu-id="70a64-131">Följ instruktionerna på skärmen.</span><span class="sxs-lookup"><span data-stu-id="70a64-131">Follow the on-screen instructions.</span></span>

<span data-ttu-id="70a64-132">När etableringen har slutförts kan du få tillgång till kundportalen i avsnittet **Dina appar** på sidan **Start**-sidan.</span><span class="sxs-lookup"><span data-stu-id="70a64-132">After provisioning is completed, you can access the Customer portal in the **Your apps** section of the **Home** page.</span></span>

> [!NOTE]
> <span data-ttu-id="70a64-133">Om den dubbelriktad lösningen inte är installerad i den miljö som du arbetar i får du ett felmeddelande och kundportalen etableras inte.</span><span class="sxs-lookup"><span data-stu-id="70a64-133">If the dual-write solution isn't installed in the environment that you're working in, you will receive an error message, and the Customer portal won't be provisioned.</span></span>

## <a name="update-the-customer-portal"></a><span data-ttu-id="70a64-134">Uppdatera kundportalen</span><span class="sxs-lookup"><span data-stu-id="70a64-134">Update the Customer portal</span></span>

<span data-ttu-id="70a64-135">Fler funktioner kan läggas till kundportalen senare.</span><span class="sxs-lookup"><span data-stu-id="70a64-135">More functionality might be added to the Customer portal later.</span></span> <span data-ttu-id="70a64-136">Alla ändringar som Microsoft gör i de underliggande lösningskomponenterna visas automatiskt i din miljö.</span><span class="sxs-lookup"><span data-stu-id="70a64-136">Any changes that Microsoft makes to the underlying solution components will automatically appear in your environment.</span></span> <span data-ttu-id="70a64-137">Den webbplats som är etablerad i miljön återspeglar dock inte automatiskt ändringar som görs i konfigurationsdata.</span><span class="sxs-lookup"><span data-stu-id="70a64-137">However, the website that is provisioned in your environment won't automatically reflect changes that are made to the configuration data.</span></span> <span data-ttu-id="70a64-138">Du måste manuellt tillämpa ändringarna genom att hämta koden från den nya mallen och koppla den till den etablerade webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="70a64-138">You will have to manually apply those changes by getting the code from the new template and merging it with the provisioned website.</span></span>

## <a name="resources"></a><span data-ttu-id="70a64-139">Resurser</span><span class="sxs-lookup"><span data-stu-id="70a64-139">Resources</span></span>

<span data-ttu-id="70a64-140">Om du vill veta hur du kan ställa in och anpassa kundportalen bör du börja med att granska följande dokumentation för den underliggande tekniken:</span><span class="sxs-lookup"><span data-stu-id="70a64-140">To learn how you can set up and customize the Customer portal, you should start by reviewing the following documentation for the underlying technologies:</span></span>

- [<span data-ttu-id="70a64-141">Power Apps-portaldokumentation</span><span class="sxs-lookup"><span data-stu-id="70a64-141">Power Apps portals documentation</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)
- [<span data-ttu-id="70a64-142">Dokumentation för dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="70a64-142">Dual-write documentation</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

<span data-ttu-id="70a64-143">Om du vill hantera portalerna effektivt måste du känna till Power Apps-portalerna och Common Data Service livscykeln.</span><span class="sxs-lookup"><span data-stu-id="70a64-143">To effectively manage your portals, you must understand the Power Apps portals and Common Data Service lifecycle.</span></span> <span data-ttu-id="70a64-144">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="70a64-144">For more information, see the following resources:</span></span>

- [<span data-ttu-id="70a64-145">Om portalens livscykel</span><span class="sxs-lookup"><span data-stu-id="70a64-145">About portal lifecycle</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/portal-lifecycle)
- [<span data-ttu-id="70a64-146">Uppgradera en portal</span><span class="sxs-lookup"><span data-stu-id="70a64-146">Upgrade a portal</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/upgrade-portal)
- [<span data-ttu-id="70a64-147">Migrera portalkonfiguration</span><span class="sxs-lookup"><span data-stu-id="70a64-147">Migrate portal configuration</span></span>](https://docs.microsoft.com/powerapps/maker/portals/admin/migrate-portal-configuration)
- [<span data-ttu-id="70a64-148">Hantering av lösningens livscykel: Dynamics 365 for Customer Engagement-appar</span><span class="sxs-lookup"><span data-stu-id="70a64-148">Solution Lifecycle Management: Dynamics 365 for Customer Engagement apps</span></span>](https://www.microsoft.com/download/details.aspx?id=57777)
