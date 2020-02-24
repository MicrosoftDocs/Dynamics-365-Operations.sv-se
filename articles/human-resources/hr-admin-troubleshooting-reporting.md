---
title: Rapporteringsalternativ
description: Det här avsnittet beskriver hur du löser problemet där en kund vill anpassa rapporter i Microsoft Dynamics 365 Human Resources eller skapa nya rapporter.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9ee6dba5e37877f1c0b3b9df8306b3194ea2f3e4
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010671"
---
# <a name="reporting-options"></a><span data-ttu-id="cefa6-103">Rapporteringsalternativ</span><span class="sxs-lookup"><span data-stu-id="cefa6-103">Reporting options</span></span>

<span data-ttu-id="cefa6-104">**Miljöinformation**</span><span class="sxs-lookup"><span data-stu-id="cefa6-104">**Environment details**</span></span>

<span data-ttu-id="cefa6-105">Det här problemet gäller alla miljöer.</span><span class="sxs-lookup"><span data-stu-id="cefa6-105">This issue applies to all environments.</span></span>

<span data-ttu-id="cefa6-106">**Symptom**</span><span class="sxs-lookup"><span data-stu-id="cefa6-106">**Symptom**</span></span>

<span data-ttu-id="cefa6-107">Kunden vill anpassa rapporter för Microsoft Dynamics 365 Human Resources eller skapa nya rapporter.</span><span class="sxs-lookup"><span data-stu-id="cefa6-107">The customer wants to customize Microsoft Dynamics 365 Human Resources reports or create new reports.</span></span>

<span data-ttu-id="cefa6-108">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="cefa6-108">**Issue**</span></span>

<span data-ttu-id="cefa6-109">Användaren kan inte anpassa inbäddade Microsoft Power BI-rapporter.</span><span class="sxs-lookup"><span data-stu-id="cefa6-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="cefa6-110">**Lösning**</span><span class="sxs-lookup"><span data-stu-id="cefa6-110">**Solution**</span></span>

- <span data-ttu-id="cefa6-111">Personal-data som flödar till Common Data Service kan rapporteras via Power Apps Common Data Service-kopplingen till Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="cefa6-111">The Human Resources data that flows to Common Data Service can be reported on via the Power Apps Common Data Service connector to Power BI Desktop.</span></span> <span data-ttu-id="cefa6-112">Observera att Common Data Service innehåller en underuppsättning av Personal-data.</span><span class="sxs-lookup"><span data-stu-id="cefa6-112">Note that Common Data Service contains a subset of Human Resources data.</span></span> <span data-ttu-id="cefa6-113">Mer information om Power BI och instrumentpaneler finns i [Skapa Power BI-rapporter och instrumentpaneler med Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="cefa6-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="cefa6-114">Elektronisk rapportering (ER) är tillgänglig för vissa rapporter i Personal.</span><span class="sxs-lookup"><span data-stu-id="cefa6-114">Electronic reporting (ER) is available for some reports in Human Resources.</span></span> <span data-ttu-id="cefa6-115">Kunddrivna anpassningar kan göras via ER-konfigurationsalternativ.</span><span class="sxs-lookup"><span data-stu-id="cefa6-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="cefa6-116">Data kan exporteras till Microsoft Excel eller Microsoft Word med hjälp av olika datatabeller som Personal tillhandahåller genom Microsoft Office-integrationen.</span><span class="sxs-lookup"><span data-stu-id="cefa6-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Human Resources provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="cefa6-117">**Långsiktig lösning**</span><span class="sxs-lookup"><span data-stu-id="cefa6-117">**Long-term solution**</span></span>

<span data-ttu-id="cefa6-118">Ytterligare alternativ för Power BI kommer att bli tillgängliga och mer data och enheter kommer att ingå i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="cefa6-118">Additional Power BI options will be available, and more data and entities will be part of Common Data Service.</span></span>
