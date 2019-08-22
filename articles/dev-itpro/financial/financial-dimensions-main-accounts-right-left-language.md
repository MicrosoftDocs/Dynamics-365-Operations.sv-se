---
title: Ekonomiska dimensioner och huvudkonton i språk som skrivs från höger till vänster
description: Det här ämnet beskriver några av implementeringsbesluten som du bör beakta när du använder ett språk som skrivs från höger till vänster och du måste ställa in ekonomiska dimensioner och huvudkontona.
author: aprilolson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 36e0af4f1b4fa0013490a2acc2bfcac0de05f5dd
ms.sourcegitcommit: 27a98a7a0f1d2623f5236a88066f483def30889c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1833348"
---
# <a name="financial-dimensions-and-main-accounts-in-right-to-left-languages"></a>Ekonomiska dimensioner och huvudkonton i språk som skrivs från höger till vänster

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver några av implementeringsbesluten som du bör beakta när du använder ett språk som skrivs från höger till vänster och du måste ställa in ekonomiska dimensioner och huvudkontona.

Ekonomiska dimensioner och huvudkonton är viktiga komponenter av planeringsfasen för en implementering. Efter att de ekonomiska dimensionerna och huvudkontona har skapats i systemet, används de på sidorna **Konfigurera kontostrukturer**, **Avancerade regelstrukturer** och **Konfiguration av ekonomisk dimension för integrering av applikationer**. Ordningen som har angetts på dessa sidor används i systemet för dataregistrering och förbrukning. På vissa ställen i systemet visas ekonomiska dimensioner och huvudkonton i separata fält. På andra ställen som t.ex. journaler visas emellertid ekonomiska dimensioner och huvudkonton som en enda sträng.

### <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a>Regelverk för att ställa in ekonomiska dimensioner och rubrikkonton i ett system från höger till vänster

-   När du väljer en av de dubbla avgränsarna väljer du ett av alternativen för dubbla avgränsare: dubbla bindestreck (--), dubbla sträck (||) eller dubbla punkter period (..), eller dubbla understreck (\_\_).
-   När du skapar värden för ekonomisk dimension och huvudkonto använder du siffror och språktecken som skrivs från höger till vänster.
-   Undvik att använda den valda kontoplanavgränsaren i värden frö ekonomisk dimension och huvudkonto.

Genom att följa regelverk, kan du garantera en konsekvent representation av den användardefinierade ordern i hela systemet.



