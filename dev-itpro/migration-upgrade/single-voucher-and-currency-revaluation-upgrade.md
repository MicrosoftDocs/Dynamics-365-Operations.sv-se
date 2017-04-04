---
title: "Enstaka verifikations- och valutaomvärdering uppgradera till Microsoft Dynamics 365 för operationer version 1611"
description: "Vissa organisationer ange journaler som innehåller en enda verifikation som har mer än en kund eller leverantör och de också köra Kundreskontra eller konton Leverantörsreskontra utländsk valuta omvärdering processen. Det här avsnittet beskrivs de steg som dessa organisationer bör följa när de uppgraderar till Microsoft Dynamics 365 för operationer version 1611."
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

# <a name="single-voucher-and-currency-revaluation-upgrade-for-microsoft-dynamics-365-for-operations-version-1611"></a>Enstaka verifikations- och valutaomvärdering uppgradera till Microsoft Dynamics 365 för operationer version 1611

Vissa organisationer ange journaler som innehåller en enda verifikation som har mer än en kund eller leverantör och de också köra Kundreskontra eller konton Leverantörsreskontra utländsk valuta omvärdering processen. Det här avsnittet beskrivs de steg som dessa organisationer bör följa när de uppgraderar till Microsoft Dynamics 365 för operationer version 1611.

Följ dessa steg när du uppgraderar till Microsoft Dynamics 365 för operationer version 1611.

1.  Innan du uppgraderar till Dynamics 365 för operationer kör processer omvärdering i utländsk valuta för kundreskontra och Leverantörsreskontra. Ange den **metod** till **fakturadatum**. En omvärderingstransaktion skapas Ångrar senaste omvärdering i utländsk valuta. Därför kan värderas de öppna transaktionerna till sina ursprungliga redovisningsvalutan.
2.  Uppgradera till Dynamics 365 för operationer version 1611.
3.  Kör Kundreskontra och konton Leverantörsreskontra utländsk valuta omvärdering processer igen. Ändra den **metod** till **Standard**. En ny omvärderingstransaktion skapas som baseras på de aktuella valutakurserna. Den här transaktionen registreras Orealiserad vinst/förlust och den korrekta Summeringskonto i redovisningen.



