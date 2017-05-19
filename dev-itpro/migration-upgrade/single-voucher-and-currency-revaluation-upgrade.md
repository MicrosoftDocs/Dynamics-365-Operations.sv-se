---
title: "Uppgradering av enstaka verifikation och valutaomvärdering"
description: "Vissa organisationer anger journaler som innehåller en enda verifikation som har mer än en kund eller leverantör och de kör också processen Omräkning i utländsk valuta för Kundreskontra eller Leverantörsreskontra. Det här avsnittet beskriver de steg som dessa organisationer bör följa när de uppgraderar till Microsoft Dynamics 365 for Operations version 1611."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: ae8a6cc1b96f49c9714799fc1c3c1b9a98add413
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="single-voucher-and-currency-revaluation-upgrade"></a>Uppgradering av enstaka verifikation och valutaomvärdering

[!include[banner](../includes/banner.md)]


Vissa organisationer anger journaler som innehåller en enda verifikation som har mer än en kund eller leverantör och de kör också processen Omräkning i utländsk valuta för Kundreskontra eller Leverantörsreskontra. Det här avsnittet beskriver de steg som dessa organisationer bör följa när de uppgraderar till Microsoft Dynamics 365 for Operations version 1611.

Följ dessa steg när du uppgraderar till Microsoft Dynamics 365 for Operations version 1611.

1.  Innan du uppgraderar till Dynamics 365 for Operations kör du processerna för omvärdering i utländsk valuta för Kundreskontra och Leverantörsreskontra. Ange fältet **Metod** till **Fakturadatum**. En omvärderingstransaktion skapas som återför den senaste omvärderingen i utländsk valuta. Därför värderas de öppna transaktionerna till sin ursprungliga redovisningsvaluta.
2.  Uppgradera till Dynamics 365 for Operations version 1611.
3.  Kör processerna för omräkning i utländsk valuta för Leverantörsreskontra och Kundreskontra Denna gång ändrar du fältet **Metod** till **Standard**. En ny omvärderingstransaktion skapas som baseras på de aktuella valutakurserna. Den här transaktionen registrerar orealiserad vinst/förlust och korrekt summeringskonto i redovisningen.





