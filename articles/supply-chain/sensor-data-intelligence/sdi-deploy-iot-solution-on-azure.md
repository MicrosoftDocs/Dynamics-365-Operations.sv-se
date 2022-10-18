---
title: Distribuera IoT-exempellösning på Azure
description: Sensor Data Intelligence använder data från sensors som är kopplade till Microsoft Azure. I den här artikeln beskrivs hur du distribuerar en IoT-lösning (Sakernas internet) för ditt Azure-abonnemang.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreAzureResourceDeploymentWizard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 5026f234f1b2f38e7041098421d0261fd468db96
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/12/2022
ms.locfileid: "9643736"
---
# <a name="deploy-an-iot-solution-on-azure"></a>Distribuera IoT-exempellösning på Azure

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Sensor Data Intelligence använder data från sensors som är kopplade till Microsoft Azure. Om du vill att Azure ska kunna hämta data från ditt konto och dela dem med Dynamics 365 Supply Chain Management, måste du distribuera en IoT-lösning i ditt Azure-abonnemang. Följande arkitekturdiagram ger en översikt över lösningen och dess komponenter.

![Sensor Data Intelligence arkitekturdiagram.](media/sdi-architecture.png "Sensor Data Intelligence arkitekturdiagram")

## <a name="video-instructions"></a>Videoanvisningar

Följande video visar hur du [aktiverar Sensor Data Intelligence-funktionen](sdi-enable-feature.md) och distribuerar de nödvändiga Azure-resurserna. Det andra avsnittet i den här artikeln innehåller samma instruktioner i ett textbaserat format.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE58g3I]

## <a name="procedure"></a>Procedur

Följ dessa steg för att distribuera de nödvändiga resurserna på Azure.

1. Logga in i Supply Chain Management som administratör.
1. Gå till **Systemadministration \> Inställningar \> Sensor Data Intelligence \> Distribuera och anslut Azure-resurser** för att öppna distributionsguiden.
1. På sidan **Välkommen** läs informationen och välj **Nästa**.
1. På sidan **Distribuera exemplet på IoT-lösningen till Azure** läser du informationen och väljer **Instruktioner** och **Distribuera**.
1. En ny flik öppnas och du kommer till Azure-portaln så att du kan distribuera Azure-resurserna. Om du blir tillfrågad loggar du in med dina inloggningsuppgifter för ditt Azure-abonnemang.
1. På sidan **Anpassad distribution**, i fältet **Abonnemang** välj abonnemang.
1. Under fältet **Resursgrupp**, välj **Skapa ny** för att skapa en resursgrupp för Azure-komponenterna som du ska distribuera.
1. I rullgardinsmenyn som visas, i **Namn**, ange ett namn för den nya resursgruppen (till exempel, *IoT-demo*). Välj sedan **OK**.
1. Ange följande fält.

    - **Resursgrupp** – Välj den resursgrupp som du just skapade.
    - **Region** – Välj en region, helst i den region där din Supply Chain Management-miljö är distribuerad. Tänk på att Azure-regioner har olika priser. Du kan visa uppskattade kostnader för din region med hjälp av [Sensor Data Intelligence-priskalkylator](https://azure.com/e/c36c4947ebff4215b2e62590c2a24c68).
    - **Supply Chain Management miljö-URL** – Ange URL:en för din Supply Chain Management-miljö.
    - **Återanvänd befintliga Azure IoT Hub** – Lämna den här kryssrutan avmarkerad.

1. Välj **Nästa: Granska + skapa**.
1. På sidan **Anpassad distribution**, verifiera att valideringen har godkänts och välj sedan **Skapa**.
1. Sidan **Distribution pågår** spårar utvecklingen av din distribution. Distributionsprocessen kan ta upp till 30 minuter. När sidan **Distribution pågår** visar det att distributionen har slutförts, markera länken för resursgruppnamnet för att öppna en sida som visar listan över resurser som har distribuerats i gruppen.
1. Sök efter posten i resurslistan där fältet **Typ** är inställt på *Hanterad identitet*. I kolumnen **Namn** välj namnet för att öppna informationssidan för resursen.
1. Kopiera värdet i fältet **Klient-ID** (genom att t.ex. välja knappen **Kopiera till Urklipp**).
1. Gå tillbaka till webbläsaren där Supply Chain Management körs, *men stäng inte fliken för Azure-portalen*. Guidsidan **Distribuera IoT-exempellösningen till Azure** ska fortfarande vara öppen. 
1. Välj **Nästa**.
1. På sidan **Ansluta Azure-resurser** i fältet **Azure AD programklient-ID**, klistra in värdet **Klient-ID** du kopierade.
1. Gå tillbaka till webbläsarfliken där Azure-portalen är öppen, *men stäng inte fliken för Supply Chain Management*. Informationssidan för resursen bör fortfarande vara öppen.
1. Välj webbläsarens **bakåt**-knapp när du vill återgå till listan över resurser i den nya resursgruppen.
1. Sök efter posten i resurslistan där fältet **Typ** är inställt på *Azure Cache for Redis*. I kolumnen **Namn** välj namnet för att öppna informationssidan för resursen.
1. I det vänstra navigeringsfönstret välj er du **Åtkomstnycklar**.
1. På sidan **Åtkomstnycklar**, kopiera värdet som visas för **Primär anslutningssträng (StackExchange.Redis)** (till exempel genom att välja knappen **Kopiera till urklipp**).
1. Gå tillbaka till webbläsaren där Supply Chain Management körs. Sidan **Ansluta Azure-resurser** ska fortfarande vara öppen.
1. I fältet **Anslutningssträng för Redis måttlagring**, klistra in värdet **Primär anslutningssträng (StackExchange.Redis)** som du kopierat.
1. Välj **Slutför**.

Azure-resurser för Sensor Data Intelligence har nu distribuerats på ditt Azure-abonnemang.

> [!NOTE]
> Du kan när som helst visa eller redigera anslutningsinformation som sparas i Supply Chain Management genom att öppna parametersidan för **Sensor Data Intelligence**.  Mer information finns i [Sensor Data Intelligence-parametrar](sdi-parameters.md).
