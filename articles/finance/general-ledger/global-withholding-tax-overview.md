---
title: Global källskatt
description: Detta ämne innehåller information om funktioner för global källskatt och hur du ställer in den. Den globala källskattefunktionen förbättras för leverantörs- och kundtransaktioner så att källskatt beräknas på artikelnivå.
author: roschlom
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2020-01-12
ms.dyn365.ops.version: AX 10.0.16
ms.openlocfilehash: 25fc503d6145872b8e9f28b8d9a4d7b9c1ba53a4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249177"
---
# <a name="global-withholding-tax"></a><span data-ttu-id="0a560-104">Global källskatt</span><span class="sxs-lookup"><span data-stu-id="0a560-104">Global withholding tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0a560-105">Detta ämne innehåller information om funktioner för global källskatt och förklarar hur du ställer in den.</span><span class="sxs-lookup"><span data-stu-id="0a560-105">This topic provides information about global withholding tax functionality and explains how to set it up.</span></span> <span data-ttu-id="0a560-106">Den nya funktionen är tillgänglig i version 10.0.17 och senare versioner.</span><span class="sxs-lookup"><span data-stu-id="0a560-106">The new functionality is available in version 10.0.17 and later.</span></span>

<span data-ttu-id="0a560-107">Den globala källskattefunktionen förbättras för leverantörs- och kundtransaktioner så att källskatt beräknas på artikelnivå.</span><span class="sxs-lookup"><span data-stu-id="0a560-107">Global withholding tax functionality is enhanced for vendor and customer transactions, so that withholding tax is calculated at the item level.</span></span> <span data-ttu-id="0a560-108">Saldot på källskattekontot från inköpstransaktioner kan kvittas genom att du kör betalningsjobbet för källskatt mot kvittningskontot för källskatt.</span><span class="sxs-lookup"><span data-stu-id="0a560-108">The balance in the withholding tax account from purchase transactions can be settled by running the withholding tax payment job against the withholding tax settlement account.</span></span>

> [!NOTE]
> <span data-ttu-id="0a560-109">Global källskatt har inte stöd för funktionen **Underhållsavgifter** på inköpsorder-, leverantörsfaktura- och försäljningsordersidorna.</span><span class="sxs-lookup"><span data-stu-id="0a560-109">Global withholding tax doesn't support the **Maintain charges** function on the purchase order, vendor invoice, and sales order pages.</span></span>

## <a name="turn-on-global-withholding-tax"></a><span data-ttu-id="0a560-110">Aktivera global källskatt</span><span class="sxs-lookup"><span data-stu-id="0a560-110">Turn on global withholding tax</span></span>

1. <span data-ttu-id="0a560-111">I arbetsytan **Funktionshantering** väljer du **Global källskatt** och sedan **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="0a560-111">In the **Feature management** workspace, select **Global withholding tax**, and then select **Enable now**.</span></span>
2. <span data-ttu-id="0a560-112">Gå till **Skatt \> Inställningar \> Parametrar \> Redovisningsparametrar** och sedan, på fliken **Källskatt**, anger du alternativet **Aktivera global källskatt** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="0a560-112">Go to **Tax \> Setup \> Parameters \> General ledger parameters**, and then, on the **Withholding tax** tab, set the **Enable global withholding tax** option to **Yes**.</span></span>
3. <span data-ttu-id="0a560-113">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="0a560-113">Select **Save**.</span></span>
4. <span data-ttu-id="0a560-114">Uppdatera sidan i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="0a560-114">Refresh the page in your web browser.</span></span>

> [!NOTE]
> <span data-ttu-id="0a560-115">Funktionen för global källskatt kan inte aktiveras för länder/regioner där det redan finns lokala lösningar för källskatt.</span><span class="sxs-lookup"><span data-stu-id="0a560-115">Global withholding tax functionality can’t be turned on for countries/regions where localized withholding tax solutions already exist.</span></span> <span data-ttu-id="0a560-116">Dessa områden omfattar, men är inte begränsade till, Indien, Brasilien, Thailand, Saudiarabien, Irland, Storbritannien och USA.</span><span class="sxs-lookup"><span data-stu-id="0a560-116">These areas include but are not restricted to India, Brazil, Thailand, Saudi Arabia, Ireland, Great Britain and the United States.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]