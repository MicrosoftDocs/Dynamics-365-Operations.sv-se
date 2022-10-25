---
title: Sensor Data Intelligence-parametrar
description: Den här artikeln innehåller information om konfigurationsinställningar som är tillgängliga på parametersidan för Sensor Data Intelligence.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreServiceParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 5240537e3a6526ceb35253b9e68f46b1753c6a37
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689384"
---
# <a name="sensor-data-intelligence-parameters"></a>Sensor Data Intelligence-parametrar

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

På **parametersidan för Sensor Data Intelligence** finns några inställningar som du kan använda för att konfigurera funktionen. De här inställningarna inkluderar anslutningsparametrar för Azure och en parameter för livstiden av notifieringsmeddelanden som skickas till användare som svar på mätning av sensor.

## <a name="read-and-change-connection-details-for-your-azure-iot-solution"></a>Läs och ändra anslutningsdetaljer för din Azure IoT-lösning

Vanligtvis skapar du din Azure IoT-lösning och ansluter den till Microsoft Dynamics 365 Supply Chain Management från **Distribuera och anslut Azure-resurser** som vägleder dig genom båda procedurerna. (Mer information finns i [Distribuera en IoT-lösning på Azure](sdi-deploy-iot-solution-on-azure.md).) Du kan även visa och redigera anslutningsinformation när som helst i Supply Chain Management genom att följa stegen nedan.

1. Gå till **Systemadministration \> Inställningar \> Sensor Data Intelligence \> Sensor Data Intelligence-parametrar**.
1. På fliken **Tidsserie** i fältet **Anslutningssträng för Redis måttlagring** ange värdet **Primär anslutningssträng (StackExchange.Redis)** för den Azure IoT-lösning som du vill ansluta till. Mer information om hur du hittar det här värdet finns i [Distribuera en IoT-lösning på Azure](sdi-deploy-iot-solution-on-azure.md).
1. På fliken **Integreringar** i fältet **Azure AD appklient-ID** ange värdet **Klient-ID** för den Azure IoT-lösning du vill ansluta till. Mer information om hur du hittar det här värdet finns i [Distribuera en IoT-lösning på Azure](sdi-deploy-iot-solution-on-azure.md).

## <a name="set-the-lifetime-of-alert-messages"></a>Ställa in livstiden för notifieringsmeddelanden

Varje gång som Sensor Data Intelligence hittar en situation som kräver användarvarning skickar den ett meddelande till relevant användare. Om du vill förhindra att meddelandena staplas i systemet bör du ange att de ska upphöra att gälla efter ett par dagar.

1. Gå till **Systemadministration \> Inställningar \> Sensor Data Intelligence \> Sensor Data Intelligence-parametrar**.
1. På fliken **Meddelanden** i fältet **Meddelandedagar till publicering** anger du antalet dagar för att spara ett meddelande. Efter den angivna tidsperioden kommer meddelandet att raderas.
