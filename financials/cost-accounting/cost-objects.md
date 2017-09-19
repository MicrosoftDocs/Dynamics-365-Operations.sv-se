---
title: Kostnadsobjektdimensioner
description: "När du analyserar kostnader använder du kostnadselementdimensioner för att definiera var kostnader flödar. Du använder kostnadsobjektdimensioner för att fastställa var du bör tilldela kostnader. Det här ämnet innehåller information om kostnadsobjektdimensioner."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 9e13fc9fa7e51a1299ca8698f581de979b680a7b
ms.openlocfilehash: ed6aa29234f8e9dc8dbb4835ec260adc538989d3
ms.contentlocale: sv-se
ms.lasthandoff: 09/18/2017

---

# <a name="cost-object-dimensions"></a><span data-ttu-id="24538-105">Kostnadsobjektdimensioner</span><span class="sxs-lookup"><span data-stu-id="24538-105">Cost object dimensions</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="24538-106">När du analyserar kostnader använder du kostnadselementdimensioner för att definiera var kostnader flödar.</span><span class="sxs-lookup"><span data-stu-id="24538-106">When you analyze costs, you use cost element dimensions to determine where costs flow to.</span></span> <span data-ttu-id="24538-107">Du använder kostnadsobjektdimensioner för att fastställa var du bör tilldela kostnader.</span><span class="sxs-lookup"><span data-stu-id="24538-107">You use cost object dimensions to determine where you should assign costs.</span></span> <span data-ttu-id="24538-108">Det här ämnet innehåller information om kostnadsobjektdimensioner.</span><span class="sxs-lookup"><span data-stu-id="24538-108">This topic provides information about cost object dimensions.</span></span>

<span data-ttu-id="24538-109">Ett kostnadsobjekt kan vara en typ av objekt som du vill beräkna, fördela kostnader till eller mäta direkt.</span><span class="sxs-lookup"><span data-stu-id="24538-109">A cost object can be any type of object that you want to estimate, allocate costs to, or measure directly.</span></span> <span data-ttu-id="24538-110">Typiska kostnadsobjekt inkluderar produkter, projekt, resurser, avdelningar, kostnadsställen och geografiska regioner.</span><span class="sxs-lookup"><span data-stu-id="24538-110">Typical cost objects include products, projects, resources, departments, cost centers, and geographical regions.</span></span> <span data-ttu-id="24538-111">Företagsledningen använder kostnadsobjekt till att kvantifiera kostnader och även till att köra lönsamhetsanalyser.</span><span class="sxs-lookup"><span data-stu-id="24538-111">Management uses cost objects to quantify costs and also to drive profitability analysis.</span></span>

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a><span data-ttu-id="24538-112">Kostnadsobjektdimensioner och kostnadsobjektets dimensionsmedlemmar</span><span class="sxs-lookup"><span data-stu-id="24538-112">Cost object dimensions and cost object dimension members</span></span>
<span data-ttu-id="24538-113">Kostnadobjekt kallas för *Kostnadsobjektdimensioner*</span><span class="sxs-lookup"><span data-stu-id="24538-113">Cost objects are known as *cost object dimensions*.</span></span> <span data-ttu-id="24538-114">När du har bestämt dig vilken enhet som kostnadsobjektdimensionen ska hänsvisa till, måste du ange de enskilda dimensionsvärdena eller importera dem från andra källsystem till Kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="24538-114">After you’ve decided which entity the cost object dimension should refer to, you must specify the individual dimension values or import them into Cost accounting from other source systems.</span></span> <span data-ttu-id="24538-115">Dessa enskilda dimensionsvärden kallas *Dimensionsmedlemmen för kostnadsobjekt*.</span><span class="sxs-lookup"><span data-stu-id="24538-115">These individual dimension values are known as *cost object dimension members*.</span></span> <span data-ttu-id="24538-116">Du kanske till exempel vill använda den ekonomiska dimension som Kostnadsställe som kostnadsobjektdimension.</span><span class="sxs-lookup"><span data-stu-id="24538-116">For example, you want to use the financial dimension that is named Cost center as the cost object dimension.</span></span> <span data-ttu-id="24538-117">Om du vill se hur kostnader flödar till de enskilda kostnadsställena, måste du importera dimensionsmedlemmarna för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="24538-117">To see how costs flow to the individual cost centers, you must import the cost object dimension members.</span></span> <span data-ttu-id="24538-118">I detta fall är dimensionsmedlemmarna för kostnadsobjekt de faktiska kostnadsställena, till exempel försäljning, produktion, administration och geografiska platser.</span><span class="sxs-lookup"><span data-stu-id="24538-118">In this case, the cost object dimension members are the actual cost centers, such as Sales, Production, Administration, and Geographic locations.</span></span> <span data-ttu-id="24538-119">Följande exempel visar en skärmdump av kostnadsställen som kostnadsobjektdimensionen med dess faktiska kostnadsställe som dimensionsmedlem för kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="24538-119">The following screenshot shows an example of Cost Centers as the cost object dimension with its actual cost centers as cost object dimension members.</span></span> 

<span data-ttu-id="24538-120">[![dimensioner-för-kostnadsobjekt](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)</span><span class="sxs-lookup"><span data-stu-id="24538-120">[![cost-object-dimensions](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)</span></span>

## <a name="import-cost-object-dimension-members-through-data-connectors"></a><span data-ttu-id="24538-121">Importera dimensionsmedlemmar för kostnadsobjekt via datakopplingar</span><span class="sxs-lookup"><span data-stu-id="24538-121">Import cost object dimension members through data connectors</span></span>
<span data-ttu-id="24538-122">Om du vill förenkla importen av dimensionsmedlemmar för kostnadsobjekt, använder du datakopplingar för att hämta värden från de enheter som du vill använda som kostnadsobjektdimensioner.</span><span class="sxs-lookup"><span data-stu-id="24538-122">To make the import of cost object dimension members easier, you use data connectors to retrieve the values from the entities that you want to use as cost object dimensions.</span></span> <span data-ttu-id="24538-123">Du kan använda antingen föruppbyggda datakopplingar eller anpassade datakopplingar som du skapar.</span><span class="sxs-lookup"><span data-stu-id="24538-123">You can use either the pre-built data connectors or custom data connectors that you build.</span></span>




