---
title: Fel fältvärde i TaxTrans
description: I detta ämne finns information om felsökning av felaktiga fältvärden i TaxTrans.
author: bijian
ms.date: 04/27/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 488ff54f1dd99208db940024a2fe8b2d25861f44
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020173"
---
# <a name="incorrect-field-value-in-taxtrans"></a><span data-ttu-id="56395-103">Fel fältvärde i TaxTrans</span><span class="sxs-lookup"><span data-stu-id="56395-103">Incorrect field value in TaxTrans</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="56395-104">Om ett fältvärde i **TaxTrans** är fel använder du informationen i detta ämne för att lösa problemet.</span><span class="sxs-lookup"><span data-stu-id="56395-104">If a field value in **TaxTrans** is incorrect, use the information in this topic to try to resolve the issue.</span></span>

## <a name="overview-of-values"></a><span data-ttu-id="56395-105">Översikt över värden</span><span class="sxs-lookup"><span data-stu-id="56395-105">Overview of values</span></span>
<span data-ttu-id="56395-106">I följande lista visas hur **TaxTrans**, **TaxUncommitted** och **TmpTaxWorkTrans** påminner om datauppsättningar men fungerar på olika sätt.</span><span class="sxs-lookup"><span data-stu-id="56395-106">The following list shows how **TaxTrans**, **TaxUncommitted**, and **TmpTaxWorkTrans** are similar data sets, but in work differently.</span></span>

  - <span data-ttu-id="56395-107">**TaxTrans** är det slutligt bokförda skattetransaktionsresultatet som finns kvar i databasen.</span><span class="sxs-lookup"><span data-stu-id="56395-107">**TaxTrans** is the final posted tax transaction result persisted in the database.</span></span>
  - <span data-ttu-id="56395-108">**TaxUncommitted** är det mellanliggande beräknade skatteresultatet som finns kvar i databasen (om tillämpligt) och som kommer att användas senare vid bokföring.</span><span class="sxs-lookup"><span data-stu-id="56395-108">**TaxUncommitted** is the intermediate calculated tax result persisted in the database (if applicable), which will be used later in posting.</span></span>
  - <span data-ttu-id="56395-109">**TmpTaxWorkTrans** är det tillfälligt beräknade skatteresultatet i registret i minnet (Registertyp = InMemory).</span><span class="sxs-lookup"><span data-stu-id="56395-109">**TmpTaxWorkTrans** is the temporary calculated tax result in the in-memory table (Table Type = InMemory).</span></span>

<span data-ttu-id="56395-110">Om du hittar rotorsaken till en felaktig **TaxTrans**-kolumn har du även funnit rotorsaken till en felaktig **TaxUncommitted**- eller **TmpTaxWorkTrans**-kolumn.</span><span class="sxs-lookup"><span data-stu-id="56395-110">If you find the root cause of an incorrect **TaxTrans** column, you've also found the root cause of an incorrect **TaxUncommitted** or **TmpTaxWorkTrans** column.</span></span> <span data-ttu-id="56395-111">Detta beror på att de tre kolumnerna kopieras från varandra.</span><span class="sxs-lookup"><span data-stu-id="56395-111">This is because the three columns are copied from each other.</span></span>

<span data-ttu-id="56395-112">I samband med skatteberäkning genereras vanligtvis **TmpTaxWorkTrans**, varefter **TaxUncommitted** genereras (om tillämpbart).</span><span class="sxs-lookup"><span data-stu-id="56395-112">Typically, during tax calculation, **TmpTaxWorkTrans** is generated, and then, if applicable, **TaxUncommitted** is generated.</span></span> <span data-ttu-id="56395-113">Under skattebokföringen genereras **TaxTrans**.</span><span class="sxs-lookup"><span data-stu-id="56395-113">During tax posting, **TaxTrans** is generated.</span></span>


## <a name="add-breakpoints"></a><span data-ttu-id="56395-114">Lägga till brytpunkter</span><span class="sxs-lookup"><span data-stu-id="56395-114">Add breakpoints</span></span>
<span data-ttu-id="56395-115">Utför följande steg för att lägga till brytpunkter:</span><span class="sxs-lookup"><span data-stu-id="56395-115">To add breakpoints, complete the following steps:</span></span> 

