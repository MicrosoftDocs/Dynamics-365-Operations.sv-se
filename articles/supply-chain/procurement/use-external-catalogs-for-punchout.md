---
title: Använd externa kataloger för PunchOut eProcurement
description: Det här avsnittet beskriver hur du kan använda externa kataloger för att skapa och skicka rekvisitioner.
author: mkirknel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchVendorPortalRequests, CatExternalCatalogBasketWizard, CatExternalCatalogPunchoutDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 30211
ms.assetid: 3c7e0e1c-703c-4bbf-b90c-84d29a131360
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cccd3517f31a82e502052f100e44322ac4cb344f
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438090"
---
# <a name="use-external-catalogs-for-punchout-e-procurement"></a><span data-ttu-id="5d0a7-103">Använd externa kataloger för PunchOut eProcurement</span><span class="sxs-lookup"><span data-stu-id="5d0a7-103">Use external catalogs for PunchOut e-procurement</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5d0a7-104">Genom att använda externa kataloger för PunchOut eProcurement behöver du inte underhålla information om dina leverantörers produkter i dina egna huvuddata.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-104">By using external catalogs for PunchOut e-procurement, you don't have to maintain information about your vendors' products in your own master data.</span></span> <span data-ttu-id="5d0a7-105">I stället konverteras shoppingvagnen på en leverantörs webbplats till rekvisitionsrader som har rätt produktinformation.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-105">Instead, the shopping cart on a vendor's website is converted to requisition lines that have the correct product information.</span></span> 

<span data-ttu-id="5d0a7-106">Undvik att underhålla beskrivningar och priser på dina leverantörers produkter i dina egna huvuddata för produkten.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-106">You should avoid maintaining the descriptions and prices of your vendors’ products in your own product master data.</span></span> <span data-ttu-id="5d0a7-107">Använd i stället externa kataloger för PunchOut eProcurement.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-107">Instead, use external catalogs for PunchOut e-procurement.</span></span> <span data-ttu-id="5d0a7-108">När medarbetare sedan skapar rekvisitioner kan de ”omdirigeras” till en extern katalogwebbplats för en leverantör (d.v.s. de lämnar ditt system och går till leverantörens webbplats).</span><span class="sxs-lookup"><span data-stu-id="5d0a7-108">Then, when employees create requisitions, they can “punch out” to a vendor’s external catalog site (in other words, they leave your system and go to the vendor’s site).</span></span> <span data-ttu-id="5d0a7-109">Produkter som läggs till i shoppingvagnen på leverantörens webbplats kan sedan att konverteras till rekvisitionsrader.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-109">The products that are added to the shopping cart on the vendor’s website can then be converted to requisition lines.</span></span> <span data-ttu-id="5d0a7-110">Därför får du rätt produktinformation: produkt-ID, namn, pris och så vidare.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-110">Therefore, you get the correct product information: product ID, name, price, and so on.</span></span>

<span data-ttu-id="5d0a7-111">Om du vill använda externa kataloger måste du skapa en rekvisition på sidan **Mina inköpsrekvisitioner**.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-111">To use external catalogs, an employee must create a requisition on the **My purchase requisitions** page.</span></span>

<span data-ttu-id="5d0a7-112">Den medarbetare som skapar en rekvisition kallas för förberedaren av rekvisitionen.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-112">The employee who creates a requisition is referred to as the preparer of the requisition.</span></span> <span data-ttu-id="5d0a7-113">Som förberedare kan du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="5d0a7-113">As a preparer, you can complete the following tasks.</span></span>

<span data-ttu-id="5d0a7-114">Använd radåtgärden **Externa kataloger** för att öppna en sida som innehåller alla externa kataloger som är tillgängliga för angivna beställaren, juridisk person för inköp och mottagande driftenhet.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-114">Use the **External catalogs** line action to open a page that includes all external catalogs that are available for the specified requester, buying legal entity, and receiving operating unit.</span></span>

