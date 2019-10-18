---
title: Ställ in företagets bankkonton för ISO20022-autogiron
description: I den här uppgiften går du igenom hur du ställer in den företagsspecifika bankkontoinformation som krävs för att generera kund-betalningsfiler.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 89c4a8d3cb504df97bad5679bf12b3cdb5931d95
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185714"
---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a><span data-ttu-id="ffbff-103">Ställ in företagets bankkonton för ISO20022-autogiron</span><span class="sxs-lookup"><span data-stu-id="ffbff-103">Set up company bank accounts for ISO20022 direct debits</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ffbff-104">I den här uppgiften går du igenom hur du ställer in den företagsspecifika bankkontoinformation som krävs för att generera kund-betalningsfiler.</span><span class="sxs-lookup"><span data-stu-id="ffbff-104">This task walks you through setting up the company specific bank account information that is required for generating customer payment files.</span></span> <span data-ttu-id="ffbff-105">I den här proceduren används formatet ISO 20022 för autogiro som exempel.</span><span class="sxs-lookup"><span data-stu-id="ffbff-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> <span data-ttu-id="ffbff-106">Andra format kanske kräver ytterligare inställningsinformation som exempelvis företagets ID eller sorteringskod.</span><span class="sxs-lookup"><span data-stu-id="ffbff-106">Other formats might require additional setup information like the Company ID or the Sort code.</span></span>



<span data-ttu-id="ffbff-107">Uppgiften har skapats med demodataföretaget DEMF.</span><span class="sxs-lookup"><span data-stu-id="ffbff-107">This task was created using the demo data company DEMF.</span></span>



<span data-ttu-id="ffbff-108">Detta är den andra av fem procedurer som demonstrerar kundbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer.</span><span class="sxs-lookup"><span data-stu-id="ffbff-108">This is the second of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>


## <a name="set-up-the-iban-and-swift-codes"></a><span data-ttu-id="ffbff-109">Ställ in IBAN- och SWIFT-koder</span><span class="sxs-lookup"><span data-stu-id="ffbff-109">Set up the IBAN and SWIFT codes</span></span>
1. <span data-ttu-id="ffbff-110">Gå till Kassa- och bankhantering > Bankkonton.</span><span class="sxs-lookup"><span data-stu-id="ffbff-110">Go to Cash and bank management > Bank accounts.</span></span>
2. <span data-ttu-id="ffbff-111">Använd snabbfiltret för att filtrera efter fältet Bankkonto med värdet "DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="ffbff-111">Use the Quick Filter to filter on the Bank account field with a value of 'DEMF OPER'.</span></span>
3. <span data-ttu-id="ffbff-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ffbff-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ffbff-113">Klicka till exempel på "DEMF-OPER" för att öppna bankkontoinformationen.</span><span class="sxs-lookup"><span data-stu-id="ffbff-113">For example, click 'DEMF OPER' to open the bank account details.</span></span>  
4. <span data-ttu-id="ffbff-114">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="ffbff-114">Click Edit.</span></span>
5. <span data-ttu-id="ffbff-115">Expandera eller komprimera avsnittet Ytterligare identifiering.</span><span class="sxs-lookup"><span data-stu-id="ffbff-115">Expand or collapse the Additional identification section.</span></span>
6. <span data-ttu-id="ffbff-116">Ange ett värde i fältet IBAN.</span><span class="sxs-lookup"><span data-stu-id="ffbff-116">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="ffbff-117">Ange till exempel "DE89370400440532013000".</span><span class="sxs-lookup"><span data-stu-id="ffbff-117">For example, enter 'DE89370400440532013000'.</span></span>  
7. <span data-ttu-id="ffbff-118">Skriv ett värde i fältet SWIFT-kod.</span><span class="sxs-lookup"><span data-stu-id="ffbff-118">In the SWIFT code field, type a value.</span></span>
    * <span data-ttu-id="ffbff-119">Ange till exempel "DEUTDEFF".</span><span class="sxs-lookup"><span data-stu-id="ffbff-119">For example, enter 'DEUTDEFF'.</span></span>    <span data-ttu-id="ffbff-120">Observera att SWIFT\BIC inte krävs för många betalningsformat, men det rekommenderas att registrera det för ett bankkonto.</span><span class="sxs-lookup"><span data-stu-id="ffbff-120">Please note that SWIFT \ BIC is not mandatory for many payment formats however it is recommended to have it registered for a bank account.</span></span>  
8. <span data-ttu-id="ffbff-121">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ffbff-121">Click Save.</span></span>

## <a name="set-up-a-bank-account-for-the-legal-entity"></a><span data-ttu-id="ffbff-122">Ställ in ett bankkonto för den juridiska personen</span><span class="sxs-lookup"><span data-stu-id="ffbff-122">Set up a bank account for the legal entity</span></span>
1. <span data-ttu-id="ffbff-123">Gå till Organisationsadministration > Organisationer > Juridiska personer.</span><span class="sxs-lookup"><span data-stu-id="ffbff-123">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="ffbff-124">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="ffbff-124">Click Edit.</span></span>
3. <span data-ttu-id="ffbff-125">Expandera eller komprimera avsnittet Bankkontoinformation.</span><span class="sxs-lookup"><span data-stu-id="ffbff-125">Expand or collapse the Bank account information section.</span></span>
4. <span data-ttu-id="ffbff-126">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Bankkonto.</span><span class="sxs-lookup"><span data-stu-id="ffbff-126">In the Bank account field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ffbff-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ffbff-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ffbff-128">Välj till exempel bankkontot "DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="ffbff-128">For example, select the "DEMF OPER" bank account.</span></span>  
6. <span data-ttu-id="ffbff-129">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ffbff-129">Click Save.</span></span>

