---
title: "POS-tillämpning och användaren språkinställningar"
description: "Det här avsnittet beskriver hur du ändrar språkinställningarna i Retail Modern POS (MPOS) och Cloud POS."
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: cabb63aea0da4b264aec8e0cc4d43b3e1014e71b
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="pos-application-and-user-language-settings"></a><span data-ttu-id="3d4e0-103">POS-tillämpning och användaren språkinställningar</span><span class="sxs-lookup"><span data-stu-id="3d4e0-103">POS application and user language settings</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="3d4e0-104">Det här avsnittet beskriver hur du ändrar språkinställningarna i Retail Modern POS (MPOS) och Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-104">This topic describes how to change language settings in Retail Modern POS (MPOS) and Cloud POS.</span></span>

<a name="overview"></a><span data-ttu-id="3d4e0-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="3d4e0-105">Overview</span></span>
========

<span data-ttu-id="3d4e0-106">Retail Modern POS (MPOS) och Cloud POS stöder miljöer där språkinställningar och översättningar kan variera mellan butiks- och användarinställningar.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-106">Retail Modern POS (MPOS) and Cloud POS support environments where language settings and translations can vary between the store and user settings.</span></span> <span data-ttu-id="3d4e0-107">Exempelvis kan butiken finnas i ett område där engelska är vanligast för kunderna, men vissa arbetare föredrar att använda programmet med fransk översättning.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-107">For example, the store could be located in a region where English is most common for their customers, but some workers prefer to use the application with French translations.</span></span>

## <a name="data-language"></a><span data-ttu-id="3d4e0-108">Data språk</span><span class="sxs-lookup"><span data-stu-id="3d4e0-108">Data language</span></span>
<span data-ttu-id="3d4e0-109">Oavsett användarens inställningar använder MPOS och Cloud POS alltid butikens språkinställningar för att bestämma vilka översättningar som används för data.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-109">Regardless of the user’s settings, MPOS and Cloud POS will always use the store's language settings to determine the translations used for data.</span></span> <span data-ttu-id="3d4e0-110">På så sätt får alla användare och kunder en enhetlig upplevelse.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-110">This will ensure that all users and customers will have a consistent experience.</span></span>  <span data-ttu-id="3d4e0-111">Exempel på data är:</span><span class="sxs-lookup"><span data-stu-id="3d4e0-111">Examples of data include:</span></span>

-   <span data-ttu-id="3d4e0-112">Produkter</span><span class="sxs-lookup"><span data-stu-id="3d4e0-112">Products</span></span>
-   <span data-ttu-id="3d4e0-113">Attribut och värden</span><span class="sxs-lookup"><span data-stu-id="3d4e0-113">Attributes and values</span></span>
-   <span data-ttu-id="3d4e0-114">Kategorinamn</span><span class="sxs-lookup"><span data-stu-id="3d4e0-114">Category names</span></span>
-   <span data-ttu-id="3d4e0-115">Skrivat ut eller emailed transaktionen inleveranser</span><span class="sxs-lookup"><span data-stu-id="3d4e0-115">Printed or emailed transaction receipts</span></span>
-   <span data-ttu-id="3d4e0-116">Betalningssätt namn</span><span class="sxs-lookup"><span data-stu-id="3d4e0-116">Payment method names</span></span>
-   <span data-ttu-id="3d4e0-117">Visning av meddelanden</span><span class="sxs-lookup"><span data-stu-id="3d4e0-117">Line display messages</span></span>

<span data-ttu-id="3d4e0-118">Butikens språk används också för POS-inloggningsskärmen, eftersom användaren inte är känd innan du loggar in.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-118">The store’s language will also be used for the main POS login screen, since the user is not known before logging in.</span></span> <span data-ttu-id="3d4e0-119">Om en översättning inte är tillgänglig för butikens språk, återgår POS till företagets språk.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-119">If a translation is not available for the store’s language, the POS will revert to the company’s language.</span></span>

### <a name="configuring-the-stores-language-setting"></a><span data-ttu-id="3d4e0-120">Konfigurera den stores språkinställning</span><span class="sxs-lookup"><span data-stu-id="3d4e0-120">Configuring the store’s language setting</span></span>

<span data-ttu-id="3d4e0-121">Butikens språk är ställs in från **Alla butiker** på sidan **Butik** under **Allmänt &gt; Nationella inställningar &gt; Språk.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-121">The store’s language setting is set from **All retail stores** on the **Retail Store** page under **General &gt; Regional Settings &gt; Language.</span></span> <span data-ttu-id="3d4e0-122">**Använd listrutan för att välja språk för varje butik.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-122">**Use the drop down to choose the language for each store.</span></span>

