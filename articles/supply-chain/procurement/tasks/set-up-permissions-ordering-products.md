--- 
title: "Ställ in behörigheter att beställa produkter för någon annans räkning"
description: "I den här proceduren visas hur du beviljar arbetare behörighet att förbereda inköpsrekvisitioner på uppdrag av andra arbetare."
author: mkirknel
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9e003f953c05facd5516e2bfa6d1c83ba6381c15
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a>Ställ in behörigheter att beställa produkter för någon annans räkning

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du beviljar arbetare behörighet att förbereda inköpsrekvisitioner på uppdrag av andra arbetare. Med andra ord kan en "förberedare" av inköpsrekvisitionen skapa en rekvisition för en annan ”begärare”. Denna procedur visar också hur du beviljar en anställd behörighet till orderartiklar och tjänster i olika juridiska personer eller driftenheter. Dessa inställningsuppgifter utförs normalt av en inköpschef. Du kan använda den här proceduren antingen i data för demonstrationsföretaget USMF eller på dina egna data.


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a>Bevilja behörighet att ange inköpsrekvisitioner på uppdrag av en annan anställd
1. Gå till Anskaffning och källa > Inställningar > Policyer > Behörighet för inköpsrekvisition.
    * Kontrollera att fältet Aktuell vy är inställd på Per förberedare.  Listan i vänstra fönstret visar personer som kan beviljas behörighet att förbereda rekvisitioner på uppdrag av andra personer.  
2. Välj den person som ska beviljas behörighet (förberedaren).
3. Klicka på Lägg till.
4. Hitta och välj den person om du vill lägga till som en beställare.
    * Beställaren är den person som förberedaren kan skapa rekvisitioner för.  
    * I fältet Auktorisering väljer du Specifik och förberedaren ska kunna skapa inköpsrekvisitioner på uppdrag av den valda arbetaren. Välj Rapporteringen om förberedaren även ska kunna skapa inköpsrekvisitioner på uppdrag av alla arbetare som rapporterar till den arbetaren.  
5. Ange ett datum i fältet Giltighet.
6. I fältet Utgång anger du datum.

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a>Visa förberedare som har behörighet att skapa inköpsrekvisitioner för en vald arbetare
1. Välj ”Per beställare” i fältet Aktuell vy.
    * Denna vy visar en lista med förberedare som har behörighet att skapa inköpsrekvisitioner för en vald anställd.  
2. Använd snabbfiltret för att hitta den arbetare som du just lade till som beställaren.
3. Välj beställare.
    * Förberedarelistan visar personer som har behörighet att beställa artiklar på uppdrag av beställaren som är vald i vänstra fönstret.   Du kan lägga till ytterligare förberedare här.   Denna vy låter dig också bevilja beställarebehörighet att skapa rekvisitioner i juridiska personer och driftenheter som inte är den personens primära juridiska person eller driftenhet.  


