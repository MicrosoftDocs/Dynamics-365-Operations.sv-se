---
title: "Uppgradering av enstaka verifikation och valutaomvärdering"
description: "Vissa organisationer anger journaler som innehåller en enda verifikation som har mer än en kund eller leverantör och de kör också processen Omräkning i utländsk valuta för Kundreskontra eller Leverantörsreskontra. Det här avsnittet beskriver de steg som dessa organisationer bör följa när de uppgraderar till Microsoft Dynamics 365 for Operations version 1611."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 13ad43cc77731727525aae1edc4d405c166acbc1
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="single-voucher-and-currency-revaluation-upgrade"></a>Uppgradering av enstaka verifikation och valutaomvärdering

[!include[banner](../includes/banner.md)]


Vissa organisationer anger journaler som innehåller en enda verifikation som har mer än en kund eller leverantör och de kör också processen Omräkning i utländsk valuta för Kundreskontra eller Leverantörsreskontra. Det här avsnittet beskriver de steg som dessa organisationer bör följa när de uppgraderar till Microsoft Dynamics 365 for Operations version 1611.

Följ dessa steg när du uppgraderar till Microsoft Dynamics 365 for Operations version 1611.

1.  Innan du uppgraderar till Dynamics 365 for Operations kör du processerna för omvärdering i utländsk valuta för Kundreskontra och Leverantörsreskontra. Ange fältet **Metod** till **Fakturadatum**. En omvärderingstransaktion skapas som återför den senaste omvärderingen i utländsk valuta. Därför värderas de öppna transaktionerna till sin ursprungliga redovisningsvaluta.
2.  Uppgradera till Dynamics 365 for Operations version 1611.
3.  Kör processerna för omräkning i utländsk valuta för Leverantörsreskontra och Kundreskontra Denna gång ändrar du fältet **Metod** till **Standard**. En ny omvärderingstransaktion skapas som baseras på de aktuella valutakurserna. Den här transaktionen registrerar orealiserad vinst/förlust och korrekt summeringskonto i redovisningen.





