---
title: Anslutna appar
description: I den här artikeln beskrivs hur du konfigurerar anslutna program i e-fakturering.
author: gionoder
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: f908caa902e4747d324480e3a5108b443d385ea7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277344"
---
# <a name="connected-applications"></a>Anslutna appar

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
6. I fältet **Typ**, välj **Dynamics 365 Finance**.
7. I fältet **Program** anger du webbadressen till den miljö du vill ansluta.
8. Ange miljöns klientorganisation i fältet **Klientorganisation**.
9. Välj **Spara**.
10. I åtgärdsfönstret väljer du **Kontrollera anslutning** om du vill testa anslutningen till miljön. Stäng sedan sidan.

## <a name="link-connected-applications-to-environments"></a>Koppla anslutna program till miljöer

1. På sidan **Miljökonfiguration** väljer du **Ny** om du vill tilldela ett anslutet program till en miljö.
2. I fältet **Anslutet program** väljer du ett anslutet program.
3. I fältet **Tjänstemiljö** väljer du en tjänstemiljö.
4. Markera **Spara** och stäng sedan sidan.
