---
title: "Periodisering av projektkostnad på inköpsinleveranser"
description: "I det här avsnittet beskrivs hur upplupna projektkostnader från inköpsinleveranser kan spåras i Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostControlCommittedCost
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 266984
ms.assetid: 61e7d2a3-5aab-4113-bccc-213f932885d2
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: bc822652abbba68f094fe5b8a65f796165a92c4c
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---

# <a name="project-cost-accrual-on-purchase-receipts"></a><span data-ttu-id="03e1e-103">Periodisering av projektkostnad på inköpsinleveranser</span><span class="sxs-lookup"><span data-stu-id="03e1e-103">Project cost accrual on purchase receipts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03e1e-104">I det här avsnittet beskrivs hur upplupna projektkostnader från inköpsinleveranser kan spåras i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="03e1e-104">This topic describes how accrued project costs from purchase receipts can be tracked in Microsoft Dynamics 365 for Finance and Operations.</span></span> 

<span data-ttu-id="03e1e-105">Fakturor för ett projekt kommer ofta senare än varorna och tjänster som levereras, vilket betydligt kan påverka projektets nyckeltal (KPI:er).</span><span class="sxs-lookup"><span data-stu-id="03e1e-105">Invoices for a project often arrive later than the goods and services are delivered, which might have a significant impact on project key performance indicators (KPIs).</span></span> <span data-ttu-id="03e1e-106">Det är viktigt att kunna spåra transaktionerna i både ekonomiska rapporter och projektrapporter.</span><span class="sxs-lookup"><span data-stu-id="03e1e-106">It important to be able to track these transactions in both financial and project reports.</span></span>

<span data-ttu-id="03e1e-107">I följande exempelscenarion illustreras detta.</span><span class="sxs-lookup"><span data-stu-id="03e1e-107">The following example scenario illustrates this.</span></span> 

<span data-ttu-id="03e1e-108">Contoso Consulting har påbörjat ett nytt molndistributionsprojekt.</span><span class="sxs-lookup"><span data-stu-id="03e1e-108">Contoso Consulting has started a new cloud deployment project.</span></span> <span data-ttu-id="03e1e-109">En inköpsorder skapas för att köpa en dator för projektet.</span><span class="sxs-lookup"><span data-stu-id="03e1e-109">A purchase order is created to buy a computer for the project.</span></span> <span data-ttu-id="03e1e-110">Datorn kommer att kosta $1500 och installationstjänster kostar $150.</span><span class="sxs-lookup"><span data-stu-id="03e1e-110">The computer will cost $1500 and installation services will cost $150.</span></span> <span data-ttu-id="03e1e-111">Leverantören har levererat och installerat datorn, men fakturan har ännu inte nått Contoso Consulting.</span><span class="sxs-lookup"><span data-stu-id="03e1e-111">The vendor has delivered and installed the computer, but the invoice has not yet reached Contoso Consulting.</span></span> <span data-ttu-id="03e1e-112">Projektledaren vill se de upplupna projektkostnaden på $1650 innan fakturan levereras.</span><span class="sxs-lookup"><span data-stu-id="03e1e-112">The project manager would like to see project cost accrual of $1650 before the invoice gets delivered.</span></span> <span data-ttu-id="03e1e-113">Kostnaden bör även återspeglas i företagets månadsslutet bokslut.</span><span class="sxs-lookup"><span data-stu-id="03e1e-113">This cost should also be reflected in the company's month end financial statements.</span></span> 

<span data-ttu-id="03e1e-114">Upplupen kostnad måste registreras på både ekonomisk nivå och projektnivå för rapportering.</span><span class="sxs-lookup"><span data-stu-id="03e1e-114">The accrued cost needs to be recorded on both the financial level and project level for reporting purposes.</span></span> <span data-ttu-id="03e1e-115">I Finance and Operations kan den ekonomiska uppdateringen av produktinleveransen spåras för artikeln och upphandlingskategorier.</span><span class="sxs-lookup"><span data-stu-id="03e1e-115">In Finance and Operations, the financial update of the product receipt can be tracked for the item and procurement categories.</span></span> 

<span data-ttu-id="03e1e-116">För artiklar, på sidan **Parametrar för leverantörsreskontra**, anger du alternativet **Bokför produktinleveranser i redovisningen**.</span><span class="sxs-lookup"><span data-stu-id="03e1e-116">For items, on the **Accounts payable parameters** page, select the **Post product receipts to ledger** option.</span></span>
<span data-ttu-id="03e1e-117">[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png)</span><span class="sxs-lookup"><span data-stu-id="03e1e-117">[![accruals1](./media/accruals1-1024x409.png)](./media/accruals1.png)</span></span> 

