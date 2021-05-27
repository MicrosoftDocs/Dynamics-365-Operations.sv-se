---
title: Registrera återställningsbara certifikatnummer för TDS
description: I det här avsnittet beskrivs hur du använder sidan Återställningsbara certifikat för att registrera certifikatnummer och datum för TDS-certifikat (skatteavdrag vid källan) som har mottagits för en viss leverantör, kund eller redovisning.
author: kailiang
mms.date: 02/12/2021
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
ms.openlocfilehash: b501c331cccc6d030f36d0a13ba0a6a13c08c733
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023584"
---
# <a name="record-tds-recoverable-certificate-numbers"></a><span data-ttu-id="acb13-103">Registrera återställningsbara certifikatnummer för TDS</span><span class="sxs-lookup"><span data-stu-id="acb13-103">Record TDS recoverable certificate numbers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="acb13-104">I det här avsnittet beskrivs hur du använder sidan **Återställningsbara certifikat** för att registrera certifikatnummer och datum för TDS-certifikat (skatteavdrag vid källan) som har mottagits för en viss leverantör, kund eller redovisning.</span><span class="sxs-lookup"><span data-stu-id="acb13-104">This topic explains how to use the **Recoverable certificates** page to record the certificate numbers and dates for Tax Deducted at Source (TDS) certificates that are received for a specific vendor, customer, or ledger.</span></span> <span data-ttu-id="acb13-105">Om du vill uppdatera TDS-certifikatnummer och datum som har registrerats för TDS-transaktioner på den här sidan, använder du sidan **Uppdatera certifikat** (**Redovisning \> Periodisk \> Källskatt \> Uppdatera certifikat**).</span><span class="sxs-lookup"><span data-stu-id="acb13-105">To update the TDS certificate numbers and dates that are recorded for TDS transactions on this page, use the **Update certificate** page (**General ledger \> Periodic \> Withholding tax \> Update certificate**).</span></span> <span data-ttu-id="acb13-106">När du är klar med att uppdatera TDS-certifikatnummer stänger du dem.</span><span class="sxs-lookup"><span data-stu-id="acb13-106">After you've finished updating TDS certificate numbers, close them.</span></span>

<span data-ttu-id="acb13-107">Följ dessa steg om du vill registrera nummer och datum för TDS-certifikat.</span><span class="sxs-lookup"><span data-stu-id="acb13-107">Follow these steps to record the TDS certificate numbers and dates.</span></span>

