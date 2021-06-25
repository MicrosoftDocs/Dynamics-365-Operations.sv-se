---
title: Kassaprogram (POS) och språkinställningar för användare
description: Det här avsnittet beskriver hur du ändrar språkinställningarna i Modern POS (MPOS) och Cloud POS.
author: jblucher
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.custom: 78891
ms.assetid: 0030940c-e0a5-4345-9511-8c3bd1f487ad
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: bdd03dff359e7c2799eff53b0e999580ce8b1c06
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193113"
---
# <a name="point-of-sale-pos-application-and-user-language-settings"></a><span data-ttu-id="a0cc8-103">Kassaprogram (POS) och språkinställningar för användare</span><span class="sxs-lookup"><span data-stu-id="a0cc8-103">Point of sale (POS) application and user language settings</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a0cc8-104">Det här avsnittet beskriver hur du ändrar språkinställningarna i Modern POS (MPOS) och Cloud POS.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-104">This topic describes how to change language settings in Modern POS (MPOS) and Cloud POS.</span></span>

## <a name="overview"></a><span data-ttu-id="a0cc8-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="a0cc8-105">Overview</span></span>
<span data-ttu-id="a0cc8-106">Modern POS (MPOS) och Cloud POS stöder miljöer där språkinställningar och översättningar kan variera mellan butiks- och användarinställningar.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-106">Modern POS (MPOS) and Cloud POS support environments where language settings and translations can vary between the store and user settings.</span></span> <span data-ttu-id="a0cc8-107">Exempelvis kan butiken finnas i ett område där engelska är vanligast för kunderna, men vissa arbetare föredrar att använda programmet med fransk översättning.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-107">For example, the store could be located in a region where English is most common for their customers, but some workers prefer to use the application with French translations.</span></span>

## <a name="data-language"></a><span data-ttu-id="a0cc8-108">Data språk</span><span class="sxs-lookup"><span data-stu-id="a0cc8-108">Data language</span></span>

<span data-ttu-id="a0cc8-109">Oavsett användarens inställningar använder MPOS och Cloud POS alltid butikens språkinställningar för att bestämma vilka översättningar som används för data.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-109">Regardless of the user's settings, MPOS and Cloud POS will always use the store's language settings to determine the translations used for data.</span></span> <span data-ttu-id="a0cc8-110">På så sätt får alla användare och kunder en enhetlig upplevelse.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-110">This will ensure that all users and customers will have a consistent experience.</span></span> <span data-ttu-id="a0cc8-111">Exempel på data är:</span><span class="sxs-lookup"><span data-stu-id="a0cc8-111">Examples of data include:</span></span>

- <span data-ttu-id="a0cc8-112">Produkter</span><span class="sxs-lookup"><span data-stu-id="a0cc8-112">Products</span></span>
- <span data-ttu-id="a0cc8-113">Attribut och värden</span><span class="sxs-lookup"><span data-stu-id="a0cc8-113">Attributes and values</span></span>
- <span data-ttu-id="a0cc8-114">Kategorinamn</span><span class="sxs-lookup"><span data-stu-id="a0cc8-114">Category names</span></span>
- <span data-ttu-id="a0cc8-115">Skrivat ut eller emailed transaktionen inleveranser</span><span class="sxs-lookup"><span data-stu-id="a0cc8-115">Printed or emailed transaction receipts</span></span>
- <span data-ttu-id="a0cc8-116">Betalningssätt namn</span><span class="sxs-lookup"><span data-stu-id="a0cc8-116">Payment method names</span></span>
- <span data-ttu-id="a0cc8-117">Visning av meddelanden</span><span class="sxs-lookup"><span data-stu-id="a0cc8-117">Line display messages</span></span>

<span data-ttu-id="a0cc8-118">Butikens språk används också för POS-inloggningsskärmen, eftersom användaren inte är känd innan du loggar in.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-118">The store's language will also be used for the main POS login screen, since the user is not known before logging in.</span></span> <span data-ttu-id="a0cc8-119">Om en översättning inte är tillgänglig för butikens språk, återgår POS till företagets språk.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-119">If a translation is not available for the store's language, the POS will revert to the company's language.</span></span>

### <a name="configuring-the-stores-language-setting"></a><span data-ttu-id="a0cc8-120">Konfigurera den stores språkinställning</span><span class="sxs-lookup"><span data-stu-id="a0cc8-120">Configuring the store's language setting</span></span>

<span data-ttu-id="a0cc8-121">Butikens språk är ställs in från Alla butiker på sidan **Alla butiker** på sidan **Butik** under **Allmänt &gt; Nationella inställningar &gt; Språk**.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-121">The store's language setting is set from **All stores** on the **Store** page under **General &gt; Regional Settings &gt; Language**.</span></span> <span data-ttu-id="a0cc8-122">Använd listrutan för att välja språk för varje butik.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-122">Use the drop-down list to choose the language for each store.</span></span>

