---
title: Arkivera utskrivna kundfakturor med hash-nummer
description: I det här avsnittet beskrivs hur du aktiverar arkivering för att lagra utskrivna kundfakturor med hash-nummer.
author: ilyako
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 841e6059f5b0d70dbd1fe12a1f8910bbb31ddc86
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018988"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a><span data-ttu-id="673bd-103">Arkivera utskrivna kundfakturor med hash-nummer</span><span class="sxs-lookup"><span data-stu-id="673bd-103">Archive printed customer invoices with hash numbers</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="673bd-104">I vissa länder finns det ett juridiskt krav på att beräknade hash-nummer lagras i systemet tillsammans med utskrifter av vissa dokument.</span><span class="sxs-lookup"><span data-stu-id="673bd-104">In some countries, there is a legal requirement to store calculated hash numbers in the system together with printouts of some documents.</span></span> <span data-ttu-id="673bd-105">Hash-nummer kan användas för rapportering till myndigheter och under granskningar.</span><span class="sxs-lookup"><span data-stu-id="673bd-105">Hash numbers can be used for reporting to authorities and during audits.</span></span>

<span data-ttu-id="673bd-106">I det här avsnittet beskrivs hur du konfigurerar arkivering för att lagra utskrivna kundfakturor med hash-nummer.</span><span class="sxs-lookup"><span data-stu-id="673bd-106">This topic explains how to configure archiving in order to store printed customer invoices with hash numbers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="673bd-107">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="673bd-107">Prerequisites</span></span>

- <span data-ttu-id="673bd-108">I arbetsytan **funktionshantering** aktivera funktionen, **Arkivera utskrivna kundfakturor med hashnummer**.</span><span class="sxs-lookup"><span data-stu-id="673bd-108">In the **Feature management** workspace, turn on the feature, **Archive printed customer invoices with hash numbers**.</span></span> <span data-ttu-id="673bd-109">Mer information finns i [Översikt för funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="673bd-109">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="673bd-110">Konfigurera utskriftsbara formaten för de nödvändiga dokumenten i **Utskriftshantering**.</span><span class="sxs-lookup"><span data-stu-id="673bd-110">Configure the printable formats of required documents in **Print management**.</span></span>

<span data-ttu-id="673bd-111">Den här funktionen kan användas i följande dokument.</span><span class="sxs-lookup"><span data-stu-id="673bd-111">This functionality is applicable to the following documents.</span></span>

<span data-ttu-id="673bd-112">**Kundreskontra**</span><span class="sxs-lookup"><span data-stu-id="673bd-112">**Accounts receivable**</span></span>
- <span data-ttu-id="673bd-113">Kundfaktura</span><span class="sxs-lookup"><span data-stu-id="673bd-113">Customer invoice</span></span>
- <span data-ttu-id="673bd-114">Kundkreditfaktura</span><span class="sxs-lookup"><span data-stu-id="673bd-114">Customer credit note</span></span>
- <span data-ttu-id="673bd-115">Fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="673bd-115">Free text invoice</span></span>
- <span data-ttu-id="673bd-116">Fritextkreditfaktura</span><span class="sxs-lookup"><span data-stu-id="673bd-116">Free text credit note</span></span>

<span data-ttu-id="673bd-117">**Projekthantering och redovisning**</span><span class="sxs-lookup"><span data-stu-id="673bd-117">**Project management and accounting**</span></span>
- <span data-ttu-id="673bd-118">Projektfaktura</span><span class="sxs-lookup"><span data-stu-id="673bd-118">Project invoice</span></span>
- <span data-ttu-id="673bd-119">Projekts kreditfaktura</span><span class="sxs-lookup"><span data-stu-id="673bd-119">Project credit note</span></span>

## <a name="configure-customer-master-data"></a><span data-ttu-id="673bd-120">Konfigurera kundhuvuddata</span><span class="sxs-lookup"><span data-stu-id="673bd-120">Configure customer master data</span></span>
<span data-ttu-id="673bd-121">Gör på följande sätt om du vill konfigurera kunddata och aktivera möjligheten att spara utskrivna fakturor automatiskt som bilagor.</span><span class="sxs-lookup"><span data-stu-id="673bd-121">Complete the following steps to configure customer data and turn on the ability to automatically save printed invoices as attachments.</span></span>

1. <span data-ttu-id="673bd-122">Gå till **Leverantörsreskontra** > **Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="673bd-122">Go to **Accounts receivable** > **All customers**.</span></span> 
2. <span data-ttu-id="673bd-123">Markera en kund och på snabbfliken **Faktura och leverans** i avsnittet **E-FAKTURA** i fältet **eInvoice bilaga** välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="673bd-123">Select a customer, and on the **Invoice and delivery** FastTab, in the **E-INVOCE** section, in the **eInvoice attachment** field, select **Yes**.</span></span>

## <a name="print-invoices"></a><span data-ttu-id="673bd-124">Skriv ut fakturor</span><span class="sxs-lookup"><span data-stu-id="673bd-124">Print invoices</span></span>
<span data-ttu-id="673bd-125">Du kan bokföra och skriva ut fritext, kund och projektfaktura eller kreditfaktura för kunden som konfigurerats i föregående procedur.</span><span class="sxs-lookup"><span data-stu-id="673bd-125">You can post and print any free text, customer, and project invoice or credit note for the customer configured in the previous procedure.</span></span>

<span data-ttu-id="673bd-126">Öppna sidan **Bilagor** för den utskrivna fakturan.</span><span class="sxs-lookup"><span data-stu-id="673bd-126">Open the **Attachments** page for the printed invoice.</span></span> <span data-ttu-id="673bd-127">På snabbfliken **Bilaga** i fältgruppen **Ytterligare detaljer** i fältet **Dokumentets hash-numret**, hitta det lagrade hash-numret beräknat för den utskrivna fakturan.</span><span class="sxs-lookup"><span data-stu-id="673bd-127">On the **Attachment** FastTab, in the **Additional details** field group, in **Document hash number** field, find the stored hash number calculated for the printed invoice.</span></span>

![Bifogat hash-nummer](media/attach-hash-num.jpg)

