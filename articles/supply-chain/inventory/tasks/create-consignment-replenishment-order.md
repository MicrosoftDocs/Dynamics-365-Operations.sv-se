---
title: Skapa en ny order för lagerpåfyllnad för försändelse
description: I det här avsnittet visas hur du skapar en lagerpåfyllnadsorder för försändelse, där du kan följa den förväntade leveransen från en leverantör till ditt försändelselager.
author: mkirknel
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple, ConsignmentProductReceiptJournal, ConsignmentReplenishmentOrderLineQuantity
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e993190150e2d82088390d8db4b7c5ada2b0161
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4438074"
---
# <a name="create-a-consignment-replenishment-order"></a>Skapa en ny order för lagerpåfyllnad för försändelse

[!include [banner](../../includes/banner.md)]

I det här avsnittet visas hur du skapar en lagerpåfyllnadsorder för försändelse, där du kan följa den förväntade leveransen från en leverantör till ditt försändelselager. Den visar även hur du registrerar en inleverans av produkter, så att försändelselagret är registrerat som lagerbehållning som ägs av leverantören. Denna procedur görs normalt av ett anskaffningsproffs. Du kan använda den här guiden i demonstrationsföretaget USMF. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations, version 1611.

## <a name="create-a-consignment-replenishment-order"></a>Skapa en ny order för lagerpåfyllnad för försändelse
1. I navigeringsfönstret, gå till **Moduler > Anskaffning och källa > Försändelse > Order för försändelseåteranskaffning**.
2. Välj **Ny**.
3. I fältet **Leverantörskonto** väljer du leverantör **US-104** (du måste välja en leverantör som är registrerad som en ägare på sidan **lagerägare**). 
4. Välj **OK**.
5. Välj **Markera rad**.
6. I fältet **Artikelnummer** anger du `M9211CI` (du måste välja en artikel som har ställts in för försändelselager).
7. Ange ett nummer i fältet **Kvantitet**.
8. Ange ett datum i fältet **Begärt leveransdatum**. Begärda och bekräftade datum används av MRP-motorn för varornas förväntade ankomst.  
9. Ange ett datum i fältet **Bekräftat leveransdatum.**
10. Visa avsnittet **Raddetaljer**.
11. Välj fliken **Lagerdimensioner**.
12. Uppdatera sidan om du vill visa ägaren i fältet **Ägare till lagerdimensioner**. Leverantören US-104 anges nu som ägare.  

## <a name="check-the-inventory-transaction-status"></a>Kontrollera statusen för lagertransaktion
1. Välj **Lager**.
2. Markera **transaktioner**
3. På den önskade raden, observera att fältet **Inleverans** anges som **Beställt**.  
4. Stäng sidan.

## <a name="receive-items"></a>Ta emot artiklar
1. Välj **produktinleverans**
2. Ange ett värde i fältet **Extern produktinleverans**.
3. Ange ett värde som är lägre än det som visas i fältet **Kvantitet**. 
4. Välj **OK**.

## <a name="check-the-on-hand-inventory"></a>Kontrollera behållningslagret
1. Välj **Lager**.
2. Välj **Behållning**.
3. Välj **Översikt**. Artiklarna som har inlevererats som ett försändelselager ägt av leverantören finns tillgängliga i lager. Återstående kvantitet i lagerpåfyllnadsordern för försändelse anges i fältet **Totalt beställt**.  
4. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]