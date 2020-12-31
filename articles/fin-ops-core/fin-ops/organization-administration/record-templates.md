---
title: Postmallar – översikt
description: Det här avsnittet innehåller en presentation av begreppet postmallar och en beskrivning av hur de kan användas för att skapa poster som delar information.
author: pvillads
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 16101
ms.assetid: 61ada2d8-84c3-44bc-b4c5-516b1aeac3d1
ms.search.region: Global
ms.author: pvillads
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0b55046e6c523398b4a30e674dc9f77bb6fedf3
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2020
ms.locfileid: "4693218"
---
# <a name="record-templates-overview"></a><span data-ttu-id="52c99-103">Postmallar – översikt</span><span class="sxs-lookup"><span data-stu-id="52c99-103">Record templates overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52c99-104">Det här avsnittet innehåller en presentation av begreppet postmallar och en beskrivning av hur de kan användas för att skapa poster som delar information.</span><span class="sxs-lookup"><span data-stu-id="52c99-104">This article introduces the concept of record templates and explains how they can be used to create records that share information.</span></span>

<span data-ttu-id="52c99-105">Med hjälp av postmallar kan du snabbare skapa poster, men du kan bara skapa postmallar för vissa posttyper.</span><span class="sxs-lookup"><span data-stu-id="52c99-105">Record templates can help you to create records more quickly, however you can only create record templates for some record types.</span></span>

<span data-ttu-id="52c99-106">Till exempel, tänk dig att du anger hyrbilsinformation för ett hyrbilsföretag som ligger i San Francisco.</span><span class="sxs-lookup"><span data-stu-id="52c99-106">For example, imagine you are entering rental information for a car rental business that is located in San Francisco.</span></span> <span data-ttu-id="52c99-107">Eftersom de flesta kunder är sannolikt från San Francisco, vore det trevligt om du kunde automatiskt fylla i värden för **delstaten**, **land** och **stad** fält i hyresformuläret.</span><span class="sxs-lookup"><span data-stu-id="52c99-107">Since most of the customers are likely to be from the San Francisco area, it would be nice if you could automatically fill in the values for the **State**, **Country**, and **City** fields on the rental form.</span></span>

> [!NOTE]
> <span data-ttu-id="52c99-108">Du kan bara använda mallar för de områden som du har tillgång till.</span><span class="sxs-lookup"><span data-stu-id="52c99-108">You can apply templates only in areas that you have access to.</span></span> <span data-ttu-id="52c99-109">Men alla malltitlar är synliga för dig när du skapar en ny post, och andra användare också, om du skapar mallar som kommer att vara tillgängliga för alla användare.</span><span class="sxs-lookup"><span data-stu-id="52c99-109">However all template titles are visible to you when you create a new record, and to other users as well, if you are creating templates that will be available for all users.</span></span> <span data-ttu-id="52c99-110">Beaktar detta när du namnger mallar.</span><span class="sxs-lookup"><span data-stu-id="52c99-110">Be sure to consider this when naming templates.</span></span> <span data-ttu-id="52c99-111">Undvik att använda namn som innehåller ord som ”provision”, om det konfidentiellt att vissa medarbetare inom företaget provision-harbaserat lön.</span><span class="sxs-lookup"><span data-stu-id="52c99-111">For example, avoid using names that include words, such as "commission," if is confidential that some employees in the company have commission-based salaries.</span></span>

<span data-ttu-id="52c99-112">När en eller flera mallar som du har tillgång till finns för ett specifikt formulär och du försöker skapa en ny post i formuläret, visas sidan **Välj en mall för**.</span><span class="sxs-lookup"><span data-stu-id="52c99-112">When one or more templates that you have access to exist for a specific form and you attempt to create a new record in the form, the **Select a template for** page is displayed.</span></span> <span data-ttu-id="52c99-113">När du väljer en mall i listan skapas den nya posten med standardinformation som är baserad på mallen du valde.</span><span class="sxs-lookup"><span data-stu-id="52c99-113">When you select a template from the list, the new record is created and contains default information that is based on the template that you selected.</span></span> <span data-ttu-id="52c99-114">Om du inte vill använda mallar när du skapar nya poster, markerar du kryssrutan **Fråga inte igen** på sidan **Välj en mall för**.</span><span class="sxs-lookup"><span data-stu-id="52c99-114">If you do not want to use templates when you create new records, select the **Do not ask again** check box in the **Select a template for** page.</span></span> <span data-ttu-id="52c99-115">Om du vill visa dialogrutan för val av mall igen högerklickar du på en post, klickar på **Postinfo** och klickar sedan på **Visa mallval**.</span><span class="sxs-lookup"><span data-stu-id="52c99-115">To display the template selection dialog box again, right-click any record, click **Record info**, and then click **Show template selection**.</span></span>
