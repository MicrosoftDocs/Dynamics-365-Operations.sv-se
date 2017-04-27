---
title: "Uppgradering av enstaka verifikation- och valutaomvärdering till Microsoft Dynamics 365 for Operations version 1611"
description: "Vissa organisationer anger journaler som innehåller en enda verifikation som har mer än en kund eller leverantör och de kör också processen Omräkning i utländsk valuta för Kundreskontra eller Leverantörsreskontra. Det här avsnittet beskriver de steg som dessa organisationer bör följa när de uppgraderar till Microsoft Dynamics 365 for Operations version 1611."
author: twheeloc
manager: AnnBe
ms.date: 2016-12-28 16 - 04 - 17
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d42c753d0dc8b8efc2a0d2a26da32a4951d85503
ms.lasthandoff: 03/31/2017


---

# <a name="single-voucher-and-currency-revaluation-upgrade-for-microsoft-dynamics-365-for-operations-version-1611"></a>Uppgradering av enstaka verifikation- och valutaomvärdering till Microsoft Dynamics 365 for Operations version 1611

Vissa organisationer anger journaler som innehåller en enda verifikation som har mer än en kund eller leverantör och de kör också processen Omräkning i utländsk valuta för Kundreskontra eller Leverantörsreskontra. Det här avsnittet beskriver de steg som dessa organisationer bör följa när de uppgraderar till Microsoft Dynamics 365 for Operations version 1611.

Följ dessa steg när du uppgraderar till Microsoft Dynamics 365 for Operations version 1611.

1.  Innan du uppgraderar till Dynamics 365 for Operations kör du processerna för omvärdering i utländsk valuta för Kundreskontra och Leverantörsreskontra. Ange fältet **Metod** till **Fakturadatum**. En omvärderingstransaktion skapas som återför den senaste omvärderingen i utländsk valuta. Därför värderas de öppna transaktionerna till sin ursprungliga redovisningsvaluta.
2.  Uppgradera till Dynamics 365 for Operations version 1611.
3.  Kör processerna för omräkning i utländsk valuta för Leverantörsreskontra och Kundreskontra Denna gång ändrar du fältet **Metod** till **Standard**. En ny omvärderingstransaktion skapas som baseras på de aktuella valutakurserna. Den här transaktionen registrerar orealiserad vinst/förlust och korrekt summeringskonto i redovisningen.



