---
title: Installera, ställ in och uppdatera kundportalen
description: Det här avsnittet innehåller licensieringsinformation och installationsinstruktioner för kundportalen.
author: dasani-madipalli
ms.date: 06/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 5c4cad305e3d130b3283ca3424c84f60e2d13307
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5907825"
---
# <a name="install-set-up-and-update-the-customer-portal"></a><span data-ttu-id="fd036-103">Installera, ställ in och uppdatera kundportalen</span><span class="sxs-lookup"><span data-stu-id="fd036-103">Install, set up, and update the Customer portal</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="licensing-requirements"></a><span data-ttu-id="fd036-104">Licensieringskrav</span><span class="sxs-lookup"><span data-stu-id="fd036-104">Licensing requirements</span></span>

<span data-ttu-id="fd036-105">Om du vill implementera kundportalen måste du ha följande licenser:</span><span class="sxs-lookup"><span data-stu-id="fd036-105">To implement the Customer portal, you must have the following licenses:</span></span>

- <span data-ttu-id="fd036-106">**Power Apps-portaler** – den här licensen krävs för att vara värd för kundportalen.</span><span class="sxs-lookup"><span data-stu-id="fd036-106">**Power Apps portals** – This license is required to host the Customer portal.</span></span> <span data-ttu-id="fd036-107">Portaler är licensierade utifrån användning.</span><span class="sxs-lookup"><span data-stu-id="fd036-107">Portals are licensed based on usage.</span></span> <span data-ttu-id="fd036-108">Mer information finns i avsnittet om [Power Apps licenskrav för portaler](/power-platform/admin/powerapps-flow-licensing-faq#portals).</span><span class="sxs-lookup"><span data-stu-id="fd036-108">For more information, see the [Power Apps portals licensing requirements](/power-platform/admin/powerapps-flow-licensing-faq#portals).</span></span>
- <span data-ttu-id="fd036-109">**Dubbelriktad skrivning** – du måste ha de licenser som krävs för att möjliggöra dubbelriktad skrivning för tabeller för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="fd036-109">**Dual-write** – You must have the necessary licenses to enable dual-write for Supply Chain Management tables.</span></span> <span data-ttu-id="fd036-110">För mer information, se [systemkrav för dubbelriktad skrivning](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span><span class="sxs-lookup"><span data-stu-id="fd036-110">For more information, see the [system requirements for dual-write](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-system-req.md).</span></span>

## <a name="dependencies-on-dual-write-and-power-apps-portals"></a><span data-ttu-id="fd036-111">Beroenden på dubbelriktad skrivning och Power Apps-portaler</span><span class="sxs-lookup"><span data-stu-id="fd036-111">Dependencies on dual-write and Power Apps portals</span></span>

<span data-ttu-id="fd036-112">Kundportalen beror på Power Apps-portaler och dubbelskrivning, vilket visas i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="fd036-112">The Customer portal depends on Power Apps portals and dual-write, as shown in the following illustration.</span></span>

<span data-ttu-id="fd036-113">![Kundportalberoenden](media/customer-portal-elements.png "Kundportalberoenden")</span><span class="sxs-lookup"><span data-stu-id="fd036-113">![Customer portal dependencies](media/customer-portal-elements.png "Customer portal dependencies")</span></span>

<span data-ttu-id="fd036-114">Till skillnad från andra funktioner från Supply Chain Management, kundportalmallen finns i Power Apps-portaler.</span><span class="sxs-lookup"><span data-stu-id="fd036-114">Unlike other features from Supply Chain Management, the Customer portal template resides in Power Apps portals.</span></span> <span data-ttu-id="fd036-115">Därför begränsas kundportalen av de funktioner som tillhandahålls av Power Apps-portaler och tabellerna i dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="fd036-115">Therefore, the Customer portal is limited by the functionality and capabilities that are provided by Power Apps portals and the tables in dual-write.</span></span>

## <a name="required-setup-to-enable-the-customer-portal"></a><a name="required-setup"></a><span data-ttu-id="fd036-116">Obligatorisk inställning för att aktivera kundportalen</span><span class="sxs-lookup"><span data-stu-id="fd036-116">Required setup to enable the Customer portal</span></span>

<span data-ttu-id="fd036-117">När du har installerat de nödvändiga licenserna kan du ställa in dubbelriktad skrivning enligt beskrivningen i [inledande synkroniseringsinställningarna för dubbelriktad skrivning](/dynamics365/supply-chain/sales-marketing/enable-entity-map).</span><span class="sxs-lookup"><span data-stu-id="fd036-117">After you've made sure that you have the required licenses, you can set up dual-write as described in the [dual-write initial synchronization instructions](/dynamics365/supply-chain/sales-marketing/enable-entity-map).</span></span>

<span data-ttu-id="fd036-118">Se till att aktivera följande tabellmappningar i dubbelriktad skrivning:</span><span class="sxs-lookup"><span data-stu-id="fd036-118">Be sure to enable the following table mappings in dual-write:</span></span>

- <span data-ttu-id="fd036-119">Försäljningsorderhuvud</span><span class="sxs-lookup"><span data-stu-id="fd036-119">Sales Order Header</span></span>
- <span data-ttu-id="fd036-120">Försäljningsorderinformation</span><span class="sxs-lookup"><span data-stu-id="fd036-120">Sales Order Details</span></span>
- <span data-ttu-id="fd036-121">Konton</span><span class="sxs-lookup"><span data-stu-id="fd036-121">Accounts</span></span>
- <span data-ttu-id="fd036-122">Kontakter</span><span class="sxs-lookup"><span data-stu-id="fd036-122">Contacts</span></span>
- <span data-ttu-id="fd036-123">Produkter</span><span class="sxs-lookup"><span data-stu-id="fd036-123">Products</span></span>

<span data-ttu-id="fd036-124">När den här inställningen har slutförts kan du etablera kundportalmallen.</span><span class="sxs-lookup"><span data-stu-id="fd036-124">After this setup is completed, you can provision the Customer portal template.</span></span>

## <a name="provision-the-customer-portal"></a><span data-ttu-id="fd036-125">Etablera kundportalen</span><span class="sxs-lookup"><span data-stu-id="fd036-125">Provision the Customer portal</span></span>

<span data-ttu-id="fd036-126">Innan du börjar ska du kontrollera att du redan har slutfört de [nödvändiga inställningarna](#required-setup).</span><span class="sxs-lookup"><span data-stu-id="fd036-126">Before you begin, make sure that you've already completed the [required setup](#required-setup).</span></span> <span data-ttu-id="fd036-127">Följ sedan dessa steg för att etablera kundportalen.</span><span class="sxs-lookup"><span data-stu-id="fd036-127">Then follow these steps to provision the Customer portal.</span></span>

1. <span data-ttu-id="fd036-128">Gå till [make.powerapps.com](https://make.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="fd036-128">Go to [make.powerapps.com](https://make.powerapps.com/).</span></span>
2. <span data-ttu-id="fd036-129">Kontrollera att du använder den miljö där du har aktiverat dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="fd036-129">Make sure that you're using the environment where you enabled dual-write.</span></span>
3. <span data-ttu-id="fd036-130">På fliken **Skapa** bläddra ned till avsnittet **Starta från mall** och välj den mall som har fått kunden för hantering av **Kundportal**.</span><span class="sxs-lookup"><span data-stu-id="fd036-130">On the **Create** tab, scroll down to the **Start from template** section, and select the template that is named **Customer Portal**.</span></span>
4. <span data-ttu-id="fd036-131">Följ instruktionerna på skärmen.</span><span class="sxs-lookup"><span data-stu-id="fd036-131">Follow the on-screen instructions.</span></span>

<span data-ttu-id="fd036-132">När etableringen har slutförts kan du få tillgång till kundportalen i avsnittet **Dina appar** på sidan **Start**-sidan.</span><span class="sxs-lookup"><span data-stu-id="fd036-132">After provisioning is completed, you can access the Customer portal in the **Your apps** section of the **Home** page.</span></span>

> [!NOTE]
> <span data-ttu-id="fd036-133">Om den dubbelriktad lösningen inte är installerad i den miljö som du arbetar i får du ett felmeddelande och kundportalen etableras inte.</span><span class="sxs-lookup"><span data-stu-id="fd036-133">If the dual-write solution isn't installed in the environment that you're working in, you will receive an error message, and the Customer portal won't be provisioned.</span></span>

## <a name="update-the-customer-portal"></a><span data-ttu-id="fd036-134">Uppdatera kundportalen</span><span class="sxs-lookup"><span data-stu-id="fd036-134">Update the Customer portal</span></span>

<span data-ttu-id="fd036-135">Fler funktioner kan läggas till kundportalen senare.</span><span class="sxs-lookup"><span data-stu-id="fd036-135">More functionality might be added to the Customer portal later.</span></span> <span data-ttu-id="fd036-136">Alla ändringar som Microsoft gör i de underliggande lösningskomponenterna visas automatiskt i din miljö.</span><span class="sxs-lookup"><span data-stu-id="fd036-136">Any changes that Microsoft makes to the underlying solution components will automatically appear in your environment.</span></span> <span data-ttu-id="fd036-137">Den webbplats som är etablerad i miljön återspeglar dock inte automatiskt ändringar som görs i konfigurationsdata.</span><span class="sxs-lookup"><span data-stu-id="fd036-137">However, the website that is provisioned in your environment won't automatically reflect changes that are made to the configuration data.</span></span> <span data-ttu-id="fd036-138">Du måste manuellt tillämpa ändringarna genom att hämta koden från den nya mallen och koppla den till den etablerade webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="fd036-138">You will have to manually apply those changes by getting the code from the new template and merging it with the provisioned website.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fd036-139">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="fd036-139">Additional resources</span></span>

<span data-ttu-id="fd036-140">Om du vill veta hur du kan ställa in och anpassa kundportalen bör du börja med att granska följande dokumentation för den underliggande tekniken:</span><span class="sxs-lookup"><span data-stu-id="fd036-140">To learn how you can set up and customize the Customer portal, you should start by reviewing the following documentation for the underlying technologies:</span></span>

- [<span data-ttu-id="fd036-141">Power Apps-portaldokumentation</span><span class="sxs-lookup"><span data-stu-id="fd036-141">Power Apps portals documentation</span></span>](/powerapps/maker/portals/overview)
- [<span data-ttu-id="fd036-142">Dokumentation för dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="fd036-142">Dual-write documentation</span></span>](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md)

<span data-ttu-id="fd036-143">Om du vill hantera portalerna effektivt måste du känna till Power Apps-portalerna och Microsoft Dataverse livscykeln.</span><span class="sxs-lookup"><span data-stu-id="fd036-143">To effectively manage your portals, you must understand the Power Apps portals and Microsoft Dataverse lifecycle.</span></span> <span data-ttu-id="fd036-144">Mer information finns i följande resurser:</span><span class="sxs-lookup"><span data-stu-id="fd036-144">For more information, see the following resources:</span></span>

- [<span data-ttu-id="fd036-145">Om portalens livscykel</span><span class="sxs-lookup"><span data-stu-id="fd036-145">About portal lifecycle</span></span>](/powerapps/maker/portals/admin/portal-lifecycle)
- [<span data-ttu-id="fd036-146">Uppgradera en portal</span><span class="sxs-lookup"><span data-stu-id="fd036-146">Upgrade a portal</span></span>](/powerapps/maker/portals/admin/upgrade-portal)
- [<span data-ttu-id="fd036-147">Migrera portalkonfiguration</span><span class="sxs-lookup"><span data-stu-id="fd036-147">Migrate portal configuration</span></span>](/powerapps/maker/portals/admin/migrate-portal-configuration)
- [<span data-ttu-id="fd036-148">Hantering av lösningens livscykel: Dynamics 365 for Customer Engagement-appar</span><span class="sxs-lookup"><span data-stu-id="fd036-148">Solution Lifecycle Management: Dynamics 365 for Customer Engagement apps</span></span>](https://www.microsoft.com/download/details.aspx?id=57777)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]