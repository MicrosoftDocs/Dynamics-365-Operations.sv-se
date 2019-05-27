---
title: Skapa en ny order för försändelseåteranskaffning
description: I den här proceduren visas hur du skapar en lagerpåfyllnadsorder för försändelse, där du kan följa den förväntade leveransen från en leverantör till ditt försändelselager.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9d3e33008d04ea8bb7d145c7b63cec23a4a45dd2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549914"
---
# <a name="create-a-consignment-replenishment-order"></a>Skapa en ny order för försändelseåteranskaffning

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar en lagerpåfyllnadsorder för försändelse, där du kan följa den förväntade leveransen från en leverantör till ditt försändelselager. Den visar även hur du registrerar en inleverans av produkter, så att försändelselagret är registrerat som lagerbehållning som ägs av leverantören. Denna procedur görs normalt av ett anskaffningsproffs. Du kan använda den här guiden i demonstrationsföretaget USMF. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations, version 1611.




## <a name="create-a-consignment-replenishment-order"></a>Skapa en ny order för lagerpåfyllnad för försändelse
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

