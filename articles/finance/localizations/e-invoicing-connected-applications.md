---
title: Anslutna program
description: I det här avsnittet beskrivs hur du konfigurerar anslutna program i e-fakturering.
author: dkalyuzh
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 59b67589139c0ce332716acf998825c6a024bded
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371742"
---
# <a name="connected-applications"></a>Anslutna program

[!include [banner](../includes/banner.md)]

Anslutna program är de instanser av Microsoft Dynamics 365 Finance och Dynamics 365 Supply Chain Management som du kanske vill nå via Regulatory Configuration Service (RCS). Med hjälp av de anslutna programmen kan du konfigurera en del av din globaliseringsfunktion i Ekonomi eller Supply Chain Management för att få hela det e-faktureringsscenariot att fungera.

När du distribuerar din globaliseringsfunktion kan den inställningsinformation som gäller för ditt Ekonomi- eller Supply Chain Management-program publiceras direkt från RCS till lämpligt anslutet program.

Tillgängligheten på Ekonomi- eller Supply Chain Management-parametrar i RCS är användbart när du har flera programmiljöer, till exempel användargodkännandetestning (UAT) och produktionsmiljöer, och du vill hålla inställningarna konsekventa genom att distribuera samma parametrar till olika miljöer.

## <a name="create-a-connected-application"></a>Skapa ett anslutet program.

1. Logga in på RCS-kontot.
2. I arbetsytan **globaliseringsfunktion** i avsnittet **Miljöer**, välj panelen **e-fakturor**.
3. På sidan **Miljökonfiguration** väljer du **Anslutna program** i åtgärdsfönstret.
4. Skapa ett anslutet program genom att välja **Ny**.
5. I fältet **Namn** anger du namnet på det program du vill ansluta.
6. I fältet **Typ** väljer du **Dynamics 365 Finance**.
7. I fältet **Program** anger du webbadressen till den miljö du vill ansluta.
8. Ange miljöns klientorganisation i fältet **Klientorganisation**.
9. Välj **Spara**.
10. I åtgärdsfönstret väljer du **Kontrollera anslutning** om du vill testa anslutningen till miljön. Stäng sedan sidan.

## <a name="link-connected-applications-to-environments"></a>Koppla anslutna program till miljöer

1. På sidan **Miljökonfiguration** väljer du **Ny** om du vill tilldela ett anslutet program till en miljö.
2. I fältet **Anslutet program** väljer du ett anslutet program.
3. I fältet **Tjänstemiljö** väljer du en tjänstemiljö.
4. Markera **Spara** och stäng sedan sidan.
