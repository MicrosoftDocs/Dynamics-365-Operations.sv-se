---
title: Integrera tillgångshantering med anläggningstillgångar
description: I det här avsnittet beskrivs hur du integrerar modulerna för Tillgångshantering och Anläggningstillgångar så att du kan koppla anläggningstillgångar med underhållstillgångar.
author: kamaybac
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: dabourq
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: a45bf1f62cdcc8abed2ec157a223e7f3fddec7ce
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809864"
---
# <a name="integrate-asset-management-with-fixed-assets"></a><span data-ttu-id="c7a78-103">Integrera tillgångshantering med anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="c7a78-103">Integrate asset management with fixed assets</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c7a78-104">Genom att integrera modulerna **Tillgångshantering** och **Anläggningstillgångar** kan du koppla anläggningstillgångar med underhållstillgångar.</span><span class="sxs-lookup"><span data-stu-id="c7a78-104">By integrating the **Asset management** and **Fixed assets** modules, you can link fixed assets with maintenance assets.</span></span> <span data-ttu-id="c7a78-105">Användare av anläggningstillgångar kan sedan skapa en underhållstillgång från en ny eller befintlig anläggningstillgång och användare av tillgångshantering kan associera en underhållsanläggning med en befintlig anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="c7a78-105">Fixed assets users can then create a maintenance asset from a new or existing fixed asset, and Asset management users can associate a maintenance asset with an existing fixed asset.</span></span> <span data-ttu-id="c7a78-106">Den här funktionen gör det också enkelt för användare med anläggningstillgångar att visa kostnader som har bokförts från arbetsorder för relaterade underhållstillgångar.</span><span class="sxs-lookup"><span data-stu-id="c7a78-106">This feature also makes it easy for Fixed assets users to view the costs that were posted from work orders for related maintenance assets.</span></span>

> [!NOTE]
> <span data-ttu-id="c7a78-107">I det här avsnittet *underhållstillgångar* hänvisar till tillgångar från modulen **tillgångshantering** och *anläggningstillgångar* hänvisar till tillgångar från modulen **anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="c7a78-107">In this topic, *maintenance assets* refer to assets from the **Asset management** module, and *fixed assets* refer to assets from the **Fixed assets** module.</span></span>

## <a name="set-a-default-location-for-new-maintenance-assets-that-are-created-from-fixed-assets-optional"></a><span data-ttu-id="c7a78-108">Ange en standardplats för nya underhållstillgångar som skapas från anläggningstillgångar (valfritt)</span><span class="sxs-lookup"><span data-stu-id="c7a78-108">Set a default location for new maintenance assets that are created from fixed assets (optional)</span></span>

<span data-ttu-id="c7a78-109">Denna valfria konfiguration låter dig ange en funktionell standardplats för nya underhållstillgångar som skapas från anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="c7a78-109">This optional configuration lets you set a default functional location for new maintenance assets that are created from fixed assets.</span></span> <span data-ttu-id="c7a78-110">Den här konfigurationen är vanligtvis bara en gång om du slutför hela.</span><span class="sxs-lookup"><span data-stu-id="c7a78-110">You typically complete this configuration this just one time, if you complete it at all.</span></span>

<span data-ttu-id="c7a78-111">Om du vill slutföra konfigurationen, gör följande.</span><span class="sxs-lookup"><span data-stu-id="c7a78-111">To complete the configuration, follow these steps.</span></span>

1. <span data-ttu-id="c7a78-112">Gå till **Tillgångshantering \> Inställningar \> Parametrar för tillgångshantering**.</span><span class="sxs-lookup"><span data-stu-id="c7a78-112">Go to **Asset management \> Setup \> Asset management parameters**.</span></span>
1. <span data-ttu-id="c7a78-113">På fliken **Anläggningstillgångar** i fältet **funktionsplats** väljer du standardplats.</span><span class="sxs-lookup"><span data-stu-id="c7a78-113">On the **Fixed assets** tab, in the **Functional location** field, select the default location.</span></span>
1. <span data-ttu-id="c7a78-114">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c7a78-114">On the Action Pane, select **Save**.</span></span>

