---
title: Lägg till plats och partrelationstyper
description: Det här avsnittet förklarar hur du lägger till en ny plats och partrelationstyp.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 00810576d36339bf7ce0657b1577e1e322c36bf0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979099"
---
# <a name="add-location-and-party-relationship-types"></a><span data-ttu-id="3ce79-103">Lägg till plats och partrelationstyper</span><span class="sxs-lookup"><span data-stu-id="3ce79-103">Add location and party relationship types</span></span> 

[!include [banner](../includes/banner.md)]

## <a name="add-location-roles"></a><span data-ttu-id="3ce79-104">Lägg till platsroller</span><span class="sxs-lookup"><span data-stu-id="3ce79-104">Add location roles</span></span>

<span data-ttu-id="3ce79-105">Det finns två sätt att lägga till en ny platsroller för adress och kontaktinformation:</span><span class="sxs-lookup"><span data-stu-id="3ce79-105">There are two ways to add a new location roles for address and contact information:</span></span>

-  <span data-ttu-id="3ce79-106">Lägg till den genom sidan **Syfte för adress och kontaktinformation**.</span><span class="sxs-lookup"><span data-stu-id="3ce79-106">Add it through the **Address and contact information purpose** page.</span></span> <span data-ttu-id="3ce79-107">Den nya rollen kommer att sparas i tabellen **LogisticsLocationRole** med typ = 0, vilket betyder att rollen inte är en systemroll som definieras i **LogisticsLocationRoleType** enum och dess tillägg.</span><span class="sxs-lookup"><span data-stu-id="3ce79-107">The new role will be saved to the **LogisticsLocationRole** table with type = 0, which indicates that the role is not a system role defined in the **LogisticsLocationRoleType** enum and its extensions.</span></span> <span data-ttu-id="3ce79-108">En användare kommer att kunna använda den här rollen när du skapar en adress eller kontaktinformation.</span><span class="sxs-lookup"><span data-stu-id="3ce79-108">A user will be able to use this role when creating address or contact information.</span></span>

    ![Syfte för adress och innehållsinformation](media/Address-Contact.PNG)

-  <span data-ttu-id="3ce79-110">Lägg till den i **LogisticsLocationRoleType** enum tillägg och låt den fyllas i genom databasens synkroniseringsprocess.</span><span class="sxs-lookup"><span data-stu-id="3ce79-110">Add it to the **LogisticsLocationRoleType** enum extension, and let it populate through the database sync process.</span></span>

    1.  <span data-ttu-id="3ce79-111">Skapa ett tillägg till enum **LogisticsLocationRoleType** och lägga till den nya rollen i tillägget.</span><span class="sxs-lookup"><span data-stu-id="3ce79-111">Create an extension to the **LogisticsLocationRoleType** enum and add the new role in the extension.</span></span> 
  
        ![Tillägg till LogisticsLocationRoleType-enum](media/Logistics.PNG)

    2. <span data-ttu-id="3ce79-113">Skapa en ny resursfil för den nya rollen och tilldela ett värde för egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="3ce79-113">Create a new resource file for the new role, and then assign a value for its properties.</span></span>
     
     ![Ny resursfil](media/Resource.PNG)
        
    3.  <span data-ttu-id="3ce79-115">Skapa en datapopulationsklass och ge en hanterarmetod för att fylla i den nya rollen.</span><span class="sxs-lookup"><span data-stu-id="3ce79-115">Create a data population class and provide a handler method to populate the new role.</span></span> 

        ![Datapopulation](media/Dirdata.PNG)

    4.  <span data-ttu-id="3ce79-117">Om du vill testa att fylla i den nya platsrollen kan du skapa en körbar klass och anropa DirDataPopulation::insertLogisticsLocationRoles() i Main().</span><span class="sxs-lookup"><span data-stu-id="3ce79-117">To test populating the new location role, you can create a runnable class, and call DirDataPopulation::insertLogisticsLocationRoles() in Main().</span></span> <span data-ttu-id="3ce79-118">När den här processen är slutförd bör du se den nya rollen ifylld i registret **LogisticsLocationRole** av typen \>0.</span><span class="sxs-lookup"><span data-stu-id="3ce79-118">After this process is complete, you should see the new role populated in the **LogisticsLocationRole** table with type \> 0.</span></span> <span data-ttu-id="3ce79-119">Den nya rollen kommer att visas på sidan **Syfte för adress och kontaktinformation**.</span><span class="sxs-lookup"><span data-stu-id="3ce79-119">The new role will display on the **Address and contact information purpose** page.</span></span>

        ![Infoga nya platser](media/InsertNewLocation.PNG)

