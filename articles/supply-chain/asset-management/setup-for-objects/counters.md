---
title: Tillgångsmått
description: Det här avsnittet beskriver hur du skapar tillgångsmåttyper i tillgångshantering.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetObjectCounterPart, EntAssetObjectCounterLookup, EntAssetCounterType, EntAssetObjectCounterTotals
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e119eee82b1438dd8c3ccbaf2d54962b59fe6ae3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808410"
---
# <a name="counters"></a><span data-ttu-id="ebee7-103">Räknare</span><span class="sxs-lookup"><span data-stu-id="ebee7-103">Counters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ebee7-104">Det här avsnittet beskriver hur du skapar räknartyper i tillgångshantering.</span><span class="sxs-lookup"><span data-stu-id="ebee7-104">The topic explains how to create counter types in Asset Management.</span></span> <span data-ttu-id="ebee7-105">Räknartyper används för att göra räknarregistreringar på tillgångar, till exempel om antalet produktionstimmar eller kvantiteten som produceras på tillgången.</span><span class="sxs-lookup"><span data-stu-id="ebee7-105">Counter types are used to make counter registrations on assets, for example, regarding number of production hours, or quantity produced on the asset.</span></span> <span data-ttu-id="ebee7-106">tillgångstyper är relaterade till räknartyperna.</span><span class="sxs-lookup"><span data-stu-id="ebee7-106">Asset types are related to the counter types.</span></span> <span data-ttu-id="ebee7-107">Det innebär att en räknare endast kan användas på en tillgång om räknaren ställs in på den tillgångstyp som används på tillgången.</span><span class="sxs-lookup"><span data-stu-id="ebee7-107">This means that a counter can only be used on an asset if the counter is set up on the asset type used on the asset.</span></span>

<span data-ttu-id="ebee7-108">Innan du kan göra räknarregistreringar på tillgångar skapar du först de räknartyper som du vill använda i **räknare**.</span><span class="sxs-lookup"><span data-stu-id="ebee7-108">Before you can make counter registrations on assets, you first create the counter types you want to use in **Counters**.</span></span> <span data-ttu-id="ebee7-109">Därefter kan du skapa räknarregistreringar för tillgångar i **räknare**.</span><span class="sxs-lookup"><span data-stu-id="ebee7-109">Next, you can create counter registrations on assets in **Counters**.</span></span> 

<span data-ttu-id="ebee7-110">Räknare kan användas i underhållsplaner.</span><span class="sxs-lookup"><span data-stu-id="ebee7-110">Counters can be used on maintenance plans.</span></span> <span data-ttu-id="ebee7-111">En underhållsplanrad kan vara av typen "räknare", till exempel när det gäller antalet produktionstimmar eller producerade kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="ebee7-111">A maintenance plan line can be of type "Counter", for example, relating to number of production hours or quantity produced.</span></span> 

<span data-ttu-id="ebee7-112">En räknarregistrering kan uppdateras manuellt eller automatiskt baserat på produktionstimmar eller producerad kvantitet.</span><span class="sxs-lookup"><span data-stu-id="ebee7-112">A counter registration can be updated manually or automatically based on production hours or quantity produced.</span></span> <span data-ttu-id="ebee7-113">En räknare kan ställas in för att använda en av tre uppdateringsmetoder (vald i fältet **uppdatera** i **räknare**):</span><span class="sxs-lookup"><span data-stu-id="ebee7-113">A counter can be set up to use one of three update methods (selected in the **Update** field in **Counters**):</span></span>
  
- <span data-ttu-id="ebee7-114">Manuell - du måste registrera värden för räknare manuellt.</span><span class="sxs-lookup"><span data-stu-id="ebee7-114">Manual - you must manually register counter values.</span></span>  
- <span data-ttu-id="ebee7-115">Produktionstimmar - räknaren uppdateras automatiskt baserat på antalet produktionstimmar.</span><span class="sxs-lookup"><span data-stu-id="ebee7-115">Production hours - the counter is automatically updated based on number of production hours.</span></span>  
- <span data-ttu-id="ebee7-116">Produktionskvantitet - räknaren uppdateras automatiskt baserat på antalet producerad kvantitet.</span><span class="sxs-lookup"><span data-stu-id="ebee7-116">Production quantity - the counter is automatically updated based on number of quantity produced.</span></span>  

