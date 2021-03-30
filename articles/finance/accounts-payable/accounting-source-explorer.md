---
title: Utforskare för redovisningskälla
description: Det här avsnittet innehåller information om utforskaren för redovisningskälla, som du kan använda för detaljerad analys av källinformation bakom redovisningsposter.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingSourceExplorer
audience: Application User
ms.reviewer: roschlom
ms.custom: 15391
ms.assetid: 57b95899-7298-43c0-8034-45b5d993cbf2
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7f92781a8e1400206f91f91c46c319b928e0010c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5250732"
---
# <a name="accounting-source-explorer"></a><span data-ttu-id="03e23-103">Utforskare för redovisningskälla</span><span class="sxs-lookup"><span data-stu-id="03e23-103">Accounting source explorer</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03e23-104">Det här avsnittet innehåller information om utforskaren för redovisningskälla, som du kan använda för detaljerad analys av källinformation bakom redovisningsposter.</span><span class="sxs-lookup"><span data-stu-id="03e23-104">This article provides information about Accounting source explorer, which you can use for detailed analysis of the source information behind general ledger accounting entries.</span></span>

<span data-ttu-id="03e23-105">Utforskaren för redovisningskälla är en ny sida som visar källinformation.</span><span class="sxs-lookup"><span data-stu-id="03e23-105">Accounting source explorer is a new page that shows source information.</span></span> <span data-ttu-id="03e23-106">Du kan använda utforskaren för redovisningskälla som ett fristående verktyg eller för att analysera detaljerna bakom kontoposterna i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="03e23-106">You can use Accounting source explorer either as a stand-alone tool or to analyze the details behind general ledger accounting entries.</span></span> <span data-ttu-id="03e23-107">Du kan exempelvis använda utforskaren för redovisningskällor för att få den mest detaljerade källinformationen för redovisningssaldo eller en verifikationstransaktion.</span><span class="sxs-lookup"><span data-stu-id="03e23-107">For example, you can use Accounting source explorer to get the most detailed source information for a balance in Trail balance or for a voucher transaction.</span></span> <span data-ttu-id="03e23-108">Du kan sedan använda funktionen för export till MS Excel för att titta noggrannare på informationen i Microsoft Excel (exempelvis i en pivottabell eller en pivotrapport).</span><span class="sxs-lookup"><span data-stu-id="03e23-108">You can then use the Export to MS Excel feature to further slice and dice the information in Microsoft Excel (for example, in a PivotTable or on a PivotTable report).</span></span>

<span data-ttu-id="03e23-109">Utforskaren för redovisningskälla visar alltid samma totalbelopp per huvudbokskonto som huvudboken visar (exempelvis i råbalansen).</span><span class="sxs-lookup"><span data-stu-id="03e23-109">Accounting source explorer always shows the same total amount per ledger account as General ledger shows (for example, in Trial balance).</span></span> <span data-ttu-id="03e23-110">I råbalansen kan du visa segment i olika kolumner.</span><span class="sxs-lookup"><span data-stu-id="03e23-110">As in Trial balance, you can display segments in separate columns.</span></span> <span data-ttu-id="03e23-111">Välj lämplig uppsättning av ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="03e23-111">Just select the appropriate financial dimension set.</span></span> 

<span data-ttu-id="03e23-112">Du kan använda parametrar för att definiera ett datumintervall för analysen.</span><span class="sxs-lookup"><span data-stu-id="03e23-112">You can use parameters to define a date interval for the analysis.</span></span> <span data-ttu-id="03e23-113">Denna funktion liknar också funktionen i råbalansen.</span><span class="sxs-lookup"><span data-stu-id="03e23-113">This functionality also resembles the functionality in Trial balance.</span></span>

<span data-ttu-id="03e23-114">För alla dokument som använder källdokumentet som ramverk, visar utforskaren för redovisningskälla ytterligare information baserat på redovisningsfördelningar samt, i tillämpliga fall, redovisningsfördelningar för projekt.</span><span class="sxs-lookup"><span data-stu-id="03e23-114">For all documents that use the source document framework, Accounting source explorer shows additional information, based on accounting distributions and, if applicable, project accounting distributions.</span></span> <span data-ttu-id="03e23-115">Denna information omfattar penningbeloppstyp, projekt, kategori, aktivitet och radegenskap.</span><span class="sxs-lookup"><span data-stu-id="03e23-115">This information includes the monetary amount type, project, activity, category, and line property.</span></span> <span data-ttu-id="03e23-116">Nedan följer några exempel på analyser som du kan göra:</span><span class="sxs-lookup"><span data-stu-id="03e23-116">Here are some examples of the analysis that you can do:</span></span>

-   <span data-ttu-id="03e23-117">Avvikelser mellan inköpsorder och leverantörsfakturor, eftersom varje avvikelse representeras av en typ av monetärt belopp, till exempel tilläggsavvikelse</span><span class="sxs-lookup"><span data-stu-id="03e23-117">Variances between purchase orders and vendor invoices, because each variance is represented by a monetary amount type, such as charge variance</span></span>
-   <span data-ttu-id="03e23-118">Fakturerbara kontra inte fakturerbara timmar och utgifter per projekt, affärsenhet och huvudkonto</span><span class="sxs-lookup"><span data-stu-id="03e23-118">Billable versus non-billable hours and expenses per project, business unit, and main account</span></span>

<span data-ttu-id="03e23-119">För källdokument som använder begreppet för källdokumentreferensidentiteter, visar källutforskaren även mer information, till exempel kund, leverantör, arbetare, produkt, kvantitet, enhettext och beskrivningar.</span><span class="sxs-lookup"><span data-stu-id="03e23-119">For source documents that use the source document reference identities concept, Accounting source explorer shows even more details, such as the customer, vendor, worker, product, quantity, unit text, and descriptions.</span></span> <span data-ttu-id="03e23-120">Nedan följer några exempel på analyser som du kan göra:</span><span class="sxs-lookup"><span data-stu-id="03e23-120">Here are some examples of the analysis that you can do:</span></span>

-   <span data-ttu-id="03e23-121">Hotellutgifter per affärsenhet och hotellkedjan för en räkenskapsperiod som baseras på utgiftsrapporter</span><span class="sxs-lookup"><span data-stu-id="03e23-121">Hotel expenses per business unit and hotel brand for a fiscal period, based on expense reports</span></span>
-   <span data-ttu-id="03e23-122">Rabatter per leverantör, produkt, avdelning</span><span class="sxs-lookup"><span data-stu-id="03e23-122">Discounts per vendor, product, department</span></span>

<span data-ttu-id="03e23-123">För dessa dokument kan du också navigera till det verkliga källdokumentet från utforskaren för redovisningskälla.</span><span class="sxs-lookup"><span data-stu-id="03e23-123">For these documents, you can also navigate to the actual source document from Accounting source explorer.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]