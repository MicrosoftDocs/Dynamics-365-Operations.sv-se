---
title: Nyheter och ändringar i Dynamics 365 Talent - Core HR (16 oktober 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/22/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-22
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d5f2aea5fcc81d0b4c1d8a392a3e56c888440a94
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462563"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-october-16-2018"></a>Nyheter och ändringar i Dynamics 365 Talent - Core HR (16 oktober 2018)

**Skapa 8.1.1067**

Det här ämnet beskriver nya eller ändrade funktioner i Core HR.

## <a name="allow-managers-to-update-time-off-requests"></a>Tillåt chefer att uppdatera ansökningar om ledig tid

Medarbetares ansökningar om ledig tid kan behöva uppdateras efter att de har godkänts i arbetsflödet. I många fall bör chefen göra uppdateringarna för den anställdes räkning. Funktionen ger möjlighet för chefer att uppdatera ansökningar om ledig tid och avbryta ansökningar om ledig tid på uppdrag av deras anställda. Funktionen styrs av parametern **Arbeta på uppdrag av** som kan ställas in på sidan **Personalparametrar**. 
 
## <a name="allow-hr-to-update-time-off-requests"></a>Tillåter HR att uppdatera ansökningar om ledig tid

Liknande funktionen ovan, kan medarbetares ansökningar om ledig tid behöva uppdateras av HR när de har godkänts tidigare i arbetsflödet. Den här funktionen ger möjligheten för HR-användare att uppdatera ansökningar om ledig tid. Funktionen har aktiverats i arbetsytan **Personer** och på sidan **Arbetare** med hjälp av ett nytt alternativ som heter **Visa ledig tid**. På dessa sidor kan HR-användare visa förfrågningar och uppdatera ledighetstransaktioner liknande hur chefer kan utföra dessa åtgärder.

Säkerhetsprogrambehörigheten som styr åtkomsten till funktionen är:
- Säkerhet: Underhåll processer för arbetarspecifik tjänstledighet och frånvaro.
- Privilegium: Underhåll tjänstledighets- och frånvaroansökningar för alla arbetare.

## <a name="other-changes"></a>Andra ändringar
Följande uppdateringar har gjorts i den här versionen:
- Ändringar av arbetares anställningsåtgärder så att de inte längre ”fastnat” i status **Arbetsflödet är slutfört**.
- Nu kan medarbetarposter skapas utan anställningens startdatum.
- Dynamics 365 Talent-registreringsdatum för en kurs som visas i Självbetjäning för medarbetare används nu på tidszonförskjutningen till datum.
- Excel-filer kan importeras flera gånger utan fel med hjälp av **medarbetare**.

## <a name="known-issue"></a>Kända problem

- **Problem**: när du lägger till en ny bilaga till en arbetare blir knapparna **Ny** och **Redigera** nedtonade. 
- **Lösning:** innan du öppnar bilagesidan, kontrollera att faktaboxar på sidan **Arbetare** är stängda. Om faktarutorna är stängda när sidan **arbetare** hämtas kommer knapparna för bifogade filer att aktiveras. (Det här problemet kommer att åtgärdas i nästa plattformsuppdatering.)
