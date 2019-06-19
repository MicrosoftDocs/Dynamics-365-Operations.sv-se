---
title: Skapa online-kanal och definiera kanalattribut
description: I den här proceduren skapar du en ny onlinekanal och lägger till den i organisationshierarkin.
author: jashanno
manager: AnnBe
ms.date: 06/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4547731d7e3bc56b1ba5e0a35ff4746c6c0e9863
ms.sourcegitcommit: 901ec3b360303bb8b4d9a9dcfecc6d75d7f844a0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2019
ms.locfileid: "1618306"
---
# <a name="create-online-channel-and-define-channel-attributes"></a>Skapa online-kanal och definiera kanalattribut

[!include[task guide banner](../includes/task-guide-banner.md)]

I den här proceduren skapar du en ny onlinekanal och lägger till den i organisationshierarkin. Du måste skapa organisationshierarkin innan du kan skapa en ny onlinekanal. I proceduren används demonstrationsföretaget USRT.


## <a name="create-a-new-online-channel"></a>Skapa en ny onlinekanal
1. Gå till Butik och handel > Kanaler > Onlinebutiker.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Ange eller välj ett värde i fältet Lagerställe.
5. Markera ett alternativ i fältet Tidszon för butik.
6. Ange eller välj ett värde i fältet Standardkund.
7. Ange eller välj ett värde i fältet Kundens adressbok.
8. Ange eller välj ett värde i fältet Betalningsvillkor.
9. Ange eller välj ett värde i fältet Betalningsmetod.
10. I fältet Meddelandeprofil för e-post, ange eller välj ett värde.
11. Expandera avsnittet Ekonomiska dimensioner.
12. Ange eller välj ett värde i fältet BusinessUnit.
    * Ange värdet på samma sätt för alla andra standarddimensioner.  
13. Klicka på Spara.

## <a name="add-the-online-channel-to-organization-hierarchy"></a>Lägg till onlinekanalen i organisationshierarkin
1. Stäng sidan.
2. Gå till Organisationsadministration > Organisationer > Organisationshierarkier.
3. Hitta och markera önskad post i listan.
4. Klicka på Visa.
5. Klicka på Redigera.
    * Du kan välja en hierarkinod som du vill infoga den nya kanalen under.  
6. Klicka på Infoga.
7. Klicka på Butikskanal.
8. Klicka på OK.
9. Klicka på Publicera om du vill öppna formuläret med listrutan för att öppna dialogrutan.
10. Ange datum och tid i fältet Giltighetsdatum.
11. Klicka på Publicera.

## <a name="configure-orders-for-near-realtime-notification"></a>Konfigurera order för nära realtidsmeddelande
1. Öppna Retail > Administrationsinställning > Parametrar > Retail-parametrar.
2. Ange Använd realtidstjänst för skapande av e-handelsorder till "Ja".
3. Kör distributionsschema 1070 för att synkronisera ändringar i databasen för kanalen. 