1. <span data-ttu-id="56395-116">Lägg till tillägg och brytpunkter i *insert()* och *update()* i tilläggen enligt nedan.</span><span class="sxs-lookup"><span data-stu-id="56395-116">Add extensions and breakpoints in *insert()* and *update()* in the extensions as shown below.</span></span>

     - <span data-ttu-id="56395-117">**TaxTrans**</span><span class="sxs-lookup"><span data-stu-id="56395-117">**TaxTrans**</span></span>

        ```x++
        [ExtensionOf(tableStr(TaxTrans))]
        public final class TaxTrans_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - <span data-ttu-id="56395-118">**TaxUncommitted**</span><span class="sxs-lookup"><span data-stu-id="56395-118">**TaxUncommitted**</span></span>

        ```x++
        [ExtensionOf(tableStr(TaxUncommitted))]
        public final class TaxUncommitted_Extension
        {
            public void insert()
            {
                next insert();
            }
        
            public void update()
            {
                next update();
            }
        
        }
        ```

     - <span data-ttu-id="56395-119">**TmpTaxWorkTrans**</span><span class="sxs-lookup"><span data-stu-id="56395-119">**TmpTaxWorkTrans**</span></span>

        ```x++
        [ExtensionOf(tableStr(TmpTaxWorkTrans))]
        public final class TmpTaxWorkTrans_Extension
        {
            public void insert(boolean _ignoreCalculatedSalesTax)
            {
                next insert(_ignoreCalculatedSalesTax);
            }
        
            public void update(boolean _ignoreCalculatedSalesTax)
            {
                next update(_ignoreCalculatedSalesTax);
            }
        
        }
        
        ```

2. <span data-ttu-id="56395-120">Du kan också lägga till brytpunkter direkt när **TaxUncommitted** inte ingår.</span><span class="sxs-lookup"><span data-stu-id="56395-120">Alternatively, you can add breakpoints directly when **TaxUncommitted** is not included.</span></span>

     - <span data-ttu-id="56395-121">*TaxTrans.insert()*, *TaxTrans.update()*</span><span class="sxs-lookup"><span data-stu-id="56395-121">*TaxTrans.insert()*, *TaxTrans.update()*</span></span>
     - <span data-ttu-id="56395-122">*TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*</span><span class="sxs-lookup"><span data-stu-id="56395-122">*TmpTaxWorkTrans.insert()*, *TmpTaxWorkTrans.update()*</span></span>

## <a name="reproduce-and-debug"></a><span data-ttu-id="56395-123">Återskapa och felsöka</span><span class="sxs-lookup"><span data-stu-id="56395-123">Reproduce and debug</span></span>

<span data-ttu-id="56395-124">När brytpunkter har ställts in visas varje databeständighetsändring under felsökningen.</span><span class="sxs-lookup"><span data-stu-id="56395-124">After the breakpoints are set, every data persistency change is visible during debugging.</span></span> <span data-ttu-id="56395-125">Om du vill hitta rotorsaken till en felaktig kolumn med **TaxTrans**, **TaxUncommitted** eller **TmpTaxWorkTrans**, kan du granska och observera följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="56395-125">To find the root cause of an incorrect column of **TaxTrans**, **TaxUncommitted**, or **TmpTaxWorkTrans**, review and note the following items:</span></span>

- <span data-ttu-id="56395-126">Den sista brytpunkten där kolumnen är korrekt.</span><span class="sxs-lookup"><span data-stu-id="56395-126">The last breakpoint where the column is correct.</span></span>
- <span data-ttu-id="56395-127">Den första brytpunkten där kolumnen är felaktig.</span><span class="sxs-lookup"><span data-stu-id="56395-127">The first breakpoint where the column is incorrect.</span></span>
- <span data-ttu-id="56395-128">Det som händer mellan dessa två poäng.</span><span class="sxs-lookup"><span data-stu-id="56395-128">What happens in between those two points.</span></span>

## <a name="determine-whether-customization-exists"></a><span data-ttu-id="56395-129">Bestäm om anpassning finns</span><span class="sxs-lookup"><span data-stu-id="56395-129">Determine whether customization exists</span></span>
<span data-ttu-id="56395-130">Om du har utfört stegen i de föregående avsnitten men inte har lyckats lösa problemet, ska du fastställa om det finns någon anpassning.</span><span class="sxs-lookup"><span data-stu-id="56395-130">If you've completed the steps in the previous sections but have not been able to resolve the issue, determine whether customization exists.</span></span> <span data-ttu-id="56395-131">Om det inte finns någon anpassning kontaktar du Microsoft Support för hjälp.</span><span class="sxs-lookup"><span data-stu-id="56395-131">If no customization exists, contact Microsoft Support for assistance.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

