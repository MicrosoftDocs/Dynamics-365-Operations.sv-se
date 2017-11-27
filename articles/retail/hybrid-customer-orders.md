---
title: Hybridkundorder
description: "Hybridkundorder är en enstaka order som innehåller produkter som kan bäras ut från butiken av kunden själv, samt produkter som hämtas eller levereras senare."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Operations, Core
ms.custom: 261164
ms.assetid: 9d99a5b9-4662-499a-bece-3ea1d6092934
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ed5d403c1321e2573df38d60956e6f89282b3de8
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="hybrid-customer-orders"></a><span data-ttu-id="2b383-103">Hybridkundorder</span><span class="sxs-lookup"><span data-stu-id="2b383-103">Hybrid customer orders</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="2b383-104">Hybridkundorder är en enstaka order som innehåller produkter som kan bäras ut från butiken av kunden själv, samt produkter som hämtas eller levereras senare.</span><span class="sxs-lookup"><span data-stu-id="2b383-104">A hybrid customer order is a single order, which contains products that can be carried out of the store by the customer, as well as products that will be picked up or shipped later.</span></span>

<span data-ttu-id="2b383-105">I Microsoft Dynamics 365 for Retail kan du välja att antingen leverera alla produkter eller att leverera valda produkter för en kundorder.</span><span class="sxs-lookup"><span data-stu-id="2b383-105">In Microsoft Dynamics 365 for Retail, you can select either carry out all products or carry out selected products for a customer order.</span></span> <span data-ttu-id="2b383-106">De produktrader som markerats att utföras faktureras automatiskt när ordern skapas; detsamma gäller för en order som ska hämtas upp när ordern skapas.</span><span class="sxs-lookup"><span data-stu-id="2b383-106">The product lines that are marked as carry out are automatically invoiced after the order is created, similarly this is the same for an order that is to be picked-up after the order is created.</span></span> <span data-ttu-id="2b383-107">Det förfallna beloppet i hybridorder bestäms genom att addera depositionsprocentsatsen för produktrader av typen plocka-och-leverera med hela beloppet för de rader som ska utföras.</span><span class="sxs-lookup"><span data-stu-id="2b383-107">The amount due on hybrid orders is determined by adding the deposit percentage on pick and ship product lines with the full amount of the carry out lines.</span></span> <span data-ttu-id="2b383-108">För hybridorder växlar systemet mellan läget för kundorder och läget för cash and carry enligt följande:</span><span class="sxs-lookup"><span data-stu-id="2b383-108">For hybrid orders, the system switches between customer order mode and cash and carry mode as follows:</span></span>

-   <span data-ttu-id="2b383-109">Om alla produkter i vagnen bär statusen **Utför leverans**, kommer ordern att behandlas som en cash and carry-transaktion.</span><span class="sxs-lookup"><span data-stu-id="2b383-109">If all products in the cart are set to **Carry out delivery**, the order will be handled as a Cash and Carry transaction.</span></span>
-   <span data-ttu-id="2b383-110">Om någon rad eller alla rader i vagnen bär statusen **Plocka** eller **Skeppa leverans** kommer ordern att hanteras som en kundordertransaktion.</span><span class="sxs-lookup"><span data-stu-id="2b383-110">If any or all lines in the cart are set to either **Pick** or **ship delivery**, the order will be handled as a Customer order transaction.</span></span>

<span data-ttu-id="2b383-111">Om en vagnrad har valts och **Plocka valda**, **Skeppa valda** eller **Leverera valda** har markerats, kommer endast den specifika vagnraden att erhålla den leveransmetoden .</span><span class="sxs-lookup"><span data-stu-id="2b383-111">If a cart line is selected and **Pick selected**, **Ship selected**, or **Carry out selected** is selected, only the specific cart line is set with that delivery method.</span></span> <span data-ttu-id="2b383-112">I så fall fortsätter det underordnade åtgärdsflödet som vanligt.</span><span class="sxs-lookup"><span data-stu-id="2b383-112">In that case, the downstream flow of the operation continues as usual.</span></span> <span data-ttu-id="2b383-113">Om emellertid **Plocka valda**, **Skeppa valda** eller **Leverera valda** har valts utan att någon vagnrad har markerats, öppnas en ny sida med en lista över alla vagnrader.</span><span class="sxs-lookup"><span data-stu-id="2b383-113">However, if **Pick selected**, **Ship selected**, or **Carry out selected** is selected without a cart line being selected, a new page opens that lists all the cart lines.</span></span> <span data-ttu-id="2b383-114">På denna skärm kan du välja flera olika rader samtidigt för inställning av leveransmetoden.</span><span class="sxs-lookup"><span data-stu-id="2b383-114">On that screen, you can select multiple lines at once for setting the delivery method.</span></span> <span data-ttu-id="2b383-115">När du använder denna metod för att välja rader, åsidosätts tidigare leveransmetod som har tilldelats raden.</span><span class="sxs-lookup"><span data-stu-id="2b383-115">When you use that method for selecting lines, any previous delivery method that has been assigned to the line will be overridden.</span></span>

<a name="see-also"></a><span data-ttu-id="2b383-116">Se även</span><span class="sxs-lookup"><span data-stu-id="2b383-116">See also</span></span>
--------

[<span data-ttu-id="2b383-117">Kundorderöversikt</span><span class="sxs-lookup"><span data-stu-id="2b383-117">Customer orders overview</span></span>](customer-orders-overview.md)




