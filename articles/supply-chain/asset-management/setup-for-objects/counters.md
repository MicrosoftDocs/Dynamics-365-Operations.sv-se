---
title: Tillgångsmått
description: Det här avsnittet beskriver hur du skapar tillgångsmåttyper i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d9c445832a649c4f6a6642036ecab325e8aa2079
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783609"
---
# <a name="asset-measures"></a><span data-ttu-id="002d9-103">Tillgångsmått</span><span class="sxs-lookup"><span data-stu-id="002d9-103">Asset measures</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="002d9-104">Det här avsnittet beskriver hur du skapar tillgångsmåttyper i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="002d9-104">The topic explains how to create asset measure types in Asset Management.</span></span> <span data-ttu-id="002d9-105">tillgångsmåttyper används för att göra mätningsregistreringar på tillgångar, till exempel om antalet produktionstimmar eller kvantiteten som produceras på tillgången.</span><span class="sxs-lookup"><span data-stu-id="002d9-105">Asset measure types are used to make measurement registrations on assets, for example, regarding number of production hours, or quantity produced on the asset.</span></span> <span data-ttu-id="002d9-106">tillgångstyper är relaterade till tillgångsmåttyperna.</span><span class="sxs-lookup"><span data-stu-id="002d9-106">Asset types are related to the asset measure types.</span></span> <span data-ttu-id="002d9-107">Det innebär att ett tillgångsmått endast kan användas på en tillgång om tillgångsmåttet ställs in på den tillgångstyp som används på tillgången.</span><span class="sxs-lookup"><span data-stu-id="002d9-107">This means that an asset measure can only be used on an asset if the asset measure is set up on the asset type used on the asset.</span></span>

<span data-ttu-id="002d9-108">Innan du kan göra mätningsregistreringar på tillgångar skapar du först de tillgångsmått typer som du vill använda i **räknare**.</span><span class="sxs-lookup"><span data-stu-id="002d9-108">Before you can make measurement registrations on assets, you first create the asset measure types you want to use in **Counters**.</span></span> <span data-ttu-id="002d9-109">Därefter kan du skapa mätningsregistreringar för tillgångar i **tillgångsmått**.</span><span class="sxs-lookup"><span data-stu-id="002d9-109">Next, you can create measurement registrations on assets in **Asset measures**.</span></span> 

<span data-ttu-id="002d9-110">Tillgångsmått kan användas i underhållsplaner.</span><span class="sxs-lookup"><span data-stu-id="002d9-110">Asset measures can be used on maintenance plans.</span></span> <span data-ttu-id="002d9-111">En underhållsplanrad kan vara av typen "räknare", till exempel när det gäller antalet produktionstimmar eller producerade kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="002d9-111">A maintenance plan line can be of type "Counter", for example, relating to number of production hours or quantity produced.</span></span> 

<span data-ttu-id="002d9-112">En tillgångsmätningsregistrering kan uppdateras manuellt eller automatiskt baserat på produktionstimmar eller producerad kvantitet.</span><span class="sxs-lookup"><span data-stu-id="002d9-112">An asset measurement registration can be updated manually or automatically based on production hours or quantity produced.</span></span> <span data-ttu-id="002d9-113">Ett tillgångsmått kan ställas in för att använda en av tre uppdateringsmetoder (vald i fältet **uppdatera** i **räknare**):</span><span class="sxs-lookup"><span data-stu-id="002d9-113">An asset measure can be set up to use one of three update methods (selected in the **Update** field in **Counters**):</span></span>
  
- <span data-ttu-id="002d9-114">Manuell - du måste registrera värden för tillgångsmått manuellt.</span><span class="sxs-lookup"><span data-stu-id="002d9-114">Manual - you must manually register asset measurement values.</span></span>  
- <span data-ttu-id="002d9-115">Produktionstimmar - räknaren uppdateras automatiskt baserat på antalet produktionstimmar.</span><span class="sxs-lookup"><span data-stu-id="002d9-115">Production hours - the counter is automatically updated based on number of production hours.</span></span>  
- <span data-ttu-id="002d9-116">Produktionskvantitet - räknaren uppdateras automatiskt baserat på antalet producerad kvantitet.</span><span class="sxs-lookup"><span data-stu-id="002d9-116">Production quantity - the counter is automatically updated based on number of quantity produced.</span></span>  