## <a name="add-party-relationship-types"></a><span data-ttu-id="3ce79-121">Lägg till partrelationstyper</span><span class="sxs-lookup"><span data-stu-id="3ce79-121">Add party relationship types</span></span> 

<span data-ttu-id="3ce79-122">Det finns två sätt att lägga till en ny relationstyp:</span><span class="sxs-lookup"><span data-stu-id="3ce79-122">There are two ways to add a new relationship type:</span></span>

-   <span data-ttu-id="3ce79-123">Lägg till den på sidan **relationstyper**.</span><span class="sxs-lookup"><span data-stu-id="3ce79-123">Add it through the **Relationship types** page.</span></span> <span data-ttu-id="3ce79-124">Den nya relationen ska sparas till **DirRelationshipTypeTable** med systemtype = 0.</span><span class="sxs-lookup"><span data-stu-id="3ce79-124">The new relationship will be saved to **DirRelationshipTypeTable** with systemtype = 0.</span></span>

    ![Relationstyper](media/Relationship.PNG)

-  <span data-ttu-id="3ce79-126">Lägg till den till tillägget för **DirSystemRelationshipType** enum och låt den fyllas i genom databasens synkroniseringsprocess.</span><span class="sxs-lookup"><span data-stu-id="3ce79-126">Add it to the extension of the **DirSystemRelationshipType** enum, and let it populate through database sync process.</span></span>

    1.  <span data-ttu-id="3ce79-127">Skapa ett tillägg till enum **DirSystemRelationshipType** och lägg till den nya relationstypen.</span><span class="sxs-lookup"><span data-stu-id="3ce79-127">Create an extension to the **DirSystemRelationshipType** enum and add the new relationship type.</span></span>

    2. <span data-ttu-id="3ce79-128">Skapa en initierare för den nya typen.</span><span class="sxs-lookup"><span data-stu-id="3ce79-128">Create an initializer for this new type.</span></span> <span data-ttu-id="3ce79-129">Du hittar flera exempel i kärnkoden, en av dem är **DirRelationshipTypeChildInitialize**.</span><span class="sxs-lookup"><span data-stu-id="3ce79-129">You can find several examples in the core code, one of them is  **DirRelationshipTypeChildInitialize**.</span></span> <span data-ttu-id="3ce79-130">Detta är initierarklass för partrelationstypen ”underordnad”.</span><span class="sxs-lookup"><span data-stu-id="3ce79-130">This is an initializer class for party relationship type “Child”.</span></span> <span data-ttu-id="3ce79-131">Du kan börja med din initierare genom att kopiera och klistra in koden och sedan uppdatera de markerade områdena.</span><span class="sxs-lookup"><span data-stu-id="3ce79-131">You can start with your initializer by copying and pasting this code and then update the highlighted areas.</span></span>
    
    ![DirRelationshipChild initierare](media/DirRelationship.PNG)

    3.  <span data-ttu-id="3ce79-133">Om du vill testa att fylla i den nya relationstypen kan du skapa en körbar klass och anropa DirDataPopulation::insertDirRelationshipTypes() i Main().</span><span class="sxs-lookup"><span data-stu-id="3ce79-133">To test populating the new relationship type, you can create a runnable class, and call DirDataPopulation::insertDirRelationshipTypes() in Main().</span></span> <span data-ttu-id="3ce79-134">Du bör se den nya relationstypen i **DirRelationshipTypeTable**, och den nya relationstypen kommer att finnas tillgänglig på sidan **relationstyper**.</span><span class="sxs-lookup"><span data-stu-id="3ce79-134">You should see the new relationship type in the **DirRelationshipTypeTable**, and the new relationship type will be available on the **Relationship types** page.</span></span>

        ![Körbar klass](media/Runnable.PNG)
