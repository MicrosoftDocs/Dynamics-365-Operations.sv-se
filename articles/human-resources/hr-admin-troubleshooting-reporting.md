---
title: Rapporteringsalternativ
description: Det här avsnittet beskriver hur du löser problemet där en kund vill anpassa rapporter i Microsoft Dynamics 365 Human Resources eller skapa nya rapporter.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: 830c8c32128a8dfc1b009557afb272e48ae3a1ff
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114268"
---
# <a name="reporting-options"></a><span data-ttu-id="c778e-103">Rapporteringsalternativ</span><span class="sxs-lookup"><span data-stu-id="c778e-103">Reporting options</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="c778e-104">**Miljöinformation**</span><span class="sxs-lookup"><span data-stu-id="c778e-104">**Environment details**</span></span>

<span data-ttu-id="c778e-105">Det här problemet gäller alla miljöer.</span><span class="sxs-lookup"><span data-stu-id="c778e-105">This issue applies to all environments.</span></span>

<span data-ttu-id="c778e-106">**Symptom**</span><span class="sxs-lookup"><span data-stu-id="c778e-106">**Symptom**</span></span>

<span data-ttu-id="c778e-107">Kunden vill anpassa rapporter för Microsoft Dynamics 365 Human Resources eller skapa nya rapporter.</span><span class="sxs-lookup"><span data-stu-id="c778e-107">The customer wants to customize Microsoft Dynamics 365 Human Resources reports or create new reports.</span></span>

<span data-ttu-id="c778e-108">**Utleverans**</span><span class="sxs-lookup"><span data-stu-id="c778e-108">**Issue**</span></span>

<span data-ttu-id="c778e-109">Användaren kan inte anpassa inbäddade Microsoft Power BI-rapporter.</span><span class="sxs-lookup"><span data-stu-id="c778e-109">The user can't customize the embedded Microsoft Power BI reports.</span></span>

<span data-ttu-id="c778e-110">**Lösning**</span><span class="sxs-lookup"><span data-stu-id="c778e-110">**Solution**</span></span>

- <span data-ttu-id="c778e-111">Personal-data som flödar till Dataverse kan rapporteras via Power Apps Dataverse-kopplingen till Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="c778e-111">The Human Resources data that flows to Dataverse can be reported on via the Power Apps Dataverse connector to Power BI Desktop.</span></span> <span data-ttu-id="c778e-112">Observera att Dataverse innehåller en underuppsättning av Personal-data.</span><span class="sxs-lookup"><span data-stu-id="c778e-112">Note that Dataverse contains a subset of Human Resources data.</span></span> <span data-ttu-id="c778e-113">Mer information om Power BI och instrumentpaneler finns i [Skapa Power BI-rapporter och instrumentpaneler med Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span><span class="sxs-lookup"><span data-stu-id="c778e-113">For more information about Power BI and dashboards, see [Create Power BI reports and dashboards with Power Apps Common Data Service](https://powerapps.microsoft.com/blog/cdsconnectortopowerbi).</span></span>
- <span data-ttu-id="c778e-114">Elektronisk rapportering (ER) är tillgänglig för vissa rapporter i Personal.</span><span class="sxs-lookup"><span data-stu-id="c778e-114">Electronic reporting (ER) is available for some reports in Human Resources.</span></span> <span data-ttu-id="c778e-115">Kunddrivna anpassningar kan göras via ER-konfigurationsalternativ.</span><span class="sxs-lookup"><span data-stu-id="c778e-115">Customer-driven customizations can be done via the ER configuration options.</span></span>
- <span data-ttu-id="c778e-116">Data kan exporteras till Microsoft Excel eller Microsoft Word med hjälp av olika datatabeller som Personal tillhandahåller genom Microsoft Office-integrationen.</span><span class="sxs-lookup"><span data-stu-id="c778e-116">Data can be exported to Microsoft Excel or Microsoft Word by using the various data entities that Human Resources provides through the Microsoft Office integration.</span></span>

<span data-ttu-id="c778e-117">**Långsiktig lösning**</span><span class="sxs-lookup"><span data-stu-id="c778e-117">**Long-term solution**</span></span>

<span data-ttu-id="c778e-118">Ytterligare alternativ för Power BI kommer att bli tillgängliga och mer data och enheter kommer att ingå i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="c778e-118">Additional Power BI options will be available, and more data and entities will be part of Dataverse.</span></span>
