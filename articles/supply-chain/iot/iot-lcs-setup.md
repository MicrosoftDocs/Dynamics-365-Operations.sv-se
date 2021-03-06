---
title: Installera tillägget för IoT-information i LCS
description: I det här avsnittet beskrivs hur du installerar IoT-information-tillägget i Microsoft Dynamics Lifecycle Services (LCS).
author: robinarh
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2d1cc9a7535be05a3e466c27e53047d694cf0160
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826453"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>Installera tillägget för IoT-information i LCS

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du installerar IoT-information-tillägget i Microsoft Dynamics Lifecycle Services (LCS). Lägg märke till att tillägg inte kan installeras i en demo/utvärderingsmiljö. Innan du kan installera tillägget måste du [skapa Azure-resurserna](iot-azure-setup.md).

## <a name="set-up-the-lcs-environment"></a>Konfigurera LCS-miljö

1. Öppna LCS och gå till din Microsoft Dynamics 365 Supply Chain Management-miljö.
2. Bläddra till avsnittet **Miljötillägg**.
3. Välj **Installera ett nytt tillägg** om du vill visa listan över tillägg som har aktiverats för miljön.
4. I dialogrutan **Välj ett tillägg att installera** väljer du **IoT-information**.
5. I dialogrutan **Tillägg för inställningar** anger du information om IoT-navet och Redis-cachen. Du hittar erforderliga värden i det nyckelvalv som du skapade i [Skapa Azure-resurser](iot-azure-setup.md).

    + **ID för klientorganisation** – Gå till nyckelvalvet i Azure-portalen och välj sedan **Översikt** i det vänstra navigeringsfönstret. Kopiera sedan värdet för **Katalog-ID**. Klistra in värdet i dialogrutan **Tillägg för konfiguration**.
    + **IoT Event Hub-kompatibel URI för slutpunktsnyckelvalv** – Gå till nyckelvalvet, välj **Översikt** i det vänstra navigeringsfönstret och kopiera värdet för **DNS-namn**. Klistra in värdet i dialogrutan **Tillägg för konfiguration**.
    + **IoT Event Hub-kompatibelt namn för slutpunktshemlighet** – Gå till nyckelvalvet, välj **Hemligheter** i det vänstra navigeringsfönstret och kopiera namnet på den hemlighet där anslutningssträngen i händelsenavet för IoT-navet lagras. Klistra in värdet i dialogrutan **Tillägg för konfiguration**.
    + **Nyckelvärdes-URI för Redis-cache** – Gå till nyckelvalvet, välj **Översikt** i det vänstra navigeringsfönstret och kopiera värdet för **DNS-namn**. Klistra in värdet i dialogrutan **Tillägg för konfiguration**.
    + **Hemligt slutpunktsnamn för Redis-cache** – Gå till nyckelvalvet, välj **Hemligheter** i det vänstra navigeringsfönstret och kopiera namnet på den hemlighet där anslutningssträngen i händelsenavet för Redis-cache lagras. Klistra in värdet i dialogrutan **Tillägg för konfiguration**.

6. Markera kryss rutan om du vill acceptera villkoren.
7. Välj **Installera**.
8. En meddelanderuta visas med statusen "Tillägget har aktiverats för installation". Välj **OK**.

LCS-konfigurationen har nu slutförts. Nästa steg är att [ställa in scenarierna](iot-scenario-setup.md).

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a>Avinstallera tillägget

1. [Avaktivera scenarierna](iot-scenario-setup.md#disable-a-scenario) i Supply Chain Management.
2. I LCS går du till informationen för Supply Chain Management.
3. Bläddra till avsnittet **Miljötillägg**.
4. Välj **Avinstallera** för tilläggsprogrammet för IoT-information.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]