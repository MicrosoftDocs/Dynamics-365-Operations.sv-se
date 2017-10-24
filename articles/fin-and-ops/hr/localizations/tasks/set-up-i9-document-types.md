--- 
title: "Ställ in 1-9-dokumenttyper"
description: "I den här proceduren visas hur du visar och ställer in dokumenttyper som används för I-9-verifiering."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3b0e7f09994367f5683ed5c6d1f3b3ba3d550cc7
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-i-9-document-types"></a><span data-ttu-id="fc229-103">Ställ in 1-9-dokumenttyper</span><span class="sxs-lookup"><span data-stu-id="fc229-103">Set up I-9 document types</span></span>

[!include[task guide banner](../../../includes/task-guide-banner.md)]

<span data-ttu-id="fc229-104">I den här proceduren visas hur du visar och ställer in dokumenttyper som används för I-9-verifiering.</span><span class="sxs-lookup"><span data-stu-id="fc229-104">This procedure shows how to view and set up document types that are used for I-9 verification.</span></span> <span data-ttu-id="fc229-105">Innan du ställer in I-9-dokumenttyper måste du även ställa in de utfärdande organisationerna och identifieringstyperna.</span><span class="sxs-lookup"><span data-stu-id="fc229-105">Before you set up I-9 document types, you must also set up the issuing agencies and identification types.</span></span> <span data-ttu-id="fc229-106">Det demodataföretag som används för att skapa den här proceduren är USMF, som innehåller exempel på utfärdande myndigheter och identifieringstyper som behövs för att slutföra proceduren.</span><span class="sxs-lookup"><span data-stu-id="fc229-106">The demo data company used to create this procedure is USMF, which includes examples of the issue agencies and identification types that are needed to complete the procedure.</span></span>

1. <span data-ttu-id="fc229-107">Gå till Personal > Arbetare > I-9 > I-9-dokumenttyper.</span><span class="sxs-lookup"><span data-stu-id="fc229-107">Go to Human resources > Workers > I-9 > I-9 document types.</span></span>
2. <span data-ttu-id="fc229-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="fc229-108">Click New.</span></span>
3. <span data-ttu-id="fc229-109">Skriv ett värde i fältet I-9-dokumenttyp.</span><span class="sxs-lookup"><span data-stu-id="fc229-109">In the I-9 document type field, type a value.</span></span>
    * <span data-ttu-id="fc229-110">Exempel: Skol-ID.</span><span class="sxs-lookup"><span data-stu-id="fc229-110">Example: School ID.</span></span>  
4. <span data-ttu-id="fc229-111">Välj identifieringstypen.</span><span class="sxs-lookup"><span data-stu-id="fc229-111">Select the identification type.</span></span>  <span data-ttu-id="fc229-112">Exempel: Skol-ID.</span><span class="sxs-lookup"><span data-stu-id="fc229-112">Example:  School ID</span></span>
    * <span data-ttu-id="fc229-113">Exempel på identifieringstyper inkluderar ett personnummer (Social Security number (SSN)), visumnummer, pass-ID, eller körkort.</span><span class="sxs-lookup"><span data-stu-id="fc229-113">Examples of identification types include a Social Security number (SSN), visa number, passport ID, or driver's licence.</span></span>  
5. <span data-ttu-id="fc229-114">Välj I-9-dokumentlistan som används för dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="fc229-114">Select the I-9 document list that is used for the document type.</span></span>
    * <span data-ttu-id="fc229-115">Som en del av processen I-9 måste medarbetare visa upp dokumentation som visar arbetsgivaren hans/hennes identitet och Employment Authorization.</span><span class="sxs-lookup"><span data-stu-id="fc229-115">As part of the I-9 process, employees must present documentation that shows the employer their identity and employment authorization.</span></span> <span data-ttu-id="fc229-116">Webbplatsen US Citizenship and Immigration Services innehåller information om vilka dokument som är godkända och vilken lista de tillhör.</span><span class="sxs-lookup"><span data-stu-id="fc229-116">The US Citizenship and Immigration Services website contains information about which documents are acceptable, and which list they belong to.</span></span>  <span data-ttu-id="fc229-117">http://www.uscis.gov</span><span class="sxs-lookup"><span data-stu-id="fc229-117">http://www.uscis.gov</span></span>  
6. <span data-ttu-id="fc229-118">Ange det officiella formulärnumret för dokumenttypen i fältet Formulär.</span><span class="sxs-lookup"><span data-stu-id="fc229-118">In the Form field, Enter the official form number for the document type.</span></span> <span data-ttu-id="fc229-119">Exempel: Skol-ID.</span><span class="sxs-lookup"><span data-stu-id="fc229-119">Example: School ID.</span></span>
    * <span data-ttu-id="fc229-120">De officiella formulärnumren hittar du på webbplatsen US Citizenship and Immigration Services.</span><span class="sxs-lookup"><span data-stu-id="fc229-120">The official form numbers can be found on the US Citizenship and Immigration Services website.</span></span>  <span data-ttu-id="fc229-121">http://www.uscis.gov</span><span class="sxs-lookup"><span data-stu-id="fc229-121">http://www.uscis.gov</span></span>  
7. <span data-ttu-id="fc229-122">Markera eller avmarkera kryssrutan Aktiv.</span><span class="sxs-lookup"><span data-stu-id="fc229-122">Check or uncheck the Active checkbox.</span></span>
8. <span data-ttu-id="fc229-123">Ange datumet till "2019-10-27" i fältet Upphör.</span><span class="sxs-lookup"><span data-stu-id="fc229-123">In the Expire field, set the date to '2019-10-27'.</span></span>
    * <span data-ttu-id="fc229-124">Det är valfritt att ange ett utgångsdatum.</span><span class="sxs-lookup"><span data-stu-id="fc229-124">The expiration date is optional.</span></span>  
9. <span data-ttu-id="fc229-125">Välj den myndighet som har utfärdat dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="fc229-125">Select the agency that issued the document type.</span></span> <span data-ttu-id="fc229-126">Exempel: Region/område</span><span class="sxs-lookup"><span data-stu-id="fc229-126">Example: Province/territory</span></span>
10. <span data-ttu-id="fc229-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="fc229-127">Click Save.</span></span>