<span data-ttu-id="03e1e-118">För upphandlingskategorier, på sidan **Kategoripolicyregel**, väljer du **Inköp**-principer och väljer sedan **Periodisera inköpskostnad vid inleverans** för varje anskaffningskategori.</span><span class="sxs-lookup"><span data-stu-id="03e1e-118">For procurement categories, on the **Category policy rule** page, select **Purchasing** policies, and then select **Accrue purchase expense on receipt** for each procurement category.</span></span>
<span data-ttu-id="03e1e-119">[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png)</span><span class="sxs-lookup"><span data-stu-id="03e1e-119">[![accruals2](./media/accruals2-1024x569.png)](./media/accruals2.png)</span></span> 

<span data-ttu-id="03e1e-120">Kontona **Inköpsomkostnad, ej fakturerad** och **Inköp, periodisering** i **Inställningar för bokföring** kommer att användas när verifikationer som är relaterade till produktinleveransen bokförs.</span><span class="sxs-lookup"><span data-stu-id="03e1e-120">The **Purchase expenditure un-invoiced** and **Purchase accrual** accounts in **Posting setup** will be used when vouchers that are related to the product receipt are posted.</span></span>
<span data-ttu-id="03e1e-121">[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png)</span><span class="sxs-lookup"><span data-stu-id="03e1e-121">[![accruals3](./media/accruals3-1024x429.png)](./media/accruals3.png)</span></span> 

<span data-ttu-id="03e1e-122">Med samma scenariot ska vi titta på hur bokföring av en produktinleverans påverkar redovisningen och projektinformationen.</span><span class="sxs-lookup"><span data-stu-id="03e1e-122">Using this same scenario, let's see how posting a product receipt will impact General ledger and Project information.</span></span> 

<span data-ttu-id="03e1e-123">**Steg 1:** Skapa och bekräfta en ny inköpsorder för att projektet för att registrera inköp av en dator för $1500 och installationstjänster för $150.</span><span class="sxs-lookup"><span data-stu-id="03e1e-123">**Step 1:** Create and confirm a new purchase order for the project to record the purchase of a computer for $1500 and installation services for $150.</span></span>
<span data-ttu-id="03e1e-124">[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png)</span><span class="sxs-lookup"><span data-stu-id="03e1e-124">[![accruals4](./media/accruals4-1024x497.png)](./media/accruals4.png)</span></span> 

<span data-ttu-id="03e1e-125">När inköpsordern har bekräftats skapas transaktioner för utfästa kostnader för projektet.</span><span class="sxs-lookup"><span data-stu-id="03e1e-125">When the purchase order is confirmed, transactions for the committed cost are created for the project.</span></span> 
<span data-ttu-id="03e1e-126">[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png)</span><span class="sxs-lookup"><span data-stu-id="03e1e-126">[![accruals5](./media/accruals5-1024x219.png)](./media/accruals5.png)</span></span> 

> [!NOTE]
> <span data-ttu-id="03e1e-127">Transaktionerna för de utfästa kostnaderna har fältet **Transaktionsursprung** inställt på **Inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="03e1e-127">The transactions for the committed cost will have the **Transaction Origin** field set to **Purchase Order**.</span></span> <span data-ttu-id="03e1e-128">Skapa och bekräfta en inköpsorder skapar inte transaktioner för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="03e1e-128">Creating and confirming a purchase order does not create transactions for a project.</span></span> 

<span data-ttu-id="03e1e-129">**Steg 2:** Varor och tjänster levereras och en produktinleverans registreras.</span><span class="sxs-lookup"><span data-stu-id="03e1e-129">**Step 2:** Goods and services get delivered and a product receipt is registered.</span></span> 

<span data-ttu-id="03e1e-130">Bokför en produktinleverans skapar och bokför en verifikation i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="03e1e-130">Posting a product receipt will generate and post a voucher to the ledger.</span></span> <span data-ttu-id="03e1e-131">Verifikationen debiterar inköpsutgiften, ofakturerat konto och krediterar kontot för inköpsperiodiseringen.</span><span class="sxs-lookup"><span data-stu-id="03e1e-131">The voucher will debit the purchase expenditure, un-invoiced account, and credit purchase accrual account.</span></span> 
<span data-ttu-id="03e1e-132">[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)</span><span class="sxs-lookup"><span data-stu-id="03e1e-132">[![accruals6](./media/accruals6-1024x214.png)](./media/accruals6.png)</span></span>

