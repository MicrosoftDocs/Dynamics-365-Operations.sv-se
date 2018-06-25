---
title: "Lägg till plats och partrelationstyper"
description: "Det här avsnittet förklarar hur du lägger till en ny plats och partrelationstyp."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: bf971bc6cf4b11de6381e369235d582678d074fc
ms.openlocfilehash: 8de914e0fb853cdc9aa36e55a02156757793abc3
ms.contentlocale: sv-se
ms.lasthandoff: 06/12/2018

---

# <a name="add-new-location-roles-and-party-relationship-types"></a><span data-ttu-id="81486-103">Lägg till nya platsroller och partrelationstyper</span><span class="sxs-lookup"><span data-stu-id="81486-103">Add new location roles and party relationship types</span></span> 

## <a name="add-new-location-roles"></a><span data-ttu-id="81486-104">Lägg till nya platsroller</span><span class="sxs-lookup"><span data-stu-id="81486-104">Add new location roles</span></span>

<span data-ttu-id="81486-105">Det finns två sätt att lägga till en ny platsroller för adress och kontaktinformation:</span><span class="sxs-lookup"><span data-stu-id="81486-105">There are two ways to add a new location roles for address and contact information:</span></span>

-  <span data-ttu-id="81486-106">Lägg till den genom sidan **Syfte för adress och kontaktinformation**.</span><span class="sxs-lookup"><span data-stu-id="81486-106">Add it through the **Address and contact information purpose** page.</span></span> <span data-ttu-id="81486-107">Den nya rollen kommer att sparas i tabellen **LogisticsLocationRole** med typ = 0, vilket betyder att rollen inte är en systemroll som definieras i **LogisticsLocationRoleType** enum och dess tillägg.</span><span class="sxs-lookup"><span data-stu-id="81486-107">The new role will be saved to the **LogisticsLocationRole** table with type = 0, which indicates that the role is not a system role defined in the **LogisticsLocationRoleType** enum and its extensions.</span></span> <span data-ttu-id="81486-108">En användare kommer att kunna använda den här rollen när du skapar en adress eller kontaktinformation.</span><span class="sxs-lookup"><span data-stu-id="81486-108">A user will be able to use this role when creating address or contact information.</span></span>

    ![Syfte för adress och innehållsinformation](media/Address-Contact.PNG)

-  <span data-ttu-id="81486-110">Lägg till den i **LogisticsLocationRoleType** enum tillägg och låt den fyllas i genom databasens synkroniseringsprocess.</span><span class="sxs-lookup"><span data-stu-id="81486-110">Add it to the **LogisticsLocationRoleType** enum extension, and let it populate through the database sync process.</span></span>

    1.  <span data-ttu-id="81486-111">Skapa ett tillägg till enum **LogisticsLocationRoleType** och lägga till den nya rollen i tillägget.</span><span class="sxs-lookup"><span data-stu-id="81486-111">Create an extension to the **LogisticsLocationRoleType** enum and add the new role in the extension.</span></span> 
  
        ![LogisticsLocationRoleType](media/Logistics.PNG)

    2. <span data-ttu-id="81486-113">Skapa en ny resursfil för den nya rollen och tilldela ett värde för egenskaperna.</span><span class="sxs-lookup"><span data-stu-id="81486-113">Create a new resource file for the new role, and then assign a value for its properties.</span></span>
     
     ![Ny resursfil](media/Resource.PNG)
        
    3.  <span data-ttu-id="81486-115">Skapa en datapopulationsklass och ge en hanterarmetod för att fylla i den nya rollen.</span><span class="sxs-lookup"><span data-stu-id="81486-115">Create a data population class and provide a handler method to populate the new role.</span></span> 

        ![Datapopulation](media/Dirdata.PNG)

    4.  <span data-ttu-id="81486-117">Om du vill testa att fylla i den nya platsrollen kan du skapa en körbar klass och anropa DirDataPopulation::insertLogisticsLocationRoles() i Main().</span><span class="sxs-lookup"><span data-stu-id="81486-117">To test populating the new location role, you can create a runnable class, and call DirDataPopulation::insertLogisticsLocationRoles() in Main().</span></span> <span data-ttu-id="81486-118">När den här processen är slutförd bör du se den nya rollen ifylld i registret **LogisticsLocationRole** av typen \>0.</span><span class="sxs-lookup"><span data-stu-id="81486-118">After this process is complete, you should see the new role populated in the **LogisticsLocationRole** table with type \> 0.</span></span> <span data-ttu-id="81486-119">Den nya rollen kommer att visas på sidan **Syfte för adress och kontaktinformation**.</span><span class="sxs-lookup"><span data-stu-id="81486-119">The new role will display on the **Address and contact information purpose** page.</span></span>

        ![Infoga nya platser](media/InsertNewLocation.PNG)

