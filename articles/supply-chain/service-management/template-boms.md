---
title: Strukturlistemallar
description: En mallstrukturlista ger dig en standardiserad lista över vilka komponenter i serviceobjekt som regelbundet servas.
author: ShylaThompson
manager: tfehr
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01cd4cf03fb0ac1a3399673097895513f7180cf1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965790"
---
# <a name="template-boms"></a><span data-ttu-id="2037f-103">Strukturlistemallar</span><span class="sxs-lookup"><span data-stu-id="2037f-103">Template BOMs</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="2037f-104">En mallstrukturlista ger dig en standardiserad lista över vilka komponenter i serviceobjekt som regelbundet servas.</span><span class="sxs-lookup"><span data-stu-id="2037f-104">A template bill of materials (BOM) provides you with a standardized list of components for service objects that are serviced regularly.</span></span> <span data-ttu-id="2037f-105">Komponenterna i mallstrukturlistan representerar de enskilda delkomponenterna i serviceobjektet.</span><span class="sxs-lookup"><span data-stu-id="2037f-105">The components that are listed in the template BOM represent the individual subcomponents of the service object.</span></span> <span data-ttu-id="2037f-106">När du använder en mallstrukturlista på ett serviceobjekt håller du med hjälp av en servicestrukturlista reda på vilka reservdelar som har ersatts i serviceobjektet.</span><span class="sxs-lookup"><span data-stu-id="2037f-106">By applying a template BOM to a service object, you can keep a record of the subcomponents that have been replaced on the service object.</span></span>

<span data-ttu-id="2037f-107">Om du vill använda en mallstrukturlista på ett serviceavtal eller en serviceorder kopplar du den till en serviceobjektrelation.</span><span class="sxs-lookup"><span data-stu-id="2037f-107">To apply a template BOM to a service agreement or a service order, you attach it to a service object relation.</span></span>


> [!NOTE]
> <P><span data-ttu-id="2037f-108">Du kan endast koppla en mallstrukturlista till varje serviceobjekt.</span><span class="sxs-lookup"><span data-stu-id="2037f-108">You can apply only one template BOM to a service object.</span></span></P>

## <a name="create-a-template-bom"></a><span data-ttu-id="2037f-109">Skapa en strukturlistemall</span><span class="sxs-lookup"><span data-stu-id="2037f-109">Create a template BOM</span></span>

<span data-ttu-id="2037f-110">Tabellen nedan innehåller information om de olika metoder som du kan använda för att skapa en mallstrukturlista.</span><span class="sxs-lookup"><span data-stu-id="2037f-110">The following table contains information about the various methods that you can use to create a template BOM.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="2037f-111">Metod</span><span class="sxs-lookup"><span data-stu-id="2037f-111">Method</span></span></p></th>
<th><p><span data-ttu-id="2037f-112">beskrivning</span><span class="sxs-lookup"><span data-stu-id="2037f-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2037f-113">Produktion</span><span class="sxs-lookup"><span data-stu-id="2037f-113">Production</span></span></p></td>
<td><p><span data-ttu-id="2037f-114"> Mallstrukturlistan baseras på en tillverkningsorder.</span><span class="sxs-lookup"><span data-stu-id="2037f-114">The template BOM is based on a production order.</span></span> <span data-ttu-id="2037f-115">Det här alternativet använder du om du arbetar i en tillverkningsmiljö.</span><span class="sxs-lookup"><span data-stu-id="2037f-115">This option is applicable only if you operate in a production environment.</span></span> <span data-ttu-id="2037f-116">Fördelen är att du har en aktuell och detaljerad lista över de komponenter som en artikel består av.</span><span class="sxs-lookup"><span data-stu-id="2037f-116">The benefit is that you have a current, detailed listing of the components that make up an item.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2037f-117">Artikel BOM</span><span class="sxs-lookup"><span data-stu-id="2037f-117">Item BOM</span></span></p></td>
<td><p><span data-ttu-id="2037f-118">Mallstrukturlistan baseras på en artikelstrukturlista</span><span class="sxs-lookup"><span data-stu-id="2037f-118">The template BOM is based on an item BOM.</span></span> <span data-ttu-id="2037f-119">Artikelstruktur, till skillnad från produktionsstrukturlistan, är en statisk lista över de komponenter som en artikel utgörs av.</span><span class="sxs-lookup"><span data-stu-id="2037f-119">The item BOM, unlike the production BOM, is a static list of the components that make up an item.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2037f-120">Befintlig mall</span><span class="sxs-lookup"><span data-stu-id="2037f-120">Existing template</span></span></p></td>
<td><p><span data-ttu-id="2037f-121">Mallen baseras på en befintlig mallstrukturlista.</span><span class="sxs-lookup"><span data-stu-id="2037f-121">The template is based on an existing template BOM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2037f-122">Manuell</span><span class="sxs-lookup"><span data-stu-id="2037f-122">Manual</span></span></p></td>
<td><p><span data-ttu-id="2037f-123">Om du vet exakt vilka reservdelar som vanligtvis måste bytas ut i serviceobjektet kanske du föredrar att skapa mallstrukturlistan manuellt.</span><span class="sxs-lookup"><span data-stu-id="2037f-123">If you know what spare parts are typically replaced on a service object, you can create your template BOM manually.</span></span> <span data-ttu-id="2037f-124">Du kan då se till att de komponenter som inkluderas i mallen avspeglar de faktiska kraven för din arbetsplats.</span><span class="sxs-lookup"><span data-stu-id="2037f-124">This method helps make sure that the components that are included in the template reflect the actual requirements of your workplace.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a><span data-ttu-id="2037f-125">Använda mallstrukturlistan för ett serviceavtal eller en serviceorder</span><span class="sxs-lookup"><span data-stu-id="2037f-125">Apply the template BOM to a service agreement or service order</span></span>

