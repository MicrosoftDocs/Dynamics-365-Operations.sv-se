---
title: Översikt över modulbibliotek
description: Det här ämnet innehåller en översikt över Microsoft Dynamics 365 Commerce modulbibliotek.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4b3440c046ff055c8afa012c80c56aba741fef27
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985571"
---
# <a name="module-library-overview"></a><span data-ttu-id="ac4e3-103">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="ac4e3-103">Module library overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ac4e3-104">Det här ämnet innehåller en översikt över Microsoft Dynamics 365 Commerce modulbibliotek.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-104">This topic presents an overview of the Microsoft Dynamics 365 Commerce module library.</span></span>

## <a name="overview"></a><span data-ttu-id="ac4e3-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="ac4e3-105">Overview</span></span>

<span data-ttu-id="ac4e3-106">Modulbiblioteket Dynamics 365 Commerce är en samling moduler som kan användas för att skapa en näthandelssajt.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-106">The Dynamics 365 Commerce module library is a collection of modules that can be used to build an e-Commerce website.</span></span> <span data-ttu-id="ac4e3-107">Moduler har både användargränssnitt och funktionsbeteenden.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-107">Modules have both user interface (UI) aspects and functional behavior aspects.</span></span>

<span data-ttu-id="ac4e3-108">Teman kan användas i moduler i modulbiblioteket för att ändra utseende och känsla.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-108">Themes can be applied to the modules in the module library to change their look and feel.</span></span> <span data-ttu-id="ac4e3-109">I teman används övergripande formatmallar (CSS).</span><span class="sxs-lookup"><span data-stu-id="ac4e3-109">The themes use Cascading Style Sheets (CSS).</span></span> <span data-ttu-id="ac4e3-110">Ett tema för en fiktiv näthandelssajt med namnet "Fabrikam" tillhandahålls som en del av modulbiblioteket och kan användas som referens.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-110">A theme for a fictitious e-Commerce site that is named "Fabrikam" is provided as part of the module library and can be used as a reference.</span></span>

## <a name="module-library-modules"></a><span data-ttu-id="ac4e3-111">Moduler för modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="ac4e3-111">Module library modules</span></span>

<span data-ttu-id="ac4e3-112">Följande typer av moduler finns i modulbiblioteket:</span><span class="sxs-lookup"><span data-stu-id="ac4e3-112">The following types of modules are provided in the module library:</span></span>

