---
title: Ställ in behörigheter för att beställa produkter för någon annans räkning
description: I det här avsnittet visas hur du beviljar arbetare behörighet att förbereda inköpsrekvisitioner på uppdrag av andra arbetare.
author: RichardLuan
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqAuthorization, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 585f5c6cf83ad93b649e3f36e0d486a037915cd4
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017302"
---
# <a name="set-up-permissions-for-ordering-products-on-behalf-of-someone-else"></a>Ställ in behörigheter för att beställa produkter för någon annans räkning

[!include [banner](../../includes/banner.md)]

I det här avsnittet visas hur du beviljar arbetare behörighet att förbereda inköpsrekvisitioner på uppdrag av andra arbetare. Med andra ord kan en "förberedare" av inköpsrekvisitionen skapa en rekvisition för en annan ”begärare”. Denna procedur visar också hur du beviljar en anställd behörighet till orderartiklar och tjänster i olika juridiska personer eller driftenheter. Dessa inställningsuppgifter utförs normalt av en inköpschef. Du kan använda den här proceduren antingen i data för demonstrationsföretaget USMF eller på dina egna data.


## <a name="grant-permission-to-enter-purchase-requisitions-on-behalf-of-another-worker"></a>Bevilja behörighet att ange inköpsrekvisitioner på uppdrag av en annan anställd
1. I navigeringsfönstret går du till **Moduler > Anskaffning och källa > Inställningar > Policyer > Behörighet för inköpsrekvisition**. Kontrollera att fältet **Aktuell vy** är inställt på **Per förberedare**. Listan i vänstra fönstret visar personer som kan beviljas behörighet att förbereda rekvisitioner på uppdrag av andra personer.  
2. Välj den person som ska beviljas behörighet (förberedaren).
3. Markera **Lägg till**.
4. Hitta och välj den person om du vill lägga till som en beställare.
    - Beställaren är den person som förberedaren kan skapa rekvisitioner för.  
    - I fältet **Auktorisering** väljer du **Specifik** och förberedaren ska kunna skapa inköpsrekvisitioner på uppdrag av den valda arbetaren. Välj **Rapportering** om förberedaren även ska kunna skapa inköpsrekvisitioner på uppdrag av alla arbetare som rapporterar till den arbetaren.  
5. Ange ett datum i fältet **Giltighet.**
6. I fältet **Utgång** anger du ett datum.

## <a name="view-preparers-who-have-permission-to-create-purchase-requisitions-for-a-selected-worker"></a>Visa förberedare som har behörighet att skapa inköpsrekvisitioner för en vald arbetare
1. Välj **Per beställare** i fältet **Aktuell vy**. Denna vy visar en lista med förberedare som har behörighet att skapa inköpsrekvisitioner för en vald anställd.  
2. Använd snabbfiltret för att hitta den arbetare som du just lade till som beställaren.
3. Välj beställare. Förberedarelistan visar personer som har behörighet att beställa artiklar på uppdrag av beställaren som är vald i vänstra fönstret.  Du kan lägga till ytterligare förberedare här. Denna vy låter dig också bevilja beställarebehörighet att skapa rekvisitioner i juridiska personer och driftenheter som inte är den personens primära juridiska person eller driftenhet.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]