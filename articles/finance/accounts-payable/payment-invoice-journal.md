---
title: Använd en betalningsplan i fakturajournal
description: I det här avsnittet beskrivs hur du lägger till en betalning i leverantörsfakturajournalen.
author: sunfzam
ms.date: 01/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: f6481c3fc033acf4bb563bf1716789216646b60b
ms.sourcegitcommit: 9cbff8a2cdeaf606488fb0044b3de4ab4409c9dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/26/2022
ms.locfileid: "8358349"
---
# <a name="apply-a-payment-schedule-to-the-invoice-journal"></a>Använd en betalningsplan i fakturajournal

[!include [banner](../includes/preview-banner.md)]

I Microsoft Dynamics 365 Finance version 10.0.25 stöds nu en betalningsplan i **leverantörsfakturajournalen**.

För att använda den här funktionen måste du aktivera **Använd betalningsplan i fakturajournal** i funktionshanteringen.

När funktionen har aktiverats läggs ett nytt fält för **Betalningsplan** har lagts till på sidan **Fakturajournal**. När du skapar en fakturajournalrad, om betalningsvillkoren bibehålls på providern och betalningsvillkoren är valda i betalningsplanen, visas fältet **Betalningsplan** uppdateras på sidan **Fakturajournal**.

Du kan ändra den betalningsplan som används, enligt ditt affärsbehov. Under bokföringen av leverantörsfakturajournalen skapas öppna leverantörstransaktioner enligt betalningsplanen.

 - För att granska flera öppna leverantörstransaktioner som genererades från betalningsschemat, gå till **Leverantörsreskontra \> Fakturor \> Öppna leverantörsfakturor** och ange fakturanumret eller leverantörskontot.
 - Om du vill granska eller konfigurera betalningsplanen går du till **Leverantörsreskontra \> Betalningsinställningar \> Betalningsplan**.
 - Om du vill konfigurera betalningsvillkoren och tilldela en betalningsplan går du till **Leverantörsreskontra \> Betalningsinställningar \> Betalningsvillkor**.
 - För att behålla betalningsvillkoren för en leverantör, gå till **Leverantörsreskontra \> Alla leverantörer**, välj leverantörskontot och sedan på fliken **Betalning**, ange fältet **Betalningsvillkor**.

Betalningsschemafunktionen är även tillgänglig i processen **Leverantörsfakturaregister**. Om en betalningsplan väljs i fakturaregisterjournalen genereras **inte** flera leverantörsbetalningsrader när fakturaregistret bokförs. Leverantörsbetalningsraderna genereras när fakturan godkänns.

## <a name="limitation"></a>Begränsning

Om betalningsplanen finns i fakturahuvudet för en pågående leverantörsfaktura finns det en avancerad sida där användarna kan redigera betalningsraderna. (Exempelvis kan användarna redigera förfallodatum och värde för respektive betalningsrad.) Betalningsrader som genereras från fakturajournalen får värdet från betalningsplanen.

Den här funktionen är tillgänglig för **Leverantörsfakturajournal** och **Pågående fakturor** i en framtida version.
