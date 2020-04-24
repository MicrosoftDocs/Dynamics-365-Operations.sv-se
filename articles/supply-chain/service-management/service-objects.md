---
title: Serviceobjekt – översikt
description: Serviceobjekt är en kunds tillgångar och produkter som du kan utföra en tjänst för.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1ac26083609a337a8d78929dd6f736e1a7c26767
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215158"
---
# <a name="service-objects-overview"></a><span data-ttu-id="0bfa6-103">Serviceobjekt – översikt</span><span class="sxs-lookup"><span data-stu-id="0bfa6-103">Service objects overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0bfa6-104">Serviceobjekt är en kunds tillgångar och produkter som du kan utföra en tjänst för.</span><span class="sxs-lookup"><span data-stu-id="0bfa6-104">Service objects are a customer’s assets and products for which you can perform a service.</span></span> <span data-ttu-id="0bfa6-105">Beroende på vilken typ av service du tillhandahåller kan objekt vara materiella eller immateriella:</span><span class="sxs-lookup"><span data-stu-id="0bfa6-105">Depending on the type of service you provide, objects can be tangible or intangible:</span></span>

-  <span data-ttu-id="0bfa6-106">Materiella objekt är saker, till exempel en maskin eller byggnad, som du kan utföra en fysisk serviceuppgift på.</span><span class="sxs-lookup"><span data-stu-id="0bfa6-106">Tangible objects are things, such as a machine or a building, on which you can perform a physical service task.</span></span>

    <span data-ttu-id="0bfa6-107">Ett materiellt serviceobjekt kan också vara en lagerartikel som du skapar i formuläret för information om frisläppt produkt.</span><span class="sxs-lookup"><span data-stu-id="0bfa6-107">A tangible service object can also be an inventory item that you create in the Released product details form.</span></span> <span data-ttu-id="0bfa6-108">Beroende på den lagerdimensionsgrupp som du kopplar till artikeln kan du skapa ett serviceobjekt till en detaljnivån som visar artikelns serienummer.</span><span class="sxs-lookup"><span data-stu-id="0bfa6-108">Depending on the inventory dimension group that you attach to the item, you can create a service object to a level of detail that includes the item serial number.</span></span> <span data-ttu-id="0bfa6-109">Detta är användbart när du måste hålla reda på exakt vilken artikel som serviceobjektet representerar.</span><span class="sxs-lookup"><span data-stu-id="0bfa6-109">This is useful when you must keep track of the exact item that the service object represents.</span></span>

    <span data-ttu-id="0bfa6-110">Ett materiellt serviceobjekt kan också vara en artikel som inte är direkt relaterad till företagets direkta tillverkning eller leveranskedja.</span><span class="sxs-lookup"><span data-stu-id="0bfa6-110">A tangible service object can also be an item that is not directly related to a company's direct production or supply chain.</span></span> <span data-ttu-id="0bfa6-111">Ett verktygskit som till exempel används för reparation i en serviceorder kan vara ett serviceobjekt som inte finns i lager.</span><span class="sxs-lookup"><span data-stu-id="0bfa6-111">For example, a tool kit that is used for repairs in a service order can be a service object that is not included in inventory.</span></span> <span data-ttu-id="0bfa6-112">I det här fallet registrerar du det inte som en lagerartikel.</span><span class="sxs-lookup"><span data-stu-id="0bfa6-112">In this case, you don’t register it as an inventory item.</span></span>

-  <span data-ttu-id="0bfa6-113">Immateriella objekt är icke fysiska ting, till exempel en grupp konton eller juridiska dokument, som du kan utföra serviceuppgifter på.</span><span class="sxs-lookup"><span data-stu-id="0bfa6-113">Intangible objects are nonphysical things, such as a set of accounts or a legal document, on which you can perform a service task.</span></span>

## <a name="example-of-an-intangible-service-object"></a><span data-ttu-id="0bfa6-114">Exempel på ett immateriellt serviceobjekt</span><span class="sxs-lookup"><span data-stu-id="0bfa6-114">Example of an intangible service object</span></span>

<span data-ttu-id="0bfa6-115">Företag A hanterar ekonomiska poster för flera mindre företag.</span><span class="sxs-lookup"><span data-stu-id="0bfa6-115">Company A maintains the financial records for several small companies.</span></span> <span data-ttu-id="0bfa6-116">En av företag A:s kunder är det lokala fotbollslaget, för vilket företag A sköter veckobokföringen den årliga granskningen av klubbens konton.</span><span class="sxs-lookup"><span data-stu-id="0bfa6-116">One of Company A's clients is the local football team, for which Company A does the weekly bookkeeping and annual audit of the club's accounts.</span></span> <span data-ttu-id="0bfa6-117">Klubbens konton ställs in i formuläret serviceobjekt och specificeras som objektet i serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="0bfa6-117">The club's accounts are set up in the Service objects form and specified as the object in the service agreement.</span></span> <span data-ttu-id="0bfa6-118">Det finns två rader för serviceavtal för objektet.</span><span class="sxs-lookup"><span data-stu-id="0bfa6-118">There are two service agreement lines for the object.</span></span> <span data-ttu-id="0bfa6-119">Rad 1 är veckobokföring med ett veckointervall som tilldelats raden, och rad 2 är den årliga granskningen med ett årligt intervall som tilldelats den.</span><span class="sxs-lookup"><span data-stu-id="0bfa6-119">Line 1 is weekly bookkeeping with a weekly interval assigned to the line, and line 2 is the annual audit with a yearly interval assigned to it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0bfa6-120">Relaterade ämnen</span><span class="sxs-lookup"><span data-stu-id="0bfa6-120">Related topics</span></span>

[<span data-ttu-id="0bfa6-121">Skapa serviceobjekt</span><span class="sxs-lookup"><span data-stu-id="0bfa6-121">Create service objects</span></span>](create-service-objects.md)

