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
ms.openlocfilehash: 17ed1dcae97f6cd28175c483be5ca3ce96d59e05
ms.sourcegitcommit: 053f4cda6862fbcd9e3aa6e9cb009e7de833beac
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/28/2021
ms.locfileid: "5075748"
---
# <a name="global-withholding-tax"></a><span data-ttu-id="2423f-104">Global källskatt</span><span class="sxs-lookup"><span data-stu-id="2423f-104">Global withholding tax</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2423f-105">Detta ämne innehåller information om funktioner för global källskatt och förklarar hur du ställer in den.</span><span class="sxs-lookup"><span data-stu-id="2423f-105">This topic provides information about global withholding tax functionality and explains how to set it up.</span></span> <span data-ttu-id="2423f-106">Den nya funktionen är tillgänglig i version 10.0.17 och senare versioner.</span><span class="sxs-lookup"><span data-stu-id="2423f-106">The new functionality is available in version 10.0.17 and later.</span></span>

<span data-ttu-id="2423f-107">Den globala källskattefunktionen förbättras för leverantörs- och kundtransaktioner så att källskatt beräknas på artikelnivå.</span><span class="sxs-lookup"><span data-stu-id="2423f-107">Global withholding tax functionality is enhanced for vendor and customer transactions, so that withholding tax is calculated at the item level.</span></span> <span data-ttu-id="2423f-108">Saldot på källskattekontot från inköpstransaktioner kan kvittas genom att du kör betalningsjobbet för källskatt mot kvittningskontot för källskatt.</span><span class="sxs-lookup"><span data-stu-id="2423f-108">The balance in the withholding tax account from purchase transactions can be settled by running the withholding tax payment job against the withholding tax settlement account.</span></span>

> [!NOTE]
> <span data-ttu-id="2423f-109">Global källskatt har inte stöd för funktionen **Underhållsavgifter** på inköpsorder-, leverantörsfaktura- och försäljningsordersidorna.</span><span class="sxs-lookup"><span data-stu-id="2423f-109">Global withholding tax doesn't support the **Maintain charges** function on the purchase order, vendor invoice, and sales order pages.</span></span>

## <a name="turn-on-global-withholding-tax"></a><span data-ttu-id="2423f-110">Aktivera global källskatt</span><span class="sxs-lookup"><span data-stu-id="2423f-110">Turn on global withholding tax</span></span>

1. <span data-ttu-id="2423f-111">I arbetsytan **Funktionshantering** väljer du **Global källskatt** och sedan **Aktivera nu**.</span><span class="sxs-lookup"><span data-stu-id="2423f-111">In the **Feature management** workspace, select **Global withholding tax**, and then select **Enable now**.</span></span>
2. <span data-ttu-id="2423f-112">Gå till **Skatt \> Inställningar \> Parametrar \> Redovisningsparametrar** och sedan, på fliken **Källskatt**, anger du alternativet **Aktivera global källskatt** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="2423f-112">Go to **Tax \> Setup \> Parameters \> General ledger parameters**, and then, on the **Withholding tax** tab, set the **Enable global withholding tax** option to **Yes**.</span></span>
3. <span data-ttu-id="2423f-113">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="2423f-113">Select **Save**.</span></span>
4. <span data-ttu-id="2423f-114">Uppdatera sidan i webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="2423f-114">Refresh the page in your web browser.</span></span>

> [!NOTE]
> <span data-ttu-id="2423f-115">Funktionen för global källskatt kan inte aktiveras för länder/regioner där det redan finns lokala lösningar för källskatt.</span><span class="sxs-lookup"><span data-stu-id="2423f-115">Global withholding tax functionality can’t be turned on for countries/regions where localized withholding tax solutions already exist.</span></span> <span data-ttu-id="2423f-116">Dessa områden omfattar, men är inte begränsade till, Indien, Brasilien, Thailand, Saudiarabien, Irland, Storbritannien och USA.</span><span class="sxs-lookup"><span data-stu-id="2423f-116">These areas include but are not restricted to India, Brazil, Thailand, Saudi Arabia, Ireland, Great Britain and the United States.</span></span>
