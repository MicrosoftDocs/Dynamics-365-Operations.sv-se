---
title: Kontrollera att dubbelriktad skrivning är konfigurerad i Finance and Operations-appar och Common Data Service
description: I det här avsnittet beskrivs hur du kan avgöra om dubbelriktad skrivning är konfigurerad i Finance and Operations-appar och i Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 2ddac76871a3ac574a1edcb5446be6c64e5e4682
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997240"
---
# <a name="verify-that-dual-write-is-configured-in-finance-and-operations-apps-and-common-data-service"></a>Kontrollera att dubbelriktad skrivning är konfigurerad i Finance and Operations-appar och Common Data Service

[!include [banner](../../includes/banner.md)]



Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service. Det beskriver särskilt hur du kan avgöra om dubbelriktad skrivning är konfigurerad i Finance and Operations-appar och i Common Data Service.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Kontrollera att dubbelriktad skrivning är konfigurerad i en Finance and Operations-app

För att avgöra om de fel som visas när du försöker spara poster för uppdatering kommer från dubbelriktad skrivning, kontrollera först att dubbelriktad skrivning är konfigurerad.

+ Om du har administratörsbehörighet i Finance and Operations-appen, gå till **Arbetsytor \> Datahantering** och välj panelen **dubbelriktad skrivning**. Om information om de länkade miljöerna och listan över entitetsmappningar som körs visas, konfigureras dubbelriktad skrivning.

    ![Verifiera Finance and Operations-appanslutningen när du har administratörsbehörighet](media/verify_fin_ops_1.png)

+ Om du inte har administratörsbehörighet visas ett felmeddelande *Det går inte att skriva data till entitet \<entity name\>*. I exemplet i följande bild kan du inte skapa en kundpost i Finance and Operations-appen eftersom dubbelriktad skrivning är konfigurerad men referensdata för kundgrupp och betalningsvillkor finns inte i Common Data Service.

    ![Verifiera Finance and Operations-appanslutningen när du inte har administratörsbehörighet](media/verify_fin_ops_2.png)

Information om hur du åtgärdar problem när du skapar data i Finance and Operations-appar finns i [Felsöka problem med realtidssynkronisering](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-common-data-service"></a>Kontrollera att dubbelriktad skrivning är konfigurerad i Common Data Service

När du skapar data, om du ser fältet **Företag** på sidor i Common Data Service, är dubbelriktad skrivning konfigurerad.

![Verifierar Common Data Service-anslutningen](media/verify_cds.png)

Information om hur du åtgärdar problem när du skapar data i Common Data Service finns i [Felsöka problem med realtidssynkronisering](dual-write-troubleshooting-live-sync.md).

Information om hur du visar felinformation om du stöter på några fel medan du skapar data i Common Data Service finns i [Aktivera och visa spårningslogg för plugin-program i Common Data Service för att visa felinformation](dual-write-troubleshooting.md#enable-and-view-the-plug-in-trace-log-in-common-data-service-to-view-error-details).
