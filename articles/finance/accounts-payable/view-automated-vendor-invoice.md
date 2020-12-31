---
title: Visa resultat från automatisering av leverantörsfakturor (förhandsversion)
description: I det här avsnittet beskrivs hur du visar status för leverantörsfakturor som finns i den automatiska sändningen till arbetsflödesprocessen.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-09-08
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ec49a621e24b6373532497b499e8b9d45c9bed14
ms.sourcegitcommit: 30c541426cf2037b768e3556e1b170a64991f64a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/17/2020
ms.locfileid: "4448179"
---
# <a name="view-vendor-invoice-automation-results"></a><span data-ttu-id="fabcb-103">Visa resultat från automatisering av leverantörsfakturor</span><span class="sxs-lookup"><span data-stu-id="fabcb-103">View vendor invoice automation results</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fabcb-104">I det här avsnittet beskrivs hur du visar status för leverantörsfakturor som finns i den automatiska sändningen till arbetsflödesprocessen.</span><span class="sxs-lookup"><span data-stu-id="fabcb-104">This topic explains how to view the status of vendor invoices that are in the automated submit-to-workflow process.</span></span> <span data-ttu-id="fabcb-105">Information om automatiseringshistoriken underhålls för varje importerad leverantörsfaktura.</span><span class="sxs-lookup"><span data-stu-id="fabcb-105">Details of the automation history are maintained for each imported vendor invoice.</span></span> <span data-ttu-id="fabcb-106">Beroende på vilka affärsprocesser du har automatiserat visar sidan **Pågående leverantörsfakturor** värdena **Automatisk mottagningsstatus** och **Automatisk överföring till statusvärden för arbetsflöden**.</span><span class="sxs-lookup"><span data-stu-id="fabcb-106">Depending on the business processes that you've automated, the **Pending vendor invoices** page shows **Automated receipt match status** and **Automated submit to workflow status** values.</span></span> <span data-ttu-id="fabcb-107">Du kan visa detaljerna och göra en plan för att fokusera på fakturorna som misslyckades med ett automatiserat steg.</span><span class="sxs-lookup"><span data-stu-id="fabcb-107">You can view the details and make a plan to focus on the invoices that failed an automated step.</span></span> <span data-ttu-id="fabcb-108">När du har korrigerat problemet kan du sedan återuppta den automatiserade processen för den importerade fakturan.</span><span class="sxs-lookup"><span data-stu-id="fabcb-108">Then, after you correct the issue, you can resume the automated process for the imported invoice.</span></span>

<span data-ttu-id="fabcb-109">Innan du kan redigera en faktura som har skickats, måste du pausa den automatiska bearbetningen.</span><span class="sxs-lookup"><span data-stu-id="fabcb-109">Before you can edit an invoice that has been submitted, you must pause the automated processing.</span></span> <span data-ttu-id="fabcb-110">Om en faktura i den automatiska sändningen till arbetsflödesprocessen måste pausas, ställer du in flöden **inkludera i automatisk bearbetning** till **Nej** på sidan **Leverantörsfakturor**.</span><span class="sxs-lookup"><span data-stu-id="fabcb-110">If an invoice in the automated submit-to-workflow process must be paused, set the **Include in Automated processing** field to **No** on the **Vendor invoices** page.</span></span> <span data-ttu-id="fabcb-111">Automatiseringen körs inte förrän **inkludera i automatisk bearbetning** anges till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="fabcb-111">Automation then won't run until **Include in Automated processing** is set to **Yes**.</span></span> <span data-ttu-id="fabcb-112">En faktura kan pausas från ytterligare automatisering om den inte redan finns i arbetsflödessystemet och inte används av den automatiska processen.</span><span class="sxs-lookup"><span data-stu-id="fabcb-112">An invoice can be paused from further automation if it isn't yet in the workflow system and isn't used by the automated process.</span></span>

<span data-ttu-id="fabcb-113">Om en importerad faktura omfattas av sändningen av arbetsflödesprocessen kan du visa värdet **automatiseringsstatus** värde på sidan **leverantörsfakturor**.</span><span class="sxs-lookup"><span data-stu-id="fabcb-113">If an imported invoice is subject to the submit-to-workflow process, you can view its **Automation status** value on the **Vendor invoices** page.</span></span> <span data-ttu-id="fabcb-114">Följande statusvärden spåras:</span><span class="sxs-lookup"><span data-stu-id="fabcb-114">The following statuses are tracked:</span></span>

- <span data-ttu-id="fabcb-115">**Inkluderat** – de automatiserade processer som har definierats på sidan **parametrar för leverantörsreskontra** körs på rätt sätt men ännu inte slutförts.</span><span class="sxs-lookup"><span data-stu-id="fabcb-115">**Included** – The automated processes that are defined on the **Accounts payable parameters** page are running correctly but haven't yet been completed.</span></span>
- <span data-ttu-id="fabcb-116">**Pausad** – de automatiserade processer som har definierats på sidan **parametrar för leverantörsreskontra** har körts, men minst ett steg i processen misslyckades.</span><span class="sxs-lookup"><span data-stu-id="fabcb-116">**Paused** – The automated processes that are defined on the **Accounts payable parameters** page have run, but at least one step in the process failed.</span></span> <span data-ttu-id="fabcb-117">Statusen **Pausad** används även om fältet **inkludera i automatisk bearbetning** är inställt på **Nej**.</span><span class="sxs-lookup"><span data-stu-id="fabcb-117">The **Paused** status is also applied if the **Include in automated processing** field is set to **No**.</span></span> <span data-ttu-id="fabcb-118">Du kan visa felen genom att välja knappen **Visa senaste resultat**.</span><span class="sxs-lookup"><span data-stu-id="fabcb-118">You can view the failures by selecting **View most recent results**.</span></span>
- <span data-ttu-id="fabcb-119">**I arbetsflödet** – den importerade fakturan har skickats till arbetsflödessystemet, antingen genom den automatiska sändningen till arbetsflödesprocessen eller manuellt.</span><span class="sxs-lookup"><span data-stu-id="fabcb-119">**In workflow** – The imported invoice has been submitted to the workflow system, either by the automated submit-to-workflow process or manually.</span></span>
- <span data-ttu-id="fabcb-120">**Arbetsflödet slutfört** – arbetsflödesprocessen har slutförts för den importerade fakturan.</span><span class="sxs-lookup"><span data-stu-id="fabcb-120">**Workflow complete** – The workflow process has been completed for the imported invoice.</span></span>
