---
title: Uppdatera certifikatnummer och datum för TDS-transaktioner
description: I det här avsnittet beskrivs hur du uppdaterar återställningsbara certifikatnummer och datum som registrerades för leverantörs-, kund- eller redovisningskonton för skatteavdrag vid källan (TDS).
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
ms.openlocfilehash: 248de8e12703a84482b67d0899857a6efb33531c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023594"
---
# <a name="update-certificate-numbers-and-dates-for-tds-transactions"></a><span data-ttu-id="131ba-103">Uppdatera certifikatnummer och datum för TDS-transaktioner</span><span class="sxs-lookup"><span data-stu-id="131ba-103">Update certificate numbers and dates for TDS transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="131ba-104">I det här avsnittet beskrivs hur du uppdaterar återställningsbara certifikatnummer och datum som registrerades för leverantörs-, kund- eller redovisningskonton för skatteavdrag vid källan (TDS).</span><span class="sxs-lookup"><span data-stu-id="131ba-104">This topic explains how to update the recoverable certificate numbers and dates that were recorded for vendor, customer, and ledger accounts for Tax Deducted at Source (TDS).</span></span> <span data-ttu-id="131ba-105">Du kan visa certifikat för TDS-transaktioner på sidan **Återställningsbara certifikat**.</span><span class="sxs-lookup"><span data-stu-id="131ba-105">You can view the certificates for TDS transactions on the **Recoverable certificates** page.</span></span> <span data-ttu-id="131ba-106">Du kan uppdatera certifikaten genom sidan **Uppdatera certifikat**.</span><span class="sxs-lookup"><span data-stu-id="131ba-106">You can update the certificates by using the **Update Certificates** page.</span></span>

<span data-ttu-id="131ba-107">Följ dessa steg om du vill uppdatera certifikatnummer och datum för TDS-transaktioner.</span><span class="sxs-lookup"><span data-stu-id="131ba-107">Follow these steps to update certificate numbers and dates for TDS transactions.</span></span>