## <a name="work-with-integrated-maintenance-assets-and-fixed-assets"></a><span data-ttu-id="c7a78-115">Arbeta med integrerade underhållstillgångar och anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="c7a78-115">Work with integrated maintenance assets and fixed assets</span></span>

<span data-ttu-id="c7a78-116">Det här avsnittet innehåller en samling procedurer som visar olika sätt som du kan arbeta med integrerad tillgångshantering och funktioner för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="c7a78-116">This section provides a collection of procedures that show various ways that you can work with the integrated Asset management and Fixed assets features.</span></span>

### <a name="associate-an-existing-maintenance-asset-with-a-fixed-asset"></a><span data-ttu-id="c7a78-117">Associera en befintlig underhållstillgång med en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="c7a78-117">Associate an existing maintenance asset with a fixed asset</span></span>

<span data-ttu-id="c7a78-118">Gör följande för att associera en befintlig underhållstillgång med en anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="c7a78-118">To associate an existing maintenance asset with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="c7a78-119">Gå till **Tillgångshantering \> Tillgångar \> Alla tillgångar** (eller **Aktiva tillgångar**).</span><span class="sxs-lookup"><span data-stu-id="c7a78-119">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="c7a78-120">Välj en tillgång.</span><span class="sxs-lookup"><span data-stu-id="c7a78-120">Select an asset.</span></span>
1. <span data-ttu-id="c7a78-121">På snabbfliken **Anläggningstillgångar** i fältet **Nummer för anläggningstillgång**, välj en befintlig anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="c7a78-121">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select an existing fixed asset.</span></span>
1. <span data-ttu-id="c7a78-122">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c7a78-122">On the Action Pane, select **Save**.</span></span>

### <a name="view-the-fixed-asset-that-is-associated-with-a-selected-maintenance-asset"></a><span data-ttu-id="c7a78-123">Visa anläggningstillgången som är kopplad till en vald underhållstillgång</span><span class="sxs-lookup"><span data-stu-id="c7a78-123">View the fixed asset that is associated with a selected maintenance asset</span></span>

<span data-ttu-id="c7a78-124">Om du vill visa anläggningstillgången som är kopplad till en vald underhållstillgång, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="c7a78-124">To view the fixed asset that is associated with a selected maintenance asset, follow these steps.</span></span>

1. <span data-ttu-id="c7a78-125">Gå till **Tillgångshantering \> Tillgångar \> Alla tillgångar** (eller **Aktiva tillgångar**).</span><span class="sxs-lookup"><span data-stu-id="c7a78-125">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="c7a78-126">Välj en tillgång.</span><span class="sxs-lookup"><span data-stu-id="c7a78-126">Select an asset.</span></span>
1. <span data-ttu-id="c7a78-127">På snabbfliken **Anläggningstillgångar** i fältet **Nummer för anläggningstillgång**, välj länken.</span><span class="sxs-lookup"><span data-stu-id="c7a78-127">On the **Fixed asset** FastTab, in the **Fixed asset number** field, select the link.</span></span>

    <span data-ttu-id="c7a78-128">Sidan **anläggningstillgångar** för den valda tillgången öppnas.</span><span class="sxs-lookup"><span data-stu-id="c7a78-128">The **Fixed assets** page for the selected asset is opened.</span></span> <span data-ttu-id="c7a78-129">(Vanligtvis finns den här sidan på **anläggningstillgångar \> anläggningstillgångar \> anläggningstillgångar**.)</span><span class="sxs-lookup"><span data-stu-id="c7a78-129">(Typically, this page is found at **Fixed assets \> Fixed assets \> Fixed assets**.)</span></span>

### <a name="view-the-maintenance-asset-that-is-associated-with-a-selected-fixed-asset"></a><span data-ttu-id="c7a78-130">Visa underhållstillgången som är kopplad till en vald anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="c7a78-130">View the maintenance asset that is associated with a selected fixed asset</span></span>

