---
title: Rapportera som färdig till en ID-nummertyrd plats från jobbkortenheten
description: I det här avsnittet beskrivs processen för att slutföra färdiga produkter i en tillverkningsorder till lagret när en registreringsskylt kontrollerar platsen.
author: johanhoffmann
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: cb809e596fd6bf3030bcee460838798435512b95
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2019
ms.locfileid: "2572139"
---
[!include [banner](../includes/banner.md)]

# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a><span data-ttu-id="e7154-103">Rapportera som färdig till en ID-nummertyrd plats från jobbkortenheten</span><span class="sxs-lookup"><span data-stu-id="e7154-103">Report as finished to a license plate controlled location from the Job card device</span></span> 

<span data-ttu-id="e7154-104">Processen som kallas rapportera som färdig slutför färdiga produkter i en tillverkningsorder till lagret.</span><span class="sxs-lookup"><span data-stu-id="e7154-104">The process called Reporting as finished completes finished products on a production order to the inventory.</span></span> <span data-ttu-id="e7154-105">Om den färdiga produkten är aktiverad för de avancerade lagerprocesserna rapporteras produkten som färdig till en plats som kallas för produktionsutleveransplats.</span><span class="sxs-lookup"><span data-stu-id="e7154-105">If the finished product is enabled for the advanced warehouse processes, the product is reported as finished to a location called the production output location.</span></span> <span data-ttu-id="e7154-106">Information om hur du ställer in produktionsutleveransplats finns i [Plats för produktionsutleverans](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location)plats för produktions utmatning.</span><span class="sxs-lookup"><span data-stu-id="e7154-106">For information about setting up the production output location, see [Production output location](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span></span>

<span data-ttu-id="e7154-107">Du måste välja ett befintligt ID-nummer för att slutföra uppgiften.</span><span class="sxs-lookup"><span data-stu-id="e7154-107">You must select an existing license plate number to complete this task.</span></span> <span data-ttu-id="e7154-108">Om produktionsutleveransplatsen har ställts in för spårning via registreringskylten måste ett ID-nummer inkluderas vid rapportering av produktionsutleveransplatsen när den är färdig.</span><span class="sxs-lookup"><span data-stu-id="e7154-108">If the production output location is set up to be tracked by license plate, then a license plate number must be included when reporting the production output location as finished.</span></span> <span data-ttu-id="e7154-109">Fältet **Registreringsskylt** visas i **Rapportera förlopp** på sidan **Jobbkortenhet**.</span><span class="sxs-lookup"><span data-stu-id="e7154-109">The **License plate** field is visible on the **Report progress** prompt on the **Job card device** page.</span></span> <span data-ttu-id="e7154-110">Fältet visas bara i meddelandet **rapportförlopp** när du rapporterar om den senaste operationen för tillverkningsordern.</span><span class="sxs-lookup"><span data-stu-id="e7154-110">The field is only visible on the **Report progress** prompt when reporting on the last operation of the production order.</span></span> <span data-ttu-id="e7154-111">Fältet visas endast om artikeln för tillverkningsordern är aktiverad för lagerstyrningsprocesserna.</span><span class="sxs-lookup"><span data-stu-id="e7154-111">The field is only shown if the item for the production order is enabled for the warehouse management processes.</span></span> 
