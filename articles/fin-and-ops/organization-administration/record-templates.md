---
title: Postmallar
description: "Det här avsnittet innehåller en presentation av begreppet postmallar och en beskrivning av hur de kan användas för att skapa poster som delar information."
author: pvillads
manager: AnnBe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e89e4a74550597a4e497a1128fe91c07e766d697
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="record-templates"></a><span data-ttu-id="5920c-103">Postmallar</span><span class="sxs-lookup"><span data-stu-id="5920c-103">Record templates</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="5920c-104">Det här avsnittet innehåller en presentation av begreppet postmallar och en beskrivning av hur de kan användas för att skapa poster som delar information.</span><span class="sxs-lookup"><span data-stu-id="5920c-104">This article introduces the concept of record templates and explains how they can be used to create records that share information.</span></span>

<span data-ttu-id="5920c-105">Postmallar kan hjälpa dig att skapa poster snabbare i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5920c-105">Record templates can help you to create records more quickly in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="5920c-106">Du kan bara skapa postmallar för vissa av posttyperna i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="5920c-106">You can create record templates for only some of the record types in Microsoft Dynamics 365 for Finance and Operations.</span></span> 

<span data-ttu-id="5920c-107">Till exempel, tänk dig att du anger hyrbilsinformation för ett hyrbilsföretag som ligger i San Francisco.</span><span class="sxs-lookup"><span data-stu-id="5920c-107">For example, imagine you are entering rental information for a car rental business that is located in San Francisco.</span></span> <span data-ttu-id="5920c-108">Eftersom de flesta kunder är sannolikt från San Francisco, vore det trevligt om du kunde automatiskt fylla i värden för **delstaten**, **land** och **stad** fält i hyresformuläret.</span><span class="sxs-lookup"><span data-stu-id="5920c-108">Since most of the customers are likely to be from the San Francisco area, it would be nice if you could automatically fill in the values for the **State**, **Country**, and **City** fields on the rental form.</span></span> 

> [!Note]
> <span data-ttu-id="5920c-109">Du kan använda mallar endast för de områden inom Finance and Operations som du har åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="5920c-109">You can apply templates only for the areas of Finance and Operations that you have access to.</span></span> <span data-ttu-id="5920c-110">Men alla malltitlar är synliga för dig när du skapar en ny post, och andra användare också, om du skapar mallar som kommer att vara tillgängliga för alla användare.</span><span class="sxs-lookup"><span data-stu-id="5920c-110">However all template titles are visible to you when you create a new record, and to other users as well, if you are creating templates that will be available for all users.</span></span> <span data-ttu-id="5920c-111">Beaktar detta när du namnger mallar.</span><span class="sxs-lookup"><span data-stu-id="5920c-111">Be sure to consider this when naming templates.</span></span> <span data-ttu-id="5920c-112">Undvik att använda namn som innehåller ord som ”provision”, om det konfidentiellt att vissa medarbetare inom företaget provision-harbaserat lön.</span><span class="sxs-lookup"><span data-stu-id="5920c-112">For example, avoid using names that include words, such as "commission," if is confidential that some employees in the company have commission-based salaries.</span></span> 

<span data-ttu-id="5920c-113">När en eller flera mallar som du har tillgång till finns för ett specifikt formulär och du försöker skapa en ny post i formuläret, visas sidan **Välj en mall för**.</span><span class="sxs-lookup"><span data-stu-id="5920c-113">When one or more templates that you have access to exist for a specific form and you attempt to create a new record in the form, the **Select a template for** page is displayed.</span></span> <span data-ttu-id="5920c-114">När du väljer en mall i listan skapas den nya posten med standardinformation som är baserad på mallen du valde.</span><span class="sxs-lookup"><span data-stu-id="5920c-114">When you select a template from the list, the new record is created and contains default information that is based on the template that you selected.</span></span> <span data-ttu-id="5920c-115">Om du inte vill använda mallar när du skapar nya poster, markerar du kryssrutan **Fråga inte igen** på sidan **Välj en mall för**.</span><span class="sxs-lookup"><span data-stu-id="5920c-115">If you do not want to use templates when you create new records, select the **Do not ask again** check box in the **Select a template for** page.</span></span> <span data-ttu-id="5920c-116">Om du vill visa dialogrutan för val av mall igen högerklickar du på en post, klickar på **Postinfo** och klickar sedan på **Visa mallval**.</span><span class="sxs-lookup"><span data-stu-id="5920c-116">To display the template selection dialog box again, right-click any record, click **Record info**, and then click **Show template selection**.</span></span>