1. <span data-ttu-id="131ba-108">Gå till **Skatt \> Deklarationer \> Källskatt \> Uppdatera certifikat**.</span><span class="sxs-lookup"><span data-stu-id="131ba-108">Go to **Tax \> Declarations \> Withholding tax \> Update certificate**.</span></span>

    <span data-ttu-id="131ba-109">[![Sidan Uppdatera certifikat](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)</span><span class="sxs-lookup"><span data-stu-id="131ba-109">[![Update certificate page](./media/apac-ind-TDS-45.png)](./media/apac-ind-TDS-45.png)</span></span>

2. <span data-ttu-id="131ba-110">På sidan **Uppdatera certifikat**, i avsnittet **Välj**, i fältet **Skattetyp**, väljer du **TDS**.</span><span class="sxs-lookup"><span data-stu-id="131ba-110">On the **Update certificate** page, in the **Select** section, in the **Tax type** field, select **TDS**.</span></span>
3. <span data-ttu-id="131ba-111">I fältet **Certifikatnummer** väljer du kundens eller leverantörens TDS-certifikatnummer.</span><span class="sxs-lookup"><span data-stu-id="131ba-111">In the **Certificate number** field, select the customer's or vendor's TDS certificate number.</span></span>

    > [!NOTE]
    > <span data-ttu-id="131ba-112">I fältet **Certifikatnummer** visas endast TDS-certifikatnummer som kryssrutan **Stängt** är avmarkerad för på sidan **Återställningsbara certifikat**.</span><span class="sxs-lookup"><span data-stu-id="131ba-112">The **Certificate number** field lists only TDS certificate numbers that the **Closed** check box is cleared for on the **Recoverable certificates** page.</span></span>

    <span data-ttu-id="131ba-113">I fältet **Certifikat** visas certifikatdatumet.</span><span class="sxs-lookup"><span data-stu-id="131ba-113">The **Certificate date** field shows the certificate date.</span></span> <span data-ttu-id="131ba-114">I fältet **Kontotyp** visas typen av konto som TDS-certifikatnumret tas emot för, och i fältet **Namn** visas namnet på kontot.</span><span class="sxs-lookup"><span data-stu-id="131ba-114">The **Account type** field shows the type of account that the TDS certificate number is received for, and the **Name** field shows the name of the account.</span></span>

5. <span data-ttu-id="131ba-115">I fälten **Från-datum** och **Till-datum** väljer du start- och slutdatum för perioden som TDS-transaktioner ska visas för.</span><span class="sxs-lookup"><span data-stu-id="131ba-115">In the **From date** and **To date** fields, select the start and end dates of the period to show the TDS transactions for.</span></span>
6. <span data-ttu-id="131ba-116">Välj **Visa data** för att visa TDS-transaktioner som bokfördes under den valda perioden.</span><span class="sxs-lookup"><span data-stu-id="131ba-116">Select **Show data** to view the TDS transactions that were posted during the selected period.</span></span>

    <span data-ttu-id="131ba-117">Under fliken **Översikt** visar rutnätet i det övre fönstret följande information om varje TDS-transaktion som bokfördes för leverantören eller kunden under den valda perioden:</span><span class="sxs-lookup"><span data-stu-id="131ba-117">On the **Overview** tab, the grid in the upper pane shows the following information about each TDS transaction that was posted for the vendor or customer during the selected period:</span></span>

    - <span data-ttu-id="131ba-118">**Verifiering** – Verifieringsnumret för TDS-transaktionen.</span><span class="sxs-lookup"><span data-stu-id="131ba-118">**Voucher** – The voucher number of the TDS transaction.</span></span>
    - <span data-ttu-id="131ba-119">**Datum** – Datum för TDS-transaktionen.</span><span class="sxs-lookup"><span data-stu-id="131ba-119">**Date** – The date of the TDS transaction.</span></span>
    - <span data-ttu-id="131ba-120">**Belopp** – Fakturabeloppet som TDS beräknades på.</span><span class="sxs-lookup"><span data-stu-id="131ba-120">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="131ba-121">**Skattebelopp** – TDS-skatten som har beräknats för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="131ba-121">**Tax amount** – The TDS tax amount that was calculated for the transaction.</span></span>

7. <span data-ttu-id="131ba-122">Om du vill flytta specifika TDS-transaktioner från det övre rutnätet till det nedre rutnätet markerar du transaktionerna och väljer **Inkludera**.</span><span class="sxs-lookup"><span data-stu-id="131ba-122">To move specific TDS transactions from the upper grid to the lower grid, select the transactions, and then select **Include**.</span></span> <span data-ttu-id="131ba-123">Du kan också välja **Inkludera alla** om du vill flytta alla TDS-transaktioner från det övre rutnätet till det nedre rutnätet.</span><span class="sxs-lookup"><span data-stu-id="131ba-123">Alternatively, select **Include all** to move all TDS transactions from the upper grid to the lower grid.</span></span>

    <span data-ttu-id="131ba-124">Om du vill flytta specifika TDS-transaktioner eller alla TDS-transaktioner från det nedre rutnätet till det övre rutnätet använder du knappen **Exkludera** eller **Exkludera alla**.</span><span class="sxs-lookup"><span data-stu-id="131ba-124">To move specific TDS transactions or all TDS transactions from the lower grid to the upper grid, use the **Exclude** or **Exclude all** button.</span></span>

8. <span data-ttu-id="131ba-125">Välj **Uppdatera** för att uppdatera fälten **Certifikatnummer** och **Certifikatdatum** för TDS-transaktioner i det nedre rutnätet.</span><span class="sxs-lookup"><span data-stu-id="131ba-125">Select **Update** to update the **Certificate number** and **Certificate date** fields for TDS transactions in the lower grid.</span></span>
10. <span data-ttu-id="131ba-126">Gå till **Skatt \> Indirekt skatt \> Källskatt \> Återställningsbart certifikat** och välj **Förfrågan** för att visa de uppdaterade transaktionsraderna som har nya certifikatnummer på sidan **Certifikattransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="131ba-126">Go to **Tax \> Indirect taxes \> Withholding tax \> Recoverable certificate**, and select **Inquiry** to view the updated transaction lines that have the new certificate numbers on the **Certificate transactions** page.</span></span>

    <span data-ttu-id="131ba-127">[![Sidan certifikattransaktioner](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)</span><span class="sxs-lookup"><span data-stu-id="131ba-127">[![Certificate transactions page](./media/apac-ind-TDS-46.png)](./media/apac-ind-TDS-46.png)</span></span>
