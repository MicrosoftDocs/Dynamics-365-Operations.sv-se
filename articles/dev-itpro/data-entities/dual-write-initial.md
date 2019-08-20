---
title: Exekveringsorder för initial synkronisering av Finance and Operations och Common Data Service
description: Det här avsnittet anger ordningen för synkroniseringen som du måste följa för att skapa de ursprungliga data.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: b74bc2d3133af7e87663a4e6bafb8780e0a6a66f
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797308"
---
# <a name="execution-order-for-initial-sychronization-of-finance-and-operations-and-common-data-service"></a><span data-ttu-id="a5680-103">Exekveringsorder för initial synkronisering av Finance and Operations och Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a5680-103">Execution order for initial sychronization of Finance and Operations and Common Data Service</span></span>

<span data-ttu-id="a5680-104">Innan du använder dataintegrering måste du skapa de ursprungliga data som krävs för kunder, leverantörer och kontakter.</span><span class="sxs-lookup"><span data-stu-id="a5680-104">Before you use data integration, you must create the initial data required for customers, vendors and contacts.</span></span> <span data-ttu-id="a5680-105">Om du till exempel vill skapa en ny artikel för **leverantörsgrupp** och ange dess **betalningsvillkor** som **Net30**, innan du försöker skapa artikeln **leverantörsgrupp** se till att **Net30** finns i både Finance and Operations och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a5680-105">For example, if you want to create a new **Vendor group** item and set its **Terms of Payment** as **Net30**, then before you attempt to create the **Vendor group** item you need to make sure that **Net30** exists in both Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="a5680-106">(I framtiden kommer vi att släppa en funktion för dubbel skrivplattform som kallas **initial synkronisering**. Den kommer att göra en engångsdatasynkronisering mellan Finance and Operations och Common Data Service som en del av dubbel skriv-installationen.)</span><span class="sxs-lookup"><span data-stu-id="a5680-106">(In the future, we will release a  dual-write platform functionality called **Initial Sync**. It will do a one-time data synchronization between Finance and Operations and Common Data Service as part of the dual-write setup.)</span></span>

<span data-ttu-id="a5680-107">Tips: vi släpper en dubbel-skriv-karta för alla referensdata inklusive **betalningsvillkor** (betalningsvillkor).</span><span class="sxs-lookup"><span data-stu-id="a5680-107">Tips: We are releasing a dual-write map for all reference data including **Terms of Payment** (Payment Terms).</span></span> <span data-ttu-id="a5680-108">Om du redan har de ursprungliga data i ett system kan en liten uppdateringsåtgärd på en post utlösa dubbel-skriv på posten.</span><span class="sxs-lookup"><span data-stu-id="a5680-108">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span> 

<span data-ttu-id="a5680-109">Du måste följa följande prioritetsordning och kontrollera att de ursprungliga data är tillgängliga på både Finance and Operations och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a5680-109">You must follow the following order of precedence and make sure that the initial data is available on both Finance and Operations and Common Data Service.</span></span>   

## <a name="vendor"></a><span data-ttu-id="a5680-110">Leverantör</span><span class="sxs-lookup"><span data-stu-id="a5680-110">Vendor</span></span>

<span data-ttu-id="a5680-111">Orderutförande för leverantör är:</span><span class="sxs-lookup"><span data-stu-id="a5680-111">The order of execution for Vendor is:</span></span>

```
Vendor Group
    Terms of payment
        Payment day & lines
        Payment schedule
Vendor payment method
```

## <a name="customer-organization"></a><span data-ttu-id="a5680-112">Kund (organisation)</span><span class="sxs-lookup"><span data-stu-id="a5680-112">Customer (Organization)</span></span>

<span data-ttu-id="a5680-113">Orderutförande för kund är:</span><span class="sxs-lookup"><span data-stu-id="a5680-113">The order of execution for Customer is:</span></span>

```
Customer Group
    Terms of payment
        Payment day & lines
        Payment 
Customer payment method
```

## <a name="contact-person"></a><span data-ttu-id="a5680-114">Kontakt (person)</span><span class="sxs-lookup"><span data-stu-id="a5680-114">Contact (Person)</span></span>

<span data-ttu-id="a5680-115">Orderutförande för kontakt är:</span><span class="sxs-lookup"><span data-stu-id="a5680-115">The order of execution for Contact is:</span></span>

```
Customer
Vendor               
```
