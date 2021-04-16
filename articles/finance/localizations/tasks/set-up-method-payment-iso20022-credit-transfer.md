---
title: Ställ in ett betalsätt för ISO20022-kreditöverföringar
description: I denna procedur visas hur du ställer in leverantörbetalsättet för ISO20022-kreditöverföring eller någon annan betalningstyp med hjälp av elektronisk rapportering, om du vill skapa en fil.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 643be31db625d0db12f1df18b9e797013da98ece
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832482"
---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a><span data-ttu-id="392a6-103">Ställ in ett betalsätt för ISO20022-kreditöverföringar</span><span class="sxs-lookup"><span data-stu-id="392a6-103">Set up method of payment for ISO20022 credit transfer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="392a6-104">I denna procedur visas hur du ställer in leverantörbetalsättet för ISO20022-kreditöverföring eller någon annan betalningstyp med hjälp av elektronisk rapportering, om du vill skapa en fil.</span><span class="sxs-lookup"><span data-stu-id="392a6-104">This procedure shows how to set up the vendor method of payment for ISO20022 credit transfer or any other payment type using electronic reporting to generate a file.</span></span> 

<span data-ttu-id="392a6-105">Innan du slutför denna uppgift måste du exportera formatkonfigurationer och skapa betalningskonton.</span><span class="sxs-lookup"><span data-stu-id="392a6-105">Before you complete this task, you must export format configurations and set up payment accounts.</span></span>

<span data-ttu-id="392a6-106">Uppgiften har skapats med DEMF-demodataföretaget.</span><span class="sxs-lookup"><span data-stu-id="392a6-106">This task was created using the DEMF demo data company.</span></span>

<span data-ttu-id="392a6-107">Detta är den tredje proceduren av fem som illustrerar leverantörbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="392a6-107">This is the third procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="392a6-108">Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.</span><span class="sxs-lookup"><span data-stu-id="392a6-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="392a6-109">Gå till Leverantörsreskontra > Betalningsinställning > Betalsätt.</span><span class="sxs-lookup"><span data-stu-id="392a6-109">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
2. <span data-ttu-id="392a6-110">Använd snabbfiltret för att söka efter poster.</span><span class="sxs-lookup"><span data-stu-id="392a6-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="392a6-111">Filtrera till exempel efter fältet Betalningsmetod med värdet "SEPA CT ".</span><span class="sxs-lookup"><span data-stu-id="392a6-111">For example, filter on the Method of payment field with a value of 'SEPA CT'.</span></span>
3. <span data-ttu-id="392a6-112">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="392a6-112">Click Edit.</span></span>
4. <span data-ttu-id="392a6-113">Välj "Summa" i fältet period.</span><span class="sxs-lookup"><span data-stu-id="392a6-113">In the Period field, select 'Total'.</span></span>
5. <span data-ttu-id="392a6-114">Välj "Elektronisk betalning" i fältet Betalningstyp.</span><span class="sxs-lookup"><span data-stu-id="392a6-114">In the Payment type field, select 'Electronic payment'.</span></span>
6. <span data-ttu-id="392a6-115">Expandera avsnittet Filformat.</span><span class="sxs-lookup"><span data-stu-id="392a6-115">Expand the File formats section.</span></span>
7. <span data-ttu-id="392a6-116">Välj Ja i fältet Allmän elektronisk rapportering.</span><span class="sxs-lookup"><span data-stu-id="392a6-116">Select Yes in the Generic electronic reporting field.</span></span>
8. <span data-ttu-id="392a6-117">Ange eller välj ett värde i fältet Exportera formatkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="392a6-117">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="392a6-118">Välj krediteringsöverföringen för värde ISO20022 (DE) i listan.</span><span class="sxs-lookup"><span data-stu-id="392a6-118">In the list, select the value ISO20022 Credit transfer (DE).</span></span> <span data-ttu-id="392a6-119">Om listan är tom innebär det att inga aktiva konfigurationer av exportformat för leverantörsbetalning har importerats.</span><span class="sxs-lookup"><span data-stu-id="392a6-119">If the list is empty, the vendor payment export format configuration is not imported and active.</span></span>  
9. <span data-ttu-id="392a6-120">Välj "Bank" i fältet Kontotyp.</span><span class="sxs-lookup"><span data-stu-id="392a6-120">In the Account type field, select 'Bank'.</span></span>
10. <span data-ttu-id="392a6-121">Ange värdena "'DEMF OPER" i fältet Betalningskonto.</span><span class="sxs-lookup"><span data-stu-id="392a6-121">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
11. <span data-ttu-id="392a6-122">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="392a6-122">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]