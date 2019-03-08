---
title: Uppgradering av enstaka verifikationsjournaler och valutaomvärderingar
description: Vissa organisationer anger journaler som innehåller en enda verifikation som har mer än en kund eller leverantör och de kör också processen Omräkning i utländsk valuta för Kundreskontra eller Leverantörsreskontra. Det här avsnittet beskriver de steg som dessa organisationer bör följa när de uppgraderar till Microsoft Dynamics 365 for Operations version 1611.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 343fa226e1cf9072696082e9ebf0a1629e553ae9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "328158"
---
# <a name="upgrade-single-voucher-journals-and-currency-revaluations"></a>Uppgradera journaler med enstaka verifikationer och valutaomvärderingar

[!include [banner](../includes/banner.md)]

Vissa organisationer anger journaler som innehåller en enda verifikation som har mer än en kund eller leverantör och de kör också processen Omräkning i utländsk valuta för Kundreskontra eller Leverantörsreskontra. Det här avsnittet beskriver de steg som dessa organisationer bör följa när de uppgraderar till Microsoft Dynamics 365 for Operations version 1611.

Gör så här när du uppgraderar till Microsoft Dynamics 365 for Operations version 1611.

1.  Innan du uppgraderar till Dynamics 365 for Operations kör du processerna för omvärdering i utländsk valuta för Kundreskontra och Leverantörsreskontra. Ange fältet **Metod** till **Fakturadatum**. En omvärderingstransaktion skapas som återför den senaste omvärderingen i utländsk valuta. Därför värderas de öppna transaktionerna till sin ursprungliga redovisningsvaluta.
2.  Uppgradera till Dynamics 365 for Operations version 1611.
3.  Kör processerna för omräkning i utländsk valuta för Leverantörsreskontra och Kundreskontra Denna gång ändrar du fältet **Metod** till **Standard**. En ny omvärderingstransaktion skapas som baseras på de aktuella valutakurserna. Den här transaktionen registrerar orealiserad vinst/förlust och korrekt summeringskonto i redovisningen.




