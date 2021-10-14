---
title: Inställning av status för färd
description: I detta avsnitt beskrivs hur man upprättar de statusvärden som användare kan tilldela till färder.
author: sherry-zheng
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ITMStatusTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-01-13
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 01bfc5198b62cfe56df9ec6763d5d0ff95f13ed5
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571003"
---
# <a name="voyage-status-setup"></a>Inställning av status för färd

[!include [banner](../../includes/banner.md)]

På sidan **Status för färd** kan du fastställa de statusvärden som användarna kan tilldela färder. Användarna kan tilldela statusvärden till alla nivåer i en färd, leveransbehållare, inköpsorder och artikel (inköpsrader och överföringsorderrader). De används för två syften:

- Informera användaren om statusen för färd, leveransbehållare, inköpsordern eller artikeln (inköpsrader och överföringsorderrader).
- Begränsa användningen av kostnadsområdet genom att förhindra ändringar eller radering.

För att ställa in dina färdstatusar, gå till **Hemtagningskostnad \> Inställningar \> Färdstatusar**. Där kan du lägga till, ta bort och redigera statusinformation genom att använda knapparna i åtgärdsfönstret.

Varje kostnadsområde har sin egen uppsättning och hierarki av statusar. Därför måste du i fältet **Kostnadsområde** på sidan **Kostnadsstatus** först välja det kostnadsområde som du vill visa eller skapa status för. För varje status anges sedan de fält som beskrivs i följande tabell efter behov. Observera att statusen för en sådan kan också ändras automatiskt av systemhändelser, t.ex. regler som upprättats med hjälp av spårningskontrollcentret.

| Fält | beskrivning |
|---|---|
| Sjötransportens status | Ange namn på färdstatus. |
| beskrivning | Ange en beskrivning av färdstatusen. |
| Ändra | Markera den här kryssrutan om användare får ändra dem som har den här statusen. |
| Radera | Markera den här kryssrutan om användare får ta bort dem som har den här statusen. |
| Obligatoriskt | Markera den här kryssrutan om du vill att färdstatus ska vara obligatorisk så att den inte kan hoppas över. |
| Överordnad | Använd det här fältet om du vill upprätta en hierarki bland statusvärdena. Färdstatus för en hierarki kan ändras (antingen manuellt eller automatiskt) bara nedåt i hierarkin, från överordnad status till något av dess underordnade status.

> [!NOTE]
> Du måste bara ställa in de speciella statusar som din organisation använder. Typiska statusen för dessa är *Bekräftat*, *Varor på väg*, *Mottagen*, *Redo för kostnadsredovisning* och *Kostnadsberäkna*. Andra status kan dock finnas med.
