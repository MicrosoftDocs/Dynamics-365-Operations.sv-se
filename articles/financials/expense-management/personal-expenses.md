---
title: Privata utgifter i en utgiftsrapport
description: "Det här avsnittet beskriver två metoder för hantering av en medarbetares privata utgifter i Microsoft Dynamics 365 for Finance and Operations."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 11739c8b2979cf7ac9aad04e5be9903d6bc1837a
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---

# <a name="personal-expenses-on-an-expense-report"></a><span data-ttu-id="eea05-103">Privata utgifter i en utgiftsrapport</span><span class="sxs-lookup"><span data-stu-id="eea05-103">Personal expenses on an expense report</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="eea05-104">Under en affärsresa kanske medarbetare ibland debiterar sitt företagskreditkort för privata utgifter.</span><span class="sxs-lookup"><span data-stu-id="eea05-104">During business travel, workers might sometimes charge personal expenses to their corporate credit cards.</span></span> <span data-ttu-id="eea05-105">Om du inte har definierat någon process för hantering av privata utgifter kanske godkännandeprocessen för utgiftsrapporterna störs när medarbetare skickar sina specificerade utgiftsrapporter.</span><span class="sxs-lookup"><span data-stu-id="eea05-105">If you don't define a process for handling personal expenses, the approval process for expense reports might be disrupted when workers submit their itemized expense reports.</span></span> 

<span data-ttu-id="eea05-106">I Microsoft Dynamics 365 for Finance and Operations finns två metoder för hantering av en medarbetares privata utgifter:</span><span class="sxs-lookup"><span data-stu-id="eea05-106">In Microsoft Dynamics 365 for Finance and Operations, there are two methods for handling a worker's personal expenses:</span></span>

- <span data-ttu-id="eea05-107">**Betald av medarbetaren** – företaget betalar inte privata utgifter som visas på kreditkortsräkningen.</span><span class="sxs-lookup"><span data-stu-id="eea05-107">**Paid by employee** – Your organization doesn't pay personal expenses that appear on the bill for the corporate credit card.</span></span> <span data-ttu-id="eea05-108">I stället skapas en rapport med de privata utgifterna tillsammans med företagets utgifter som har debiterats kortet.</span><span class="sxs-lookup"><span data-stu-id="eea05-108">Instead, it creates a report that shows personal expenses together with the corporate expenses that were charged to the corporate credit card.</span></span>
- <span data-ttu-id="eea05-109">**Betalad av företaget** – Företaget betalar hela kreditkortsräkningen och debiterar sedan de privata utgifterna på medarbetarkontot.</span><span class="sxs-lookup"><span data-stu-id="eea05-109">**Paid by company** – Your organization pays the whole bill for the corporate credit card and then debits the worker's account for the personal expenses.</span></span>

<span data-ttu-id="eea05-110">Du kan välja den metod som används i din organisation på sidan **parametrar för utgiftshantering**.</span><span class="sxs-lookup"><span data-stu-id="eea05-110">You can select the method that your organization uses on the **Expense management parameters** page.</span></span>

