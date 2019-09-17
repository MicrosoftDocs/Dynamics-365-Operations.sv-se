---
title: Rapportalternativ i Talent
description: Det här avsnittet beskriver hur du löser problemet där en kund vill anpassa rapporter i Microsoft Dynamics 365 for Talent eller skapa nya rapporter.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 8e7348a515b08523c15aa8f74d5616a3daf645b7
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741808"
---
# <a name="reporting-options-in-talent"></a><span data-ttu-id="ee298-103">Rapportalternativ i Talent</span><span class="sxs-lookup"><span data-stu-id="ee298-103">Reporting options in Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ee298-104">**Miljöinformation**</span><span class="sxs-lookup"><span data-stu-id="ee298-104">**Environment details**</span></span>

<span data-ttu-id="ee298-105">Det här problemet gäller alla miljöer.</span><span class="sxs-lookup"><span data-stu-id="ee298-105">This issue applies to all environments.</span></span>

<span data-ttu-id="ee298-106">**Symptom**</span><span class="sxs-lookup"><span data-stu-id="ee298-106">**Symptom**</span></span>

<span data-ttu-id="ee298-107">Kunden vill anpassa rapporter för Microsoft Dynamics 365 for Talent eller skapa nya rapporter.</span><span class="sxs-lookup"><span data-stu-id="ee298-107">The customer wants to customize Microsoft Dynamics 365 for Talent reports or create new reports.</span></span>

<span data-ttu-id="ee298-108">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="ee298-108">**Issue**</span></span>

<span data-ttu-id="ee298-109">Användaren kan inte anpassa inbäddade Microsoft Power BI-rapporter.</span><span class="sxs-lookup"><span data-stu-id="ee298-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="ee298-110">**Lösning**</span><span class="sxs-lookup"><span data-stu-id="ee298-110">**Solution**</span></span>

- <span data-ttu-id="ee298-111">Core HR-data som flödar till Common Data Service kan rapporteras via PowerApps Common Data Service-kopplingen till Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="ee298-111">The Core HR data that flows to Common Data Service can be reported on via the PowerApps Common Data Service connector to Power BI Desktop.</span></span> <span data-ttu-id="ee298-112">Observera att Common Data Service innehåller en underuppsättning av Core HR-data.</span><span class="sxs-lookup"><span data-stu-id="ee298-112">Note that Common Data Service contains a subset of Core HR data.</span></span> <span data-ttu-id="ee298-113">Mer information om Power BI och instrumentpaneler finns i [Skapa Power BI-rapporter och instrumentpaneler med PowerApps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="ee298-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with PowerApps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="ee298-114">Elektronisk rapportering (ER) är tillgänglig för vissa rapporter i Talent.</span><span class="sxs-lookup"><span data-stu-id="ee298-114">Electronic reporting (ER) is available for some reports in Talent.</span></span> <span data-ttu-id="ee298-115">Kunddrivna anpassningar kan göras via ER-konfigurationsalternativ.</span><span class="sxs-lookup"><span data-stu-id="ee298-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="ee298-116">Data kan exporteras till Microsoft Excel eller Microsoft Word med hjälp av olika datatabeller som Talent tillhandahåller genom Microsoft Office-integrationen.</span><span class="sxs-lookup"><span data-stu-id="ee298-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Talent provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="ee298-117">**Långsiktig lösning**</span><span class="sxs-lookup"><span data-stu-id="ee298-117">**Long-term solution**</span></span>

<span data-ttu-id="ee298-118">Ytterligare alternativ för Power BI kommer att bli tillgängliga och mer data och enheter kommer att ingå i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ee298-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service.</span></span>
