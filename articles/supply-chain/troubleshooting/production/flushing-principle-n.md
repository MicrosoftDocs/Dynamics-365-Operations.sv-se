---
title: Inställningarna för avräkningsprincipen på strukturlisterader respekteras inte
description: Inställningarna för avräkningsprincipen på strukturlisterader (BOM) respekteras inte.
author: johanhoffmann
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: PurchTable,ProdParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 84a84728016119a2a02f59f6903171afbceb48e7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026917"
---
# <a name="flushing-principle-settings-on-bom-lines-arent-respected"></a><span data-ttu-id="3686a-103">Inställningarna för avräkningsprincipen på strukturlisterader respekteras inte</span><span class="sxs-lookup"><span data-stu-id="3686a-103">Flushing principle settings on BOM lines aren't respected</span></span>

<span data-ttu-id="3686a-104">KB-nummer: 4612725</span><span class="sxs-lookup"><span data-stu-id="3686a-104">KB number: 4612725</span></span>

## <a name="symptoms"></a><span data-ttu-id="3686a-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="3686a-105">Symptoms</span></span>

<span data-ttu-id="3686a-106">Det här problemet uppstår när fältet **Automatisk BOM-konsumtion** under fliken **Automatisk uppdatering** på sidan **Produktionskontrollparametrar** är inställt på *Avräkningsprincip*.</span><span class="sxs-lookup"><span data-stu-id="3686a-106">This issue occurs when the **Automatic BOM consumption** field on the **Automatic update** tab of the **Production control parameters** page is set to *Flushing principle*.</span></span> <span data-ttu-id="3686a-107">Denna inställning visar att alla strukturlisterader (BOM) automatiskt ska förbrukas när en inköpsorder tas emot.</span><span class="sxs-lookup"><span data-stu-id="3686a-107">This setting indicates that all bill of materials (BOM) lines should automatically be consumed when a purchase order is received.</span></span> <span data-ttu-id="3686a-108">Om fältet **Avräkningsprincip** på BOM-rader har ställts in på *Manuellt*, kan du förvänta dig att BOM-raderna inte förbrukas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="3686a-108">If the **Flushing principle** field on BOM lines is explicitly set to *Manual*, you might expect that the BOM lines won't automatically be consumed.</span></span> <span data-ttu-id="3686a-109">När det här problemet uppstår förbrukas dock strukturlisterader där fältet **Avräkningsprincip** är inställt på *Manuellt* automatiskt.</span><span class="sxs-lookup"><span data-stu-id="3686a-109">However, when this issue occurs, BOM lines where the **Flushing principle** field is set to *Manual* are automatically consumed anyway.</span></span>

## <a name="resolution"></a><span data-ttu-id="3686a-110">Upplösning</span><span class="sxs-lookup"><span data-stu-id="3686a-110">Resolution</span></span>

<span data-ttu-id="3686a-111">Om du upplever det här problemet kan produktionskontrollparametrarna ställas in så att de åsidosätter inställningen för **Avräkningsprincip** på strukturlisterader.</span><span class="sxs-lookup"><span data-stu-id="3686a-111">If you're experiencing this issue, your production control parameters might be set up to override the **Flushing principle** setting on BOM lines.</span></span> <span data-ttu-id="3686a-112">På sidan **Produktionskontrollparametrar**, under fliken **Automatisk uppdatering**, kontrollerar du värdet för fältet **Automatisk strukturlisteförbrukning**.</span><span class="sxs-lookup"><span data-stu-id="3686a-112">On the **Production control parameters** page, on the **Automatic update** tab, check the value of the **Automatic BOM consumption** field.</span></span> <span data-ttu-id="3686a-113">Vid inställning på *Alltid* ignorerar systemet inställningen för **Avräkningsprincip** på alla strukturlisterader och avräknar alltid raderna.</span><span class="sxs-lookup"><span data-stu-id="3686a-113">If it's set to *Always*, the system will disregard the **Flushing principle** setting on all BOM lines and will always flush the lines.</span></span> <span data-ttu-id="3686a-114">Om du vill att systemet respekterar inställningen för **Avräkningsprincip** på strukturlisterader, ändrar du värdet för fältet **Automatisk strukturlisteförbrukning** till *Avräkningsprincip*.</span><span class="sxs-lookup"><span data-stu-id="3686a-114">To make the system respect the **Flushing principle** setting on BOM lines, change the value of the **Automatic BOM consumption** field to *Flushing principle*.</span></span>