<span data-ttu-id="2037f-126">Mallstrukturlistan kan användas i ett serviceavtal och en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="2037f-126">You can apply a template BOM to a service agreement, a service order, or both.</span></span> <span data-ttu-id="2037f-127">Serviceavtalet omfattar vanligtvis en långtidsrelation med kunden.</span><span class="sxs-lookup"><span data-stu-id="2037f-127">The service agreement usually covers a long-term relationship with a customer.</span></span> <span data-ttu-id="2037f-128">Ersättningshistoriken i servicestrukturlistan är användbar information att registrera i serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="2037f-128">The history of replacements that is recorded in the service BOM is useful data to have for the service agreement.</span></span>

<span data-ttu-id="2037f-129">Du kan också använda en strukturlistemall till en serviceorder om du vill registrera historiken över den service som har utförts på ett serviceobjekt.</span><span class="sxs-lookup"><span data-stu-id="2037f-129">You can also apply a template BOM to a service order to record the history of the service that has been performed on a service object.</span></span>

## <a name="copy-the-history-of-a-service-bom"></a><span data-ttu-id="2037f-130">Kopiera historiken för en servicestrukturlista</span><span class="sxs-lookup"><span data-stu-id="2037f-130">Copy the history of a service BOM</span></span>

<span data-ttu-id="2037f-131">Du kan kopiera historiken för en servicestrukturlisterad från ett serviceavtal till ett annat serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="2037f-131">You can copy the history of a service BOM line from one service agreement to another service agreement.</span></span> <span data-ttu-id="2037f-132">Genom att kopiera servicehistoriken mellan serviceavtalen kan du bibehålla ersättningsposterna för en artikel.</span><span class="sxs-lookup"><span data-stu-id="2037f-132">By copying the service history between service agreements, you can preserve the record of replacements for an item.</span></span>

<span data-ttu-id="2037f-133">**Exempel**</span><span class="sxs-lookup"><span data-stu-id="2037f-133">**Example**</span></span>

