---
title: Arbetsflöden för rabatthantering
description: I det här avsnittet beskrivs hur du ställer in ett arbetsflöde för rabatthantering när du vill godkänna och aktivera erbjudanden.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: ee342de6d069131e230120c5d65aef58da8e632a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020397"
---
# <a name="rebate-management-deal-workflows"></a><span data-ttu-id="4c296-103">Arbetsflöden för rabatthantering</span><span class="sxs-lookup"><span data-stu-id="4c296-103">Rebate management deal workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4c296-104">Om du vill godkänna rabatterbjudanden använder Rabatthantering samma arbetsflödesplattform som andra Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="4c296-104">To approve rebate deals, Rebate management uses the same workflow platform as other Finance and Operations apps.</span></span> <span data-ttu-id="4c296-105">Två jobbprocesser associeras med varje arbetsflöde:</span><span class="sxs-lookup"><span data-stu-id="4c296-105">Two job processes are associated with every workflow:</span></span>

- <span data-ttu-id="4c296-106">Ett element i arbetsflödet aktiverar affären så att användaren eller arbetsflödesprocessen kan godkänna transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="4c296-106">One element of the workflow activates the deal so that the user or workflow process can approve the transactions.</span></span>
- <span data-ttu-id="4c296-107">Ett element i arbetsflödet godkänner erbjudandet.</span><span class="sxs-lookup"><span data-stu-id="4c296-107">One element of the workflow approves the deal.</span></span>

<span data-ttu-id="4c296-108">Innan du kan använda ett rabattavtal måste det vara aktivt i modulen **Rabatthantering**.</span><span class="sxs-lookup"><span data-stu-id="4c296-108">Before you can use a rebate deal, it must be active in the **Rebate management** module.</span></span> <span data-ttu-id="4c296-109">Om du vill aktivera ett erbjudande måste du först skapa och konfigurera ett arbetsflöde för *rabatthantering*.</span><span class="sxs-lookup"><span data-stu-id="4c296-109">To activate a deal, you must first create and configure a *Rebate management deal workflow*.</span></span>

<span data-ttu-id="4c296-110">När ett arbetsflöde har aktiverats för Rabatthantering kan användarna inte godkänna erbjudanden manuellt.</span><span class="sxs-lookup"><span data-stu-id="4c296-110">After a workflow is activated for Rebate management, users can't manually approve deals.</span></span> <span data-ttu-id="4c296-111">Arbetsflödet måste alltid användas.</span><span class="sxs-lookup"><span data-stu-id="4c296-111">The workflow must be always used.</span></span>

## <a name="create-and-manage-rebate-management-deal-workflows"></a><span data-ttu-id="4c296-112">Skapa och hantera arbetsflöden för rabatthantering</span><span class="sxs-lookup"><span data-stu-id="4c296-112">Create and manage Rebate management deal workflows</span></span>

<span data-ttu-id="4c296-113">För att arbeta med dina arbetsflöden för rabatthantering, gå till **Rabatthantering \> Inställningar \> Arbetsflöden för rabatthantering**.</span><span class="sxs-lookup"><span data-stu-id="4c296-113">To work with your Rebate management deal workflows, go to **Rebate management \> Setup \> Rebate management workflows**.</span></span> <span data-ttu-id="4c296-114">Där kan du visa, skapa och uppdatera arbetsflöden efter behov.</span><span class="sxs-lookup"><span data-stu-id="4c296-114">There, you can view, create, and update workflows as required.</span></span> <span data-ttu-id="4c296-115">Endast ett arbetsflöde av denna typ kan vara aktiv åt gången.</span><span class="sxs-lookup"><span data-stu-id="4c296-115">Only one workflow of this type can be active at a time.</span></span> <span data-ttu-id="4c296-116">Mer information om arbetsflöden, hur du arbetar med sidan **Arbetsflöden för rabatthantering** och hur du skapar arbetsflöden finns i [översikten över arbetsflödessystem](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) och dess relaterade avsnitt.</span><span class="sxs-lookup"><span data-stu-id="4c296-116">For more information about workflows, how to work with the **Rebate management workflows** page, and how to create workflows, see [Workflow system overview](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) and its related topics.</span></span>

## <a name="use-a-workflow-to-activate-a-deal"></a><span data-ttu-id="4c296-117">Använd ett arbetsflöde för att aktivera ett erbjudande</span><span class="sxs-lookup"><span data-stu-id="4c296-117">Use a workflow to activate a deal</span></span>

<span data-ttu-id="4c296-118">Om du vill aktivera ett erbjudande via ett arbetsflöde öppnar du erbjudandet (till exempel på sidan **Alla rabatthanteringserbjudanden**).</span><span class="sxs-lookup"><span data-stu-id="4c296-118">To activate a deal through a workflow, open the deal (for example, on the **All rebate management deals** page).</span></span> <span data-ttu-id="4c296-119">Sedan i åtgärdsfönstret, välj **Arbetsflöde \> Skicka**.</span><span class="sxs-lookup"><span data-stu-id="4c296-119">Then, on the Action Pane, select **Workflow \> Submit**.</span></span> <span data-ttu-id="4c296-120">När det nya erbjudandet har bearbetats och godkänts i arbetsflödet är den aktiv och klar att användas.</span><span class="sxs-lookup"><span data-stu-id="4c296-120">After the new deal has been processed and approved through the workflow, it will be active and ready to use.</span></span>

<span data-ttu-id="4c296-121">När ett erbjudande har aktiverats kan du inte ändra dess inställningar.</span><span class="sxs-lookup"><span data-stu-id="4c296-121">After a deal has been activated, you can't change its setup.</span></span> <span data-ttu-id="4c296-122">Om du måste ändra ett aktivt erbjudande, inaktivera det och skapa sedan ett nytt erbjudande.</span><span class="sxs-lookup"><span data-stu-id="4c296-122">If you must change an active deal, inactivate it, and then create a new deal.</span></span> <span data-ttu-id="4c296-123">Om den nya affären ska liknar det gamla erbjudandet kan du skapa det genom att kopiera det gamla erbjudandet.</span><span class="sxs-lookup"><span data-stu-id="4c296-123">If the new deal will resemble the old deal, you can create it by copying the old deal.</span></span>
