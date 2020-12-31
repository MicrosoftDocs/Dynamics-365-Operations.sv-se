---
title: Betalningskontrollöversikt
description: Den här artikeln innehåller information om betalningskontroll, som används för att generera en elektronisk lista med checkar som kan skickas till en bank.
author: panolte
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 88463
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: f64b2bc6c336ba833cbd95f83596fe516bce8b56
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447963"
---
# <a name="positive-pay-overview"></a><span data-ttu-id="9edd9-103">Betalningskontrollöversikt</span><span class="sxs-lookup"><span data-stu-id="9edd9-103">Positive pay overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9edd9-104">Den här artikeln innehåller information om betalningskontroll, som används för att generera en elektronisk lista med checkar som kan skickas till en bank.</span><span class="sxs-lookup"><span data-stu-id="9edd9-104">This article provides information about positive pay, which is used to generate an electronic list of checks that can be presented to a bank.</span></span> 

<span data-ttu-id="9edd9-105">Du kan använda betalningskontroll för att generera en elektronisk lista med checkar som kan skickas till en bank.</span><span class="sxs-lookup"><span data-stu-id="9edd9-105">Positive pay is used to generate an electronic list of checks that can be presented to a bank.</span></span> <span data-ttu-id="9edd9-106">Betalningskontrollfiler kan hjälpa bankerna att förhindra checkbedrägerier.</span><span class="sxs-lookup"><span data-stu-id="9edd9-106">Positive pay files can help banks prevent check fraud.</span></span> <span data-ttu-id="9edd9-107">Du ställer in betalningskontroll för att generera en elektronisk lista med checkar varje gång checkarna skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="9edd9-107">You set up positive pay to generate an electronic list of checks every time that checks are printed.</span></span> <span data-ttu-id="9edd9-108">När en check sedan visas för banken, jämför banken checken med listan med checkar som tidigare har skickats in.</span><span class="sxs-lookup"><span data-stu-id="9edd9-108">Then, when a check is presented to the bank, the bank compares the check with the list of checks that you previously submitted.</span></span> <span data-ttu-id="9edd9-109">Om checken matchar en check i listan behandlar banken checken.</span><span class="sxs-lookup"><span data-stu-id="9edd9-109">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="9edd9-110">Om checken inte matchar en check in listan kvarhåller banken checken för granskning.</span><span class="sxs-lookup"><span data-stu-id="9edd9-110">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

<span data-ttu-id="9edd9-111">Betalningskontrollfil kallas också SafePay.</span><span class="sxs-lookup"><span data-stu-id="9edd9-111">Positive pay is also known as SafePay.</span></span> 

<span data-ttu-id="9edd9-112">Betalningskontrollfiler kan innehålla känslig information om betalningsmottagare och checkbelopp.</span><span class="sxs-lookup"><span data-stu-id="9edd9-112">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="9edd9-113">Se därför till att du använder lämpliga säkerhetsåtgärder från det att filerna skapas tills det att de tas emot av banken.</span><span class="sxs-lookup"><span data-stu-id="9edd9-113">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="9edd9-114">Betalningskontrollfiler hämtas enligt hämtningsinstruktionerna för webbläsaren.</span><span class="sxs-lookup"><span data-stu-id="9edd9-114">Positive pay files are downloaded according to the download instructions for the web browser.</span></span> 

<span data-ttu-id="9edd9-115">Betalningskontrollfiler skapas genom att använda dataentiteter.</span><span class="sxs-lookup"><span data-stu-id="9edd9-115">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="9edd9-116">Innan du skapar en betalningskontrollfil, måste du ställa in transformeringsformaten för den XML som översätter data till ett format som banken kan förbruka.</span><span class="sxs-lookup"><span data-stu-id="9edd9-116">Before you generate a positive pay file, you must set up the transformation formats for the XML that translates the data into a format that the bank can consume.</span></span> 

<span data-ttu-id="9edd9-117">För varje bankkonto som du vill skapa information om betalningskontroll för måste du tilldela betalningskontrollformatet.</span><span class="sxs-lookup"><span data-stu-id="9edd9-117">For each bank account that you want to generate positive pay information for, you must assign the positive pay format.</span></span> <span data-ttu-id="9edd9-118">När du har genererat betalningarna kan du generera en betalningskontrollfil för en enda juridisk person och ett enskilt bankkonto.</span><span class="sxs-lookup"><span data-stu-id="9edd9-118">After you generate payments, you can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="9edd9-119">Du kan även generera betalningskontrollfiler för flera juridiska personer och bankkonton samtidigt.</span><span class="sxs-lookup"><span data-stu-id="9edd9-119">Alternatively, you can generate positive pay files for multiple legal entities and bank accounts at the same time.</span></span> 

<span data-ttu-id="9edd9-120">När checkarna som anges i en betalningskontrollfil har betalats får du ett bekräftelsenummer från banken.</span><span class="sxs-lookup"><span data-stu-id="9edd9-120">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="9edd9-121">Sedan kan du bekräfta betalningskontrollfilen i systemet.</span><span class="sxs-lookup"><span data-stu-id="9edd9-121">You can then confirm the positive pay file in the system.</span></span> 

<span data-ttu-id="9edd9-122">Om du måste ändra en betalningskontrollfil kan du sedan återkalla den.</span><span class="sxs-lookup"><span data-stu-id="9edd9-122">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="9edd9-123">Sedan, för varje check i betalningskontrollfilen återställs fältet som anger om denna check har inkluderats i en betalningskontrollfil.</span><span class="sxs-lookup"><span data-stu-id="9edd9-123">Then, for each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span>

<span data-ttu-id="9edd9-124">Mer information finns i [Ställa in och generera betalningskontrollfiler](set-up-generate-positive-pay-files.md).</span><span class="sxs-lookup"><span data-stu-id="9edd9-124">For more information, see [Set up and generate positive pay files](set-up-generate-positive-pay-files.md).</span></span>



