---
title: Flytta, ersätt och installera tillgångar
description: Det här avsnittet förklarar hur du flyttar, ersätter och installerar tillgångar i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectReplace, EntAssetObjectInstallLookup, EntAssetObjectMove, EntAssetObjectTableEditSubObjects
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec150adb35eb0600844245b14cbec9e9632ab337
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/25/2020
ms.locfileid: "3889563"
---
# <a name="move-replace-and-install-assets"></a><span data-ttu-id="4ce66-103">Flytta, ersätt och installera tillgångar</span><span class="sxs-lookup"><span data-stu-id="4ce66-103">Move, replace, and install assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="4ce66-104">Det här avsnittet förklarar hur du flyttar, ersätter och installerar tillgångar i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="4ce66-104">This topic explains how to move, replace, and install assets in Asset Management.</span></span> <span data-ttu-id="4ce66-105">Du kan skapa enskilda tillgångar som inte har några relationer till andra tillgångar eller du kan skapa en tillgångsstruktur som innehåller en överordnad tillgång (tillgång på översta nivån) och relaterade underordnade tillgångar (undertillgångar).</span><span class="sxs-lookup"><span data-stu-id="4ce66-105">You can create individual assets that have no relations to other assets, or you can create an asset structure that includes a parent asset (top-level asset) and related child assets (sub-assets).</span></span> <span data-ttu-id="4ce66-106">I tillgångshantering finns tre metoder för att flytta och ändra platsen för en tillgång:</span><span class="sxs-lookup"><span data-stu-id="4ce66-106">In Asset Management, there are three approaches to moving and changing the location of an asset:</span></span>

- <span data-ttu-id="4ce66-107">**Flytta** – Flytta en tillgång antingen till en annan tillgångsstruktur eller till en annan plats i samma tillgångsstruktur.</span><span class="sxs-lookup"><span data-stu-id="4ce66-107">**Move** – Move an asset either to another asset structure or to another location in the same asset structure.</span></span>
- <span data-ttu-id="4ce66-108">**Ersätt** – ta tillfälligt bort en tillgång från en tillgångsstruktur så att den kan repareras eller renoveras och sedan lägga tillbaka den renoverade tillgången i tillgångsstrukturen senare.</span><span class="sxs-lookup"><span data-stu-id="4ce66-108">**Replace** – Temporarily remove an asset from an asset structure so that it can be repaired or refurbished, and then add the refurbished asset back to the asset structure later.</span></span> <span data-ttu-id="4ce66-109">Du kan också permanent ersätta en begagnad tillgång med en ny tillgång.</span><span class="sxs-lookup"><span data-stu-id="4ce66-109">Alternatively, permanently replace a used asset with a new asset.</span></span>
- <span data-ttu-id="4ce66-110">**Installera** – installera en överordnad tillgång och eventuella relaterade underordnade tillgångar på en funktionsplats.</span><span class="sxs-lookup"><span data-stu-id="4ce66-110">**Install** – Install a parent asset and any related child assets on a functional location.</span></span>

> [!NOTE]
> <span data-ttu-id="4ce66-111">Den tillgång som du flyttar, ersätter eller installerar kan relateras till en annan funktionsplats.</span><span class="sxs-lookup"><span data-stu-id="4ce66-111">The asset that you move, replace, or install might be related to another functional location.</span></span> <span data-ttu-id="4ce66-112">I så fall kan tillgången använda ekonomiska dimensioner för den funktionsplatsen.</span><span class="sxs-lookup"><span data-stu-id="4ce66-112">In that case, the asset might use financial dimensions of the functional location.</span></span> <span data-ttu-id="4ce66-113">På sidan **funktionsplatstyper** ställer du in hanteringen av ekonomiska dimensioner på funktionsplatser.</span><span class="sxs-lookup"><span data-stu-id="4ce66-113">On the **Functional location types** page, you set up the handling of financial dimensions on functional locations.</span></span>

## <a name="move-asset"></a><span data-ttu-id="4ce66-114">Flytta tillgång</span><span class="sxs-lookup"><span data-stu-id="4ce66-114">Move asset</span></span>