- <span data-ttu-id="ac4e3-113">**Behållarmodul** – en behållarmodul är en enkel modul som fungerar som värd för andra moduler.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-113">**Container module** – A container module is a simple module that acts as a host for other modules.</span></span> <span data-ttu-id="ac4e3-114">Den styr layouten för modulerna som finns inuti.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-114">It controls the layout of the modules that are inside it.</span></span>
- <span data-ttu-id="ac4e3-115">**Marknadsföringsmoduler** – marknadsföringsmoduler omfattar innehållsblock-, textblock-, videospelar- och karusellmoduler.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-115">**Marketing modules** – Marketing modules include content block, text block, video player, and carousel modules.</span></span> <span data-ttu-id="ac4e3-116">Alla dessa moduler kan användas för att presentera innehåll.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-116">All these modules can be used to showcase content.</span></span> <span data-ttu-id="ac4e3-117">De kan placeras på vilken sida som helst och styrs av data från innehållshanteringssystemet (CMS).</span><span class="sxs-lookup"><span data-stu-id="ac4e3-117">They can be put on any page and are driven by data from the content management system (CMS).</span></span>
- <span data-ttu-id="ac4e3-118">**Modulerna sidhuvud och sidfot** – modulerna sidhuvud och sidfot visas i sidhuvudet och sidfoten på alla webbplatssidor.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-118">**Header and footer modules** – Header and footer modules appear in the header and footer of all site pages.</span></span> <span data-ttu-id="ac4e3-119">Dessa moduler kan konfigureras efter behov via egenskaper.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-119">These modules can be configured as required through properties.</span></span>
- <span data-ttu-id="ac4e3-120">**Sökmoduler** – produkter kan identifieras med hjälp av sökmodulen i rubriken.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-120">**Search modules** – Products can be discovered by using the search module in the header.</span></span> <span data-ttu-id="ac4e3-121">Sökresultat visas på sidan med sökresultat.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-121">Search results appear on the search results page.</span></span> <span data-ttu-id="ac4e3-122">Produkter kan också upptäckas på kategorisidor, som är dedikerade sidor för varje kategori som stöds i kanalens navigeringshierarki.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-122">Products can also be discovered on category pages, which are dedicated pages for each category that is supported in the channel navigation hierarchy.</span></span> <span data-ttu-id="ac4e3-123">Dessutom kan förfiningsmoduler användas för att ytterligare filtrera resultat på sökresultat och kategorisidor.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-123">In addition, refiner modules can be used to further filter results on search results and category pages.</span></span>
- <span data-ttu-id="ac4e3-124">**Moduler för produktinformationssida** – produktinformationssidor använder flera moduler för att visa produktinformation.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-124">**Product details page modules** – Product details pages use several modules to show product information.</span></span> <span data-ttu-id="ac4e3-125">I modulen inköpsruta kan kunderna visa produkter och lägga till dem i vagnen.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-125">The buy box module lets customers view products and add them to the cart.</span></span> <span data-ttu-id="ac4e3-126">Andra moduler som till exempel modulen tekniska specifikationer visar produktinformation.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-126">Other modules, such as the tech specs module, show the product details.</span></span> <span data-ttu-id="ac4e3-127">Modulen värderingar och recensioner kan användas för att visa och ge recensioner.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-127">The ratings and reviews module can used to view and provide reviews.</span></span>
- <span data-ttu-id="ac4e3-128">**Modulen Köp online, hämta i butik** – Modulen Köp online, hämta i butik är integrerad med Bing Maps.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-128">**Buy online pick up in store module** – The buy online pick up in store module is integrated with Bing Maps.</span></span> <span data-ttu-id="ac4e3-129">Den kan användas för att hitta butiker i närheten där kunderna kan hämta produkter som de har köpt.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-129">It can be used to find nearby stores where customers can pick up products that they have purchased.</span></span>
- <span data-ttu-id="ac4e3-130">**Inköpsmoduler** – i inköps moduler ingår modulen kundvagn, som kan användas för att lägga till artiklar i kundvagnen.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-130">**Purchase modules** – Purchase modules include the cart module, which can be used to add items to the cart.</span></span> <span data-ttu-id="ac4e3-131">Kassamodulen visar leveransadress, leveransalternativ och presentkort, bonusprogram och kreditkortsinformation så att en order kan bearbetas.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-131">The checkout module captures the shipping address, delivery options, and gift card, loyalty program, and credit card information, so that an order can be processed.</span></span> <span data-ttu-id="ac4e3-132">När en order har placerats kan orderbekräftelsemodulen användas för att visa bekräftelseinformationen.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-132">After an order is placed, the order confirmation module can be used to show the confirmation details.</span></span>
- <span data-ttu-id="ac4e3-133">**Moduler för kontohantering** – med hjälp av inloggningsmodulen kan kunderna logga in på ett befintligt konto och registreringsmodulen skapa ett nytt konto.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-133">**Account management modules** – The sign-in module lets customers sign in to an existing account, and the sign-up module lets them create a new account.</span></span> <span data-ttu-id="ac4e3-134">När ett konto har skapats kan modulen för orderhistorik användas för att visa nya order och modulen orderspecifikationer kan användas för att visa orderdetaljer.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-134">After an account is created, the order history module can be used to view recent orders, and the order details module can be used to view order details.</span></span>
- <span data-ttu-id="ac4e3-135">**Rekommendationsmodulen-** – rekommendationerna visas med modulen produktplacering.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-135">**Recommendations module** – Recommendations are shown by using the product placement module.</span></span> <span data-ttu-id="ac4e3-136">Den här modulen stöder de algoritmiska och redaktionella listor som kan visas på alla sidor.</span><span class="sxs-lookup"><span data-stu-id="ac4e3-136">This module supports algorithmic and editorial lists that can be showcased on any page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ac4e3-137">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ac4e3-137">Additional resources</span></span>

[<span data-ttu-id="ac4e3-138">Behållaremodul</span><span class="sxs-lookup"><span data-stu-id="ac4e3-138">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="ac4e3-139">Modul för inköpsruta</span><span class="sxs-lookup"><span data-stu-id="ac4e3-139">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="ac4e3-140">Kundvagnsmodul</span><span class="sxs-lookup"><span data-stu-id="ac4e3-140">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="ac4e3-141">Kassamodul</span><span class="sxs-lookup"><span data-stu-id="ac4e3-141">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ac4e3-142">Modul för orderbekräftelse</span><span class="sxs-lookup"><span data-stu-id="ac4e3-142">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ac4e3-143">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="ac4e3-143">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="ac4e3-144">Modul för sidfot</span><span class="sxs-lookup"><span data-stu-id="ac4e3-144">Footer module</span></span>](author-footer-module.md)
