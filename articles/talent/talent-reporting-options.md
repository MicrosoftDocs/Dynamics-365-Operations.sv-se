---
title: Rapportalternativ i Talent
description: "Det här avsnittet beskriver hur du löser problemet där en kund vill anpassa rapporter i Microsoft Dynamics 365 for Talent eller skapa nya rapporter."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 2007e6adec7255b0b3abda7490c2103a8583393f
ms.contentlocale: sv-se
ms.lasthandoff: 12/04/2018

---

# <a name="reporting-options-in-talent"></a><span data-ttu-id="84b36-103">Rapportalternativ i Talent</span><span class="sxs-lookup"><span data-stu-id="84b36-103">Reporting options in Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="84b36-104">**Miljöinformation**</span><span class="sxs-lookup"><span data-stu-id="84b36-104">**Environment details**</span></span>

<span data-ttu-id="84b36-105">Det här problemet gäller alla miljöer.</span><span class="sxs-lookup"><span data-stu-id="84b36-105">This issue applies to all environments.</span></span>

<span data-ttu-id="84b36-106">**Symptom**</span><span class="sxs-lookup"><span data-stu-id="84b36-106">**Symptom**</span></span>

<span data-ttu-id="84b36-107">Kunden vill anpassa rapporter för Microsoft Dynamics 365 for Talent eller skapa nya rapporter.</span><span class="sxs-lookup"><span data-stu-id="84b36-107">The customer wants to customize Microsoft Dynamics 365 for Talent reports or create new reports.</span></span>

<span data-ttu-id="84b36-108">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="84b36-108">**Issue**</span></span>

<span data-ttu-id="84b36-109">Användaren kan inte anpassa inbäddade Microsoft Power BI-rapporter.</span><span class="sxs-lookup"><span data-stu-id="84b36-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="84b36-110">**Lösning**</span><span class="sxs-lookup"><span data-stu-id="84b36-110">**Solution**</span></span>

- <span data-ttu-id="84b36-111">Core HR-data som flödar till Common Data Service för appar kan rapporteras via PowerApps CDS-kopplingen till Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="84b36-111">The Core HR data that flows to Common Data Service for Apps can be reported on via the PowerApps CDS connector to Power BI Desktop.</span></span> <span data-ttu-id="84b36-112">Observera att Common Data Service för appar innehåller en underuppsättning av Core HR-data.</span><span class="sxs-lookup"><span data-stu-id="84b36-112">Note that Common Data Service for Apps contains a subset of Core HR data.</span></span> <span data-ttu-id="84b36-113">Läs mer om Power BI och instrumentpaneler i [Skapa Power BI-rapporter och -instrumentpaneler med PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="84b36-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with PowerApps Common Data Service](https://powerapps.microsoft.com/en-us/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="84b36-114">Elektronisk rapportering (ER) är tillgänglig för vissa rapporter i Talent.</span><span class="sxs-lookup"><span data-stu-id="84b36-114">Electronic reporting (ER) is available for some reports in Talent.</span></span> <span data-ttu-id="84b36-115">Kunddrivna anpassningar kan göras via ER-konfigurationsalternativ.</span><span class="sxs-lookup"><span data-stu-id="84b36-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="84b36-116">Data kan exporteras till Microsoft Excel eller Microsoft Word med hjälp av olika datatabeller som Talent tillhandahåller genom Microsoft Office-integrationen.</span><span class="sxs-lookup"><span data-stu-id="84b36-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Talent provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="84b36-117">**Långsiktig lösning**</span><span class="sxs-lookup"><span data-stu-id="84b36-117">**Long-term solution**</span></span>

<span data-ttu-id="84b36-118">Ytterligare alternativ för Power BI kommer att bli tillgängliga och mer data och enheter kommer att ingå i Common Data Service för appar.</span><span class="sxs-lookup"><span data-stu-id="84b36-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service for Apps.</span></span>

