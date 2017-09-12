---
title: "Ställ upp bedrägerivarningar"
description: "Det här avsnittet innehåller information om hur du ställer in regler för att varna kundtjänstrepresentanter om eventuell falsk information när order bearbetas. Du kan definiera särskilda koder som ska användas automatiskt eller manuellt för att spärra misstänkta order."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 09d80015298c3d0219b6ffb290dc456990536a62
ms.contentlocale: sv-se
ms.lasthandoff: 06/29/2017



---

# <a name="set-up-fraud-alerts"></a><span data-ttu-id="a8461-104">Ställ upp bedrägerivarningar</span><span class="sxs-lookup"><span data-stu-id="a8461-104">Set up fraud alerts</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="a8461-105">Det här avsnittet innehåller information om hur du ställer in regler för att varna kundtjänstrepresentanter om eventuell falsk information när order bearbetas.</span><span class="sxs-lookup"><span data-stu-id="a8461-105">This topic explains how to set up rules to alert customer service representatives of potentially fraudulent information when orders are processed.</span></span> <span data-ttu-id="a8461-106">Du kan definiera särskilda koder som ska användas automatiskt eller manuellt för att spärra misstänkta order.</span><span class="sxs-lookup"><span data-stu-id="a8461-106">You can define specific codes to use to automatically or manually put suspicious orders on hold.</span></span> 

<span data-ttu-id="a8461-107">Innan du installerar och använder bedrägeri kontroll regler, måste du aktivera bedrägeri kontroll och definiera grundläggande bedrägeri kontrollvärden i call center-parametrar.</span><span class="sxs-lookup"><span data-stu-id="a8461-107">Before you set up and use fraud checking rules, you must enable fraud checking and define the basic fraud checking values in the call center parameters.</span></span> <span data-ttu-id="a8461-108">Det finns två typer av bedrägerier regler:</span><span class="sxs-lookup"><span data-stu-id="a8461-108">There are two types of fraud rules:</span></span>

-   <span data-ttu-id="a8461-109">**Statiska regler** använder ett visst värde, t.ex. ett telefonnummer som har blivit svartlistad.</span><span class="sxs-lookup"><span data-stu-id="a8461-109">**Static rules** use a specific value, such as a phone number that has been blacklisted.</span></span>
-   <span data-ttu-id="a8461-110">**Dynamiska regler** kan bestå av variabler och villkor.</span><span class="sxs-lookup"><span data-stu-id="a8461-110">**Dynamic rules** can be composed from variables and conditions.</span></span>

<span data-ttu-id="a8461-111">Innan du skapar en dynamisk regel måste du skapa variabler och villkor som definierar som regeln gäller när regeln ska tillämpas.</span><span class="sxs-lookup"><span data-stu-id="a8461-111">Before you create a dynamic rule, you must create the variables and conditions that define who the rule applies to and when the rule should be applied.</span></span> <span data-ttu-id="a8461-112">Om du till exempel vill skapa en regel som kräver att alla order som kunden 1202 platser som är värda skrivaremarginaler eller mer parkeras tills kunden betalningen kan verifieras.</span><span class="sxs-lookup"><span data-stu-id="a8461-112">For example, you want to create a rule to require that any sales order that customer 1202 places that is worth 1,000.00 or more be put on hold until the customer payment can be verified.</span></span> <span data-ttu-id="a8461-113">I detta fall variablerna kund 1202 och totalt skrivaremarginaler.</span><span class="sxs-lookup"><span data-stu-id="a8461-113">In this case, the variables are customer 1202 and an order total of 1,000.00.</span></span> <span data-ttu-id="a8461-114">Villkoret anger att om kunden 1202 placerar en order, och det totala beloppet är lika med eller mer än skrivaremarginaler, försäljning order måste läggas på is tills kunden betalningen kan verifieras.</span><span class="sxs-lookup"><span data-stu-id="a8461-114">The condition specifies that if customer 1202 places an order, and the total amount of the order is equal to or more than 1,000.00, the sales order must be put on hold until the customer payment can be verified.</span></span>




