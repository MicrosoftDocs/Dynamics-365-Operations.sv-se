---
title: Rapportera som färdig till en ID-nummertyrd plats från jobbkortenheten
description: I det här avsnittet beskrivs processen för att slutföra färdiga produkter i en tillverkningsorder till lagret när en registreringsskylt kontrollerar platsen.
author: johanhoffmann
manager: tfehr
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JmgRegistration, ProdJournalTransJob, ProdJournalTransRoute, ProdParmReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19351
ms.assetid: bcc9e242-b4b8-4144-b14d-c3c106fb40ec
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2019-09-06
ms.dyn365.ops.version: AX 10.0.6
ms.openlocfilehash: 74e1e30f5afe51cd0ecec2530ffcb9a59eec5fee
ms.sourcegitcommit: 89022f39502b19c24c0997ae3a01a64b93280f42
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2020
ms.locfileid: "3367255"
---
# <a name="report-as-finished-to-a-license-plate-controlled-location-from-the-job-card-device"></a><span data-ttu-id="e4375-103">Rapportera som färdig till en ID-nummertyrd plats från jobbkortenheten</span><span class="sxs-lookup"><span data-stu-id="e4375-103">Report as finished to a license plate controlled location from the Job card device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4375-104">Processen som kallas rapportera som färdig slutför färdiga produkter i en tillverkningsorder till lagret.</span><span class="sxs-lookup"><span data-stu-id="e4375-104">The process called Reporting as finished completes finished products on a production order to the inventory.</span></span> <span data-ttu-id="e4375-105">Om den färdiga produkten är aktiverad för de avancerade lagerprocesserna rapporteras produkten som färdig till en plats som kallas för produktionsutleveransplats.</span><span class="sxs-lookup"><span data-stu-id="e4375-105">If the finished product is enabled for the advanced warehouse processes, the product is reported as finished to a location called the production output location.</span></span> <span data-ttu-id="e4375-106">Information om hur du ställer in produktionsutleveransplats finns i [Plats för produktionsutleverans](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location)plats för produktions utmatning.</span><span class="sxs-lookup"><span data-stu-id="e4375-106">For information about setting up the production output location, see [Production output location](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/production-output-location).</span></span>

<span data-ttu-id="e4375-107">Om produktionens utgångsplats styrs av registreringsskylt, måste en registreringsskylt tillhandahållas vid rapportering som färdigt.</span><span class="sxs-lookup"><span data-stu-id="e4375-107">If the production output location is license plate controlled, then a license plate must be provided when reporting as finished.</span></span> <span data-ttu-id="e4375-108">Fältet **Registreringsskylt** visas i **Rapportera förlopp** på sidan **Jobbkortenhet**.</span><span class="sxs-lookup"><span data-stu-id="e4375-108">The **License plate** field is visible on the **Report progress** prompt on the **Job card device** page.</span></span> <span data-ttu-id="e4375-109">Fältet visas bara på frågan **rapportstatus** när du rapporterar om den senaste operationen i produktionsordern och artikeln för tillverkningsordern är aktiverad för lagerstyrningsprocesserna.</span><span class="sxs-lookup"><span data-stu-id="e4375-109">The field is only visible on the **Report progress** prompt when reporting on the last operation of the production order and the item for the production order is enabled for the warehouse management processes.</span></span>

<span data-ttu-id="e4375-110">Det finns två alternativ för att tillhandahålla registreringsskylten:</span><span class="sxs-lookup"><span data-stu-id="e4375-110">There are two options for providing the license plate:</span></span>

- <span data-ttu-id="e4375-111">Användaren väljer en befintlig registreringsskylt i fältet för registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="e4375-111">The user selects an existing license plate in the license plate field.</span></span>
- <span data-ttu-id="e4375-112">Registreringsskylten genereras automatiskt från en nummerserie och fallerar till fältet registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="e4375-112">The license plate is automatically generated from a number sequence and defaulted to the license plate field.</span></span>

<span data-ttu-id="e4375-113">Alternativet att låta registreringsskylten genereras automatiskt konfigureras genom att välja alternativet **Generera registreringsskylt** på sidan **konfigurera jobbkort för enheter**.</span><span class="sxs-lookup"><span data-stu-id="e4375-113">The option to have the license plate generated automatically is configured by selecting the option **Generate license plate** on the **Configure job card for devices** page.</span></span>
