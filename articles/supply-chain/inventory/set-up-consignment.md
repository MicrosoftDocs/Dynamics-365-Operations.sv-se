---
title: "Ställa in försändelse"
description: "Det här avsnittet beskriver hur du konfigurerar inkommande försändelselageroperationer."
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirPartyTable, EcoResTrackingDimensionGroup, InventJournalName, InventJournalOwnershipChange, InventOwner, InventTableInventoryDimensionGroups, VendTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 220804
ms.assetid: 88822f78-4de5-462c-a55f-1f766c572719
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 3e86aa8a718a36d61cfb3bd0c93007b209636113
ms.contentlocale: sv-se
ms.lasthandoff: 01/17/2018

---

# <a name="set-up-consignment"></a><span data-ttu-id="98f16-103">Ställa in försändelse</span><span class="sxs-lookup"><span data-stu-id="98f16-103">Set up consignment</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="98f16-104">Det här avsnittet beskriver hur du konfigurerar inkommande försändelselageroperationer.</span><span class="sxs-lookup"><span data-stu-id="98f16-104">This topic explains how to configure inbound consignment inventory operations.</span></span>

<span data-ttu-id="98f16-105">Försändelselagret är lager som ägs av en leverantör, men som lagras på din site.</span><span class="sxs-lookup"><span data-stu-id="98f16-105">Consignment inventory is inventory that’s owned by a vendor, but stored at your site.</span></span> <span data-ttu-id="98f16-106">När du är klar att förbruka eller använda lagret, tar du över ägarskapet för lagret.</span><span class="sxs-lookup"><span data-stu-id="98f16-106">When you’re ready to consume or use the inventory, you take over the ownership of the inventory.</span></span> <span data-ttu-id="98f16-107">I det här avsnittet beskrivs de inställningar som krävs för att aktivera försändelseprocesser.</span><span class="sxs-lookup"><span data-stu-id="98f16-107">This topic describes the setup needed to enable consignment processes.</span></span> <span data-ttu-id="98f16-108">Mer information om hur du ställer in försändelseprocesser hittar du på [Försändelse](consignment.md).</span><span class="sxs-lookup"><span data-stu-id="98f16-108">For more information about consignment processes, see [Consignment](consignment.md).</span></span>

## <a name="inventory-owners"></a><span data-ttu-id="98f16-109">Lagerägare</span><span class="sxs-lookup"><span data-stu-id="98f16-109">Inventory owners</span></span>
<span data-ttu-id="98f16-110">Om du vill registrera det fysiska inkommande försändelselagret måste du definiera en leverantörsägare.</span><span class="sxs-lookup"><span data-stu-id="98f16-110">In order to record physical inbound consignment inventory, you need to define a vendor owner.</span></span> <span data-ttu-id="98f16-111">Detta görs på sidan **Lagerägare**.</span><span class="sxs-lookup"><span data-stu-id="98f16-111">This is done on the **Inventory owner** page.</span></span> <span data-ttu-id="98f16-112">När du väljer ett **Leverantörskonto** genererar detta förvalda värden för fälten **Namn** och **Ägare**.</span><span class="sxs-lookup"><span data-stu-id="98f16-112">When you select a **Vendor account** this generates default values for the **Name** and **Owner** fields.</span></span> <span data-ttu-id="98f16-113">Värdet i fältet **Ägare** visas för leverantören, så du kanske vill ändra det om ditt leverantörkontonamn inte är svårt för externa kontakter att känna igen.</span><span class="sxs-lookup"><span data-stu-id="98f16-113">The value in the **Owner** field will be visible to the vendor, so you might want to change it if your vendor account names aren’t easy for external people to recognize.</span></span> <span data-ttu-id="98f16-114">Det är möjligt att redigera fältet **Ägare**, men bara fram till den punkt när du sparar posten **Lagerägare**.</span><span class="sxs-lookup"><span data-stu-id="98f16-114">It’s possible to edit the **Owner** field, but only up to the point when you save the **Inventory owner** record.</span></span> <span data-ttu-id="98f16-115">Fältet **Namn** fylls i med namnet på den part som leverantörskontot är kopplat till och detta kan inte ändras.</span><span class="sxs-lookup"><span data-stu-id="98f16-115">The **Name** field is populated with the name of the party that the vendor account is associated with, and this cannot be changed.</span></span>

