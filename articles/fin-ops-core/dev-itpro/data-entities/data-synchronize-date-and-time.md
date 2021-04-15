---
title: Synkronisera datum och tid i importjobb
description: Använd UTC-tidszoner i importjobb för att undvika problem med tidszonskonverteringen.
author: Sunil-Garg
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: sunilg
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41c0ec805a20a525989e0133e5dffb29ce3fed39
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748679"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a><span data-ttu-id="49e4b-103">Synkronisera datum och tid i importjobb</span><span class="sxs-lookup"><span data-stu-id="49e4b-103">Synchronize date and time in import jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="49e4b-104">Det är viktigt att ange tidszonen för ditt importjobb till Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="49e4b-104">It's important to set the time zone for your import job to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="49e4b-105">Oväntade datum och tider i importerade data kanske visas om du använder en annan inställning.</span><span class="sxs-lookup"><span data-stu-id="49e4b-105">You might see unexpected dates and times in your imported data if you use a different setting.</span></span> <span data-ttu-id="49e4b-106">Utan rätt inställning konverterar importprocessen UTC-datumet till det lokala formatet och sedan konverterar systeminställningarna det igen.</span><span class="sxs-lookup"><span data-stu-id="49e4b-106">Without the correct setting, the import process converts the UTC date to the local format, and then system settings converts it again.</span></span>

<span data-ttu-id="49e4b-107">Denna dubbla konvertering gör att datum ändras mellan program.</span><span class="sxs-lookup"><span data-stu-id="49e4b-107">This dual conversion causes dates to change between applications.</span></span> <span data-ttu-id="49e4b-108">Till exempel kan den dubbla konverteringen orsaka att en anställds startdatum skiljer sig mellan Dynamics 365 Human Resources och Dynamics 365 Finance på grund av skillnader i lokala tidszoner.</span><span class="sxs-lookup"><span data-stu-id="49e4b-108">For example, the dual conversion could cause an employee's start date to be different between Dynamics 365 Human Resources and Dynamics 365 Finance due to differences in local time zones.</span></span> <span data-ttu-id="49e4b-109">Om du ställer in importjobbet på UTC löser du problemet.</span><span class="sxs-lookup"><span data-stu-id="49e4b-109">Setting the import job to UTC resolves this problem.</span></span>

1. <span data-ttu-id="49e4b-110">I Dynamics 365 Finance and Operations, välj **Datahantering**.</span><span class="sxs-lookup"><span data-stu-id="49e4b-110">In Dynamics 365 Finance and Operations, select **Data management**.</span></span>

2. <span data-ttu-id="49e4b-111">Välj **Importera projekt** och välj sedan projektet.</span><span class="sxs-lookup"><span data-stu-id="49e4b-111">Select **Import projects**, and then select the project.</span></span>

3. <span data-ttu-id="49e4b-112">Under **Källdatumformat**, välj **CSV-Unicode**.</span><span class="sxs-lookup"><span data-stu-id="49e4b-112">Under **Source date format**, select **CSV-Unicode**.</span></span>

   <span data-ttu-id="49e4b-113">[![Ändra källdatumformat till UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span><span class="sxs-lookup"><span data-stu-id="49e4b-113">[![Change source date format to UTC](./media/data-source-date-format.png)](./media/data-source-date-format.png)</span></span>

4. <span data-ttu-id="49e4b-114">Ändra **Tidszon** till **Coordinated Universal Timezone** och ändra **Språk** till **En-US**.</span><span class="sxs-lookup"><span data-stu-id="49e4b-114">Change **Timezone** to **Coordinated Universal Timezone**, and change **Language** to **En-US**.</span></span>




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]