>[!NOTE]
><span data-ttu-id="ebee7-117">Om den producerade kvantiteten används inkluderas *alla* registrerade artiklar i räknarregistreringen, god kvantitet samt felkvantitet.</span><span class="sxs-lookup"><span data-stu-id="ebee7-117">If quantity produced is used, *all* registered items are included in the counter registration, good quantity as well as error quantity.</span></span> <span data-ttu-id="ebee7-118">Det är alltid möjligt att göra manuella räknarregistreringar, om det behövs.</span><span class="sxs-lookup"><span data-stu-id="ebee7-118">It is always possible to make manual counter registrations, if required.</span></span>

## <a name="create-counter-types-for-asset-counter-registrations"></a><span data-ttu-id="ebee7-119">Skapa räknartyper för tillgångsräknarregistreringar</span><span class="sxs-lookup"><span data-stu-id="ebee7-119">Create counter types for asset counter registrations</span></span>

1. <span data-ttu-id="ebee7-120">Välj **tillgångshantering** > **inställningar** > **tillgångstyper** > **räknare**.</span><span class="sxs-lookup"><span data-stu-id="ebee7-120">Select **Asset management** > **Setup** > **Asset types** > **Counters**.</span></span>
2. <span data-ttu-id="ebee7-121">Skapa en ny räknartyp genom att välja **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="ebee7-121">Select **New** to create a new counter type.</span></span>
3. <span data-ttu-id="ebee7-122">Infoga ett ID i fältet **räknare** och ett räknarnamn i fältet **namn**.</span><span class="sxs-lookup"><span data-stu-id="ebee7-122">Insert an ID in the **Counter** field, and a counter name in the **Name** field.</span></span>
4. <span data-ttu-id="ebee7-123">På snabbfliken **Allmänt** väljer du räknarenhet i fältet **enhet**.</span><span class="sxs-lookup"><span data-stu-id="ebee7-123">On the **General** FastTab, select a counter unit in the **Unit** field.</span></span>
5. <span data-ttu-id="ebee7-124">I fältet **uppdatera** väljer du den uppdateringsmetod som ska användas för räknare.</span><span class="sxs-lookup"><span data-stu-id="ebee7-124">In the **Update** field, select the update method to be used for the counter.</span></span>
6. <span data-ttu-id="ebee7-125">Välj "Ja" på växlingsknappen **Ärva räknarvärden** om underordnade tillgångar i en tillgångsstruktur automatiskt ska ärva räknarregistreringar som gjorts på den överordnade tillgången.</span><span class="sxs-lookup"><span data-stu-id="ebee7-125">Select "Yes" on the **Inherit counter values** toggle button if child assets in an asset structure should automatically inherit counter registrations made on the parent asset.</span></span>
7. <span data-ttu-id="ebee7-126">I fältet **total sammanlagd** väljer du den summeringsmetod som ska användas för en räknare med den här räknartypen.</span><span class="sxs-lookup"><span data-stu-id="ebee7-126">In the **Total aggregate** field, select the summation method to be used for a counter using this counter type.</span></span> <span data-ttu-id="ebee7-127">"Summa" är det standardval som används för att kontinuerligt lägga till registrerade värden till det totala värdet.</span><span class="sxs-lookup"><span data-stu-id="ebee7-127">"Sum" is the standard selection used to continuously add registered values to the total value.</span></span> <span data-ttu-id="ebee7-128">"Genomsnitt" kan användas om en räknare har ställts in för att övervaka ett tröskelvärde, till exempel när det gäller temperatur, vibrationer eller slitage på en tillgång.</span><span class="sxs-lookup"><span data-stu-id="ebee7-128">"Average" can be used if a counter is set up to monitor a threshold, for example, regarding temperature, vibrations, or wear and tear on an asset.</span></span> 
8. <span data-ttu-id="ebee7-129">I fältet **avvikelse över** infogar du den övre nivån i procent för validering om manuella räknarregistreringar ligger inom ett förväntat intervall.</span><span class="sxs-lookup"><span data-stu-id="ebee7-129">In the **Deviation over** field, insert the upper level in percent for validating if manual counter registrations are within an expected range.</span></span> <span data-ttu-id="ebee7-130">Valideringen baseras på en linjär ökning av befintliga räknarregistreringar.</span><span class="sxs-lookup"><span data-stu-id="ebee7-130">The validation is based on a linear increase in existing counter registrations.</span></span>
9. <span data-ttu-id="ebee7-131">I fältet **avvikelse under** infogar du den nedre nivån i procent för validering om manuella räknarregistreringar ligger inom ett förväntat intervall.</span><span class="sxs-lookup"><span data-stu-id="ebee7-131">In the **Deviation under** field, insert the lower level in percent for validating if manual counter registrations are within an expected range.</span></span> <span data-ttu-id="ebee7-132">Valideringen baseras på en linjär minska av befintliga räknarregistreringar.</span><span class="sxs-lookup"><span data-stu-id="ebee7-132">The validation is based on a linear decrease in existing counter registrations.</span></span>
10. <span data-ttu-id="ebee7-133">I fältet **typ** väljer du den typ av meddelande (information, varning, fel) som ska visas om avvikelser utanför det definierade intervallet inträffar när du gör manuella räknarregistreringar.</span><span class="sxs-lookup"><span data-stu-id="ebee7-133">In the **Type** field, select the type of message (information, warning, error) to be shown if deviations outside the defined range occur when you make manual counter registrations.</span></span>
11. <span data-ttu-id="ebee7-134">På snabbfliken **tillgångstyper** lägger du till de tillgångstyper som ska kunna använda räknare.</span><span class="sxs-lookup"><span data-stu-id="ebee7-134">On the **Asset types** FastTab, add the asset types that should be able to use the counter.</span></span>
12. <span data-ttu-id="ebee7-135">På snabbfliken **relaterade tillgångsräknare** lägger du till de räknare som du vill ska uppdateras automatiskt när den här räknaren uppdateras.</span><span class="sxs-lookup"><span data-stu-id="ebee7-135">On the **Related asset counters** FastTab, add the counter that you want to be automatically updated when this counter is updated.</span></span>


