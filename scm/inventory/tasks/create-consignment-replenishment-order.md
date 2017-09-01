--- 
title: "Skapa en ny order för försändelseåteranskaffning"
description: "I den här proceduren visas hur du skapar en lagerpåfyllnadsorder för försändelse, där du kan följa den förväntade leveransen från en leverantör till ditt försändelselager."
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 5e268f640be11b0905457ff6b7697c90411f53e5
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="create-a-consignment-replenishment-order"></a>Skapa en ny order för försändelseåteranskaffning

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar en lagerpåfyllnadsorder för försändelse, där du kan följa den förväntade leveransen från en leverantör till ditt försändelselager. Den visar även hur du registrerar en inleverans av produkter, så att försändelselagret är registrerat som lagerbehållning som ägs av leverantören. Denna procedur görs normalt av ett anskaffningsproffs. Du kan använda den här guiden i demonstrationsföretaget USMF. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations, version 1611.




## <a name="create-a-consignment-replenishment-order"></a>Skapa en ny order för försändelseåteranskaffning
1. Gå till Anskaffning och källa > Försändelse > Order för försändelseåteranskaffning.
2. Klicka på Ny.
3. Ange leverantör US-104 i Vendor account.
    * Du måste välja en leverantör som har registrerats som en ägare i sida för lagerägare.  
4. Klicka på OK.
5. Klicka på Lägg till rad.
6. I fältet Item number anger du M9211CI.
    * Du måste välja en artikel som har ställts in för försändelselager.  
7. Ange ett tal i fältet Kvantitet.
8. Ange ett datum i fältet Requested delivery date.
    * Begärda och bekräftade datum används av MRP-motorn för varornas förväntade ankomst.  
9. I fältet Bekräftat leveransdatum, ange ett datum.
10. Expandera avsnittet Radinformation.
11. Klicka på fliken Lagerdimensioner.
12. Uppdatera sidan om du vill visa ägaren i fältet Inventory dimensions owner.
    * Leverantören US-104 anges nu som ägare.  

## <a name="check-the-inventory-transaction-status"></a>Kontrollera statusen för lagertransaktion
1. Klicka på Lager.
2. Klicka på Transaktioner.
3. Markera vald rad i listan.
    * Observera att fältet Receipt anges som Ordered.  
4. Stäng sidan.

## <a name="receive-items"></a>Ta emot artiklar
1. Klicka på Produktinleverans.
2. Ange ett värde i fältet External product receipt.
3. Ange ett värde som är lägre än det som visas i fältet Quantity. 
4. Klicka på OK.

## <a name="check-the-on-hand-inventory"></a>Kontrollera behållningslagret
1. Klicka på Lager.
2. Klicka på On-hand.
3. Klicka på Overview.
    * Artiklarna som har inlevererats som ett försändelselager ägt av leverantören finns tillgängliga i lager. Återstående kvantitet i lagerpåfyllnadsordern för försändelse anges i fältet Ordered in total.  
4. Stäng sidan.
5. Klicka på Stäng.

