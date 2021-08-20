---
title: Masstäng räkenskapsperiod
description: I det här avsnittet visas hur du spärrar eller permanent stänger ner en period eller mer än en juridisk person åt gången.
author: aprilolson
ms.date: 08/16/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerCalendar, LedgerPeriodModuleAccessControlUpdate, SysLookupPicklist, LedgerFiscalCalendarPeriodStatus
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7dac267d2d4ce0824bc47b63b8d07913a8dd7f02bcccc025880701cb4d0bdd3d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751287"
---
# <a name="mass-financial-period-close"></a>Masstäng räkenskapsperiod

[!include [banner](../../includes/banner.md)]

I det här avsnittet visas hur du spärrar eller permanent stänger ner en period eller mer än en juridisk person åt gången. Dessutom kommer uppgiften att visa hur du begränsar bokföring från användargrupper till specifika moduler.

1. i navigeringsfönstret, gå till **Moduler > Redovisning > Periodstängning > Redovisningskalendrar**. Observera att listan med juridiska personer som visas är beroende av räkenskapskalendern som har valts på sidan. Endast juridiska personer som använder vald räkenskapskalender kommer att visas.
2. Välj **Redigera**.
3. Välj den period som du vill ändra statusen för.
4. Välj den juridiska person som du vill uppdatera statusen för. Du kan snabbt välja alla juridiska personer genom att välja bocken uppe på rutnätets vänstra sida.  
5. Välj **Uppdatera modulåtkomst** för att definiera bokföringsåtkomsten för en vald modul. Modulstatusen kan också uppdateras individuellt genom att redigera posterna i rutnätet. Knappen är praktisk när du snabbt vill uppdatera flera juridiska personposter.  
6. Välj den modul för vilken du vill uppdatera statusen i modulen **Program** . Klicka på **Välj**.
7. På nivån **Åtkomst**, välj **Alla**, **Ingen** eller en specifik användargrupp. Klicka på **Välj**. Alla innebär att alla användare med redigeringsåtkomst till modulen kan bokföra om perioden är öppen. "None" innebär att användare inte kan bokföra i modulen om perioden är öppen. En specifik användargrupp anger att endast användare i gruppen får bokföra i modulen, om perioden är öppen.  
8. Välj **Uppdatera**.
9. Välj en annan period för att uppdatera statusen.
10. Välj de juridiska personer för vilka du vill uppdatera periodstatusen.
11. Välj **Uppdatera periodstatus** och ställ in statusen **Spärrad**, **Öppen** eller **Permanent stängd**. **Öppen** visar att bokföring kan göras i perioden, förutsatt att användare har åtkomst. **Spärrad** innebär att inga bokföringar till perioden kan genomföras, men den kan öppnas igen. **Permanent stängd** innebär att perioden är stängd och aldrig kan öppnas på nytt. Inga justeringar kan bokföra. Vi rekommenderar ingen att ställa in en period som **Permanent stängd** förrän alla justeringar och revisioner har avslutats.  
12. Välj **Uppdatera**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]