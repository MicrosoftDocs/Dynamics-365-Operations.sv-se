---
title: Ange växelkurs
description: Det här ämnet innehåller information om valutakurser i Microsoft Dynamics 365 Finance.
author: abruer
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 146794557a3a6ba1801598fe6b814e209d9f5fc6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447851"
---
# <a name="specify-the-cross-rate"></a>Ange växelkurs

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver syftet med en växlingskurs och hur du anger växlingskursen när du kvittar en betalning mot en faktura. Använd en växlingskurs när alla följande villkor gäller: 
-   Du kvittar en betalning mot en faktura. 
-   Betalningsraden och fakturaraden använder olika valutor. 
-   Ingen av valutorna är redovisningsvalutan. 

Växlingskursen används inte för att beräkna valutaregistrering för betalningstransaktionen till betalningens redovisningsvaluta. I stället hämtas valutakurser från valutakurstabellerna för att beräkna värdet på betalningstransaktionens valutabelopp och betalningsredovisningens valutabelopp. 

Redovisningsvalutan är till exempel USD, fakturavalutan CAD och betalningsvalutan EUR. Med växlingskursen kan du ange en valutakurs för att översätta direkt mellan CAD och EUR utan att behöva översätta via USD. När du väljer en faktura och en primär betalning, kan du ange en växlingskurs för fakturaraden. Växlingskursen är växelkursen mellan valutorna för dessa transaktioner på kvittningsdatumet.

1.  Gå till en av följande sidor:
- **Kundreskontra > Allmänt > Kunder > Alla kunder** 
- **Leverantörsreskontra > Allmänt > Leverantörer > Alla leverantörer** 
- **Anskaffning och källa > Allmänt > Leverantörer > Alla leverantörer.**
2.  Välj kunden eller leverantören som du kvittar öppna transaktioner för. 
3.  För en kund, på listsidan **Alla kunder**, gå till **Samla in > Kvitta öppna transaktioner**. För en leverantör, på listsidan **Alla leverantörer**, gå till **Faktura > Kvitta öppna transaktioner**. 
4.  Välj transaktionen som är den primära betalningen och klicka på **Markera betalning**. Kryssrutan i kolumnen **Markera** markeras och en informationsikon visas i kolumnen **Primär betalning**. 
5.  I fältet **Växlingskurs** ange valutakursen mellan fakturavalutan och betalningsvalutan, på kvittningsdatumet. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]