<span data-ttu-id="2037f-134">Anta att du har ett treårigt serviceavtal för en kunds bil.</span><span class="sxs-lookup"><span data-stu-id="2037f-134">You have set up a three-year service agreement for a customer's car.</span></span> <span data-ttu-id="2037f-135">Under denna period blir kunden van vid företagets bra service som företaget erbjuder kunden.</span><span class="sxs-lookup"><span data-stu-id="2037f-135">During that period, the customer becomes accustomed to the good service that the company provides.</span></span> <span data-ttu-id="2037f-136">Därför när avtalet förfaller vill kunden sätta upp ett nytt.</span><span class="sxs-lookup"><span data-stu-id="2037f-136">Therefore, after the agreement expires, the customer wants to set up a new one.</span></span> <span data-ttu-id="2037f-137">Du kan nu förhandla fram ett mer fördelaktigt avtal för företaget.</span><span class="sxs-lookup"><span data-stu-id="2037f-137">You are now able to negotiate a more favorable agreement for the company.</span></span> <span data-ttu-id="2037f-138">Eftersom du kan ha nytta av posten för ersättningskomponenter kopierar du servicestrukturlistans historik till det nya avtalet.</span><span class="sxs-lookup"><span data-stu-id="2037f-138">Because the record of replaced components might be useful in the future, you copy the history of the service BOM to the new agreement.</span></span>

## <a name="modify-the-template-bom"></a><span data-ttu-id="2037f-139">Ändra mallstrukturlistan</span><span class="sxs-lookup"><span data-stu-id="2037f-139">Modify the template BOM</span></span>

<span data-ttu-id="2037f-140">Om mallstrukturlistan inte har kopplats till något serviceobjekt kan du ändra eller ta bort rader.</span><span class="sxs-lookup"><span data-stu-id="2037f-140">If a template BOM has not been attached to a service object, you can modify or delete lines in it.</span></span> <span data-ttu-id="2037f-141">När mallstrukturlistan har kopplats till ett serviceobjekt kan du endast ändra den lokala versionen av strukturlistan.</span><span class="sxs-lookup"><span data-stu-id="2037f-141">After the template BOM is attached to a service object, you can modify only the local version of the BOM.</span></span> <span data-ttu-id="2037f-142">Om du vill kopiera inställningen för en lokal version av en mallstrukturlista kan du skapa en ny mallstrukturlista som baseras på den lokala versionen.</span><span class="sxs-lookup"><span data-stu-id="2037f-142">If you want to duplicate the setup of a local version of a template BOM, you can create a new template BOM based on the local version.</span></span> <span data-ttu-id="2037f-143">Mer information finns i [Modifiera servicestrukturlista](modify-service-bom.md).</span><span class="sxs-lookup"><span data-stu-id="2037f-143">For more information, see [Modify a Service BOM](modify-service-bom.md).</span></span>

<span data-ttu-id="2037f-144">Om du ersätter en artikel i strukturlistan kan du registrera ersättningen på strukturlisteraden i strukturlistedesignern.</span><span class="sxs-lookup"><span data-stu-id="2037f-144">If you replace an item in the BOM, you can register the replacement on the BOM line in the BOM designer.</span></span> <span data-ttu-id="2037f-145">Alternativt kan du skapa en serviceorderrad för ersättningsobjekten.</span><span class="sxs-lookup"><span data-stu-id="2037f-145">Optionally, you can create a service order line for the replacement object.</span></span> <span data-ttu-id="2037f-146">Om en serviceorderrad skapas kan du fakturera ersättningsartikeln.</span><span class="sxs-lookup"><span data-stu-id="2037f-146">If you create a service order line, you can invoice the replacement item.</span></span> <span data-ttu-id="2037f-147">Om du inte skapar någon serviceorderrad för en ersättning sparas registreringen av ersättningen för posterna så att du kan spåra serviceobjektets historik.</span><span class="sxs-lookup"><span data-stu-id="2037f-147">If you do not create a service order line for a replacement, the replacement registration is kept to track the history of the service object.</span></span>

## <a name="change-how-information-on-the-bom-line-is-displayed"></a><span data-ttu-id="2037f-148">Ändra visningen av information på strukturlisteraden</span><span class="sxs-lookup"><span data-stu-id="2037f-148">Change how information on the BOM line is displayed</span></span>

<span data-ttu-id="2037f-149">Du kan ändra sättet på vilket information på strukturlisteraderna visas i alla mallar och servicestrukturlistor.</span><span class="sxs-lookup"><span data-stu-id="2037f-149">You can change the way that information on the BOM line is displayed for all template and service BOMs.</span></span> <span data-ttu-id="2037f-150">Ändringarna tillämpas på alla mallstrukturlistor och servicestrukturlistor.</span><span class="sxs-lookup"><span data-stu-id="2037f-150">The changes are applied to all template BOMs and service BOMs.</span></span> <span data-ttu-id="2037f-151">Inklusive de som är kopplade till ett serviceobjekt.</span><span class="sxs-lookup"><span data-stu-id="2037f-151">This includes those that are attached to service objects.</span></span>