>[!NOTE]
><span data-ttu-id="ebee7-136">En relaterad räknare uppdateras automatiskt endast om den relaterade räknaren har tillgångstypen, till vilken den är relaterad, i inställningarna för räknare.</span><span class="sxs-lookup"><span data-stu-id="ebee7-136">A related counter is automatically updated only if the related counter has the asset type, to which it is related, in the counter setup.</span></span> <span data-ttu-id="ebee7-137">Exempel: du ställer in en räknare för "produktionstimmar" och lägger till tillgångstypen "lastbilsmotor".</span><span class="sxs-lookup"><span data-stu-id="ebee7-137">For example: You set up a counter for "Production hours" and add the asset type "Truck Engine".</span></span> <span data-ttu-id="ebee7-138">När den räknaren uppdateras kommer även en relaterad räknare "olja" att uppdateras med samma värden för räknare.</span><span class="sxs-lookup"><span data-stu-id="ebee7-138">When that counter is updated, a related counter "Oil" is also updated with the same counter values.</span></span> <span data-ttu-id="ebee7-139">Inställningen i **räknare** innehåller inställningarna på "timmar".</span><span class="sxs-lookup"><span data-stu-id="ebee7-139">The setup in **Counters** includes the setup on "Hours".</span></span> <span data-ttu-id="ebee7-140">På räknaren "Olja" bör "lastbilsmotor" läggas till på snabbfliken **tillgångstyper** för att säkerställa räknarrelationen.</span><span class="sxs-lookup"><span data-stu-id="ebee7-140">Also, on the "Oil" counter, the asset type "Truck Engine" should be added to the **Asset types** FastTab to ensure the counter relation.</span></span> <span data-ttu-id="ebee7-141">Se skärmdumparna nedan för ett exempel på inställningen på räknarna timmar och olja.</span><span class="sxs-lookup"><span data-stu-id="ebee7-141">See the screenshots below for an example of the setup on the Hours and Oil counters.</span></span>

<span data-ttu-id="ebee7-142">När tillgångstyper läggs till en räknartyp i **räknare**, läggs den räknaren automatiskt till tillgångstyperna på snabbfliken **räknare** i [tillgångstyper](../setup-for-objects/object-types.md).</span><span class="sxs-lookup"><span data-stu-id="ebee7-142">When asset types are added to a counter type in **Counters**, that counter is automatically added to the asset types on the **Counters** FastTab in [Asset types](../setup-for-objects/object-types.md).</span></span>

![Figur 1](media/071-setup-for-objects.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]