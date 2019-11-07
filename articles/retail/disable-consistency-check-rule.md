---
title: Inaktivera regler i konsekvenskontrollen för butikstransaktioner
description: I det här avsnittet beskrivs funktionen för att avaktivera regler för konsekvenskontroll av butikstransaktioner som infördes i Microsoft Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4bf8df2fb9f8f5c33ceb13eb012fb6879f81ec66
ms.sourcegitcommit: bdbca89bd9b328c282ebfb681f75b8f1ed96e7a8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/14/2019
ms.locfileid: "2586307"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a><span data-ttu-id="2912e-103">Inaktivera regler i konsekvenskontrollen för butikstransaktioner</span><span class="sxs-lookup"><span data-stu-id="2912e-103">Disable rules in the retail transaction consistency checker</span></span> 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="2912e-104">Återförsäljare kan ha affärsscenarier och processer som är unika för dem.</span><span class="sxs-lookup"><span data-stu-id="2912e-104">Retailers can have business scenarios and processes that are unique to them.</span></span> <span data-ttu-id="2912e-105">Därför gäller inte alla regler som ingår som standard i konsekvenskontrollen av butikstransaktioner för alla detaljhandlare.</span><span class="sxs-lookup"><span data-stu-id="2912e-105">Therefore, not all the rules that are included by default in the retail transaction consistency checker are applicable to all retailers.</span></span> <span data-ttu-id="2912e-106">För att hantera skillnader innehåller Microsoft Dynamics 365 Retail funktioner som kan användas för att inaktivera regler som inte är tillämpliga.</span><span class="sxs-lookup"><span data-stu-id="2912e-106">To accommodate differences, Microsoft Dynamics 365 Retail provides functionality that can be used to disable the rules that aren't applicable.</span></span>

<span data-ttu-id="2912e-107">Om du vill visa en lista över regler som är tillgängliga i konsekvenskontrollen av butikstransaktioner i din miljö, och se status för varje regel, gå till **Butik \> Administrationsinställningar \> Parametrar \> Butiksparametrar**, och välj fliken **Transaktionsvalidering**.</span><span class="sxs-lookup"><span data-stu-id="2912e-107">To view the list of rules that are available in the retail transaction consistency checker in your environment, and to see the status of each rule, go to **Retail \> Headquarters setup \> Parameters \> Retail parameters**, and select the **Transaction validation** tab.</span></span>

<span data-ttu-id="2912e-108">Som standard är status för varje regel inställd på **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="2912e-108">By default, the status of every rule is set to **Enabled**.</span></span> <span data-ttu-id="2912e-109">Därför används alla regler för att validera butikstransaktioner innan de hämtas till butiksutdragen.</span><span class="sxs-lookup"><span data-stu-id="2912e-109">Therefore, all the rules are used to validate retail transactions before they are pulled into the retail statements.</span></span> <span data-ttu-id="2912e-110">Om du vill inaktivera en regel ändrar du dess status till **Inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="2912e-110">To disable a rule, change its status to **Disabled**.</span></span> <span data-ttu-id="2912e-111">Inaktiverade regler beaktas inte när butikstransaktioner valideras under utdragsberäkningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="2912e-111">Disabled rules aren't considered when retail transactions are validated during the statement calculation process.</span></span>

<span data-ttu-id="2912e-112">Om du vill kringgå hela valideringsprocessen, oavsett vilka regler som aktiveras, går du till **Butik \> Administrationsinställningar \> Parametrar \> Butiksparametrar**, och sedan, på fliken **Transaktionsvalidering** ställer du in valet för **Inaktivera konsekvenskontroll för butikstransaktioner** på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="2912e-112">To bypass the whole validation process, regardless of the rules that are enabled, go to **Retail \> Headquarters setup \> Parameters \> Retail parameters**, and then, on the **Transaction validation** tab, set the **Disable consistency checker for Retail transactions** option to **Yes**.</span></span> <span data-ttu-id="2912e-113">När alternativet är inställt på **Nej** kan det inte ställas tillbaka till **Ja** från användargränssnittet (UI).</span><span class="sxs-lookup"><span data-stu-id="2912e-113">After this option is set to **No**, it can't be set back to **Yes** from the user interface (UI).</span></span>
