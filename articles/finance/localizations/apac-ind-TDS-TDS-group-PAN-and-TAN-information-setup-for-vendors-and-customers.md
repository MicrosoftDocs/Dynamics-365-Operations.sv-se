---
title: Ställa in TDS-grupp, PAN- och TAN-information för leverantörer och kunder
description: I det här avsnittet beskrivs hur du ställer in information om gruppen Skatteavdrag vid källa (TDS), permanent kontonummer (PAN) och skattekontonummer (TAN) för leverantörer och kunder.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: fd33b1775afefed798f1e9bb7601f4112222c430
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023599"
---
# <a name="tds-group-pan-and-tan-information-setup-for-vendors-and-customers"></a><span data-ttu-id="04d01-103">TDS-grupp, PAN- och TAN-information för leverantörer och kunder</span><span class="sxs-lookup"><span data-stu-id="04d01-103">TDS group, PAN, and TAN information setup for vendors and customers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04d01-104">I det här avsnittet beskrivs hur du ställer in information om gruppen Skatteavdrag vid källa (TDS), permanent kontonummer (PAN) och skattekontonummer (TAN) för leverantörer och kunder.</span><span class="sxs-lookup"><span data-stu-id="04d01-104">This topic explains how to set up information about the Tax Deducted at Source (TDS) group, permanent account number (PAN), and tax account number (TAN) for vendors and customers.</span></span>

