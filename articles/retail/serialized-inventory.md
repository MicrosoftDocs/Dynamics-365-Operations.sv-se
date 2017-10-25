---
title: "Kassaförbättringar för serialiserade produkter"
description: "Detta avsnitt listar förbättringar som har gjorts på serialiserade produkter i syfte att hjälpa dig att spara tid och bli mer produktiv."
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-08-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 214452d0f40265c0ed9fac7a74844ad89782257d
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="pos-improvements-for-serialized-products"></a><span data-ttu-id="f89e3-103">Kassaförbättringar för serialiserade produkter</span><span class="sxs-lookup"><span data-stu-id="f89e3-103">POS improvements for serialized products</span></span>

[!include[banner](includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="f89e3-104">Översikt</span><span class="sxs-lookup"><span data-stu-id="f89e3-104">Overview</span></span> 
<span data-ttu-id="f89e3-105">Baserat på inställningarna i detaljhandelns huvudkontor kan produkterna klassificeras som antingen serialiserade eller icke-serialiserade.</span><span class="sxs-lookup"><span data-stu-id="f89e3-105">Based on the settings in Retail headquarters, products can be classified as either serialized or non-serialized.</span></span> <span data-ttu-id="f89e3-106">När produkterna serialiseras kan respektive vara tilldelas ett unikt nummer som hjälper dig att spåra garantier och artiklar, samt bekräfta ägarskap.</span><span class="sxs-lookup"><span data-stu-id="f89e3-106">When products are serialized, each item can be assigned a unique number that helps track warranties, trace items, and confirm ownership.</span></span> <span data-ttu-id="f89e3-107">Även om möjligheten att tillhandahålla serienummer för serialiserade produkter redan fanns i vårt moderna kassasystem/kassasystem via moln har vissa förbättringar införts i syfte att hjälpa kassapersonalen att spara tid och vara mer produktiv.</span><span class="sxs-lookup"><span data-stu-id="f89e3-107">Although, the ability to provide serial numbers for serialized products existed in our Modern/Cloud Point of Sale (POS), some improvements have been added to help cashiers save time and be more productive.</span></span>  

## <a name="pos-improvements"></a><span data-ttu-id="f89e3-108">Kassaförbättringar</span><span class="sxs-lookup"><span data-stu-id="f89e3-108">POS improvements</span></span>

- <span data-ttu-id="f89e3-109">**Serienummer krävs inte före kassan** – Tidigare måste en kassör som lade till en serialiserad produkt i transaktionen även ange ett serienummer.</span><span class="sxs-lookup"><span data-stu-id="f89e3-109">**Serial numbers aren't required until checkout** – Previously, a cashier who added a serialized product to the transaction was required to provide a serial number.</span></span> <span data-ttu-id="f89e3-110">Detta krav blev ett problem i samband med kundmöten då kassörer och säljmedarbetare hade möjlighet till merförsäljning.</span><span class="sxs-lookup"><span data-stu-id="f89e3-110">This requirement became an issue in clienteling scenarios, if cashiers and sales associates had an opportunity to up-sell products.</span></span> <span data-ttu-id="f89e3-111">Före betalsteget uppdaterades produkterna ofta i kundvagnen.</span><span class="sxs-lookup"><span data-stu-id="f89e3-111">Until the payment step, the products were often updated in the cart.</span></span> <span data-ttu-id="f89e3-112">Varje gång en kassör lade till en ny produkt efterfrågade systemet därför serienumret.</span><span class="sxs-lookup"><span data-stu-id="f89e3-112">Therefore, every time that a cashier added a new product, the system prompted him or her for the serial number.</span></span> <span data-ttu-id="f89e3-113">Dialogrutan för serienummer innehåller nu knappen **Lägg till senare**.</span><span class="sxs-lookup"><span data-stu-id="f89e3-113">The serial number dialog box now includes an **Add later** button.</span></span> <span data-ttu-id="f89e3-114">Säljmedarbetarna kan därför lägga till varan i transaktionen, men kan ange serienumret senare.</span><span class="sxs-lookup"><span data-stu-id="f89e3-114">Therefore, the sales associates can add the item to the transaction but can provide the serial number later.</span></span> <span data-ttu-id="f89e3-115">Säljmedarbetarna kan snabbt lägga till och byta ut serialiserade varor i kundvagnen och sedan kan ange serienumret precis före kassan.</span><span class="sxs-lookup"><span data-stu-id="f89e3-115">Sales associates can quickly add and replace serialized items in the cart, and then provide the serial number just before checkout.</span></span> <span data-ttu-id="f89e3-116">Om serienumret inte anges för en serialiserad produkt kommer an kassör som försöker slutföra transaktionen att få ett felmeddelande.</span><span class="sxs-lookup"><span data-stu-id="f89e3-116">If the serial number isn't provided for any serialized product, a cashier who tries to complete the transaction receives an error message.</span></span> <span data-ttu-id="f89e3-117">Detta meddelande anger att kassören måste ange de serienummer som saknas innan han eller hon kan fortsätta.</span><span class="sxs-lookup"><span data-stu-id="f89e3-117">This messages that states that the cashier must provide the missing serial numbers before he or she can continue.</span></span>

    <span data-ttu-id="f89e3-118">En kommentar visas under transaktionsraden för varje enskild serialiserad vara där serienumret hoppades över.</span><span class="sxs-lookup"><span data-stu-id="f89e3-118">For each serialized item where the serial number was skipped, a comment appears under the transaction line.</span></span> <span data-ttu-id="f89e3-119">Denna kommentar anger att serienumret inte har angetts för varan.</span><span class="sxs-lookup"><span data-stu-id="f89e3-119">This comment states that the serial number hasn't been provided for the item.</span></span> <span data-ttu-id="f89e3-120">Kassören kan därför snabbt hitta varor som saknar ett serienummer.</span><span class="sxs-lookup"><span data-stu-id="f89e3-120">Therefore, the cashier can quickly find items that are missing a serial number.</span></span>

    <span data-ttu-id="f89e3-121">Den nya åtgärden **Lägg till serienummer** tillhandahåller även serienummer för varor som saknar serienummer.</span><span class="sxs-lookup"><span data-stu-id="f89e3-121">A new **Add serial number** operation also provides the serial number for items that are missing a serial number.</span></span> <span data-ttu-id="f89e3-122">Ett angivet serienummer kan inte redigeras.</span><span class="sxs-lookup"><span data-stu-id="f89e3-122">After the serial number is provided, it can't be edited.</span></span> <span data-ttu-id="f89e3-123">Kassören måste ogiltigförklara raden och lägga till produkten på nytt.</span><span class="sxs-lookup"><span data-stu-id="f89e3-123">The cashier must void the line and add the product again.</span></span> 
    
- <span data-ttu-id="f89e3-124">**Inga serienummer krävs för att lägga kundorder** – Kundorder kan läggas i en butik och utföras från en annan.</span><span class="sxs-lookup"><span data-stu-id="f89e3-124">**Serial numbers aren't required in order to place customer orders** – Customer orders can be placed in one store and fulfilled from another.</span></span> <span data-ttu-id="f89e3-125">En kassör som lägger en kundorder behöver inte ange något serienummer.</span><span class="sxs-lookup"><span data-stu-id="f89e3-125">A cashier who places a customer order doesn't have to provide the serial number.</span></span> <span data-ttu-id="f89e3-126">Serienumret anges i samband med plock eller hämtning.</span><span class="sxs-lookup"><span data-stu-id="f89e3-126">The serial number will be provided during the picking or pickup step.</span></span> <span data-ttu-id="f89e3-127">Ett serienummer måste emellertid anges för samtliga radobjekt som leveranstypen **Utkörning** väljs för.</span><span class="sxs-lookup"><span data-stu-id="f89e3-127">However, a serial number must be provided for all line items that the **Carry out** delivery type is selected for.</span></span> <span data-ttu-id="f89e3-128">I annat fall kan transaktionen inte slutföras.</span><span class="sxs-lookup"><span data-stu-id="f89e3-128">Otherwise, the transaction can't be completed.</span></span>    
- <span data-ttu-id="f89e3-129">**Serialiserade produkter sammanställs inte på transaktionsskärmen** – Inställningen **Sammanställda produkter** i fältgruppen **Terminal** på sidan **Funktionalitetsprofil** låter dig sammanställa samma icke-serialiserade produkter på transaktionsskärmen.</span><span class="sxs-lookup"><span data-stu-id="f89e3-129">**Serialized products aren't aggregated on the transaction screen** – The **Aggregate products** setting in the **Terminal** field group on the **Functionality profile** page lets you aggregate the same non-serialized products on the transaction screen.</span></span> <span data-ttu-id="f89e3-130">När samma produkter sammanställs blir de lättare att se i transaktionsrutnätet.</span><span class="sxs-lookup"><span data-stu-id="f89e3-130">When the same products are aggregated, they are easier to see in the transaction grid.</span></span> <span data-ttu-id="f89e3-131">Eftersom serienummer som regel är unika och försäljningsmedarbetare inte behöver ange serienummer före kassan, gäller inställningen **Sammanställda produkter** emellertid inte serialiserade produkter.</span><span class="sxs-lookup"><span data-stu-id="f89e3-131">However, because serial numbers are generally unique, and sales associates don't have to enter serial numbers until checkout, the **Aggregate products** setting doesn't apply to serialized products.</span></span> <span data-ttu-id="f89e3-132">Därför kommer serialiserade produkter inte att sammanställas på transaktionsskärmen om inställningen **Sammanställ produkter** väljs.</span><span class="sxs-lookup"><span data-stu-id="f89e3-132">Therefore, serialized products won't be aggregated on the transaction screen if the **Aggregate products** setting is selected.</span></span>
