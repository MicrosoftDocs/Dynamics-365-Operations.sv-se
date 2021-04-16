---
title: Serviceobjektgrupper
description: Objektgrupper är användbara för att sortera och filtrera data om objekt för rapporter och statistik.
author: ShylaThompson
ms.date: 05/11/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a559bdc8f7851e38274d9d23070f969502942ad8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835880"
---
# <a name="service-object-groups"></a><span data-ttu-id="ff119-103">Serviceobjektgrupper</span><span class="sxs-lookup"><span data-stu-id="ff119-103">Service object groups</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ff119-104">Objektgrupper är användbara för att sortera och filtrera data om objekt för rapporter och statistik.</span><span class="sxs-lookup"><span data-stu-id="ff119-104">Object groups are useful for sorting and filtering the data about objects for reports and statistics.</span></span> <span data-ttu-id="ff119-105">Du kan exempelvis gruppera objekt efter geografisk placering eller typ.</span><span class="sxs-lookup"><span data-stu-id="ff119-105">For example, you can group objects by geographical location or by type.</span></span>

## <a name="group-by-geographical-location"></a><span data-ttu-id="ff119-106">Gruppera efter geografisk placering</span><span class="sxs-lookup"><span data-stu-id="ff119-106">Group by geographical location</span></span>

<span data-ttu-id="ff119-107">Du kan använda den här grupperingsmetoden för att visa var olika objekt som ditt företag utför tjänster hos finns.</span><span class="sxs-lookup"><span data-stu-id="ff119-107">You can use this grouping method to show where the various different objects that your company services are located.</span></span> <span data-ttu-id="ff119-108">Att gruppera objekt efter geografisk placering kan också vara användbart om du till exempel måste identifiera de objekt som ditt företag redan utför tjänster hos i ett visst land/region.</span><span class="sxs-lookup"><span data-stu-id="ff119-108">Grouping objects by geographical location can also be useful if, for example, you must identify the objects that your company already provides services for in a particular country/region.</span></span>

## <a name="example"></a><span data-ttu-id="ff119-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="ff119-109">Example</span></span>

<span data-ttu-id="ff119-110">En kund från Belgien ringer ditt servicecenter och vill skapa ett serviceavtal för ett objekt, ABC.</span><span class="sxs-lookup"><span data-stu-id="ff119-110">A customer from Belgium calls your service center and wants to create a service agreement for an object, ABC.</span></span> <span data-ttu-id="ff119-111">Du har kopplat en objektgrupp med den geografiska placeringen "Belgien" till alla objekt som företaget utför service hos i Belgien.</span><span class="sxs-lookup"><span data-stu-id="ff119-111">You have attached an object group for geographical location, Belgium, to all objects that are serviced in Belgium.</span></span> <span data-ttu-id="ff119-112">Genom att filtrera efter den här gruppen kan du snabbt ta reda på om ABC redan finns som en post i programmet eller om du måste skapa ett nytt objekt.</span><span class="sxs-lookup"><span data-stu-id="ff119-112">By using this group as a filter, you can quickly search to see whether you already have a record for ABC in the program, or whether you must set up a new object.</span></span> 

## <a name="group-by-type"></a><span data-ttu-id="ff119-113">Gruppera efter typ</span><span class="sxs-lookup"><span data-stu-id="ff119-113">Group by type</span></span>

<span data-ttu-id="ff119-114">Du kan använda den här grupperingsmetoden för att visa vilka typer av objekt som ditt företag utför tjänster hos.</span><span class="sxs-lookup"><span data-stu-id="ff119-114">You can use this grouping method to show the types of objects that your company services.</span></span> <span data-ttu-id="ff119-115">Att gruppera objekt efter typ kan också vara praktiskt om du exempelvis vill skapa ett nytt objekt baserat på liknande objekt som redan finns i programmet.</span><span class="sxs-lookup"><span data-stu-id="ff119-115">Grouping objects by type can also be useful if, for example, you want to create a new object based on similar objects that already exist in the program.</span></span>

## <a name="example"></a><span data-ttu-id="ff119-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="ff119-116">Example</span></span>

