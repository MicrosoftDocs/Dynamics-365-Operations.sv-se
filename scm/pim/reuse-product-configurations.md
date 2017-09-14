---
title: "Återanvända produktkonfigurationer"
description: "Du kan ange att du automatiskt vill återanvända en befintlig konfiguration för en produkt. När en användare sedan har slutfört en konfigurationssession, kontrollerar systemet om en konfiguration som matchar användarens val redan finns. Om en matchande konfiguration hittas, kommer konfigurationens ID, motsvarande strukturlista och flöde att återanvändas."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 201813
ms.assetid: 4985e308-7824-41fc-83fd-fd0bdae888e3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6dd2aa1ebc713287120106a9d1ec7dc15c24def9
ms.openlocfilehash: b4d61c869577a3e18d1ac951f32dae286937a51c
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2017

---

# <a name="reuse-product-configurations"></a><span data-ttu-id="cac1e-105">Återanvända produktkonfigurationer</span><span class="sxs-lookup"><span data-stu-id="cac1e-105">Reuse product configurations</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="cac1e-106">Du kan ange att du automatiskt vill återanvända en befintlig konfiguration för en produkt.</span><span class="sxs-lookup"><span data-stu-id="cac1e-106">You can specify that you want to automatically reuse an existing configuration for a product.</span></span> <span data-ttu-id="cac1e-107">När en användare sedan har slutfört en konfigurationssession, kontrollerar systemet om en konfiguration som matchar användarens val redan finns.</span><span class="sxs-lookup"><span data-stu-id="cac1e-107">Then, when a user has completed a configuration session, the system verifies whether a configuration that matches the user’s selections already exists.</span></span> <span data-ttu-id="cac1e-108">Om en matchande konfiguration hittas, kommer konfigurationens ID, motsvarande strukturlista och flöde att återanvändas.</span><span class="sxs-lookup"><span data-stu-id="cac1e-108">If a matching configuration is found, the configuration ID, corresponding bill of materials (BOM), and route are reused.</span></span>

<a name="requirements-for-reusing-configurations"></a><span data-ttu-id="cac1e-109">Krav på att återanvända konfigurationer</span><span class="sxs-lookup"><span data-stu-id="cac1e-109">Requirements for reusing configurations</span></span>
---------------------------------------

<span data-ttu-id="cac1e-110">Om du vill aktivera konfigurationer som ska återanvändas, måste du ange följande information för komponenter och attribut på sidan **Information om produktkonfigurationsmodell**:</span><span class="sxs-lookup"><span data-stu-id="cac1e-110">To enable configurations to be reused, you must specify the following information for the components and attributes on the **Product configuration model details** page:</span></span>

-   <span data-ttu-id="cac1e-111">**Komponenter och delkomponenter** – På snabbfliken **Allmänt** i fältet **Återanvänd konfigurationer** väljer du **Ja**.</span><span class="sxs-lookup"><span data-stu-id="cac1e-111">**Components and subcomponents** – On the **General** FastTab, in the **Reuse configurations** field, select **Yes**.</span></span>
-   <span data-ttu-id="cac1e-112">**Attribut** – På snabbfliken **Attribut** väljer du alternativet **Inkludera i återanvändning**.</span><span class="sxs-lookup"><span data-stu-id="cac1e-112">**Attributes** – On the **Attributes** FastTab, select the **Include in reuse** option.</span></span> <span data-ttu-id="cac1e-113">Detta alternativ visas endast om den relaterade komponenten aktiveras för återanvändning.</span><span class="sxs-lookup"><span data-stu-id="cac1e-113">This option appears only when the related component is enabled for reuse.</span></span> <span data-ttu-id="cac1e-114">Om du inte väljer några attribut för återanvändning kommer komfigurationen alltid att återanvändas, oavsett användarens val under en konfigurationssession.</span><span class="sxs-lookup"><span data-stu-id="cac1e-114">If you don't select any attributes for reuse, the configuration is always reused, regardless of the user’s selections during a configuration session.</span></span> <span data-ttu-id="cac1e-115">Attributvärdena i den befintliga konfigurationen måste matcha användarens val.</span><span class="sxs-lookup"><span data-stu-id="cac1e-115">The attribute values in the existing configuration must match the user’s selections.</span></span> <span data-ttu-id="cac1e-116">Om användaren till exempel väljer **blå** som färg under en konfigurationssession, kontrollerar systemet om en befintlig konfiguration av komponenten har färgen blå.</span><span class="sxs-lookup"><span data-stu-id="cac1e-116">For example, if the user selects **Blue** as the color during a configuration session, the system verifies whether an existing configuration of the component has the color blue.</span></span>

## <a name="resetting-configuration-reuse"></a><span data-ttu-id="cac1e-117">Återställa konfigurationsåteranvändning</span><span class="sxs-lookup"><span data-stu-id="cac1e-117">Resetting configuration reuse</span></span>
<span data-ttu-id="cac1e-118">Tidigare skapade konfigurationer beaktas inte längre när du återställer återanvändningen av konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="cac1e-118">When you reset configuration reuse, previously created configurations are no longer considered.</span></span> <span data-ttu-id="cac1e-119">Du kanske vill återställa återanvändningen av konfigurationen om strukturlistan eller flödet har ändrats, men inga relaterade attribut ändrades.</span><span class="sxs-lookup"><span data-stu-id="cac1e-119">You might want to reset configuration reuse if the BOM or route was changed, but no related attributes were changed.</span></span> <span data-ttu-id="cac1e-120">Du återställer konfigurationen för komponenten på snabbfliken **Allmänt**.</span><span class="sxs-lookup"><span data-stu-id="cac1e-120">You reset configuration reuse on the **General** FastTab for the component.</span></span>




