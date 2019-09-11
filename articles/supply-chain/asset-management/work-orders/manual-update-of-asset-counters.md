---
title: Manuell uppdatering av tillgångsräknare
description: Det här avsnittet beskriver manuell uppdatering av tillgångsräknare i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e7c5ec288404c18b00f9dcd0e66f50744d0aa2f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875905"
---
# <a name="manual-update-of-asset-counters"></a><span data-ttu-id="ef92f-103">Manuell uppdatering av tillgångsräknare</span><span class="sxs-lookup"><span data-stu-id="ef92f-103">Manual update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="ef92f-104">Räknare används för att skapa registreringar för en tillgång angående t.ex. antal timmar i drift eller antalet producerade kvantiteter.</span><span class="sxs-lookup"><span data-stu-id="ef92f-104">Counters are used to create registrations on an asset regarding, for example, number of hours in operation, or the number of quantities produced.</span></span>

<span data-ttu-id="ef92f-105">Om den valda räknartypen för en räknare är inställd på att ärva räknarvärden (**Tillgångshantering** > **Inställningar** > **Tillgångstyper** > **Räknare** >  snabbfliken **Allmänt** > växlingsknappen **Ärv värden för tillgångsräknare** inställd på "Ja"), och när du sedan skapar en ny räknarrad av den typen, uppdateras alla underordnade tillgångar som använder samma räknartyp automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ef92f-105">If the counter type selected for a counter is set to inherit counter values (**Asset management** > **Setup** > **Asset types** > **Counters** > **General** FastTab > **Inherit asset counter values** toggle button set to "Yes"), then, when you create a new counter line of that type, every child asset that uses the same counter type is automatically updated.</span></span>

<span data-ttu-id="ef92f-106">I **Alla tillgångar** kan du skapa tim- eller kvantitetsräknarregistreringar för en tillgång, baserat på dina avläsningar av tillgången.</span><span class="sxs-lookup"><span data-stu-id="ef92f-106">In **All assets**, you create hours or quantity counter registrations on an asset, based on your readings on the asset.</span></span>

1. <span data-ttu-id="ef92f-107">Klicka på **Tillgångshantering** > **Allmänt** > **Tillgångar** > **Alla tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="ef92f-107">Click **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="ef92f-108">Välj tillgång i listan och klicka på **Räknare**.</span><span class="sxs-lookup"><span data-stu-id="ef92f-108">Select the asset in the list, and click **Counters**.</span></span> <span data-ttu-id="ef92f-109">I formuläret **Tillgångsräknare** visas en lista över alla tidigare räknarregistreringar för den valda tillgången.</span><span class="sxs-lookup"><span data-stu-id="ef92f-109">In the **Asset counters** form, you see a list of all previous counter registrations on the selected asset.</span></span>

3. <span data-ttu-id="ef92f-110">Klicka på **Ny** om du vill skapa en ny registrering.</span><span class="sxs-lookup"><span data-stu-id="ef92f-110">Click **New** to create a new registration.</span></span> <span data-ttu-id="ef92f-111">Tillgångens ID infogas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ef92f-111">The asset ID is automatically inserted.</span></span>

4. <span data-ttu-id="ef92f-112">Välj relevant räknare i fältet **Räknare**.</span><span class="sxs-lookup"><span data-stu-id="ef92f-112">In the **Counter** field, select the relevant counter.</span></span> <span data-ttu-id="ef92f-113">Endast räknare som hör till den tillgångstyp som valts i tillgången är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="ef92f-113">Only counters related to the asset type selected on the asset are available.</span></span> <span data-ttu-id="ef92f-114">Den relaterade enheten infogas automatiskt i fältet **Enhet**.</span><span class="sxs-lookup"><span data-stu-id="ef92f-114">The related unit is automatically inserted in the **Unit** field.</span></span>

5. <span data-ttu-id="ef92f-115">Välj datum och tid för räknarregistreringen.</span><span class="sxs-lookup"><span data-stu-id="ef92f-115">Select date and time for the counter registration.</span></span>

6. <span data-ttu-id="ef92f-116">I fältet **Värde** anger du numret sedan den senaste räknarregistreringen eller, i fältet **Sammanlagt värde**, infogar du det totala antalet.</span><span class="sxs-lookup"><span data-stu-id="ef92f-116">In the **Value** field, insert the number since the last counter registration, or, in the **Aggregated value** field, insert the total count number.</span></span>

- <span data-ttu-id="ef92f-117">Om du installerar en ny räknare för en tillgång fysiskt måste du registrera ändringen i tillgången i **Tillgångsräknare**.</span><span class="sxs-lookup"><span data-stu-id="ef92f-117">If you physically install a new counter on an asset, you need to register the change on the asset in **Asset counters**.</span></span> <span data-ttu-id="ef92f-118">Sedan måste du skapa två registreringsrader med identiska tidsstämplar, och på raden för den nya räknaren markerar du kryssrutan **Återställ räknare**.</span><span class="sxs-lookup"><span data-stu-id="ef92f-118">Next, you must create two registration lines with identical timestamps, and on the line regarding the new counter, you select the **Counter reset** check box.</span></span> <span data-ttu-id="ef92f-119">När du skapar de två registreringsraderna måste den första raden vara för den räknare som du ersätter.</span><span class="sxs-lookup"><span data-stu-id="ef92f-119">When you create the two registration lines, the first line must be for the counter that you are replacing.</span></span> <span data-ttu-id="ef92f-120">I fältet **Summor** är den totala räknarsumman summan av alla registrerade värden på den räknartypen.</span><span class="sxs-lookup"><span data-stu-id="ef92f-120">In the **Totals** field, the total count number is the sum of the counter total of all registered values on that counter type.</span></span>  
- <span data-ttu-id="ef92f-121">Om kryssrutan **Återställ räknare** har markerats för en tillgång med en underhållsplan med intervalltypen "En gång från..." eller "När...nås" är räknaren fortfarande aktiv på den nya räknarraden, eftersom du skapar en separat räknarrad och börjar om med en ny räknare.</span><span class="sxs-lookup"><span data-stu-id="ef92f-121">If the **Counter reset** check box is selected on an asset using a maintenance plan with a "Once from..." or "Once reached..." interval type, the counter is still active on the new counter line because you create a separate counter line and start over with a new counter.</span></span>

![Figur 1](media/11-work-orders.png)


<span data-ttu-id="ef92f-123">Om du behöver göra räknarregistreringar för flera tillgångar kan du utföra dem i **Tillgångshantering** > **Förfrågningar** > **Tillgångar** > **Tillgångsräknare**.</span><span class="sxs-lookup"><span data-stu-id="ef92f-123">If you need to make counter registrations on several assets, that can be done in **Asset management** > **Inquiries** > **Assets** > **Asset counters**.</span></span>

>[!NOTE]
><span data-ttu-id="ef92f-124">Du kan ställa in ett intervall för att definiera avvikelser i manuella räknarregistreringar, och vilken typ av meddelande som ska visas om registreringarna ligger utanför det definierade intervallet.</span><span class="sxs-lookup"><span data-stu-id="ef92f-124">You can set up a range to define deviations in manual counter registrations, and the type of message that should be displayed if registrations are outside the defined range.</span></span> <span data-ttu-id="ef92f-125">Information om hur du ställer in räknare finns i avsnittet [Räknare](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="ef92f-125">Refer to the [Counters](../setup-for-objects/counters.md) topic regarding setup of counters.</span></span>