<span data-ttu-id="ff119-117">En kund ringer och vill skapa ett serviceavtal för en luftkonditioneringsmaskin, HIJ.</span><span class="sxs-lookup"><span data-stu-id="ff119-117">A customer calls and wants to set up a service agreement for an air conditioning machine, HIJ.</span></span> <span data-ttu-id="ff119-118">Du har inte en post för den här maskinen ännu.</span><span class="sxs-lookup"><span data-stu-id="ff119-118">You do not already have a record for this machine.</span></span> <span data-ttu-id="ff119-119">Men du har ställt in en objektgrupp som heter luftkonditioneringsapparater och du har kopplat den här gruppen till alla sådana objekt.</span><span class="sxs-lookup"><span data-stu-id="ff119-119">However, you have set up an object group titled Air Conditioners, and you have attached this group to all air conditioning objects.</span></span> <span data-ttu-id="ff119-120">Därför kan du snabbt söka efter och identifiera alla andra luftkonditioneringsapparater och använda mallinformationen från de här objekten för att skapa serviceavtalsrader för HIJ.</span><span class="sxs-lookup"><span data-stu-id="ff119-120">Therefore, you can quickly search for and identify all other air conditioning machines and use the template information from these objects to create service agreement lines for HIJ.</span></span> <span data-ttu-id="ff119-121">Genom att använda objektgrupper på det här sättet sparar du tid när du skapar nya objekt och avgör vilka serviceuppgifter som ska utföras på dem.</span><span class="sxs-lookup"><span data-stu-id="ff119-121">By using object groups in this manner, you can quickly set up new objects and determine the service tasks that must be performed on them.</span></span> 

## <a name="create-service-object-groups"></a><span data-ttu-id="ff119-122">Skapa en serviceobjektgrupp</span><span class="sxs-lookup"><span data-stu-id="ff119-122">Create service object groups</span></span>

<span data-ttu-id="ff119-123">Skapa grupper som du kan tilldela till serviceobjekt till.</span><span class="sxs-lookup"><span data-stu-id="ff119-123">Create groups that you can assign service objects to.</span></span> <span data-ttu-id="ff119-124">Serviceobjekt är lagerartiklar andra produkter som tjänster utförs för.</span><span class="sxs-lookup"><span data-stu-id="ff119-124">Service objects are inventory items and other products for which services are performed.</span></span> <span data-ttu-id="ff119-125">Genom att gruppera serviceobjekt kan du skapa rapporter för liknande och relaterade serviceobjekt.</span><span class="sxs-lookup"><span data-stu-id="ff119-125">By grouping service objects, you can create reports for similar and related service objects.</span></span> <span data-ttu-id="ff119-126">En serviceobjektgrupp kan till exempel bestå av två serviceobjekt: Ett serviceobjekt är ett paket och det andra serviceobjektet är tjänsten för att installera paketet.</span><span class="sxs-lookup"><span data-stu-id="ff119-126">For example, a service object group might consist of two service objects: One service object is a kit, and the second service object is the service to install the kit.</span></span>

<span data-ttu-id="ff119-127">Om du vill skapa serviceobjektgrupper, följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="ff119-127">To create service object groups, follow these steps:</span></span>

1. <span data-ttu-id="ff119-128">Klicka på **servicehantering > inställningar > serviceobjekt > serviceobjektgrupper**.</span><span class="sxs-lookup"><span data-stu-id="ff119-128">Click **Service management > Setup > Service objects > Service object groups**.</span></span>

2. <span data-ttu-id="ff119-129">Klicka på **Ny** om du vill skapa en ny serviceobjektgrupp.</span><span class="sxs-lookup"><span data-stu-id="ff119-129">Click **New** to create a new service object group.</span></span>

3. <span data-ttu-id="ff119-130">Ange ett unikt namn på serviceobjektgruppen och eventuellt en beskrivning.</span><span class="sxs-lookup"><span data-stu-id="ff119-130">Enter a unique name for the service object group and, optionally, a description.</span></span>

<span data-ttu-id="ff119-131">Du kan tilldela serviceobjekt till gruppen med hjälp av formuläret **Serviceobjekt**.</span><span class="sxs-lookup"><span data-stu-id="ff119-131">You can assign service objects to the group by using the **Service objects** form.</span></span> 

## <a name="see-also"></a><span data-ttu-id="ff119-132">Se även</span><span class="sxs-lookup"><span data-stu-id="ff119-132">See also</span></span>

[<span data-ttu-id="ff119-133">Skapa serviceobjekt</span><span class="sxs-lookup"><span data-stu-id="ff119-133">Create service objects</span></span>](create-service-objects.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]