## <a name="set-up-number-sequences-for-template-boms"></a><span data-ttu-id="2037f-152">Ställa in nummerserier för mallstrukturlistorna</span><span class="sxs-lookup"><span data-stu-id="2037f-152">Set up number sequences for template BOMs</span></span>

<span data-ttu-id="2037f-153">Du måste ställa in två nummerserier om du vill använda mallstrukturlistor.</span><span class="sxs-lookup"><span data-stu-id="2037f-153">To use template BOMs, you must set up two number sequences.</span></span> <span data-ttu-id="2037f-154">Ställ in en nummerserie för mallstrukturlista och en för radnumret i strukturlistans historik.</span><span class="sxs-lookup"><span data-stu-id="2037f-154">Set up one number sequence for the template BOM and one for the BOM history line number.</span></span>


> [!NOTE]
> <P><span data-ttu-id="2037f-155">Nummerserier används i för att fördela identifierare till poster som krävs.</span><span class="sxs-lookup"><span data-stu-id="2037f-155">Number sequences are used to allocate identifiers to records that require them.</span></span> <span data-ttu-id="2037f-156">Innan du kan tilldela en nummerserie till en mallstrukturlista eller en radnumret i strukturlistans historik, måste du ställa in nummerserier för streckkoder.</span><span class="sxs-lookup"><span data-stu-id="2037f-156">Before you can assign a number sequence to a template BOM or a BOM history line number, you must set up number sequences codes.</span></span></P>


## <a name="set-up-number-sequences"></a><span data-ttu-id="2037f-157">Ställa in nummerserier</span><span class="sxs-lookup"><span data-stu-id="2037f-157">Set up number sequences</span></span>

1.  <span data-ttu-id="2037f-158">På sidan **nummerserier**, skapat du nummerserier för mallstrukturlistor och radnumret för strukturlistans historik.</span><span class="sxs-lookup"><span data-stu-id="2037f-158">On the **Number sequences** list page, create number sequences for template BOMs and the BOM history line number.</span></span> 

2.  <span data-ttu-id="2037f-159">Klicka på **servicehantering** \> **inställningar** \> **servicehanteringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="2037f-159">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

3.  <span data-ttu-id="2037f-160">Klicka på **nummerserier**, och välj en nummerseriekod för den nummerseriereferenser som du skapat i formuläret **nummerserier**.</span><span class="sxs-lookup"><span data-stu-id="2037f-160">Click **Number sequences**, and then select a number sequence code for the number sequence references that you created in the **Number sequences** form.</span></span>

4.  <span data-ttu-id="2037f-161">Stäng formuläret så att ändringarna sparas.</span><span class="sxs-lookup"><span data-stu-id="2037f-161">Close the form to save your changes.</span></span>


> [!NOTE]
> <P><span data-ttu-id="2037f-162">Radnumret i strukturlistans historik används av systemet för att koppla transaktionerna i strukturlistans historik till ett serviceavtal eller en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="2037f-162">The BOM history line number is used by the system to associate the transactions in the BOM history with a service agreement or service order.</span></span> <span data-ttu-id="2037f-163">Numret visas inte i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="2037f-163">The number is not displayed in the user interface.</span></span></P>



## <a name="see-also"></a><span data-ttu-id="2037f-164">Se även</span><span class="sxs-lookup"><span data-stu-id="2037f-164">See also</span></span>

[<span data-ttu-id="2037f-165">Skapa en strukturlistemall</span><span class="sxs-lookup"><span data-stu-id="2037f-165">Create a template BOM</span></span>](create-template-bom.md)

[<span data-ttu-id="2037f-166">Hantera strukturlistemallar på objektrelationer</span><span class="sxs-lookup"><span data-stu-id="2037f-166">Manage template BOMs on object relations</span></span>](manage-template-boms-on-object-relations.md)

[<span data-ttu-id="2037f-167">Ändra en servicestrukturlista</span><span class="sxs-lookup"><span data-stu-id="2037f-167">Modify a Service BOM</span></span>](modify-service-bom.md)

 


