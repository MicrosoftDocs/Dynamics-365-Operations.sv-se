---
title: Skapa en standardskund
description: I det här avsnittet beskrivs hur du skapar en standardkund som kan användas för att skapa en kanal i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ecdf4e5618d3397527bf83977857fbe3f8dbb265
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799189"
---
# <a name="create-a-default-customer"></a>Skapa en standardskund

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en standardkund som kan användas för att skapa en kanal i Microsoft Dynamics 365 Commerce.

När du skapar en kanal måste du ange en standardkund. En standardkund kan enkelt skapas efter att du först har skapat kundgruppen och kundadressboken.

## <a name="create-a-customer-group"></a>Skapa en kundgrupp

Om det inte finns några kundgrupper ännu kan du skapa en. Exempel på det kan vara grupper att representera olika kundgrupper, till exempel grossist, butik, Internet, anställda osv.

Gör så här om du vill skapa en kundgrupp.

1. I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kunder \> Kundgrupper**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I rutan **kundgrupp** anger du ett kundgrupp-ID.
1. I rutan **beskrivning** ange en lämplig beskrivning.
1. I rutan **Betalningsvillkor** ange ett lämpligt värde.
1. I rutan **Tid mellan fakturadatum och betalningsdatum** anger du ett lämpligt datum.
1. I rutan **Standardmomsgrupp** anger du en momsgrupp om det är tillämpligt.
1. Markera kryssrutan **Priser inkluderar moms** om tillämpligt.
1. I rutan **Standardorsak till avskrivning** anger du ett lämpligt värde, om det är tillämpligt.

I följande bild visas flera konfigurerade kundgrupper.

![Kundgrupper](media/customer-groups.png)

## <a name="create-a-customer-address-book"></a>Skapa en kundadressbok

En kund måste vara kopplad till en adressbok. Om en sådan inte ännu har skapats måste du skapa en.

Följ dessa steg för att skapa en kundadressbok.

1. I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Adressböcker**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ange sedan ett namn i rutan **Namn**.
1. Ange en beskrivning i rutan **beskrivning**.
1. Klicka på **Spara** i åtgärdsfönstret.

I bilden nedan visas ett exempel på adressbok.

![Adressbok](media/address-book.png)

## <a name="create-a-default-customer&quot;></a>Skapa en standardskund

Gör så här om du vill skapa en standardkund.

1. I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kunder \> Alla kunder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I listrutan **Typ** väljer du &quot;Person&quot;.
1. I listrutan **kundkonto** väljer du eller anger ett kontonummer (t.ex. &quot;100001").
1. I listrutan **Förnamn** väljer du eller anger ett namn (till exempel "standard").
1. I listrutan **Mellannamn** väljer du eller anger ett namn (till exempel "butik").
1. I listrutan **Efternamn** väljer du eller anger ett namn (till exempel "kund").
1. I listrutan **Valuta** väljer du eller anger en valuta (till exempel "USD").
1. I listrutan **valuta** väljer du den kundgrupp som du skapade tidigare.
1. I listrutan **Adressböcker** väljer du en befintlig kundadressbok.
1. Välj **spara** om du vill spara och återgå till fönstret med kundinformation för den nya kunden.

> [!NOTE]
> Det är inte nödvändigt att lägga till en adress för en standardkund.

I bilden nedan visas ett exempel på skapande av kund.

![Skapa en standardkund](media/default-customer-creation.png)

Följande bild visar en standardkundkonfiguration.

![Exempel på kundkonfiguration](media/default-customer-configuration1.png)

De flesta standardvärdena i informationsskärmen kund kan vara kvar, men två värden ska ändras.

1. På informationsskärmen för kund expanderar du **standardvärden för försäljningsorde**.
1. I listrutan **Webbplats** välj eller ange en förkonfigurerad webbplats.
1. I listrutan **Lagerställe** välj eller ange ett förkonfigurerat lagerställe.

I bilden nedan visas ett exempel på skapande av kundkonfiguration.

![Exempel på kundkonfiguration](media/default-customer-configuration2.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över kanaler](channels-overview.md)

[Förutsättningar för att ställa in kanaler](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
