---
title: Nyheter och ändringar i Dynamics 365 for Talent Core HR (16 oktober 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent Core HR.
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
ms.openlocfilehash: 51cfe8a92d1ac611e946934fe8ebbc99053788f1
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2019
ms.locfileid: "858363"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-19-2018"></a>Nyheter och ändringar i Dynamics 365 for Talent Core HR (19 oktober 2018)

[!include[banner](includes/banner.md)]

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
