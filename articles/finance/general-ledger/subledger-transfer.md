---
title: Överför delredovisning till redovisningen
description: Det här ämnet beskriver funktionerna i Microsoft Dynamics 365 Finance som rör överföringsprocessen för delredovisningen i redovisningen.
author: roschlom
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: de9328f69938151c5558d41263d36b873d117e4b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975493"
---
# <a name="subledger-transfer-to-the-general-ledger"></a><span data-ttu-id="e59fd-103">Överför delredovisning till redovisningen</span><span class="sxs-lookup"><span data-stu-id="e59fd-103">Subledger transfer to the General ledger</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e59fd-104">I det här avsnittet beskrivs funktioner i Microsoft Dynamics 365 Finance som är relaterade till reglerna för överföring av delredovisningsjournalposter.</span><span class="sxs-lookup"><span data-stu-id="e59fd-104">This topic describes capabilities in Microsoft Dynamics 365 Finance that are related to the rules for transferring batches of subledger journal entries.</span></span>

<span data-ttu-id="e59fd-105">I version 8.1 gjordes ändringar för att tillåta överföring av regler, vilket föråldrade alternativet **Synkront**.</span><span class="sxs-lookup"><span data-stu-id="e59fd-105">In version 8.1, changes were made to allow the transfer of rules, which deprecated the **Synchronous** option.</span></span> <span data-ttu-id="e59fd-106">Mer information finns i [borttagna eller gamla funktioner för Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).</span><span class="sxs-lookup"><span data-stu-id="e59fd-106">For more information, see [Removed or deprecated features for Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).</span></span>

<span data-ttu-id="e59fd-107">Följande alternativ är tillgängliga för överföring av delredovisningsbatchar.</span><span class="sxs-lookup"><span data-stu-id="e59fd-107">The following options are available for transferring subledger batches.</span></span> 

 - <span data-ttu-id="e59fd-108">Asynkron – det här alternativet schemalägger omedelbart överföringen av delredovisningstransaktionerna till redovisningen.</span><span class="sxs-lookup"><span data-stu-id="e59fd-108">Asynchronous – This option will immediately schedule the transfer of the subledger accounting entries to the general ledger.</span></span> <span data-ttu-id="e59fd-109">Redovisningsverifikationen registreras så snart resurser är fria att bearbeta denna begäran på servern.</span><span class="sxs-lookup"><span data-stu-id="e59fd-109">The general ledger voucher will be recorded as soon as resources are free to process this request on the server.</span></span> 

- <span data-ttu-id="e59fd-110">Tidsplanerad batch – med det här alternativet läggs delredovisning poster för redovisningen till som överförs till bearbetningskön i redovisningen, där posterna kommer att bearbetas i inlevererade order.</span><span class="sxs-lookup"><span data-stu-id="e59fd-110">Scheduled batch – This option will add the subledger accounting entries that are being transferred to the processing queue in the general ledger, where the entries will be processed in order received.</span></span> <span data-ttu-id="e59fd-111">Redovisningsverifikationen registreras på den schemalagda tiden om resurser är fria att bearbeta detta batchjobb på servern.</span><span class="sxs-lookup"><span data-stu-id="e59fd-111">The general ledger voucher will be recorded at the scheduled time if resources are free to process this batch job on the server.</span></span> 
 
<span data-ttu-id="e59fd-112">I version 10.0.8 har förbättringar gjorts för att förbättra prestanda för alternativet Asynkront.</span><span class="sxs-lookup"><span data-stu-id="e59fd-112">In version 10.0.8, improvements were made to enhance the performance of the Asynchronous option.</span></span> <span data-ttu-id="e59fd-113">Den här funktionen aktiveras under funktionsnamnet **Prestandaoptimering för överföring av delredovisning till redovisning**.</span><span class="sxs-lookup"><span data-stu-id="e59fd-113">This feature is enabled under the feature name **Subledger transfer to General Ledger performance optimization**.</span></span> 
 
<span data-ttu-id="e59fd-114">Den här funktionen gör det enklare att överföra data från delredovisningen till redovisningen.</span><span class="sxs-lookup"><span data-stu-id="e59fd-114">This functionality improves the transfer of data from the subledger to the general ledger.</span></span> <span data-ttu-id="e59fd-115">Det gör att processen blir effektivare och grupper av mindre transaktioner som kan överföras till varandra.</span><span class="sxs-lookup"><span data-stu-id="e59fd-115">It allows the process to be more efficient, and it groups together sets of smaller transactions to transfer.</span></span> <span data-ttu-id="e59fd-116">På så sätt kan du använda batch-servern mer effektivt.</span><span class="sxs-lookup"><span data-stu-id="e59fd-116">This allows for a more efficient use of the batch server.</span></span> <span data-ttu-id="e59fd-117">Denna funktion kräver att batch-servern ställs in online och fungerar för att det asynkrona överföringsalternativet ska fungera.</span><span class="sxs-lookup"><span data-stu-id="e59fd-117">This functionality requires that the batch server be set up, online, and functioning in order for the Asynchronous transfer option to work.</span></span> 
