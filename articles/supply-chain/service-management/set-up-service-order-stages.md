---
title: Ställ in serviceorderfaser
description: Ställ in serviceorderfaser.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9aca699283a9de6ea551bd02184498aed88143e9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991650"
---
# <a name="set-up-service-order-stages"></a><span data-ttu-id="05a81-103">Ställ in serviceorderfaser</span><span class="sxs-lookup"><span data-stu-id="05a81-103">Set up service order stages</span></span> 

[!include [banner](../includes/banner.md)]


1.  <span data-ttu-id="05a81-104">Klicka på **servicehantering**\>**inställningar**\>**serviceorder**\>**Servicefaser**.</span><span class="sxs-lookup"><span data-stu-id="05a81-104">Click **Service management** \> **Setup** \> **Service orders** \> **Service stages**.</span></span>

2.  <span data-ttu-id="05a81-105">Skapa en ny post genom att trycka på CTRL+N.</span><span class="sxs-lookup"><span data-stu-id="05a81-105">Press CTRL+N to create a new record.</span></span>

3.  <span data-ttu-id="05a81-106">I fälten **Servicefas** och **Beskrivning**, ange ett servicefas-ID och beskrivning.</span><span class="sxs-lookup"><span data-stu-id="05a81-106">In the **Service stage** and **Description** fields, specify a service stage ID and description.</span></span>

4.  <span data-ttu-id="05a81-107">Välj lämpliga parametrar för fasen.</span><span class="sxs-lookup"><span data-stu-id="05a81-107">Select the appropriate parameters for the stage.</span></span>

5.  <span data-ttu-id="05a81-108">Välj överordnad fas för den aktuella fasen eller lämna fältet **Överordnad** blankt om fasen finns i den ursprungliga fasen i inställningarna för fas.</span><span class="sxs-lookup"><span data-stu-id="05a81-108">Select the parent stage for the current stage or leave the **Parent** field blank if the stage is the initial stage in the stage setup.</span></span>


> [!NOTE]
> <P><span data-ttu-id="05a81-109">Du kan inte ändra fältet <STRONG>Överordnad</STRONG> efter att du sparat fasen.</span><span class="sxs-lookup"><span data-stu-id="05a81-109">You cannot modify the <STRONG>Parent</STRONG> field after you save the stage.</span></span> <span data-ttu-id="05a81-110">Istället kan du ta bort posten och skapa om den med ett annat urval i fältet <STRONG>Överordnad</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="05a81-110">Instead, you can delete the record and create the record again with a different selection in the <STRONG>Parent</STRONG> field.</span></span></P>
> <P><span data-ttu-id="05a81-111">Du kan bara skapa en fas med ett tomt fält för <STRONG>Överordnad</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="05a81-111">Also, you can only create one stage with a blank <STRONG>Parent</STRONG> field.</span></span> <span data-ttu-id="05a81-112">Det innebär att endast en ursprunglig fas tillåts.</span><span class="sxs-lookup"><span data-stu-id="05a81-112">That is, only one initial stage is permitted.</span></span></P>


  


