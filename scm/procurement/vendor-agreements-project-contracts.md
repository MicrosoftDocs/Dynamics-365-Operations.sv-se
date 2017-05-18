---
title: "Leverantörsavtal betala vid betalning"
description: "Det här avsnittet innehåller villkor för betalning-vid-betalad för leverantörsavtal. Med villkor för betalning-vid-betalad kan du helt eller delvis hålla inne betalning till en leverantör, tills kunden betalar för projektet till dig. Det här avsnittet innehåller även ett verkligt exempel för att visa hur du kan använda villkor för betalning-vid-betalad för ett projekt."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ProjProjectsListPage
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 23131
ms.assetid: 20bf1d7f-8813-4c69-9cd7-576884a7e169
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: ff4e31434da0fa200cc1c563fb53c8650a643443
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="pay-when-paid-vendor-agreements"></a>Leverantörsavtal betala vid betalning

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller villkor för betalning-vid-betalad för leverantörsavtal. Med villkor för betalning-vid-betalad kan du helt eller delvis hålla inne betalning till en leverantör, tills kunden betalar för projektet till dig. Det här avsnittet innehåller även ett verkligt exempel för att visa hur du kan använda villkor för betalning-vid-betalad för ett projekt.

När du godkänner en leverantör till att arbeta på ett projekt som underleverantör, kan du hålla inne betalningen till leverantören eller underleverantören tills du har betalats av kunden för projektet. Om du vill hålla inne en betalning till en leverantör, ställ in betala vid betalning (PWP) när du ställer in inköpsordern för leverantören. När du skapar en inköpsorder för leverantören och tilldelar ett projekt-ID till inköpsordern, associeras villkor för betala vid betalning i projektet med inköpsordern och leverantören. På sidan **Leverantörsfakturor med betala vid betalning** kan du visa en lista med obetalda leverantörsfakturor för en inköpsorder och de kopplade kundfakturorna. Använd detta formulär för att bestämma om och hur mycket du betalar en leverantör. Till exempel när en kund betalar ett belopp på en projektfaktura kan du frisläppa en del av eller alla relaterade leverantörsfakturor för betalning. Du kan ställa in betala vid betalning-villkor som anger om en leverantör betalas när du har fått en viss procent av den relaterade betalningen från en kund. När du får delvis betalning från en kund, kan du manuellt frisläppa några av de relaterade leverantörsfakturorna för betalning. Följande exempel visar hur betala vid betalning-villkor används för att hålla inne betalning till en leverantör eller underleverantör tills kunden betalar dig. Din organisation ingår ett avtal med en kund att ge 100 datorer på vilka du installerar program som kunden begär. Priset som du och kunden avtalar är 150,00 för varje dator. Du anlitar tjänster från en tredje part som tillhandahåller datorerna till dig. Kunden vill godkänna kvaliteten på datorerna innan din organisation betalas. Din organisations policy är att undanhålla betalningen till tredje partsleverantören tills du har betalats av kunden i ett projekt. Därför kan du ställa in projektet med en betala vid betalning-procentsats på 100 procent, så att du undanhåller alla betalningar till leverantören tills du får full betalning för kundfakturan. Leverantören debiterar 100,00 för varje dator. När leverantören skickar datorerna till dig inkluderar leveransen en faktura på 10 000, 00 för 100 datorer. Eftersom du har ställt in projektet med betala vid betalning-villkor betalar du inte leverantören. När du har fått datorerna från leverantören installerar du programmet på datorerna. När du skickar datorerna till kunden skickar du också kunden en faktura på 15 000,00. Kunden kontrollerar datorerna och godkänner kvaliteten på produkten. Kunden betalar sedan din organisation hela beloppet för projektfakturan. När du har tagit emot hela betalningen från kunden betalar du leverantören hela beloppet för leverantörsfakturan, 10 000,00.




