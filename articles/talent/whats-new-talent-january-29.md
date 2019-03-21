---
title: Nyheter och ändringar i Dynamics 365 for Talent (31 januari 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 01/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-29
ms.dyn365.ops.version: Talent
ms.openlocfilehash: ab43bab53afd979d64099425f0582f6c1bb5a8b0
ms.sourcegitcommit: 383a344deb5abf48584ea2ee7774b8dbbbec49b3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2019
ms.locfileid: "377860"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-january-31-2019"></a><span data-ttu-id="70347-103">Nyheter och ändringar i Dynamics 365 for Talent (31 januari 2019)</span><span class="sxs-lookup"><span data-stu-id="70347-103">What's new or changed in Dynamics 365 for Talent (January 31, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="70347-104">Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 for Talent.</span><span class="sxs-lookup"><span data-stu-id="70347-104">This topic describes features that are either new or changed in Dynamics 365 for Talent</span></span>

<span data-ttu-id="70347-105">**Skapa 8.1.2128**</span><span class="sxs-lookup"><span data-stu-id="70347-105">**Build 8.1.2128**</span></span>

## <a name="core-hr-changes"></a><span data-ttu-id="70347-106">Ändringar i Core HR</span><span class="sxs-lookup"><span data-stu-id="70347-106">Core HR Changes</span></span>

### <a name="time-off-taken-on-leave-people-card-doesnt-consider-leave-plan-dates"></a><span data-ttu-id="70347-107">Tjänstledighet på personkortet beaktar inte datumen i tjänstledighetsplanen</span><span class="sxs-lookup"><span data-stu-id="70347-107">Time off taken on leave people card doesn't consider leave plan dates</span></span>
<span data-ttu-id="70347-108">För de som har tjänstledighetsplaner som inte fungerar på ett kalenderår, visas nu kortet **tagen** ledig tid som sker under plandefinierade tjänstledighetsåret.</span><span class="sxs-lookup"><span data-stu-id="70347-108">For those that have leave plans that don’t run on a calendar year, the **Taken** card now displays time off that’s been taken in the plan-defined leave year.</span></span> <span data-ttu-id="70347-109">Om en organisation tjänstledighetsår är 1 juni till och med den 30 maj och en medarbetare har tagit 3 dagar ledigt i december kommer kortet **tagen** den 15 januari, visa 3 dagar.</span><span class="sxs-lookup"><span data-stu-id="70347-109">For example, if an organization’s leave year is June 1 through May 30 and an employee has taken 3 days off in December, the **Taken** card on January 15, will display 3 days.</span></span> 

### <a name="accrual-amounts-not-matching-tier-date-basis"></a><span data-ttu-id="70347-110">Upplupna belopp matchar inte nivådatumbasen</span><span class="sxs-lookup"><span data-stu-id="70347-110">Accrual amounts not matching tier date basis</span></span>
<span data-ttu-id="70347-111">Nya alternativ har lagts till ledighet och frånvaro (**personal** parametrar) för att låta kunder bestämma när anställdas månader av tjänstdatum är effektiva.</span><span class="sxs-lookup"><span data-stu-id="70347-111">New options have been added to leave and absence (**Human resources** parameters) to enable customers to determine when employees’ months of service date are effective.</span></span> <span data-ttu-id="70347-112">För vissa organisationer är datumet slutet på månaden, men för andra kan det vara början på nästa månad.</span><span class="sxs-lookup"><span data-stu-id="70347-112">For some organizations, the date is the end of the month, but for others it may be the start of the next month.</span></span> <span data-ttu-id="70347-113">Till exempel en organisation får tilldela tjänstledigt 31 december, medan en annan får tilldela tjänstledigt 1 januari.</span><span class="sxs-lookup"><span data-stu-id="70347-113">For example, one organization may award time off on December 31, while another may award time off on January 1.</span></span> <span data-ttu-id="70347-114">Det här alternativet låter dig välja när tilldelningen ska ske.</span><span class="sxs-lookup"><span data-stu-id="70347-114">This option will allow you to choose when the award should occur.</span></span> 

### <a name="worker-hire-actions-are-stuck-in-workflow-complete-state"></a><span data-ttu-id="70347-115">Arbetarens anställningåtgärder ligger kvar i tillståndet ”Arbetsflöde slutfört”</span><span class="sxs-lookup"><span data-stu-id="70347-115">Worker hire actions are stuck in "Workflow complete" state</span></span>
<span data-ttu-id="70347-116">Ändringar har gjorts som korrigerar ett problem där ett litet antal arbetsflöden slutförs med status ”arbetsflöde slutfört”.</span><span class="sxs-lookup"><span data-stu-id="70347-116">Changes have been made to correct an issue where a small number of workflows finished with a "Workflow complete" status.</span></span> <span data-ttu-id="70347-117">Nya arbetsflöden ska gå till läget ”slutfört” när arbetsflödet har slutförts.</span><span class="sxs-lookup"><span data-stu-id="70347-117">New workflows should now move to a "Completed" state when the workflow finishes.</span></span> <span data-ttu-id="70347-118">Alla arbetsflöden i en slutförd arbetsflödesstatus kommer övergå till felstatus för att uppdatera eller ta bort om det behövs.</span><span class="sxs-lookup"><span data-stu-id="70347-118">Any workflows in a workflow completed status will be transitioned to an error status to allow for updating or removal if required.</span></span> 
