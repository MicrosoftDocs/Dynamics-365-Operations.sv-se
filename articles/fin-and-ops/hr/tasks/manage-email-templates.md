---
title: Hantera e-postmallar
description: Du kan överföra information från organisationens databas till bokmärkena i ett nytt dokument och använda den i mallarna som hjälper dig att kommunicera på ett effektivt sätt med sökande och kandidater.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMApplicationWordBookmark, HRMApplicationEmailTemplate
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4667d0506c5ae6bea87b982c7feebab8963797a6
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2019
ms.locfileid: "859170"
---
# <a name="manage-email-templates"></a><span data-ttu-id="57718-103">Hantera e-postmallar</span><span class="sxs-lookup"><span data-stu-id="57718-103">Manage email templates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="57718-104">Du kan överföra information från organisationens databas till bokmärkena i ett nytt dokument och använda den i mallarna som hjälper dig att kommunicera på ett effektivt sätt med sökande och kandidater.</span><span class="sxs-lookup"><span data-stu-id="57718-104">You can transfer information from your organization’s database to the bookmarks in a new document and use it in templates that help you communicate efficiently with applicants and candidates.</span></span> <span data-ttu-id="57718-105">Om du vill göra detta skapar du en mall som innehåller standardtext och några bokmärken där systemdata ska infogas.</span><span class="sxs-lookup"><span data-stu-id="57718-105">To do this, you create a template that contains standard text and some bookmarks where the system data should be inserted.</span></span> <span data-ttu-id="57718-106">Du kan till exempel infoga adress- och kontaktinformation för en sökande i ett Microsoft Word-dokument som du kan använda när du kommunicerar med den sökande.</span><span class="sxs-lookup"><span data-stu-id="57718-106">For example, you can insert address and contact information for an applicant into a Microsoft Word document that you can use when communicating with that applicant.</span></span> <span data-ttu-id="57718-107">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="57718-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="select-which-bookmarks-to-use-in-your-email-templates"></a><span data-ttu-id="57718-108">Välj vilka bokmärken som ska användas i e-postmallarna</span><span class="sxs-lookup"><span data-stu-id="57718-108">Select which bookmarks to use in your email templates</span></span>
1. <span data-ttu-id="57718-109">Gå till Ansökningsbokmärken.</span><span class="sxs-lookup"><span data-stu-id="57718-109">Go to Application bookmarks.</span></span>
2. <span data-ttu-id="57718-110">Hitta och markera önskad korrespondensåtgärd.</span><span class="sxs-lookup"><span data-stu-id="57718-110">In the list, find and select the desired correspondence action.</span></span>
3. <span data-ttu-id="57718-111">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="57718-111">Click Edit.</span></span>
4. <span data-ttu-id="57718-112">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="57718-112">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="57718-113">Markera de fält som du vill kunna använda i en e-postmeddelandemall för den valda korrespondensåtgärden och flytta dem till bokmärkesfälten.</span><span class="sxs-lookup"><span data-stu-id="57718-113">Select the fields you would like to be able to use in an email template for the selected Correspondence action and move them to the Bookmark fields.</span></span>  
5. <span data-ttu-id="57718-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="57718-114">Close the page.</span></span>

## <a name="create-an-email-template"></a><span data-ttu-id="57718-115">Skapa en e-postmall</span><span class="sxs-lookup"><span data-stu-id="57718-115">Create an email template</span></span>
1. <span data-ttu-id="57718-116">Gå till Personal Rekrytering > Kommunikations > E-postmallar för ansökningar.</span><span class="sxs-lookup"><span data-stu-id="57718-116">Go to Human resources > Recruitment > Communication > Application e-mail templates.</span></span>
2. <span data-ttu-id="57718-117">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="57718-117">Click New.</span></span>
3. <span data-ttu-id="57718-118">Välj "Intervju" i fältet Korrespondensåtgärd.</span><span class="sxs-lookup"><span data-stu-id="57718-118">In the Correspondence action field, select 'Interview'.</span></span>
    * <span data-ttu-id="57718-119">Välj den korrespondensåtgärd som innehåller bokmärkena som ska användas för den här typen av e-postkommunikationen.</span><span class="sxs-lookup"><span data-stu-id="57718-119">Select the correspondence action that contains the bookmarks to use for this type of email communication.</span></span>  
4. <span data-ttu-id="57718-120">Skriv ett värde i fältet E-postmall.</span><span class="sxs-lookup"><span data-stu-id="57718-120">In the E-mail template field, type a value.</span></span>
5. <span data-ttu-id="57718-121">Skriv ett värde i fältet Ämne.</span><span class="sxs-lookup"><span data-stu-id="57718-121">In the Subject field, type a value.</span></span>
6. <span data-ttu-id="57718-122">Skriv ett värde i fältet Text.</span><span class="sxs-lookup"><span data-stu-id="57718-122">In the Text field, type a value.</span></span>
7. <span data-ttu-id="57718-123">Hitta och markera önskat bokmärkesfält.</span><span class="sxs-lookup"><span data-stu-id="57718-123">In the list, find and select the desired bookmark field.</span></span>
8. <span data-ttu-id="57718-124">Fortsätt skriva ditt e-postmeddelande och infoga bokmärkesfälten där de behövs.</span><span class="sxs-lookup"><span data-stu-id="57718-124">Continue typing your email message, inserting the bookmark fields where you need them.</span></span>
    * <span data-ttu-id="57718-125">Fortsätt skriva ditt e-postmeddelande för att infoga bokmärkesfälten där så önskas.</span><span class="sxs-lookup"><span data-stu-id="57718-125">Continue typing your email message inserting the bookmark fields where desired.</span></span>  
9. <span data-ttu-id="57718-126">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="57718-126">Click Save.</span></span>

