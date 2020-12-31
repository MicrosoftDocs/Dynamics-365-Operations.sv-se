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
ms.search.scope: Core, Operations
ms.custom: 13991
ms.assetid: 2a0a4789-8619-4974-bef9-0923cc848420
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-05-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: e38d0bd75ad865b7885182f798beb43551576beb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448037"
---
# <a name="add-location-and-party-relationship-types"></a>Lägg till plats och partrelationstyper 

[!include [banner](../includes/banner.md)]

## <a name="add-location-roles"></a>Lägg till platsroller

Det finns två sätt att lägga till en ny platsroller för adress och kontaktinformation:

-  Lägg till den genom sidan **Syfte för adress och kontaktinformation**. Den nya rollen kommer att sparas i tabellen **LogisticsLocationRole** med typ = 0, vilket betyder att rollen inte är en systemroll som definieras i **LogisticsLocationRoleType** enum och dess tillägg. En användare kommer att kunna använda den här rollen när du skapar en adress eller kontaktinformation.

    ![Syfte för adress och innehållsinformation](media/Address-Contact.PNG)

-  Lägg till den i **LogisticsLocationRoleType** enum tillägg och låt den fyllas i genom databasens synkroniseringsprocess.

    1.  Skapa ett tillägg till enum **LogisticsLocationRoleType** och lägga till den nya rollen i tillägget. 
  
        ![Tillägg till LogisticsLocationRoleType-enum](media/Logistics.PNG)

    2. Skapa en ny resursfil för den nya rollen och tilldela ett värde för egenskaperna.
     
     ![Ny resursfil](media/Resource.PNG)
        
    3.  Skapa en datapopulationsklass och ge en hanterarmetod för att fylla i den nya rollen. 

        ![Datapopulation](media/Dirdata.PNG)

    4.  Om du vill testa att fylla i den nya platsrollen kan du skapa en körbar klass och anropa DirDataPopulation::insertLogisticsLocationRoles() i Main(). När den här processen är slutförd bör du se den nya rollen ifylld i registret **LogisticsLocationRole** av typen \>0. Den nya rollen kommer att visas på sidan **Syfte för adress och kontaktinformation**.

        ![Infoga nya platser](media/InsertNewLocation.PNG)

## <a name="add-party-relationship-types"></a>Lägg till partrelationstyper 

Det finns två sätt att lägga till en ny relationstyp:

-   Lägg till den på sidan **relationstyper**. Den nya relationen ska sparas till **DirRelationshipTypeTable** med systemtype = 0.

    ![Relationstyper](media/Relationship.PNG)

-  Lägg till den till tillägget för **DirSystemRelationshipType** enum och låt den fyllas i genom databasens synkroniseringsprocess.

    1.  Skapa ett tillägg till enum **DirSystemRelationshipType** och lägg till den nya relationstypen.

    2. Skapa en initierare för den nya typen. Du hittar flera exempel i kärnkoden, en av dem är **DirRelationshipTypeChildInitialize**. Detta är initierarklass för partrelationstypen ”underordnad”. Du kan börja med din initierare genom att kopiera och klistra in koden och sedan uppdatera de markerade områdena.
    
    ![DirRelationshipChild initierare](media/DirRelationship.PNG)

    3.  Om du vill testa att fylla i den nya relationstypen kan du skapa en körbar klass och anropa DirDataPopulation::insertDirRelationshipTypes() i Main(). Du bör se den nya relationstypen i **DirRelationshipTypeTable**, och den nya relationstypen kommer att finnas tillgänglig på sidan **relationstyper**.

        ![Körbar klass](media/Runnable.PNG)