> [!NOTE]
> <span data-ttu-id="03e1e-133">Bokför en produktinleverans använder bokföringsinställningar för anskaffningskategorier och produkter, inte bokföringsinställningarna för projektkategorier.</span><span class="sxs-lookup"><span data-stu-id="03e1e-133">Posting a product receipt will use the posting setup for procurement categories and products, and not the posting setup for the project categories.</span></span> <span data-ttu-id="03e1e-134">För att korrekt återspegla den ekonomiska effekten av inköpsperiodiseringar, måste denna inställning justeras.</span><span class="sxs-lookup"><span data-stu-id="03e1e-134">In order to correctly reflect financial impact of purchase accruals, this setup needs to be aligned.</span></span> 

<span data-ttu-id="03e1e-135">Du kan mappa anskaffningskategorier till projektkategorier på sidan **Anskaffningskategori**.</span><span class="sxs-lookup"><span data-stu-id="03e1e-135">It is possible to map procurement categories to project categories on the **Procurement category** page.</span></span>
<span data-ttu-id="03e1e-136">[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)</span><span class="sxs-lookup"><span data-stu-id="03e1e-136">[![accruals7](./media/accruals7-1024x390.png)](./media/accruals7.png)</span></span>

<span data-ttu-id="03e1e-137">**Steg 3:** Skapa ett utkast till leverantörsfaktura.</span><span class="sxs-lookup"><span data-stu-id="03e1e-137">**Step 3:** Create a draft vendor invoice.</span></span> 

<span data-ttu-id="03e1e-138">I Finance and Operations påverkar bokföringen av en produktinleverans inte projektinformationen.</span><span class="sxs-lookup"><span data-stu-id="03e1e-138">In Finance and Operations, posting a product receipt does not impact project information.</span></span> <span data-ttu-id="03e1e-139">Som tillfällig lösning kan du generera du ett utkast till leverantörsfaktura direkt när inleveransen har bokförts.</span><span class="sxs-lookup"><span data-stu-id="03e1e-139">As a workaround, you could generate a draft vendor invoice right after posting the purchase receipt.</span></span> <span data-ttu-id="03e1e-140">Gå till sidan **Inköpsorder** &gt; **fliken Faktura** &gt; **Generera** &gt; **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="03e1e-140">Go to the **Purchase Order** page &gt; **Invoice tab** &gt; **Generate** &gt; **Invoice**.</span></span> <span data-ttu-id="03e1e-141">Då skapas ett väntande fakturadokumentet som uppdaterar projektinformation.</span><span class="sxs-lookup"><span data-stu-id="03e1e-141">This creates a pending invoice document that updates project information.</span></span> 

<span data-ttu-id="03e1e-142">När ett utkast till leverantörsfaktura skapas genereras pågående projekttransaktioner.</span><span class="sxs-lookup"><span data-stu-id="03e1e-142">Creating a draft vendor invoice will generate pending project transactions.</span></span> 
<span data-ttu-id="03e1e-143">[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png)</span><span class="sxs-lookup"><span data-stu-id="03e1e-143">[![accruals8](./media/accruals8-1024x225.png)](./media/accruals8.png)</span></span> 

<span data-ttu-id="03e1e-144">På sidan **Utfästa kostnader** stängs poster som skapats i steg 1 och nya poster skapas för att återspegla kostnadsåtaganden från den väntande leverantörsfakturan.</span><span class="sxs-lookup"><span data-stu-id="03e1e-144">In the **Committed cost** page, records created in step 1 will be closed and new records will be created to reflect cost commitment coming from the pending vendor invoice.</span></span> <span data-ttu-id="03e1e-145">Fältet **Transaktionsursprung** för den utfästa kostnaden ställs in på **Leverantörsfaktura**.</span><span class="sxs-lookup"><span data-stu-id="03e1e-145">The **Transaction origin** field for the committed cost will be set to **Vendor invoice**.</span></span>
<span data-ttu-id="03e1e-146">[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)</span><span class="sxs-lookup"><span data-stu-id="03e1e-146">[![accruals9](./media/accruals9-1024x200.png)](./media/accruals9.png)</span></span>

<span data-ttu-id="03e1e-147">Leverantörsfakturan förblir väntande tills den faktiska leverantörsfakturan anländer.</span><span class="sxs-lookup"><span data-stu-id="03e1e-147">The vendor invoice will remain in a pending state until the actual vendor invoice arrives.</span></span>