<span data-ttu-id="c7a78-131">Om du vill visa underhållstillgången som är kopplad till en vald anläggningstillgång, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="c7a78-131">To view the maintenance asset that is associated with a selected fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="c7a78-132">Gå till **Anläggningstillgångar \> Anläggningstillgångar \> Anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="c7a78-132">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="c7a78-133">Välj en tillgång.</span><span class="sxs-lookup"><span data-stu-id="c7a78-133">Select an asset.</span></span>
1. <span data-ttu-id="c7a78-134">I åtgärdsfönstret på fliken **Tillgångshantering** i gruppen **Vy** väljer du **underhållstillgång**.</span><span class="sxs-lookup"><span data-stu-id="c7a78-134">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance asset**.</span></span>

    <span data-ttu-id="c7a78-135">Sidan **underhållstillgång** för den tillgång som är kopplad till en vald anläggningstillgång öppnas.</span><span class="sxs-lookup"><span data-stu-id="c7a78-135">The **Maintenance asset** page for the asset that is associated with the selected fixed asset is opened.</span></span> <span data-ttu-id="c7a78-136">(Vanligtvis finns den här sidan på **Tillgångshantering \> Tillgångar \> Alla tillgångar**.)</span><span class="sxs-lookup"><span data-stu-id="c7a78-136">(Typically, this page is found at **Asset management \> Assets \> All assets**.)</span></span>

### <a name="view-maintenance-costs-that-are-associated-with-a-fixed-asset"></a><span data-ttu-id="c7a78-137">Visa underhållskostnader som är associerade med en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="c7a78-137">View maintenance costs that are associated with a fixed asset</span></span>

<span data-ttu-id="c7a78-138">Arbetsorder för tillgångshantering kan bokföras för underhållstillgångar och varje arbetsorder har normalt en kostnad.</span><span class="sxs-lookup"><span data-stu-id="c7a78-138">Asset management work orders can be posted for maintenance assets, and each of those work orders typically has a cost.</span></span> <span data-ttu-id="c7a78-139">När en anläggningstillgång är kopplad med en underhållstillgång kan du gå direkt från anläggningstillgången för att visa relaterade kostnader.</span><span class="sxs-lookup"><span data-stu-id="c7a78-139">When a fixed asset is associated with a maintenance asset, you can go directly from the fixed asset to view the related costs.</span></span>

<span data-ttu-id="c7a78-140">Om du vill visa underhållskostnad som är kopplad till en anläggningstillgång, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="c7a78-140">To view the maintenance costs that are associated with a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="c7a78-141">Gå till **Anläggningstillgångar \> Anläggningstillgångar \> Anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="c7a78-141">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="c7a78-142">Välj en tillgång.</span><span class="sxs-lookup"><span data-stu-id="c7a78-142">Select an asset.</span></span>
1. <span data-ttu-id="c7a78-143">I åtgärdsfönstret på fliken **Tillgångshantering** i gruppen **Vy** väljer du **underhållskostnad**.</span><span class="sxs-lookup"><span data-stu-id="c7a78-143">On the Action Pane, on the **Asset management** tab, in the **View** group, select **Maintenance cost**.</span></span>

    <span data-ttu-id="c7a78-144">Sidan **underhållskostnad** öppnas och visar relaterade kostnader.</span><span class="sxs-lookup"><span data-stu-id="c7a78-144">The **Maintenance cost** page is opened and shows the related costs.</span></span>

### <a name="create-a-new-maintenance-asset-for-an-existing-fixed-asset"></a><a name="new-maintenance-from-fixed"></a><span data-ttu-id="c7a78-145">Skapa en ny underhållstillgång för en befintlig anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="c7a78-145">Create a new maintenance asset for an existing fixed asset</span></span>