## <a name="add-new-party-relationship-types"></a><span data-ttu-id="81486-121">Lägg till nya partrelationstyper</span><span class="sxs-lookup"><span data-stu-id="81486-121">Add new party relationship types</span></span> 

<span data-ttu-id="81486-122">Det finns två sätt att lägga till en ny relationstyp:</span><span class="sxs-lookup"><span data-stu-id="81486-122">There are two ways to add a new relationship type:</span></span>

-   <span data-ttu-id="81486-123">Lägg till den på sidan **relationstyper**.</span><span class="sxs-lookup"><span data-stu-id="81486-123">Add it through the **Relationship types** page.</span></span> <span data-ttu-id="81486-124">Den nya relationen ska sparas till **DirRelationshipTypeTable** med systemtype = 0.</span><span class="sxs-lookup"><span data-stu-id="81486-124">The new relationship will be saved to **DirRelationshipTypeTable** with systemtype = 0.</span></span>

    ![Relationstyper](media/Relationship.PNG)

-  <span data-ttu-id="81486-126">Lägg till den till tillägget för **DirSystemRelationshipType** enum och låt den fyllas i genom databasens synkroniseringsprocess.</span><span class="sxs-lookup"><span data-stu-id="81486-126">Add it to the extension of the **DirSystemRelationshipType** enum, and let it populate through database sync process.</span></span>

    1.  <span data-ttu-id="81486-127">Skapa ett tillägg till enum **DirSystemRelationshipType** och lägg till den nya relationstypen.</span><span class="sxs-lookup"><span data-stu-id="81486-127">Create an extension to the **DirSystemRelationshipType** enum and add the new relationship type.</span></span>

    2. <span data-ttu-id="81486-128">Skapa en initierare för den nya typen.</span><span class="sxs-lookup"><span data-stu-id="81486-128">Create an initializer for this new type.</span></span> <span data-ttu-id="81486-129">Du hittar flera exempel i kärnkoden, en av dem är **DirRelationshipTypeChildInitialize**.</span><span class="sxs-lookup"><span data-stu-id="81486-129">You can find several examples in the core code, one of them is  **DirRelationshipTypeChildInitialize**.</span></span> <span data-ttu-id="81486-130">Detta är initierarklass för partrelationstypen ”underordnad”.</span><span class="sxs-lookup"><span data-stu-id="81486-130">This is an initializer class for party relationship type “Child”.</span></span> <span data-ttu-id="81486-131">Du kan börja med din initierare genom att kopiera och klistra in koden och sedan uppdatera de markerade områdena.</span><span class="sxs-lookup"><span data-stu-id="81486-131">You can start with your initializer by copying and pasting this code and then update the highlighted areas.</span></span>
    
    ![DirRelationshipChild](media/DirRelationship.PNG)

    3.  <span data-ttu-id="81486-133">Om du vill testa att fylla i den nya relationstypen kan du skapa en körbar klass och anropa DirDataPopulation::insertDirRelationshipTypes() i Main().</span><span class="sxs-lookup"><span data-stu-id="81486-133">To test populating the new relationship type, you can create a runnable class, and call DirDataPopulation::insertDirRelationshipTypes() in Main().</span></span> <span data-ttu-id="81486-134">Du bör se den nya relationstypen i **DirRelationshipTypeTable**, och den nya relationstypen kommer att finnas tillgänglig på sidan **relationstyper**.</span><span class="sxs-lookup"><span data-stu-id="81486-134">You should see the new relationship type in the **DirRelationshipTypeTable**, and the new relationship type will be available on the **Relationship types** page.</span></span>

        ![Körbar klass](media/Runnable.PNG)