## <a name="user-interface-language"></a><span data-ttu-id="a0cc8-123">Språk för användargränssnittet</span><span class="sxs-lookup"><span data-stu-id="a0cc8-123">User interface language</span></span>

<span data-ttu-id="a0cc8-124">Kassaanvändarens språkinställning anger vilka översättningar som används i programmets användargränssnitt.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-124">The POS user's language setting determines the translations used in the application user interface.</span></span> <span data-ttu-id="a0cc8-125">Det inkluderar alla etiketter, menyer och listor som inte betraktas som data.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-125">This includes all labels, menus, and lists that are not considered data.</span></span> <span data-ttu-id="a0cc8-126">Ett undantag är den text som visas i på kassans knappsatser.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-126">One exception is the text that is displayed on POS button grids.</span></span> <span data-ttu-id="a0cc8-127">Knappsatser stöder inte översättningar, och de visar alltid texten som definieras på knappen.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-127">The button grids don't support translations, so they will always show the text as defined on the button.</span></span> <span data-ttu-id="a0cc8-128">För att stödja översatta knappar måste du kopiera och underhålla separata knappsatser och tilldela dem till användare enligt önskemål.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-128">In order to support translated buttons, you'll have to copy and maintain separate button grids and assign them to the users as appropriate.</span></span>

### <a name="configuring-the-users-language-setting"></a><span data-ttu-id="a0cc8-129">Konfigurera användarens språk inställning</span><span class="sxs-lookup"><span data-stu-id="a0cc8-129">Configuring the user's language setting</span></span>

<span data-ttu-id="a0cc8-130">POS användarens språk är inställd på **Alla arbetare** på sidan **Arbetare** under **Butik och handel &gt; Språk**.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-130">The POS user's language setting is set from **All workers** on the **Worker** page under **Retail and Commerce &gt; Language**.</span></span> <span data-ttu-id="a0cc8-131">Detta är inte inställt på fliken Profil. Den här inställningen används inte av POS.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-131">It is not set on the main Profile tab. This setting is not used by POS.</span></span> <span data-ttu-id="a0cc8-132">Om användarens språk är inte inställd eller till ett språk där översättningar är inte tillgängliga, POS återgår till butiken språk.</span><span class="sxs-lookup"><span data-stu-id="a0cc8-132">If the user's language is not set or it is set to a language where translations are not available, the POS will revert to the store's language.</span></span>

| &nbsp;      | <span data-ttu-id="a0cc8-133">UI-språk  </span><span class="sxs-lookup"><span data-stu-id="a0cc8-133">UI language</span></span>                | <span data-ttu-id="a0cc8-134">Data språk (produkter, kvitto format, radvisning etc.)</span><span class="sxs-lookup"><span data-stu-id="a0cc8-134">Data language (products, receipt formats, line display, etc.)</span></span> |
|-------------|----------------------------|---------------------------------------------------------------|
| <span data-ttu-id="a0cc8-135">**Företag**</span><span class="sxs-lookup"><span data-stu-id="a0cc8-135">**Company**</span></span> | <span data-ttu-id="a0cc8-136">Standard</span><span class="sxs-lookup"><span data-stu-id="a0cc8-136">Default</span></span>                    | <span data-ttu-id="a0cc8-137">Standard</span><span class="sxs-lookup"><span data-stu-id="a0cc8-137">Default</span></span>                                                       |
| <span data-ttu-id="a0cc8-138">**Butik**</span><span class="sxs-lookup"><span data-stu-id="a0cc8-138">**Store**</span></span>   | <span data-ttu-id="a0cc8-139">Åsidosätter företaget</span><span class="sxs-lookup"><span data-stu-id="a0cc8-139">Overrides company</span></span>          | <span data-ttu-id="a0cc8-140">Åsidosätter företaget</span><span class="sxs-lookup"><span data-stu-id="a0cc8-140">Overrides company</span></span>                                             |
| <span data-ttu-id="a0cc8-141">**Användare**</span><span class="sxs-lookup"><span data-stu-id="a0cc8-141">**User**</span></span>    | <span data-ttu-id="a0cc8-142">Åsidosätter butiken eller företaget</span><span class="sxs-lookup"><span data-stu-id="a0cc8-142">Overrides store or company</span></span> | <span data-ttu-id="a0cc8-143">Aldrig</span><span class="sxs-lookup"><span data-stu-id="a0cc8-143">Never</span></span>                                                         |


[!INCLUDE[footer-include](../includes/footer-banner.md)]