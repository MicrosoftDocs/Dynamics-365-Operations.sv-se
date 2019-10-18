---
title: Filformat för betalningsmetod
description: Det här avsnittet beskriver två metoder för att hämta de filformat som du kan använda för betalningsmetoder.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPaymMode, VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 262514
ms.search.region: Belgium, France, Germany, Norway, Spain, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 36f12fbc21fe782555c348f8a401e7aef6219f41
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183947"
---
# <a name="file-formats-for-methods-of-payment"></a><span data-ttu-id="cb83e-103">Filformat för betalningsmetod</span><span class="sxs-lookup"><span data-stu-id="cb83e-103">File formats for methods of payment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cb83e-104">Det här avsnittet beskriver två metoder för att hämta de filformat som du kan använda för betalningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="cb83e-104">This topic describes the two methods for getting file formats that you can use for methods of payment.</span></span>

<span data-ttu-id="cb83e-105">Det finns två sätt att få filformat som du kan använda med betalningsmetoder, filformat för elektronisk rapportering (ER) eller X++ -filformat.</span><span class="sxs-lookup"><span data-stu-id="cb83e-105">There are two methods that you can use to get file formats for use with methods of payment, electronic reporting (ER) file formats or X++ file formats.</span></span> <span data-ttu-id="cb83e-106">När du anger en betalningsmetod för en kund eller leverantör anger du vilka filformat och standarder som ska användas för betalningar och hur betalningar ska bearbetas.</span><span class="sxs-lookup"><span data-stu-id="cb83e-106">When you set up a method of payment for a customer or vendor, you indicate which file formats and standards should be used for payments and how payments will be processed.</span></span> <span data-ttu-id="cb83e-107">Du kan välja mellan följande format:</span><span class="sxs-lookup"><span data-stu-id="cb83e-107">You can select from the following types of formats:</span></span>

-   <span data-ttu-id="cb83e-108">Exportera</span><span class="sxs-lookup"><span data-stu-id="cb83e-108">Export</span></span>
-   <span data-ttu-id="cb83e-109">Importera</span><span class="sxs-lookup"><span data-stu-id="cb83e-109">Import</span></span>
-   <span data-ttu-id="cb83e-110">Retur</span><span class="sxs-lookup"><span data-stu-id="cb83e-110">Return</span></span>
-   <span data-ttu-id="cb83e-111">Remittering</span><span class="sxs-lookup"><span data-stu-id="cb83e-111">Remittance</span></span>

### <a name="method-1-electronic-reporting-file-formats"></a><span data-ttu-id="cb83e-112">Metod 1: Filformat för elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="cb83e-112">Method 1: Electronic reporting file formats</span></span>

<span data-ttu-id="cb83e-113">För filformat som baseras på ER-konfigurationer måste du importera konfigurationer från Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="cb83e-113">For file formats that are based on ER configurations, you must import the configurations from Lifecycle Services (LCS).</span></span> <span data-ttu-id="cb83e-114">Mer information finns i [Hämta elektroniska rapporteringskonfigurationer från Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="cb83e-114">For more information, see [Download Electronic reporting configurations from Lifecycle Services](../../dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span> <span data-ttu-id="cb83e-115">När du importerar rapporteringskonfigurationer för dess filformat, blir importerade format tillgängliga för val på sidan **Betalningsmetoder**.</span><span class="sxs-lookup"><span data-stu-id="cb83e-115">After you import reporting configurations for those file formats, the imported formats will be available to select on the **Methods of payment** page.</span></span> <span data-ttu-id="cb83e-116">Hur du importerar och väljer filformat för Europa liknar proceduren för Japan.</span><span class="sxs-lookup"><span data-stu-id="cb83e-116">The process for importing and selecting file formats for Europe is similar to the procedure for Japan.</span></span> <span data-ttu-id="cb83e-117">Mer information finns i [Aktivera JBA-betalningsfilformat](tasks/jba-payment-file-format.md)</span><span class="sxs-lookup"><span data-stu-id="cb83e-117">For more details, see [Enable the JBA payment file format](tasks/jba-payment-file-format.md)</span></span>

### <a name="method-2-x-file-formats"></a><span data-ttu-id="cb83e-118">Metod 2: X++ -filformat</span><span class="sxs-lookup"><span data-stu-id="cb83e-118">Method 2: X++ file formats</span></span>

<span data-ttu-id="cb83e-119">Gör följande om du vill välja filformat som baseras på X++ -kod.</span><span class="sxs-lookup"><span data-stu-id="cb83e-119">To select file formats that are based on X++ code, complete the following steps.</span></span>

1.  <span data-ttu-id="cb83e-120">Gå till sidan **Betalningsmetoder**.</span><span class="sxs-lookup"><span data-stu-id="cb83e-120">Go to the **Methods of payment** page.</span></span>
2.  <span data-ttu-id="cb83e-121">På snabbfliken **Filformat** klickar du på **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="cb83e-121">On the **File formats** FastTab, click **Setup**.</span></span>
3.  <span data-ttu-id="cb83e-122">Välj den flik som motsvarar filformatet.</span><span class="sxs-lookup"><span data-stu-id="cb83e-122">Select the tab that corresponds with the file format type.</span></span>
4.  <span data-ttu-id="cb83e-123">Välj ett filformat i listan **Tillgänglig** listan och flytta det till listan **Markerat** med pilkontrollen.</span><span class="sxs-lookup"><span data-stu-id="cb83e-123">Select a file format from the **Available** list and move it to the **Selected** list with the arrow control.</span></span>
5.  <span data-ttu-id="cb83e-124">Stäng sidan **Filformat för betalningsmetoder**.</span><span class="sxs-lookup"><span data-stu-id="cb83e-124">Close the **File formats for methods of payment** page.</span></span>
6.  <span data-ttu-id="cb83e-125">På snabbfliken **Filformat** väljer du det filformat som ska användas för betalningsmetoden i motsvarande filformatsfält.</span><span class="sxs-lookup"><span data-stu-id="cb83e-125">On the **File formats** FastTab, select the file format to use for the method of payment from the appropriate file format field.</span></span> <span data-ttu-id="cb83e-126">De allmänna alternativen för elektronisk rapportering bör anges som **Nej** for X++ -filformat.</span><span class="sxs-lookup"><span data-stu-id="cb83e-126">The General electronic reporting options should be set to **No** for X++ file formats.</span></span>




