---
title: Nyheter och ändringar i Dynamics 365 for Talent Core HR (15 november 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0e9de5e36e67941ab09c773a63b0e7045105a07e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "306197"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-15-2018"></a>Nyheter och ändringar i Dynamics 365 for Talent Core HR (15 november 2018)

[!include [banner](includes/banner.md)]

**Skapa 8.1.2045**

Det här ämnet beskriver nya eller ändrade funktioner i Core HR.

## <a name="other-changesfixes"></a>Andra ändringar/korrigeringar

### <a name="unable-to-change-employees-current-position-to-a-future-open-position"></a>Det går inte att ändra medarbetarens nuvarande befattning till en framtida ledig befattning

En ändring har gjorts för att aktivera befattningsöverföringar när befattningen bara finns i framtiden. 

### <a name="position-does-not-display-when-creating-a-new-employee"></a>Befattningen visas inte när du skapar en ny medarbetare

En ändring har gjorts för att visa alla lediga befattningar som är tillgängliga för tilldelning när du anställer en ny medarbetare i Talent. Detta inkluderar historiska befattningar eller om befattningarna har framtida datum. Befattningar visas nu på rätt sätt, baserat på anställningens startdatum. 

### <a name="termination-date-is-displaying-based-on-user-settings"></a>Uppsägningsdatum visas baserat på användarinställningar

En ändring har gjorts i listan över tidigare anställda för att ta hänsyn till de tidszonsförskjutningar för den prioriterade medarbetarens tidszon när de visade uppsägningsdatumet.

### <a name="work-items-assigned-to-me-links-not-displaying-the-correct-information"></a>Arbetsuppgifter som tilldelats till mig visar inte korrekt information

Med denna ändring, om du navigerar till detaljerad information om enskilda arbetsuppgifter i listan kommer korrekt information för den valda artikeln att visas. Det här problemet uppstod endast med avancerade säkerhetsalternativ.


## <a name="known-issue"></a>Kända problem

- **Problem**: när du lägger till en ny bilaga till en arbetare blir knapparna **Ny** och **Redigera** nedtonade. 
- **Lösning:** innan du öppnar bilagesidan, kontrollera att faktaboxar på sidan **Arbetare** är stängda. Om faktarutorna är stängda när sidan **arbetare** hämtas kommer knapparna för bifogade filer att aktiveras. (Det här problemet kommer att åtgärdas i nästa plattformsuppdatering.)
