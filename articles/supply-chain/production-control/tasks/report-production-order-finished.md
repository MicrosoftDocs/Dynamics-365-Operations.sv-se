---
title: Rapportera en produktionsorder som färdig
description: I den här proceduren visas hur du rapporterar en produktionsorder som färdig.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd, ProdSetupReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa27691942b27886e85c52b7b3a736a62db7b7bd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580610"
---
# <a name="report-a-production-order-as-finished"></a>Rapportera en produktionsorder som färdig

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du rapporterar en produktionsorder som färdig. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Detta är den sjätte proceduren av sju som förklarar produktionsorderns livscykel.


## <a name="report-a-production-order-as-finished"></a>Rapportera en produktionsorder som färdig
1. Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.
    * Välj en produktionsorder som har statusen Startat.  
2. Klicka på Produktionsorder i åtgärdsfönstret.
3. Klicka på Rapportera som färdig.
    * På den här sidan kan du bekräfta kvantiteten av den färdiga produkten som ska rapporteras som färdig.  
4. Klicka på fliken Allmänt.
5. Ställ in Godkänd kvantitet på 18.
6. Ställ in Antal fel på 2.
7. Välj Material i fältet Felorsak.
8. Markera eller avmarkera kryssrutan Slutjobb.
9. Markera eller avmarkera kryssrutan Godta fel.
10. Klicka på OK.

## <a name="verify-the-report-as-finished-journal"></a>Verifiera journalen Rapporterat som färdigt
1. Klicka på Visa i åtgärdsfönstret.
2. Klicka på Rapporterat som färdigt.
3. Markera vald rad i listan.
4. Klicka på länken på den valda raden i listan.
    * Journalen för rapportering som slutfört bokförs. Om du vill göra justeringar i journalen, kan du manuellt skapa en ny journal där du kan göra ändringar.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]