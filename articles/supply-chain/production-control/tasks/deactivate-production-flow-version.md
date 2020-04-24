---
title: Inaktivera en produktionsflödesversion
description: När en aktiv produktionsflödesversion är inte längre behövs kan den inaktiveras.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ec2d9f8b275cd4babdf46434aebf0cbf9105eed
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212122"
---
# <a name="deactivate-a-production-flow-version"></a><span data-ttu-id="3da93-103">Inaktivera en produktionsflödesversion</span><span class="sxs-lookup"><span data-stu-id="3da93-103">Deactivate a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3da93-104">När en aktiv produktionsflödesversion är inte längre behövs kan den inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="3da93-104">When an active production flow version is no longer needed, it can be deactivated.</span></span> <span data-ttu-id="3da93-105">Du bör bara använda detta alternativ om alla kanban-regler och -aktiviteter har avslutat och inte ska aktiveras igen.</span><span class="sxs-lookup"><span data-stu-id="3da93-105">You should only use this option if all kanban rules and activities have ended and will not be activated again.</span></span> <span data-ttu-id="3da93-106">Observera att utgångsdatum för alla kanbanregler relaterade till denna produktionsflödesversion uppdateras med det aktuella datumet och tiden.</span><span class="sxs-lookup"><span data-stu-id="3da93-106">Note that the expiry date of all kanban rules related to this production flow version will be updated with the current date and time.</span></span> 

<span data-ttu-id="3da93-107">Överväg att ange ett utgångsdatum för den aktiva versionen och skapa en ny version, du vill ändra en aktiv produktionsflödesversion.</span><span class="sxs-lookup"><span data-stu-id="3da93-107">To modify an active production flow version, consider setting an expiry date for the active version and create a new version.</span></span> <span data-ttu-id="3da93-108">Detta gör att du fortsätta din produktionsverksamhet samtidigt som du förbereder den nya versionen och relaterade kanban-regler.</span><span class="sxs-lookup"><span data-stu-id="3da93-108">This will allow you to continue your production operations while preparing the new version and related kanban rules.</span></span> 

<span data-ttu-id="3da93-109">För att låta en aktiv produktionsflödesversion upphöra måste du ange ett utgångsdatum.</span><span class="sxs-lookup"><span data-stu-id="3da93-109">To expire an active production flow version, you need to set an expiry date.</span></span> <span data-ttu-id="3da93-110">På så sätt är inaktivering mer som ett undantag än en regel.</span><span class="sxs-lookup"><span data-stu-id="3da93-110">In that sense, deactivation is more like an exception than a rule.</span></span> 

<span data-ttu-id="3da93-111">För den här proceduren behöver du ett produktionsflöde med en version som kan inaktiveras.</span><span class="sxs-lookup"><span data-stu-id="3da93-111">For this procedure you need a production flow with a version that can be deactivated.</span></span> <span data-ttu-id="3da93-112">Försök inte detta i en produktionsmiljö om du inte är 100 % säker på att versionen är helt föråldrad.</span><span class="sxs-lookup"><span data-stu-id="3da93-112">Do not try this in a production environment unless you are 100% positive that the version is fully obsolete.</span></span>


## <a name="deactivate-a-production-flow-version"></a><span data-ttu-id="3da93-113">Inaktivera en produktionsflödesversion</span><span class="sxs-lookup"><span data-stu-id="3da93-113">Deactivate a production flow version</span></span>
1. <span data-ttu-id="3da93-114">Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.</span><span class="sxs-lookup"><span data-stu-id="3da93-114">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="3da93-115">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="3da93-115">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="3da93-116">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="3da93-116">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="3da93-117">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="3da93-117">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="3da93-118">Klicka på Deactivate.</span><span class="sxs-lookup"><span data-stu-id="3da93-118">Click Deactivate.</span></span>
    * <span data-ttu-id="3da93-119">Fortsätt inte om du inte är 100 % säker på att denna produktionsflödesversion är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="3da93-119">Do not proceed if you are not 100% positive that this production flow version is obsolete.</span></span> <span data-ttu-id="3da93-120">Om du klickar på Ok kommer alla aktiva kanban-regler att hävas och omedelbart stoppa alla produktions- och lagerpåfyllnadsaktiviteter för denna produktionsflödesversion.</span><span class="sxs-lookup"><span data-stu-id="3da93-120">Clicking Ok will expire all active kanban rules and put an immediate stop to all production and replenishment activities of this production flow version.</span></span>  
6. <span data-ttu-id="3da93-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="3da93-121">Click OK.</span></span>

