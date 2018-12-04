---
title: "Översikt över arbetsflöde för abonnemang"
description: "Det här ämnet ger en översikt över arbetsflöde för abonnemang."
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMASubscriptionGroup, SMASubscriptionCreateDialog
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: b4872c0753b54bdddf2c7778a13819726eea4a90
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---


# <a name="subscription-workflow-overview"></a>Översikt över arbetsflöde för abonnemang 

[!include [banner](../includes/banner.md)]


Du är abonnemangsadministratör för ett ljusföretag som erbjuder abonnemang på underhåll av ljusramper. En kund kommer till ditt företag för att köpa ett årsabonnemang på underhåll av ljusramper.

## <a name="setting-up-subscriptions"></a>Ställa in abonnemang

När du vill ställa in ett abonnemang ska du först skapa en abonnemangsgrupp för det nya serviceavtalet, eller verifiera att det finns en abonnemangsgrupp. Om det finns en abonnemangsgrupp, måste den ställas in att fakturera kunden per år och tillåta periodisering av försäljningsintäkter varje månad under året. Mer information om hur du ställer in abonnemang hittar du på [Ställ in abonnemangsgrupper](set-up-subscription-groups.md).

När du har skapat abonnemangsgruppen kan du skapa abonnemanget. Mer information om hur du skapar serviceabonnemang finns i [Skapa serviceabonnemang från en abonnemangsgrupp](create-service-subscriptions-from-subscription-group.md).

## <a name="create-and-modify-subscription-transactions"></a>Skapa och ändra abonnemangstransaktioner

När du har skapat abonnemanget skapar du abonnemangsavgiftstransaktionen för den första faktureringsperioden, som är ett år. Transaktionerna är av typen **Vanligt**. Du kan därför bara skapa abonnemangstransaktioner där från- och till-datumet motsvarar befintliga perioder som har skapats tidigare i formuläret **Periodtyper**. Mer information om avgiftstransaktioner finns i [skapa transaktioner för abonnemangsavgifter](create-subscription-fee-transactions.md).

När du har ställt in abonnemanget för kunden, kommer du ihåg att de har förhandlat fram 10 % rabatt på alla listpriser för service. Därför måste du minska priset på transaktionsavgiften som du har skapat.

Senare under dagen ringer din kontaktperson upp dig och säger att de fortfarande vill ha serviceavtalet för ljusrampen, men planerar att skaffa en ny ljusramp senare under året. De behöver bara underhåll till och med oktober 2013. Du minskar antalet månader för kundens abonnemang genom att skapa en ny abonnemangsavgiftstransaktion av typen **Reduceringsdagar**. Mer information om hur du minskar dagar finns [minska antalet dagar på abonnemangsavgifter](reduce-the-days-on-subscription-fees.md).

## <a name="invoice-and-accrue-subscription-transactions"></a>Fakturering och periodisering av abonnemangstransaktioner

Du har nu ställt in abonnemangen och är redo att fakturera kunden för abonnemanget. Mer information om hur du ställer in fakturaabonnemang hittar du på [Fakturera abonnemangstransaktioner](invoice-subscription-transactions.md).

Två dagar senare ringer kunden och säger att abonnemanget ska faktureras i amerikanska dollar och inte i euro. Du skapar en kreditnota och skapar en ny abonnemangstransaktion i korrekt valuta. Mer information om hur du ställer in Kreditera abonnemangstransaktioner hittar du på [Kreditera abonnemangstransaktioner](credit-subscription-transactions.md).

I slutet av varje månad periodiserar du en månads intäkt från kundens abonnemang på vinst- och förlustkontot och PIA-kontona. Mer information om hur du periodiserar intäkt för abonnemang finns i [Periodisera abonnemangsintäkt ](accrue-subscription-revenue.md).

  