## <a name="user-interface-language"></a><span data-ttu-id="3d4e0-123">Språk för användargränssnittet</span><span class="sxs-lookup"><span data-stu-id="3d4e0-123">User interface language</span></span>
<span data-ttu-id="3d4e0-124">Kassaanvändarens språkinställning anger vilka översättningar som används i programmets användargränssnitt.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-124">The POS user’s language setting determines the translations used in the application user interface.</span></span> <span data-ttu-id="3d4e0-125">Det inkluderar alla etiketter, menyer och listor som inte betraktas som data.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-125">This includes all labels, menus, and lists that are not considered data.</span></span> <span data-ttu-id="3d4e0-126">Ett undantag är den text som visas i på kassans knappsatser.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-126">One exception is the text that is displayed on POS button grids.</span></span> <span data-ttu-id="3d4e0-127">Knappsatser stöder inte översättningar, och de visar alltid texten som definieras på knappen.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-127">The button grids don't support translations, so they will always show the text as defined on the button.</span></span> <span data-ttu-id="3d4e0-128">För att stödja översatta knappar måste du kopiera och underhålla separata knappsatser och tilldela dem till användare enligt önskemål.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-128">In order to support translated buttons, you'll have to copy and maintain separate button grids and assign them to the users as appropriate.</span></span>

### <a name="configuring-the-users-language-setting"></a><span data-ttu-id="3d4e0-129">Konfigurera användarens språk inställning</span><span class="sxs-lookup"><span data-stu-id="3d4e0-129">Configuring the user’s language setting</span></span>

<span data-ttu-id="3d4e0-130">Kassaanvändarens språk ställs in från **Alla arbetare** på sidan **Arbetare** under **Butik &gt; Språk**.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-130">The POS user’s language setting is set from **All workers** on the **Worker** page under **Retail &gt; Language**.</span></span>  <span data-ttu-id="3d4e0-131">Detta är inte inställt på fliken Profil. Den här inställningen används inte av POS.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-131">It is not set on the main Profile tab.  This setting is not used by POS.</span></span> <span data-ttu-id="3d4e0-132">Om användarens språk är inte inställd eller till ett språk där översättningar är inte tillgängliga, POS återgår till butiken språk.</span><span class="sxs-lookup"><span data-stu-id="3d4e0-132">If the user’s language is not set or it is set to a language where translations are not available, the POS will revert to the store’s language.</span></span>  

|             |                            |                                                                   |
|-------------|----------------------------|-------------------------------------------------------------------|
| <span data-ttu-id="3d4e0-133">** **</span><span class="sxs-lookup"><span data-stu-id="3d4e0-133">** **</span></span>       | <span data-ttu-id="3d4e0-134">**UI-språk** ** **</span><span class="sxs-lookup"><span data-stu-id="3d4e0-134">**UI language** ** **</span></span>      | <span data-ttu-id="3d4e0-135">**Data språk (produkter, kvitto format, radvisning etc.)**</span><span class="sxs-lookup"><span data-stu-id="3d4e0-135">**Data language (products, receipt formats, line display, etc.)**</span></span> |
| <span data-ttu-id="3d4e0-136">**Företag**</span><span class="sxs-lookup"><span data-stu-id="3d4e0-136">**Company**</span></span> | <span data-ttu-id="3d4e0-137">Standard</span><span class="sxs-lookup"><span data-stu-id="3d4e0-137">Default</span></span>                    | <span data-ttu-id="3d4e0-138">Standard</span><span class="sxs-lookup"><span data-stu-id="3d4e0-138">Default</span></span>                                                           |
| <span data-ttu-id="3d4e0-139">**Butik**</span><span class="sxs-lookup"><span data-stu-id="3d4e0-139">**Store**</span></span>   | <span data-ttu-id="3d4e0-140">Åsidosätter företaget</span><span class="sxs-lookup"><span data-stu-id="3d4e0-140">Overrides company</span></span>          | <span data-ttu-id="3d4e0-141">Åsidosätter företaget</span><span class="sxs-lookup"><span data-stu-id="3d4e0-141">Overrides company</span></span>                                                 |
| <span data-ttu-id="3d4e0-142">**Användare**</span><span class="sxs-lookup"><span data-stu-id="3d4e0-142">**User**</span></span>    | <span data-ttu-id="3d4e0-143">Åsidosätter butiken eller företaget</span><span class="sxs-lookup"><span data-stu-id="3d4e0-143">Overrides store or company</span></span> | <span data-ttu-id="3d4e0-144">Aldrig</span><span class="sxs-lookup"><span data-stu-id="3d4e0-144">Never</span></span>                                                             |