1. <span data-ttu-id="acb13-108">Gå till **Skatt \> Indirekt skatt \> Källskatt \> Återställningsbara certifikat**.</span><span class="sxs-lookup"><span data-stu-id="acb13-108">Go to **Tax \> Indirect tax \> Withholding tax \> Recoverable certificates**.</span></span>

    <span data-ttu-id="acb13-109">[![Sidan Återställningsbara certifikat](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png)</span><span class="sxs-lookup"><span data-stu-id="acb13-109">[![Recoverable certificates page](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png)</span></span> 

2. <span data-ttu-id="acb13-110">På sidan **Återställningsbara certifikat**, i fältet **Skattetyp**, väljer du **TDS**.</span><span class="sxs-lookup"><span data-stu-id="acb13-110">On the **Recoverable certificates** page, in the **Tax type** field, select **TDS**.</span></span>
3. <span data-ttu-id="acb13-111">Välj **Ny** för att skapa en post.</span><span class="sxs-lookup"><span data-stu-id="acb13-111">Select **New** to create a record.</span></span>
4. <span data-ttu-id="acb13-112">I fältet **Certifikatnummer** anger du numret på TDS-certifikatet.</span><span class="sxs-lookup"><span data-stu-id="acb13-112">In the **Certificate number** field, enter the TDS certificate number.</span></span>
5. <span data-ttu-id="acb13-113">I fältet **Kontotyp** väljer du den typ av konto som TDS-certifikatet tas emot för: **Leverantör**, **Kund** eller **Redovisning**.</span><span class="sxs-lookup"><span data-stu-id="acb13-113">In the **Account type** field, select the type of account that the TDS certificate is received for: **Vendor**, **Customer**, or **Ledger**.</span></span>
6. <span data-ttu-id="acb13-114">I fältet **Konto** väljer du kontonumret för leverantör, kund eller redovisning, beroende på vilken kontotyp du har valt.</span><span class="sxs-lookup"><span data-stu-id="acb13-114">In the **Account** field, select the vendor, customer, or ledger account number, depending on the account type that you selected.</span></span> <span data-ttu-id="acb13-115">I fältet **Namn** visas namnet på leverantören, kunden eller redovisningen.</span><span class="sxs-lookup"><span data-stu-id="acb13-115">The **Name** field shows the name of the vendor, customer, or ledger account.</span></span>
7. <span data-ttu-id="acb13-116">I fältet **Certifikatbelopp** anger du beloppet för TDS-certifikatet.</span><span class="sxs-lookup"><span data-stu-id="acb13-116">In the **Certificate amount** field, enter the amount of the TDS certificate.</span></span>
8. <span data-ttu-id="acb13-117">I fältet **Datum** anger du certifikatdatumet för certifikatnumret.</span><span class="sxs-lookup"><span data-stu-id="acb13-117">In the **Date** field, enter the certificate date for the certificate number.</span></span>
9. <span data-ttu-id="acb13-118">Välj **Förfrågningar** för att öppna sidan **Certifikattransaktioner**, där du kan visa TDS-transaktioner som numret och datumet för TDS-certifikatet har uppdaterats för.</span><span class="sxs-lookup"><span data-stu-id="acb13-118">Select **Inquiries** to open the **Certificate transactions** page, where you can view the TDS transactions that the TDS certificate number and date are updated for.</span></span> <span data-ttu-id="acb13-119">Den här informationen kan uppdateras på sidan **Uppdatera certifikat** (**Skatt \> Deklarationer \> Källskatt \> Uppdatera certifikat**).</span><span class="sxs-lookup"><span data-stu-id="acb13-119">This information can be updated on the **Update certificate** page (**Tax \> Declarations \> Withholding tax \> Update certificate**).</span></span>

    <span data-ttu-id="acb13-120">På sidan **Uppdatera certifikat** visas följande information för varje TDS-transaktion:</span><span class="sxs-lookup"><span data-stu-id="acb13-120">The **Update certificate** page shows the following information for each TDS transaction:</span></span>

    - <span data-ttu-id="acb13-121">**Datum** – Bokföringsdatum för TDS-transaktionen.</span><span class="sxs-lookup"><span data-stu-id="acb13-121">**Date** – The posting date of the TDS transaction.</span></span>
    - <span data-ttu-id="acb13-122">**Verifiering** – Verifieringsnumret för TDS-transaktionen.</span><span class="sxs-lookup"><span data-stu-id="acb13-122">**Voucher** – The voucher number of the TDS transaction.</span></span>
    - <span data-ttu-id="acb13-123">**Källa** – Modulen där TDS-transaktionen skapades.</span><span class="sxs-lookup"><span data-stu-id="acb13-123">**Source** – The module that the TDS transaction was created in.</span></span>
    - <span data-ttu-id="acb13-124">**Konto** – Kontonummer för leverantör, kund eller redovisning som TDS-transaktionen skapades för.</span><span class="sxs-lookup"><span data-stu-id="acb13-124">**Account** – The vendor, customer, or ledger account number that the TDS transaction was created for.</span></span>
    - <span data-ttu-id="acb13-125">**Namn** – Namnet på kontot för leverantör, kund eller redovisning som TDS-transaktionen skapades för.</span><span class="sxs-lookup"><span data-stu-id="acb13-125">**Name** – The name of the vendor, customer, or ledger account that the TDS transaction was created for.</span></span>
    - <span data-ttu-id="acb13-126">**Belopp** – Fakturabeloppet som TDS beräknades på.</span><span class="sxs-lookup"><span data-stu-id="acb13-126">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="acb13-127">**Skattebelopp** – TDS-skatten som har beräknats för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="acb13-127">**Tax amount** – The TDS tax amount that was calculated for the transaction.</span></span>
    - <span data-ttu-id="acb13-128">**Certifikatdatum** – TDS-certifikatdatumet som uppdaterades för TDS-transaktionen.</span><span class="sxs-lookup"><span data-stu-id="acb13-128">**Certificate date** – The TDS certificate date that was updated for the TDS transaction.</span></span>
    - <span data-ttu-id="acb13-129">**Certifikatnummer** – TDS-certifikatnummer som uppdaterades för TDS-transaktionen.</span><span class="sxs-lookup"><span data-stu-id="acb13-129">**Certificate number** – TDS certificate number that was updated for the TDS transaction.</span></span>

10. <span data-ttu-id="acb13-130">På sidan **Återställningsbara certifikat** markerar du kryssrutan **Stängd** för att stänga TDS-certifikatnumret när du är klar med uppdateringen för TDS-transaktioner på sidan **Uppdatera certifikat**.</span><span class="sxs-lookup"><span data-stu-id="acb13-130">On the **Recoverable certificates** page, select the **Closed** check box to close the TDS certificate number after you've finished updating it for TDS transactions on the **Update certificate** page.</span></span>

    <span data-ttu-id="acb13-131">För att markera kryssrutan **Stängd** för alla poster på sidan väljer du **Markera alla**.</span><span class="sxs-lookup"><span data-stu-id="acb13-131">To select the **Closed** check box for all records on the page, select **Mark all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="acb13-132">TDS-certifikatnummer som kryssrutan **Stängd** har markerats för är inte tillgängliga på sidan **Uppdatera certifikat**.</span><span class="sxs-lookup"><span data-stu-id="acb13-132">TDS certificate numbers that the **Closed** check box is selected for aren't available on the **Update certificate** page.</span></span>