>[!NOTE]
><span data-ttu-id="002d9-117">Om den producerade kvantiteten används inkluderas *alla* registrerade artiklar i mätningsregistreringen, god kvantitet samt felkvantitet.</span><span class="sxs-lookup"><span data-stu-id="002d9-117">If quantity produced is used, *all* registered items are included in the measurement registration, good quantity as well as error quantity.</span></span> <span data-ttu-id="002d9-118">Det är alltid möjligt att göra manuella tillgångsmätningsregistreringar, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="002d9-118">It is always possible to make manual asset measurement registrations, if required.</span></span>

## <a name="create-counter-types-for-asset-counter-registrations"></a><span data-ttu-id="002d9-119">Skapa räknartyper för tillgångsräknarregistreringar</span><span class="sxs-lookup"><span data-stu-id="002d9-119">Create counter types for asset counter registrations</span></span>

1. <span data-ttu-id="002d9-120">Välj **tillgångshantering** > **inställningar** > **tillgångstyper** > **räknare**.</span><span class="sxs-lookup"><span data-stu-id="002d9-120">Select **Asset management** > **Setup** > **Asset types** > **Counters**.</span></span>
2. <span data-ttu-id="002d9-121">Skapa en ny tillgångsmåttyp genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="002d9-121">Select **New** to create a new asset measure type.</span></span>
3. <span data-ttu-id="002d9-122">Infoga ett ID i fältet **räknare** och ett räknarnamn i fältet **namn**.</span><span class="sxs-lookup"><span data-stu-id="002d9-122">Insert an ID in the **Counter** field, and a counter name in the **Name** field.</span></span>
4. <span data-ttu-id="002d9-123">På snabbfliken **Allmänt** väljer du måttenhet i fältet **enhet**.</span><span class="sxs-lookup"><span data-stu-id="002d9-123">On the **General** FastTab, select a measurement unit in the **Unit** field.</span></span>
5. <span data-ttu-id="002d9-124">I fältet **uppdatera** väljer du den uppdateringsmetod som ska användas för tillgångsmåttet.</span><span class="sxs-lookup"><span data-stu-id="002d9-124">In the **Update** field, select the update method to be used for the asset measure.</span></span>
6. <span data-ttu-id="002d9-125">Välj "Ja" på växlingsknappen **Ärva räknarvärden** om underordnade tillgångar i en tillgångsstruktur automatiskt ska ärva tillgångsmåttregistreringar som gjorts på den överordnade tillgången.</span><span class="sxs-lookup"><span data-stu-id="002d9-125">Select "Yes" on the **Inherit counter values** toggle button if child assets in an asset structure should automatically inherit asset measure registrations made on the parent asset.</span></span>
7. <span data-ttu-id="002d9-126">I fältet **total sammanlagd** väljer du den summeringsmetod som ska användas för en tillgångsmått med den här tillgångsmåttypen.</span><span class="sxs-lookup"><span data-stu-id="002d9-126">In the **Total aggregate** field, select the summation method to be used for an asset measure using this asset measure type.</span></span> <span data-ttu-id="002d9-127">"Summa" är det standardval som används för att kontinuerligt lägga till registrerade värden till det totala värdet.</span><span class="sxs-lookup"><span data-stu-id="002d9-127">"Sum" is the standard selection used to continuously add registered values to the total value.</span></span> <span data-ttu-id="002d9-128">"Genomsnitt" kan användas om ett tillgångsmått har ställts in för att övervaka ett tröskelvärde, till exempel när det gäller temperatur, vibrationer eller slitage på en tillgång.</span><span class="sxs-lookup"><span data-stu-id="002d9-128">"Average" can be used if an asset measure is set up to monitor a threshold, for example, regarding temperature, vibrations, or wear and tear on an asset.</span></span> 
8. <span data-ttu-id="002d9-129">I fältet **avvikelse över** infogar du den övre nivån i procent för validering om manuella tillgångsmåttregistreringar ligger inom ett förväntat intervall.</span><span class="sxs-lookup"><span data-stu-id="002d9-129">In the **Deviation over** field, insert the upper level in percent for validating if manual asset measure registrations are within an expected range.</span></span> <span data-ttu-id="002d9-130">Valideringen baseras på en linjär ökning av befintliga tillgångsmåttregistreringar.</span><span class="sxs-lookup"><span data-stu-id="002d9-130">The validation is based on a linear increase in existing asset measure registrations.</span></span>
9. <span data-ttu-id="002d9-131">I fältet **avvikelse under** infogar du den nedre nivån i procent för validering om manuella tillgångsmåttregistreringar ligger inom ett förväntat intervall.</span><span class="sxs-lookup"><span data-stu-id="002d9-131">In the **Deviation under** field, insert the lower level in percent for validating if manual asset measure registrations are within an expected range.</span></span> <span data-ttu-id="002d9-132">Valideringen baseras på en linjär minskning av befintliga tillgångsmåttregistreringar.</span><span class="sxs-lookup"><span data-stu-id="002d9-132">The validation is based on a linear decrease in existing asset measure registrations.</span></span>
10. <span data-ttu-id="002d9-133">I fältet **typ** väljer du den typ av meddelande (information, varning, fel) som ska visas om avvikelser utanför det definierade intervallet inträffar när du gör manuella tillgångsmåttregistreringar.</span><span class="sxs-lookup"><span data-stu-id="002d9-133">In the **Type** field, select the type of message (information, warning, error) to be shown if deviations outside the defined range occur when you make manual asset measure registrations.</span></span>
11. <span data-ttu-id="002d9-134">På snabbfliken **tillgångstyper** lägger du till de tillgångstyper som ska kunna använda tillgångsmåttet.</span><span class="sxs-lookup"><span data-stu-id="002d9-134">On the **Asset types** FastTab, add the asset types that should be able to use the asset measure.</span></span>
12. <span data-ttu-id="002d9-135">På snabbfliken **relaterade tillgångsmått** lägger du till de tillgångsmått som du vill ska uppdateras automatiskt när den här tillgångsmåtten uppdateras.</span><span class="sxs-lookup"><span data-stu-id="002d9-135">On the **Related asset measures** FastTab, add the asset measures that you want to be automatically updated when this asset measure is updated.</span></span>