<span data-ttu-id="4ce66-115">Använd funktionen **Flytta tillgång** för att flytta en tillgång antingen till en annan tillgångsstruktur eller till en annan plats i samma tillgångsstruktur.</span><span class="sxs-lookup"><span data-stu-id="4ce66-115">Use the **Move asset** function to move an asset either to another asset structure or to another location in the same asset structure.</span></span> <span data-ttu-id="4ce66-116">Du kan också flytta en tillgång från en tillgångsstruktur så att den blir en fristående tillgång som inte har några strukturrelationer.</span><span class="sxs-lookup"><span data-stu-id="4ce66-116">You can also move an asset out of an asset structure so that it becomes a standalone asset that has no structure relations.</span></span>

> [!NOTE]
> <span data-ttu-id="4ce66-117">Använd inte den här funktionen om tillgångarna repareras eller tillfälligt ersätts.</span><span class="sxs-lookup"><span data-stu-id="4ce66-117">Don't use this function if assets are being repaired or temporarily replaced.</span></span> <span data-ttu-id="4ce66-118">Använd i stället funktionen **Ersätt tillgång** som beskrivs senare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="4ce66-118">Instead, use the **Replace asset** functionality that is described later in this topic.</span></span>

1. <span data-ttu-id="4ce66-119">Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Alla tillgångar** eller **Aktiva tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="4ce66-119">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="4ce66-120">Välj tillgången som ska flyttas i listan.</span><span class="sxs-lookup"><span data-stu-id="4ce66-120">In the list, select the asset to move.</span></span> <span data-ttu-id="4ce66-121">Om tillgången har underordnade tillgångar kan du också flytta dessa tillgångar.</span><span class="sxs-lookup"><span data-stu-id="4ce66-121">If the asset has child assets, you also move those assets.</span></span>
3. <span data-ttu-id="4ce66-122">Välj **Flytta tillgång**.</span><span class="sxs-lookup"><span data-stu-id="4ce66-122">Select **Move asset**.</span></span>
4. <span data-ttu-id="4ce66-123">Om du vill flytta tillgången så att den blir en del av en tillgångsstruktur väljer du den nya överordnade tillgången i fältet **överordnad tillgång**.</span><span class="sxs-lookup"><span data-stu-id="4ce66-123">To move the asset so that it becomes part of an asset structure, select the new parent asset in the **Parent asset** field.</span></span> <span data-ttu-id="4ce66-124">Om du flyttar en underordnad tillgång och du vill göra den till en fristående tillgång som inte har några strukturrelationer lämnar du fältet **överordnad tillgång** tomt.</span><span class="sxs-lookup"><span data-stu-id="4ce66-124">If you're moving a child asset, and you want to make it a standalone asset that has no structure relations, leave the **Parent asset** field blank.</span></span>
5. <span data-ttu-id="4ce66-125">Som standard är fältet **Giltighet** inställt på aktuellt datum och aktuell tid.</span><span class="sxs-lookup"><span data-stu-id="4ce66-125">By default, the **Effective** field is set to the current date and time.</span></span> <span data-ttu-id="4ce66-126">Du kan dock välja ett annat datum och en annan tidpunkt som tillgångens flyttning är giltig från.</span><span class="sxs-lookup"><span data-stu-id="4ce66-126">However, you can select a different date and time that the asset move is valid from.</span></span>
6. <span data-ttu-id="4ce66-127">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ce66-127">Select **OK**.</span></span>

## <a name="replace-asset"></a><span data-ttu-id="4ce66-128">Ersätt tillgång</span><span class="sxs-lookup"><span data-stu-id="4ce66-128">Replace asset</span></span>

