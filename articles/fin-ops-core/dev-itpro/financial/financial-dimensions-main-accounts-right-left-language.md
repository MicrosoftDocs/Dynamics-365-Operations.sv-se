---
title: Ekonomiska dimensioner och huvudkonton i språk som skrivs från höger till vänster
description: Det här ämnet beskriver besluten som du bör göra när du använder ett språk som skrivs från höger till vänster och du måste ställa in ekonomiska dimensioner och huvudkontona.
author: RyanCCarlson2
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 222564
ms.assetid: 875dcebb-1bbb-4841-a8c6-9e134da07e96
ms.search.region: global
ms.author: rcarlson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b1e2c0ef5cd405232332847078c70af42f056e17
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8866772"
---
# <a name="financial-dimensions-and-main-accounts-in-right-to-left-languages"></a>Ekonomiska dimensioner och huvudkonton i språk som skrivs från höger till vänster

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver några av implementeringsbesluten som du bör beakta när du använder ett språk som skrivs från höger till vänster och du måste ställa in ekonomiska dimensioner och huvudkontona.

Ekonomiska dimensioner och huvudkonton är viktiga komponenter av planeringsfasen för en implementering. Efter att de ekonomiska dimensionerna och huvudkontona har skapats i systemet, används de på sidorna **Konfigurera kontostrukturer**, **Avancerade regelstrukturer** och **Konfiguration av ekonomisk dimension för integrering av applikationer**. Ordningen som har angetts på dessa sidor används i systemet för dataregistrering och förbrukning. På vissa ställen i systemet visas ekonomiska dimensioner och huvudkonton i separata fält. På andra ställen som t.ex. journaler visas ekonomiska dimensioner och huvudkonton som en enda sträng.

## <a name="best-practices-for-setting-up-financial-dimensions-and-main-accounts-in-a-right-to-left-system"></a>Regelverk för att ställa in ekonomiska dimensioner och rubrikkonton i ett system från höger till vänster

- När du väljer en av de dubbla avgränsarna väljer du ett av alternativen för dubbla avgränsare: dubbla bindestreck (`--`), dubbelstreck (`||`) eller dubbla punkter (`..`), eller dubbla understreck (`\\`).
- När du skapar värden för ekonomisk dimension och huvudkonto använder du siffror och språktecken som skrivs från höger till vänster.
- Undvik att använda den valda kontoplanavgränsaren i värden frö ekonomisk dimension och huvudkonto.

Genom att följa regelverk, kan du garantera en konsekvent representation av den användardefinierade ordern i hela systemet.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