<span data-ttu-id="5d0a7-115">Beroende på dina behörigheter, ändra beställaren, den juridiska personen för inköp och den mottagande driftenheten.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-115">Depending on your permissions, change the requester, buying legal entity, and receiving operating unit.</span></span> <span data-ttu-id="5d0a7-116">En ändring av dessa värden kan ändra listan över externa kataloger som är tillgängliga för en beställare.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-116">A change in those values might change the list of external catalogs that are available to a requester.</span></span> <span data-ttu-id="5d0a7-117">Vilka externa kataloger som är tillgängliga beror på de aktuella aktiva inköpspolicyerna för den juridiska personen för inköp och den mottagande driftenheten.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-117">The external catalogs that are available depend on the current active purchasing policies for the buying legal entity or the receiving operating unit.</span></span> <span data-ttu-id="5d0a7-118">Dessa policyer kan tillåta eller neka åtkomst till specifika anskaffningskategorier.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-118">These policies can allow or prevent access to specific procurement categories.</span></span> <span data-ttu-id="5d0a7-119">Därför kan listan över externa kataloger som är mappade till dessa anskaffningskategorier påverkas.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-119">Therefore, the list of external catalogs that are mapped to these procurement categories can be affected.</span></span>

<span data-ttu-id="5d0a7-120">Mer information om hur du ställer in policyer finns i [Inköpspolicyer - översikt](../procurement/purchase-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5d0a7-120">For more information about policies, see [Purchasing policies overview](../procurement/purchase-policies.md).</span></span>

- <span data-ttu-id="5d0a7-121">Mata in text i katalogens sökfält om du vill söka efter externa kataloger för specifika anskaffningskategorier.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-121">To find external catalogs for specific procurement categories, enter text in the catalog search field.</span></span>
- <span data-ttu-id="5d0a7-122">Klicka på den externa katalogen om du vill lägga till produkter från en leverantörs extern katalog på leverantörens webbplats.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-122">To add products from a vendor’s external catalog on the vendor’s website, click the external catalog.</span></span> <span data-ttu-id="5d0a7-123">Lägg sedan till produkter i shoppingvagnen och checka ut. Shoppingvagnsraderna överförs till Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-123">Then add products to the shopping cart, and check out. The shopping cart lines will be transferred to Microsoft Dynamics 365.</span></span>

<span data-ttu-id="5d0a7-124">Om det finns flera alternativ för anskaffningskategorier, markera rätt anskaffningskategori innan du lägger till rader i rekvisitionen.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-124">If there are multiple options for procurement categories, select the correct procurement category before you add the lines to the requisition.</span></span>
<span data-ttu-id="5d0a7-125">När rader har lagts till i en inköpsrekvisition kan du lägga till fler rader utan att använda externa kataloger.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-125">After lines have been added to a requisition, you can add more lines without using external catalogs.</span></span> <span data-ttu-id="5d0a7-126">Alternativt kan du fortsätta att använda externa kataloger för att lägga till rader.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-126">Alternatively, you can continue to use external catalogs to add lines.</span></span>

<span data-ttu-id="5d0a7-127">När rekvisitionen är klar använder du åtgärden **Srbetsflöde** > **Skicka** för att skicka den för godkännande.</span><span class="sxs-lookup"><span data-stu-id="5d0a7-127">When the requisition is ready, use the **Workflow** > **Submit** action to submit it for approval.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5d0a7-128">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5d0a7-128">Additional resources</span></span>

- [<span data-ttu-id="5d0a7-129">Ställ in en extern katalog för PunchOut eProcurement</span><span class="sxs-lookup"><span data-stu-id="5d0a7-129">Set up an external catalog for PunchOut e-procurement</span></span>](set-up-external-catalog-for-punchout.md)
- [<span data-ttu-id="5d0a7-130">Förbättringar i inköps-cXML</span><span class="sxs-lookup"><span data-stu-id="5d0a7-130">Purchasing cXML enhancements</span></span>](purchasing-cxml-enhancements.md)