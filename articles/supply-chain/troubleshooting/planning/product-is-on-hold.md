---
title: Produkten är spärrad för transaktioner
description: När du har bekräftat planeringsorder visas ett felmeddelande med information om att artikeln är spärrad för transaktioner
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 6654e6437a088218db116b955631be4c7e62de5f
ms.sourcegitcommit: f9b145ef4a81cec81f420871b4130b05db4f4500
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301289"
---
# <a name="product-is-on-hold-for-transactions"></a>Produkten är spärrad för transaktioner

Felkod: SYS13295

## <a name="symptoms"></a>Symtom

När du har bekräftat planerade order visas följande felmeddelande:

> Artikel %1 har spärrats för transaktioner i %2.

## <a name="cause"></a>Orsak

När de beskriver spärrade artiklar använder systemet villkoren *spärrade*, *stoppade* och *spärrade* utan att göra det. Det här felet innebär att artikeln har ställts in som **Stoppad** i sina standardorderinställningar.

Om en artikel är spärrad och du lägger till den på en inköpsorder- eller försäljningsorderrad visas ett varningsmeddelande. När artikeln är spärrad kan lagertransaktioner som gäller inköps- eller försäljningsorderraden inte ändras, till exempel när du bokför en följesedel eller en faktura. Du kan spärra en inköpt artikel och samtidigt sälja artikeln. I det här fallet markeras kryssrutan **Stoppad** på en inköpsorder, men det är inte spärrat i lager eller på en försäljningsorder.

Här är några av villkoren som kan göra så att ett artikelnummer spärras från att säljas:

- Artikeln fortfarande är under utveckling eller tillverkning. Därför vill du inte att den ska säljas eller reserveras.
- Du har fått många defekta artiklar, och defekterna måste korrigeras innan artikeln kan säljas.

I fall av denna typ kan du spärra artikeln tills problemet har lösts.

När en artikel är spärrad och du skapar en returorderrad får du ett meddelande. Du kan inte spärra en serie eller ett parti av artikeln. Om delar av artikeln ska spärras, kan du göra detta genom att flytta lagret eller genom att spärra hela lagret av denna artikel under den aktuella perioden.

## <a name="resolution"></a>Lösning

- Öppna sidan **Standardorderinställningar** för artikeln och avmarkera kryssrutan **Stoppat**.
