---
title: Metod för halvårs avskrivningspraxis
description: Det här ämnet beskriver den metod som anläggningstillgångar använder för att beräkna avskrivning med hjälp av halvårspraxis, som beräknar sex månader från avskrivningen under en tillgångs första och sista tjänstår.
author: moaamer
manager: Ann Beebe
ms.date: 08/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-17
ms.dyn365.ops.version: 10.0.12
ms.openlocfilehash: 6ec4c3a0bd86e15ee015fc2e2c49c92b035243b6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009303"
---
# <a name="half-year-depreciation-convention-methodology"></a><span data-ttu-id="21d11-103">Metod för halvårs avskrivningspraxis</span><span class="sxs-lookup"><span data-stu-id="21d11-103">Half-year depreciation convention methodology</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="21d11-104">I det här avsnittet beskrivs metoden som används i anläggningstillgångar för att beräkna avskrivning med hjälp av halvårspraxis.</span><span class="sxs-lookup"><span data-stu-id="21d11-104">This topic describes the method that is used in fixed assets to calculate depreciation using the half-year convention.</span></span> <span data-ttu-id="21d11-105">Halvårspraxis beräknar sex månader från avskrivningen under en tillgångs första och sista tjänstår.</span><span class="sxs-lookup"><span data-stu-id="21d11-105">The half-year convention calculates six months of depreciation during an asset’s first and last year of service.</span></span> <span data-ttu-id="21d11-106">Mer information finns om avskrivningspraxis finns i [Avskrivningsmetoder och avskrivningspraxis](Fixed-asset-depreciation-conventions.md).</span><span class="sxs-lookup"><span data-stu-id="21d11-106">For more information about depreciation conventions, see [Depreciation methods and conventions](Fixed-asset-depreciation-conventions.md).</span></span> 

<span data-ttu-id="21d11-107">När du använder avskrivningspraxis för sex månader använder systemet anskaffningsåret eller året som tillgången togs i bruk och därefter beräknas fem avskrivningsår från det året och därefter läggs sex månader till.</span><span class="sxs-lookup"><span data-stu-id="21d11-107">When you use the six-month depreciation convention, the system uses the acquisition year or the year that the asset was placed in service, then calculates five years of depreciation from that year, and then adds six months.</span></span> <span data-ttu-id="21d11-108">För att illustrera denna process bör du överväga en tillgång som har anskaffats för priset på 50 000 och som var i drift i april 2020.</span><span class="sxs-lookup"><span data-stu-id="21d11-108">To illustrate this process, consider an asset that was acquired for the price of 50,000, and placed in service in April 2020.</span></span> <span data-ttu-id="21d11-109">Anta också att tillgången har ett fem års tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="21d11-109">Also assume that the asset has a five-year service life.</span></span>

<span data-ttu-id="21d11-110">Det första året i tjänst kommer att ingå i december 2020, vilket innebär att slutet på till gångens fem års tjänstelivstid kommer att vara den 2024 december.</span><span class="sxs-lookup"><span data-stu-id="21d11-110">The first year of service will conclude in December 2020, which means the end of the asset’s five-year service life will be December 2024.</span></span> <span data-ttu-id="21d11-111">Halvårsvis avskrivningspraxis lägger till sex månader till tillgångens livslängd, vilket innebär att dess tjänstelivstid slutar i juni 2025.</span><span class="sxs-lookup"><span data-stu-id="21d11-111">The half-year depreciation convention will add six months to the asset’s life, which means its service life will end in June 2025.</span></span> 

> <span data-ttu-id="21d11-112">Årlig avskrivning 50 000/5 = 10 000 månatlig avskrivning 10000/12 = 833,33</span><span class="sxs-lookup"><span data-stu-id="21d11-112">Yearly depreciation 50,000/5 = 10,000 monthly depreciation 10,000/12 = 833.33</span></span> <br>
> <span data-ttu-id="21d11-113">Avskrivning första året 10 000/2 = 5 000 och den efterföljande månadsavskrivningen 5000/9 = 555,56</span><span class="sxs-lookup"><span data-stu-id="21d11-113">First year depreciation 10,000/2 = 5,000  and the subsequent monthly depreciation 5,000/9 = 555.56</span></span>

   <span data-ttu-id="21d11-114">[![Avskrivningsschema för halvårs avskrivningspraxis](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)</span><span class="sxs-lookup"><span data-stu-id="21d11-114">[![Depreciation schedule for half-year depreciation convention](./media/half-yr-dprectn-cnvntn.png)](./media/half-yr-dprectn-cnvntn.png)</span></span>

<span data-ttu-id="21d11-115">De utökade avskrivningsperioder som läggs till med halvårspraxis ger en mer korrekt fördelning av avskrivningen.</span><span class="sxs-lookup"><span data-stu-id="21d11-115">The extended depreciation periods that are added by the half-year convention provide more accurate allocation of depreciation.</span></span> <span data-ttu-id="21d11-116">Den sex månaders praxis representerar avskrivningskostnaderna mer jämt, vilket är användbart för rapportering av resultaträkningen.</span><span class="sxs-lookup"><span data-stu-id="21d11-116">The six-month convention represents depreciation expenses more equally, which is useful for reporting on the profit and loss statement.</span></span>
