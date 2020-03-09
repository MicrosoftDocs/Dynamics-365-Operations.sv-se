---
title: Inaktivera regler i konsekvenskontrollen för butikstransaktioner
description: I det här avsnittet beskrivs funktionen för att avaktivera regler för konsekvenskontroll av transaktioner i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 51a02d6f305cbad9784cf1b811188d0e06b6f15b
ms.sourcegitcommit: 12b9d6f2dd24e52e46487748c848864909af6967
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/14/2020
ms.locfileid: "3057647"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a><span data-ttu-id="cdab8-103">Inaktivera regler i konsekvenskontrollen för butikstransaktioner</span><span class="sxs-lookup"><span data-stu-id="cdab8-103">Disable rules in the retail transaction consistency checker</span></span> 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="cdab8-104">Återförsäljare kan ha affärsscenarier och processer som är unika för dem.</span><span class="sxs-lookup"><span data-stu-id="cdab8-104">Retailers can have business scenarios and processes that are unique to them.</span></span> <span data-ttu-id="cdab8-105">Därför gäller inte alla regler som ingår som standard i konsekvenskontrollen av handelstransaktioner för alla detaljhandlare.</span><span class="sxs-lookup"><span data-stu-id="cdab8-105">Therefore, not all the rules that are included by default in the commerce transaction consistency checker are applicable to all retailers.</span></span> <span data-ttu-id="cdab8-106">För att hantera skillnader innehåller Microsoft Dynamics 365 Commerce funktioner som kan användas för att inaktivera regler som inte är tillämpliga.</span><span class="sxs-lookup"><span data-stu-id="cdab8-106">To accommodate differences, Microsoft Dynamics 365 Commerce provides functionality that can be used to disable the rules that aren't applicable.</span></span>

<span data-ttu-id="cdab8-107">Om du vill visa en lista över regler som är tillgängliga i konsekvenskontrollen av butikstransaktioner i din miljö, och se status för varje regel, gå till **Retail och Commerce \> Administrationsinställningar \> Parametrar \> Commerce-parametrar**, och välj fliken **Transaktionsvalidering**.</span><span class="sxs-lookup"><span data-stu-id="cdab8-107">To view the list of rules that are available in the transaction consistency checker in your environment, and to see the status of each rule, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**, and select the **Transaction validation** tab.</span></span>

<span data-ttu-id="cdab8-108">Som standard är status för varje regel inställd på **Aktiverad**.</span><span class="sxs-lookup"><span data-stu-id="cdab8-108">By default, the status of every rule is set to **Enabled**.</span></span> <span data-ttu-id="cdab8-109">Därför används alla regler för att validera butikstransaktioner innan de hämtas till butiksutdragen.</span><span class="sxs-lookup"><span data-stu-id="cdab8-109">Therefore, all the rules are used to validate transactions before they are pulled into the commerce statements.</span></span> <span data-ttu-id="cdab8-110">Om du vill inaktivera en regel ändrar du dess status till **Inaktiverad**.</span><span class="sxs-lookup"><span data-stu-id="cdab8-110">To disable a rule, change its status to **Disabled**.</span></span> <span data-ttu-id="cdab8-111">Inaktiverade regler beaktas inte när transaktioner valideras under utdragsberäkningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="cdab8-111">Disabled rules aren't considered when transactions are validated during the statement calculation process.</span></span>

<span data-ttu-id="cdab8-112">Om du vill kringgå hela valideringsprocessen, oavsett vilka regler som aktiveras, går du till **Retail och Commerce \> Administrationsinställningar \> Parametrar \> Commerce-parametrar**, och sedan, på fliken **Transaktionsvalidering** ställer du in valet för **Inaktivera konsekvenskontroll för Commerce-transaktioner** på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="cdab8-112">To bypass the whole validation process, regardless of the rules that are enabled, go to **Retail and Commerce \> Headquarters setup \> Parameters \> Commerce parameters**, and then, on the **Transaction validation** tab, set the **Disable consistency checker for Commerce transactions** option to **Yes**.</span></span> <span data-ttu-id="cdab8-113">När alternativet är inställt på **Nej** kan det inte ställas tillbaka till **Ja** från användargränssnittet (UI).</span><span class="sxs-lookup"><span data-stu-id="cdab8-113">After this option is set to **No**, it can't be set back to **Yes** from the user interface (UI).</span></span>