<span data-ttu-id="4ce66-129">Använd funktionen **Ersätt tillgång** i samband med reparationer, renovering eller permanent ersättning av en utsliten tillgång genom en ny tillgång.</span><span class="sxs-lookup"><span data-stu-id="4ce66-129">Use the **Replace asset** function in connection with repairs, refurbishment, or permanent replacement of a worn-out asset by a new asset.</span></span> <span data-ttu-id="4ce66-130">Den här funktionen används för att ersätta underordnade tillgångar i en tillgångsstruktur.</span><span class="sxs-lookup"><span data-stu-id="4ce66-130">This function is used to replace child assets in an asset structure.</span></span> <span data-ttu-id="4ce66-131">För överordnade tillgångar (dvs. tillgångar som för närvarande inte har en överordnad tillgång), görs denna ersättning på en funktionsplats.</span><span class="sxs-lookup"><span data-stu-id="4ce66-131">For parent assets (that is, assets that don't currently have a parent asset), this replacement is done on a functional location.</span></span> <span data-ttu-id="4ce66-132">Mer information om hur du ersätter överordnade tillgångar på en funktionsplats finns i [Installera tillgångar på funktionsplatser](../functional-locations/install-objects-on-functional-locations.md).</span><span class="sxs-lookup"><span data-stu-id="4ce66-132">For more information about how to replace parent assets on a functional location, see [Install assets on functional locations](../functional-locations/install-objects-on-functional-locations.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4ce66-133">Om en reparationsverkstad är relaterad till din produktionsavdelning kan du skapa funktionsplatser som **reparation**, **kassation**och **lagring** för att hantera reparation och utbyte av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="4ce66-133">If a repair shop is related to your production department, you can create functional locations such as **Repair**, **Scrap**, and **Storage** to handle the repair and replacement of assets.</span></span>

1. <span data-ttu-id="4ce66-134">Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Alla tillgångar** eller **Aktiva tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="4ce66-134">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="4ce66-135">Välj den underordnade tillgången som ska bytas ut i listan.</span><span class="sxs-lookup"><span data-stu-id="4ce66-135">In the list, select the child asset to replace.</span></span> <span data-ttu-id="4ce66-136">Om tillgången har underordnade tillgångar kan du också byta ut dessa tillgångar.</span><span class="sxs-lookup"><span data-stu-id="4ce66-136">If the asset has child assets, you also replace those assets.</span></span>
3. <span data-ttu-id="4ce66-137">Välj **Ersätt tillgång**.</span><span class="sxs-lookup"><span data-stu-id="4ce66-137">Select **Replace asset**.</span></span>

    <span data-ttu-id="4ce66-138">I fältet **strukturändring** visas det senaste datumet och den tidpunkt då den valda tillgången och de relaterade underordnade tillgångarna flyttades till tillgångsstrukturen.</span><span class="sxs-lookup"><span data-stu-id="4ce66-138">The **Structure change** field shows the last date and time that the selected asset and related child assets were moved in the asset structure.</span></span>

4. <span data-ttu-id="4ce66-139">I avsnittet **Vald tillgång** i fältet **Målfunktionsplats** väljer du den funktionsplats som tillgången ska flyttas till.</span><span class="sxs-lookup"><span data-stu-id="4ce66-139">In the **Selected asset** section, in the **Target functional location** field, select the functional location to move the asset to.</span></span> <span data-ttu-id="4ce66-140">Välj till exempel platsen **reparera** eller **kassation**.</span><span class="sxs-lookup"><span data-stu-id="4ce66-140">For example, select the **Repair** or **Scrap** location.</span></span>

    <span data-ttu-id="4ce66-141">I avsnittet **överordnad tillgång** visar fältet **Giltighet** det sista datum och tid som den överordnade tillgången och relaterade underordnade tillgångar har installerats eller flyttats på den aktuella funktionsplatsen.</span><span class="sxs-lookup"><span data-stu-id="4ce66-141">In the **Parent asset** section, the **Effective** field shows the last date and time that the parent asset and related child assets were installed or moved on the current functional location.</span></span>

5. <span data-ttu-id="4ce66-142">I avsnittet **ny tillgång** i fältet **tillgång** väljer du tillgången som ska infogas som en temporär eller permanent ersättning för den valda tillgången.</span><span class="sxs-lookup"><span data-stu-id="4ce66-142">In the **New asset** section, in the **Asset** field, select the asset to insert as a temporary or permanent replacement for the selected asset.</span></span> <span data-ttu-id="4ce66-143">Den här tillgången kan för närvarande finnas på en annan funktionsplats, t.ex. **lagring**.</span><span class="sxs-lookup"><span data-stu-id="4ce66-143">This asset might currently be located on another functional location, such as **Storage**.</span></span>
7. <span data-ttu-id="4ce66-144">I avsnittet **Giltig från** anges fältet **Giltighet** som standard till aktuellt datum och aktuell tid.</span><span class="sxs-lookup"><span data-stu-id="4ce66-144">In the **Effective from** section, the **Effective** field is set to the current date and time by default.</span></span> <span data-ttu-id="4ce66-145">Du kan dock välja ett annat datum och en annan tidpunkt som tillgångens ersättning är giltig från.</span><span class="sxs-lookup"><span data-stu-id="4ce66-145">However, you can select a different date and time that the asset replacement is valid from.</span></span>
8. <span data-ttu-id="4ce66-146">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ce66-146">Select **OK**.</span></span>

## <a name="install-asset"></a><span data-ttu-id="4ce66-147">Installera tillgång</span><span class="sxs-lookup"><span data-stu-id="4ce66-147">Install asset</span></span>

<span data-ttu-id="4ce66-148">Använd funktionen **installera tillgång** för att installera en tillgångsstruktur på en funktionsplats.</span><span class="sxs-lookup"><span data-stu-id="4ce66-148">Use the **Install asset** function to install an asset structure on a functional location.</span></span>

> [!NOTE]
> <span data-ttu-id="4ce66-149">Välj alltid en överordnad tillgång.</span><span class="sxs-lookup"><span data-stu-id="4ce66-149">Always select a parent asset.</span></span> <span data-ttu-id="4ce66-150">Överordnad tillgång och relaterade underordnade tillgångar kommer att flyttas till den valda funktionsplatsen.</span><span class="sxs-lookup"><span data-stu-id="4ce66-150">The parent asset and related child assets will be moved to the selected functional location.</span></span>

1. <span data-ttu-id="4ce66-151">Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Alla tillgångar** eller **Aktiva tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="4ce66-151">Select **Asset management** \> **Common** \> **Assets** \> **All assets** or **Active assets**.</span></span>
2. <span data-ttu-id="4ce66-152">I listan väljer du den överordnade tillgången som ska installeras på en annan funktionsplats.</span><span class="sxs-lookup"><span data-stu-id="4ce66-152">In the list, select the parent asset to install on another functional location.</span></span>
3. <span data-ttu-id="4ce66-153">Välj **Installera tillgång**.</span><span class="sxs-lookup"><span data-stu-id="4ce66-153">Select **Install asset**.</span></span>

    <span data-ttu-id="4ce66-154">Avsnittet **Attribut** visar de tillgångsattribut som anges på den överordnade tillgången.</span><span class="sxs-lookup"><span data-stu-id="4ce66-154">The **Attributes** section shows the asset attributes that are set up on the parent asset.</span></span>

4. <span data-ttu-id="4ce66-155">I fältet **Funktionsplats** väljer du den nya platsen.</span><span class="sxs-lookup"><span data-stu-id="4ce66-155">In the **Functional location** field, select the new location.</span></span>
5. <span data-ttu-id="4ce66-156">Som standard är fältet **Giltighet** inställt på aktuellt datum och aktuell tid.</span><span class="sxs-lookup"><span data-stu-id="4ce66-156">By default, the **Effective** field is set to the current date and time.</span></span> <span data-ttu-id="4ce66-157">Du kan dock välja ett annat datum och en annan tidpunkt som installationen på tillgångens struktur är giltig från.</span><span class="sxs-lookup"><span data-stu-id="4ce66-157">However, you can select a different date and time that the installation on the asset structure is valid from.</span></span>
6. <span data-ttu-id="4ce66-158">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ce66-158">Select **OK**.</span></span>
