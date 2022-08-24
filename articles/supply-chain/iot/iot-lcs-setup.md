---
title: Installera tillägget för IoT-information i LCS
description: lagerbehållning beskrivs hur du installerar IoT-information-tillägget i Microsoft Dynamics Lifecycle Services (LCS).
author: johanhoffmann
ms.date: 08/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e18b05be1f2ba78c71515e4e76f180355d044b98
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2022
ms.locfileid: "9227861"
---
# <a name="install-the-iot-intelligence-add-in-in-lcs"></a>Installera tillägget för IoT-information i LCS

[!include [banner](../../includes/banner.md)]
[!INCLUDE [iot-sdi-announcement](../../includes/iot-sdi-announcement.md)]

lagerbehållning beskrivs hur du installerar IoT-information-tillägget i Microsoft Dynamics Lifecycle Services (LCS). Lägg märke till att tillägg inte kan installeras i en demo/utvärderingsmiljö. Innan du kan installera tillägget måste du [skapa Azure-resurserna](iot-azure-setup.md).

Du kan konfigurera och konfigurera IoT-information utan att skriva någon kod. Här är de grundläggande stegen.

1. [Ställ in Azure-resurser](iot-azure-setup.md) – Skapa en IoT hub, en Redis-cache och ett nyckelvalv som du får åtkomst till från Supply Chain Management.
2. [Meddelandeschemaformat för IoT Hub](iot-schema-format.md) – Konfigurera dina enheter så att de skickar meddelanden till IoT Hub och definiera JavaScript Object Notation (JSON) meddelandeformat.
3. Aktivera funktionen IoT-information i Funktionshantering.
4. Installera tillägget IoT-information i Microsoft Dynamics Lifecycle Services (LCS) – Installera tillägget i LCS och konfigurera Azure-hemligheter (som beskrivs i denna artikel).
5. [Ställ in mått](iot-metrics-setup.md) – Ställ in mått i Supply Chain Management.
6. [Scenarioinställningar](iot-scenario-setup.md) – Ange scenarier i Supply Chain Management.

## <a name="set-up-the-lcs-environment"></a>Konfigurera LCS-miljö

1. Öppna LCS och gå till din Microsoft Dynamics 365 Supply Chain Management-miljö.
2. Bläddra till avsnittet **Miljötillägg**.
3. Välj **Installera ett nytt tillägg** om du vill visa listan över tillägg som har aktiverats för miljön.
4. I dialogrutan **Välj ett tillägg att installera** väljer du **IoT-information**.
5. I dialogrutan **Tillägg för inställningar** anger du information om IoT-hubben och Redis-cachen. Du hittar erforderliga värden i det nyckelvalv som du skapade i [Skapa Azure-resurser](iot-azure-setup.md).

    + **ID för klientorganisation** – Gå till nyckelvalvet i Azure-portalen och välj sedan **Översikt** i det vänstra navigeringsfönstret. Kopiera sedan värdet för **Katalog-ID**. Klistra in värdet i dialogrutan **Tillägg för konfiguration**.
    + **IoT Event Hub-kompatibel URI för slutpunktsnyckelvalv** – Gå till nyckelvalvet, välj **Översikt** i det vänstra navigeringsfönstret och kopiera värdet för **DNS-namn**. Klistra in värdet i dialogrutan **Tillägg för konfiguration**.
    + **IoT Event Hub-kompatibelt namn för slutpunktshemlighet** – Gå till nyckelvalvet, välj **Hemligheter** i det vänstra navigeringsfönstret och kopiera namnet på den hemlighet där anslutningssträngen i händelsehubbent för IoT-hubben lagras. Klistra in värdet i dialogrutan **Tillägg för konfiguration**.
    + **Nyckelvärdes-URI för Redis-cache** – Gå till nyckelvalvet, välj **Översikt** i det vänstra navigeringsfönstret och kopiera värdet för **DNS-namn**. Klistra in värdet i dialogrutan **Tillägg för konfiguration**.
    + **Hemligt slutpunktsnamn för Redis-cache** – Gå till nyckelvalvet, välj **Hemligheter** i det vänstra navigeringsfönstret och kopiera namnet på den hemlighet där anslutningssträngen i händelsehubben för Redis-cache lagras. Klistra in värdet i dialogrutan **Tillägg för konfiguration**.

6. Markera kryss rutan om du vill acceptera villkoren.
7. Välj **Installera**.
8. En meddelanderuta visas med statusen "Tillägget har aktiverats för installation". Välj **OK**.

LCS-konfigurationen har nu slutförts. Nästa steg är att [konfigurera scenarierna](iot-scenario-setup.md).

## <a name="uninstall-the-add-in"></a><a id="uninstall-addin"></a>Avinstallera tillägget

1. [Avaktivera scenarierna](iot-scenario-setup.md#disable-a-scenario) i Supply Chain Management.
2. I LCS går du till informationen för Supply Chain Management.
3. Bläddra till avsnittet **Miljötillägg**.
4. Välj **Avinstallera** för tilläggsprogrammet för IoT-information.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]