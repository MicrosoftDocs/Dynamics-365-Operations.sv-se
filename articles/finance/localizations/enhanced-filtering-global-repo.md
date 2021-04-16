---
title: RCS-utökad filtrering i den globala RCS-databasen
description: I det här avsnittet beskrivs förbättrade filtreringsfunktioner för den globala RCS-databasen, som har förbättrats för att inkludera ytterligare filter.
author: JaneA07
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERWorkspace
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 31df79159caa1094a68743ba07f308a2029e4071
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832654"
---
# <a name="rcs-enhanced-filtering-options-for-finding-configurations-in-the-rcsglobal-repository"></a><span data-ttu-id="70cae-103">RCS-utökade filtreringsalternativ för att hitta konfigurationer i RCS/globala databasen</span><span class="sxs-lookup"><span data-stu-id="70cae-103">RCS enhanced filtering options for finding configurations in the RCS/Global repository</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="70cae-104">I det här avsnittet beskrivs förbättrade filtreringsfunktioner för den globala RCS-databasen (Regulatory Configuration Services), som har förbättrats för att inkludera möjlighet att filtrera med följande kriterier:</span><span class="sxs-lookup"><span data-stu-id="70cae-104">This topic describes enhanced filtering capabilities for Regulatory Configuration Services (RCS) Global repository, which have been improved to include the ability to filter with the following criteria:</span></span> 
- <span data-ttu-id="70cae-105">**Land/region** – baserad på ISO-landskoder</span><span class="sxs-lookup"><span data-stu-id="70cae-105">**Country/region** - Based on ISO country codes</span></span>  
- <span data-ttu-id="70cae-106">**Tagga** typer för:</span><span class="sxs-lookup"><span data-stu-id="70cae-106">**Tags** types for:</span></span>
  - <span data-ttu-id="70cae-107">Funktionellt område</span><span class="sxs-lookup"><span data-stu-id="70cae-107">Functional area</span></span>
  - <span data-ttu-id="70cae-108">Funktionsområde</span><span class="sxs-lookup"><span data-stu-id="70cae-108">Feature area</span></span>
  - <span data-ttu-id="70cae-109">Bransch</span><span class="sxs-lookup"><span data-stu-id="70cae-109">Industry</span></span> 
  - <span data-ttu-id="70cae-110">Affärsdokument</span><span class="sxs-lookup"><span data-stu-id="70cae-110">Business document</span></span> 

<span data-ttu-id="70cae-111">För att göra det lättare att upptäcka specifika eller relaterade konfigurationer kan du använda filter, antingen individuellt eller som en grupp.</span><span class="sxs-lookup"><span data-stu-id="70cae-111">To make it easier to discover specific or related configurations you can apply filters, either individually or as a group.</span></span> <span data-ttu-id="70cae-112">Om du till exempel vill söka efter en enskild typ av "konfigurerbara affärsdokument som är relaterade till leverantörs fakturor, kan använda filtret **affärsdokumenttyp** för att söka efter den typen av dokument.</span><span class="sxs-lookup"><span data-stu-id="70cae-112">For example, to find a single type of 'configurable business documents that are related to vendor invoices, you could apply a **Business document type** filter to search for that type of document.</span></span> 

<span data-ttu-id="70cae-113">[![Filteravsnitt för global databas](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span><span class="sxs-lookup"><span data-stu-id="70cae-113">[![Filter section for Global repository](media/rcs-enhanced-filter-section.JPG)](./media/rcs-enhanced-filter-section.JPG)</span></span> 

<span data-ttu-id="70cae-114">Du kan förfina sökningen ytterligare genom att välja dokumenttyp, till exempel leverantörsfaktura och klicka på **Använd filter**.</span><span class="sxs-lookup"><span data-stu-id="70cae-114">You can further refine the search by selecting document type, for example 'vendor invoice' and clicking **Apply filter**.</span></span> <span data-ttu-id="70cae-115">I följande exempel visas resultatet när du filtrerar **affärsdokumenttypen** med dokumenttypen tillagd.</span><span class="sxs-lookup"><span data-stu-id="70cae-115">The following example shows the results when filtering on **Business document type** with the document type added.</span></span> 

<span data-ttu-id="70cae-116">[![Använt filter och importerar för affärsdokumenttyp](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span><span class="sxs-lookup"><span data-stu-id="70cae-116">[![Applied filter and Import for business document type](media/rcs-enhanced-filtering-applied.JPG)](./media/rcs-enhanced-filtering-applied.JPG)</span></span> 

<span data-ttu-id="70cae-117">Filtrerade resultat kan importeras till en användares RCS-databas eller en Dynamics 365 Finance-miljö, antingen individuellt eller som en uppsättning.</span><span class="sxs-lookup"><span data-stu-id="70cae-117">Filtered results can be imported into a users RCS repository or a Dynamics 365 Finance environment, either individually or as a set.</span></span> <span data-ttu-id="70cae-118">Det gör du genom att markera gruppen med konfigurationer och klicka på **importera**.</span><span class="sxs-lookup"><span data-stu-id="70cae-118">To do this, select the group of configurations, and click **Import**.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]