>[!NOTE]
><span data-ttu-id="002d9-136">Ett relaterat tillgångsmått uppdateras automatiskt endast om det relaterade tillgångsmåttet har tillgångstypen, till vilken den är relaterad, i inställningarna för tillgångsmått.</span><span class="sxs-lookup"><span data-stu-id="002d9-136">A related asset measure is automatically updated only if the related asset measure has the asset type, to which it is related, in the asset measure setup.</span></span> <span data-ttu-id="002d9-137">Exempel: du ställer in ett tillgångsmått för "produktionstimmar" och lägger till tillgångstypen "lastbilsmotor".</span><span class="sxs-lookup"><span data-stu-id="002d9-137">For example: You set up an asset measure for "Production hours" and add the asset type "Truck Engine".</span></span> <span data-ttu-id="002d9-138">När det tillgångsmåttet uppdateras kommer även en relaterad räknare "olja" att uppdateras med samma värden för tillgångsmått.</span><span class="sxs-lookup"><span data-stu-id="002d9-138">When that asset measure is updated, a related counter "Oil" is also updated with the same asset measure values.</span></span> <span data-ttu-id="002d9-139">Inställningen i **räknare** innehåller inställningarna på "timmar".</span><span class="sxs-lookup"><span data-stu-id="002d9-139">The setup in **Counters** includes the setup on "Hours".</span></span> <span data-ttu-id="002d9-140">På tillgångsmåttet "Oil" bör tillgångstypen "lastbilsmotor" läggas till på snabbfliken **tillgångstyper** för att säkerställa att tillgångsmåttrelationen.</span><span class="sxs-lookup"><span data-stu-id="002d9-140">Also, on the "Oil" asset measure, the asset type "Truck Engine" should be added to the **Asset types** FastTab to ensure the asset measure relation.</span></span> <span data-ttu-id="002d9-141">Se skärmdumparna nedan för ett exempel på inställningen på tillgångsmåtten timmar och olja.</span><span class="sxs-lookup"><span data-stu-id="002d9-141">See the screenshots below for an example of the setup on the Hours and Oil asset measures.</span></span>

<span data-ttu-id="002d9-142">När tillgångstyper läggs till en tillgångsmåtttyp i **räknare**, läggs det tillgångsmåttet automatiskt till tillgångstyperna på snabbfliken **räknare** i [tillgångstyper](../setup-for-objects/object-types.md).</span><span class="sxs-lookup"><span data-stu-id="002d9-142">When asset types are added to an asset measure type in **Counters**, that asset measure is automatically added to the asset types on the **Counters** FastTab in [Asset types](../setup-for-objects/object-types.md).</span></span>

![Figur 1](media/071-setup-for-objects.png)


