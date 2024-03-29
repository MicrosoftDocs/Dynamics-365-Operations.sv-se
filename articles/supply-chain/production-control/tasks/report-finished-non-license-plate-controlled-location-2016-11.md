---
title: Rapportera som färdig till en ej registreringsskyltstyrd plats (ansökan, maj 2016)
description: Den här uppgiftsguiden visar ett exempel på rapporteringen som slutförd till en plats som inte är ID-nummertyrd.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrResourceGroup, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdParmCostEstimation, ProdParmStartUp, ProdParmReportFinished, WHSWorkTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f891b2e3b20993a08138dfac1aed4f4bab33c6b1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576722"
---
# <a name="report-as-finished-to-a-non-license-plate-controlled-location--application-may-2016"></a>Rapportera som färdig till en ej registreringsskyltstyrd plats (ansökan, maj 2016)

[!include [banner](../../includes/banner.md)]

Den här uppgiftsguiden visar ett exempel på rapporteringen som slutförd till en plats som inte är ID-nummertyrd. En tillämplig arbetspolicy är förutsättningen är den här uppgiften. En tidigare uppgiftsguide visade inställningarna för arbetspolicyn. Den här uppgiftsguiden kräver Dynamics AX program 7.0.1 eller senare.




## <a name="set-up-an-output-location"></a>Ställ in en utleveransplats
1. Gå till Organisationsadministration > Resurser > Resursgrupper.
2. Välj resursgrupp "5102" i listan.
3. Klicka på Redigera.
4. Ange "51" i fältet Utleveranslagerställe.
5. Ange "001" i fältet Utleveransplats.
    * Plats 001 är en ej ID-nummertyrd plats. Du kan ställa in en plats för ej ID-nummertyrd utleveransplats bara om en lämplig arbetspolicy finns för platsen.  

## <a name="create-a-production-order-and-report-it-as-finished"></a>Skapa en produktionsorder och rapportera den som färdig.
1. Stäng sidan.
2. Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.
3. Klicka på Ny produktionsorder.
4. Ange ett artikelnummer i fältet "L0101".
5. Klicka på Skapa.
6. Klicka på Produktionsorder i åtgärdsfönstret.
7. Klicka på Uppskattning.
8. Klicka på OK.
9. Klicka på Start.
10. Klicka på fliken Allmänt.
11. Välj "Aldrig" i fältet Automatisk strukturlisteförbrukning.
12. Klicka på OK.
13. Klicka på Rapportera som färdigt.
14. Klicka på fliken Allmänt.
15. Välj Ja i fältet Godkänn fel.
16. Klicka på OK.
17. Klicka på Lagerställe i åtgärdsfönstret.
18. Klicka på Information om arbete.
    * När tillverkningsordern rapporterades som färdig, genererades inget arbete för plats. Detta inträffar, eftersom en arbetspolicy definieras som hindrar arbete från att genereras när produkten L0101 rapporterats som färdig till plats 001.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]