<span data-ttu-id="98f16-116">[![lagerägare](./media/inventory-owners.png)](./media/inventory-owners.png)</span><span class="sxs-lookup"><span data-stu-id="98f16-116">[![inventory-owners](./media/inventory-owners.png)](./media/inventory-owners.png)</span></span>

## <a name="tracking-dimension-group"></a><span data-ttu-id="98f16-117">Spårningsdimensionsgrupp</span><span class="sxs-lookup"><span data-stu-id="98f16-117">Tracking dimension group</span></span>
<span data-ttu-id="98f16-118">Artiklar som ska användas i försändelseprocesser, måste associeras med en **Spårningsdimensionsgrupp** där dimensionen **Ägare** är inställd på **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="98f16-118">Items that are going to be used in consignment processes must be associated with a **Tracking dimension group** where the **Owner** dimension is set to **Active**.</span></span> <span data-ttu-id="98f16-119">Dimensionen Ägare har alltid alternativen **Fysiskt lager** och **Ekonomiskt lager** markerade.</span><span class="sxs-lookup"><span data-stu-id="98f16-119">The Owner dimension always has the **Physical inventory** and **Financial inventory** options selected.</span></span> <span data-ttu-id="98f16-120">**Disponera per dimension** markeras aldrig.</span><span class="sxs-lookup"><span data-stu-id="98f16-120">The **Coverage plan by dimension** is never selected.</span></span>

<span data-ttu-id="98f16-121">[![spårningsdimensionsgrupp](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)</span><span class="sxs-lookup"><span data-stu-id="98f16-121">[![tracking-dimension-group](./media/tracking-dimension-group.png)](./media/tracking-dimension-group.png)</span></span>

## <a name="inventory-ownership-change-journal"></a><span data-ttu-id="98f16-122">Journal för lagerägarskapsändring</span><span class="sxs-lookup"><span data-stu-id="98f16-122">Inventory ownership change journal</span></span>
<span data-ttu-id="98f16-123">Journalen **Lagerägarskapsändring**används till att bokföra överföringen av ägandeskap av försändelselager från leverantören till den nuvarande juridisk person som förbrukar den.</span><span class="sxs-lookup"><span data-stu-id="98f16-123">The **Inventory ownership change** journal is used to record the transfer of ownership of consignment inventory from the vendor to the legal entity that’s consuming it.</span></span> <span data-ttu-id="98f16-124">Till skillnad från lagerjournal måste den identifieras med ett Lagerjournalnamn.</span><span class="sxs-lookup"><span data-stu-id="98f16-124">Like any inventory journal, it must be identified with an Inventory journal name.</span></span> <span data-ttu-id="98f16-125">Dessa namn skapas på sidan **Lagerjournalnamn** och **Journaltyp** måste ställas in på **Ägarskapsändring**.</span><span class="sxs-lookup"><span data-stu-id="98f16-125">These names are created on the **Inventory journal names** page, and the **Journal type** must be set to **Ownership change**.</span></span>

<span data-ttu-id="98f16-126">[![journal-för-lagerägarskapsändring](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)</span><span class="sxs-lookup"><span data-stu-id="98f16-126">[![inventory-ownership-change-journal](./media/inventory-ownership-change-journal.png)](./media/inventory-ownership-change-journal.png)</span></span>

## <a name="vendor-collaboration-in-consignment-processes"></a><span data-ttu-id="98f16-127">Leverantörssamarbete i försändelseprocesser</span><span class="sxs-lookup"><span data-stu-id="98f16-127">Vendor collaboration in consignment processes</span></span>
<span data-ttu-id="98f16-128">Om dina leverantörer använder leverantörsamarbetesgränssnittet, kan du använda det för att övervaka förbrukningen av lager på din site.</span><span class="sxs-lookup"><span data-stu-id="98f16-128">If your vendors are using the vendor collaboration interface, they can use this to monitor the consumption of inventory at your site.</span></span> <span data-ttu-id="98f16-129">Mer information finns i [Konfigurering av säkerhet för leverantörssamarbetesanvändare](../procurement/configure-security-vendor-portal-users.md).</span><span class="sxs-lookup"><span data-stu-id="98f16-129">For more information about setting up vendors to use vendor collaboration, see [Configuration of security for vendor collaboration users](../procurement/configure-security-vendor-portal-users.md).</span></span>