<span data-ttu-id="c7a78-146">För att skapa en ny underhållstillgång för en befintlig anläggningstillgång följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="c7a78-146">To create a new maintenance asset for an existing fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="c7a78-147">Gå till **Anläggningstillgångar \> Anläggningstillgångar \> Anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="c7a78-147">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="c7a78-148">Välj en tillgång.</span><span class="sxs-lookup"><span data-stu-id="c7a78-148">Select an asset.</span></span>
1. <span data-ttu-id="c7a78-149">I åtgärdsfönstret på fliken **Tillgångshantering** i gruppen **Ny** väljer du **Skapa underhållstillgång**.</span><span class="sxs-lookup"><span data-stu-id="c7a78-149">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span> <span data-ttu-id="c7a78-150">(Om det här alternativet inte är tillgängligt kanske en underhållstillgång redan är kopplad till den valda anläggningstillgången.)</span><span class="sxs-lookup"><span data-stu-id="c7a78-150">(If this option is unavailable, a maintenance asset might already be associated with the selected fixed asset.)</span></span>
1. <span data-ttu-id="c7a78-151">Slutför skapandet av tillgången såsom beskrivs i [Skapa en tillgång](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="c7a78-151">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="create-a-new-fixed-asset-and-add-a-new-maintenance-asset-for-it"></a><span data-ttu-id="c7a78-152">Skapa en ny anläggningstillgång och lägg till en ny underhållstillgång för den</span><span class="sxs-lookup"><span data-stu-id="c7a78-152">Create a new fixed asset and add a new maintenance asset for it</span></span>

<span data-ttu-id="c7a78-153">För att skapa en ny anläggningstillgång och lägga till en ny underhållstillgång för den följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="c7a78-153">To create a new fixed asset and add a new maintenance asset for it, follow these steps.</span></span>

1. <span data-ttu-id="c7a78-154">Gå till **Anläggningstillgångar \> Anläggningstillgångar \> Anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="c7a78-154">Go to **Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
1. <span data-ttu-id="c7a78-155">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c7a78-155">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c7a78-156">Slutför skapandet av anläggningstillgången såsom beskrivs i [Skapa en anläggningstillgång](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span><span class="sxs-lookup"><span data-stu-id="c7a78-156">Finish creating the fixed asset as described in [Create a fixed asset](../../../finance/fixed-assets/tasks/create-fixed-asset.md).</span></span>
1. <span data-ttu-id="c7a78-157">I åtgärdsfönstret på fliken **Tillgångshantering** i gruppen **Ny** väljer du **Skapa underhållstillgång**.</span><span class="sxs-lookup"><span data-stu-id="c7a78-157">On the Action Pane, on the **Asset management** tab, in the **New** group, select **Create maintenance asset**.</span></span>
1. <span data-ttu-id="c7a78-158">Slutför skapandet av tillgången såsom beskrivs i [Skapa en tillgång](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="c7a78-158">Finish creating the asset as described in [Create an asset](../objects/create-an-object.md).</span></span>

### <a name="remove-the-association-between-two-assets"></a><span data-ttu-id="c7a78-159">Ta bort kopplingen mellan två resurser</span><span class="sxs-lookup"><span data-stu-id="c7a78-159">Remove the association between two assets</span></span>

<span data-ttu-id="c7a78-160">I vissa fall måste du kanske avassociera en underhållstillgång från anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="c7a78-160">In some cases, you might have to disassociate a maintenance asset from its fixed asset.</span></span> <span data-ttu-id="c7a78-161">Om du till exempel vill [skapa en ny underhållstillgång](#new-maintenance-from-fixed) från en anläggningstillgång, måste du först ta bort alla befintliga associationer.</span><span class="sxs-lookup"><span data-stu-id="c7a78-161">For example, if you want to [create a new maintenance asset](#new-maintenance-from-fixed) from a fixed asset, you must first remove any existing association.</span></span>

<span data-ttu-id="c7a78-162">Följ dessa steg för att ta bort en befintlig koppling mellan en underhållstillgång och en anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="c7a78-162">To remove an existing association between a maintenance asset and a fixed asset, follow these steps.</span></span>

1. <span data-ttu-id="c7a78-163">Gå till **Tillgångshantering \> Tillgångar \> Alla tillgångar** (eller **Aktiva tillgångar**).</span><span class="sxs-lookup"><span data-stu-id="c7a78-163">Go to **Asset management \> Assets \> All assets** (or **Active assets**).</span></span>
1. <span data-ttu-id="c7a78-164">Hitta och öppna anläggningstillgången.</span><span class="sxs-lookup"><span data-stu-id="c7a78-164">Find and open the fixed asset.</span></span>
1. <span data-ttu-id="c7a78-165">På snabbfliken **anläggningstillgång** avmarkerar du värdet från fältet **funktionsplats**.</span><span class="sxs-lookup"><span data-stu-id="c7a78-165">On the **Fixed asset** FastTab, clear the value from the **Functional location** field.</span></span>
1. <span data-ttu-id="c7a78-166">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c7a78-166">On the Action Pane, select **Save**.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]