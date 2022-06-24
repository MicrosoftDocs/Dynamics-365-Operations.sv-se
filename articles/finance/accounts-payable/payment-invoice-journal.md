---
title: Använda ett betalningsschema i fakturajournalen
description: I den här artikeln beskrivs hur du lägger till en betalning i leverantörsfakturajournalen.
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
ms.openlocfilehash: f3ae08ea46be66dd8bf26f7f91bd73f6c5b9192f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863142"
---
# <a name="apply-a-payment-schedule-to-the-invoice-journal"></a>Använda ett betalningsschema i fakturajournalen

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