1. <span data-ttu-id="04d01-105">Gå till **Leverantörsreskontra \> Leverantörer \> Alla leverantörer** eller **Kundreskontra \> Kunder \> Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="04d01-105">Go to **Accounts payable \> Vendors \> All vendors** or **Accounts receivable \> Customers \> All customers**.</span></span>

    <span data-ttu-id="04d01-106">[![Sidan Alla leverantörer](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)</span><span class="sxs-lookup"><span data-stu-id="04d01-106">[![All vendors page](./media/apac-ind-TDS-55.png)](./media/apac-ind-TDS-55.png)</span></span>

2. <span data-ttu-id="04d01-107">I åtgärdsfönstret väljer du **Ny** för att skapa en leverantör eller kund och anger den information som krävs.</span><span class="sxs-lookup"><span data-stu-id="04d01-107">On the Action Pane, select **New** to create a vendor or customer, and enter the required details.</span></span> <span data-ttu-id="04d01-108">Du kan även välja en befintlig leverantör eller kund.</span><span class="sxs-lookup"><span data-stu-id="04d01-108">Alternatively, select an existing vendor or customer.</span></span>
3. <span data-ttu-id="04d01-109">Under snabbfliken **Faktura och leverans**, i avsnittet **Källskatt**, ställer du in alternativet **Beräkna källskatt** på **Ja** för att beräkna källskatt, TDS eller skatt insamlad vid källan (TCS) för leverantören eller kunden.</span><span class="sxs-lookup"><span data-stu-id="04d01-109">On the **Invoice and delivery** FastTab, in the **Withholding tax** section, set the **Calculate withholding tax** option to **Yes** to calculate withholding tax, TDS, or Tax Collected at Source (TCS) for the vendor or customer.</span></span>
4. <span data-ttu-id="04d01-110">TDS för en inköpsfaktura beräknas baserat på standardgruppen för TDS som har definierats för leverantören eller kunden.</span><span class="sxs-lookup"><span data-stu-id="04d01-110">TDS for a purchase invoice is calculated based on the default TDS group that is defined for the vendor or customer.</span></span> <span data-ttu-id="04d01-111">I fältet **TDS-grupp** väljer du standard-TDS-grupp.</span><span class="sxs-lookup"><span data-stu-id="04d01-111">In the **TDS group** field, select the default TDS group.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04d01-112">När du väljer en TDS-grupp i fältet **TDS-grupp** blir fälten **Källskattegrupp** och **TCS-grupp** otillgängliga.</span><span class="sxs-lookup"><span data-stu-id="04d01-112">When you select a TDS group in the **TDS group** field, the **Withholding tax group** and **TCS group** fields become unavailable.</span></span>

5. <span data-ttu-id="04d01-113">Under snabbfliken **Skatteinformation**, i avsnittet **PAN-information**, i fältet **Status**, väljer du status för permanent kontonummer för leverantören eller kunden:</span><span class="sxs-lookup"><span data-stu-id="04d01-113">On the **Tax information** FastTab, in the **PAN information** section, in the **Status** field, select the status of the permanent account number for the vendor or customer:</span></span>

    - <span data-ttu-id="04d01-114">**Inte tillgängligt** – Leverantören eller kunden har inte ett PAN.</span><span class="sxs-lookup"><span data-stu-id="04d01-114">**Not available** – The vendor or customer doesn't have a PAN.</span></span>
    - <span data-ttu-id="04d01-115">**Mottaget** – Leverantören eller kunden har PAN.</span><span class="sxs-lookup"><span data-stu-id="04d01-115">**Received** – The vendor or customer has a PAN.</span></span>
    - <span data-ttu-id="04d01-116">**Ansökt** – Leverantören eller kunden har ansökt om PAN.</span><span class="sxs-lookup"><span data-stu-id="04d01-116">**Applied** – The vendor or customer has applied for a PAN.</span></span>
    - <span data-ttu-id="04d01-117">**Ogiltigt** – Leverantören eller kunden har PAN, men det är ogiltigt.</span><span class="sxs-lookup"><span data-stu-id="04d01-117">**Invalid** – The vendor or customer has a PAN, but it isn't valid.</span></span>

6. <span data-ttu-id="04d01-118">Om du har valt **Mottaget** i fältet **Status** för att indikera att leverantören eller kunden har PAN, anger du PAN i fältet **Nummer**.</span><span class="sxs-lookup"><span data-stu-id="04d01-118">If you selected **Received** in the **Status** field to indicate that the vendor or customer has a PAN, enter the PAN in the **Number** field.</span></span> <span data-ttu-id="04d01-119">PAN måste bestå av fem alfabetiska tecken, därefter fyra numeriska tecken och därefter ett alfabetiskt tecken.</span><span class="sxs-lookup"><span data-stu-id="04d01-119">The PAN must consist of five alphabetic characters, then four numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="04d01-120">Här är ett exempel: **ABCDE1260A**.</span><span class="sxs-lookup"><span data-stu-id="04d01-120">Here is an example: **ABCDE1260A**.</span></span>
7. <span data-ttu-id="04d01-121">Om du har valt **Ansökt** i fältet **Status** för att indikera att leverantören eller kunden har ansökt om PAN, anger du referensnumret i fältet **Referensnummer**.</span><span class="sxs-lookup"><span data-stu-id="04d01-121">If you selected **Applied** in the **Status** field to indicate that the vendor or customer has applied for PAN, enter the reference number in the **Reference number** field.</span></span>
8. <span data-ttu-id="04d01-122">I fältet **Typ av bedömare** väljer du typen av bedömningskategori som leverantören eller kunden tillhör:</span><span class="sxs-lookup"><span data-stu-id="04d01-122">In the **Nature of assessee** field, select the nature of assessee category that the vendor or customer belongs to:</span></span>

    - <span data-ttu-id="04d01-123">Företag</span><span class="sxs-lookup"><span data-stu-id="04d01-123">Company</span></span>
    - <span data-ttu-id="04d01-124">HUF</span><span class="sxs-lookup"><span data-stu-id="04d01-124">HUF</span></span>
    - <span data-ttu-id="04d01-125">Bekräfta</span><span class="sxs-lookup"><span data-stu-id="04d01-125">Firm</span></span>
    - <span data-ttu-id="04d01-126">Enskild</span><span class="sxs-lookup"><span data-stu-id="04d01-126">Individual</span></span>
    - <span data-ttu-id="04d01-127">AOP</span><span class="sxs-lookup"><span data-stu-id="04d01-127">AOP</span></span>
    - <span data-ttu-id="04d01-128">BOI</span><span class="sxs-lookup"><span data-stu-id="04d01-128">BOI</span></span>
    - <span data-ttu-id="04d01-129">Lokal myndighet</span><span class="sxs-lookup"><span data-stu-id="04d01-129">Local authority</span></span>
    - <span data-ttu-id="04d01-130">Annat</span><span class="sxs-lookup"><span data-stu-id="04d01-130">Others</span></span>

    <span data-ttu-id="04d01-131">[![Snabbfliken Skatteinformation](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)</span><span class="sxs-lookup"><span data-stu-id="04d01-131">[![Tax information FastTab](./media/apac-ind-TDS-56.png)](./media/apac-ind-TDS-56.png)</span></span>

9. <span data-ttu-id="04d01-132">I åtgärdsfönstret, under fliken **Leverantör**, i gruppen **Registrering**, väljer du **Registrerings-ID** för att öppna sidan **Hantera adresser**.</span><span class="sxs-lookup"><span data-stu-id="04d01-132">On the Action Pane, on the **Vendor** tab, in the **Registration** group, select **Registration IDs** to open the **Manage addresses** page.</span></span>
10. <span data-ttu-id="04d01-133">På sidan **Hantera adresser**, under snabbfliken **Skatteinformation**, väljer du **Lägg till** eller **Redigera** för att öppna sidan **Hantera skatteinformation**, där du kan bibehålla skatteregistreringsposten.</span><span class="sxs-lookup"><span data-stu-id="04d01-133">On the **Manage addresses** page, on the **Tax information** FastTab, select **Add** or **Edit** to open the **Manage tax information** page, where you can maintain the tax registration entry.</span></span>
11. <span data-ttu-id="04d01-134">På sidan **Hantera skatteinformation**, under snabbfliken **Källskatt**, i fältet **Skattekontonummer (TAN)**, anger du TAN.</span><span class="sxs-lookup"><span data-stu-id="04d01-134">On the **Manage tax information** page, on the **Withholding tax** FastTab, in the **Tax Account Number (TAN)** field, enter the TAN.</span></span> <span data-ttu-id="04d01-135">TAN måste bestå av fyra alfabetiska tecken, därefter fem numeriska tecken och därefter ett alfabetiskt tecken.</span><span class="sxs-lookup"><span data-stu-id="04d01-135">The TAN must consist of four alphabetic characters, then five numeric characters, and then one alphabetic character.</span></span> <span data-ttu-id="04d01-136">Här är ett exempel: **AFGH54821T**.</span><span class="sxs-lookup"><span data-stu-id="04d01-136">Here is an example: **AFGH54821T**.</span></span>
12. <span data-ttu-id="04d01-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="04d01-137">Close the page.</span></span>
