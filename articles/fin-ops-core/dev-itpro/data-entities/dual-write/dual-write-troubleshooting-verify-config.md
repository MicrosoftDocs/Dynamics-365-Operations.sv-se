---
title: Kontrollera att dubbelriktad skrivning i Finance and Operations-appar och Dataverse
description: I det här avsnittet beskrivs hur du kan avgöra om dubbelriktad skrivning är konfigurerad i Finance and Operations-appar och i Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: af746d1d20ddd1552bce797288c6d62d69d7bd16
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748859"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Kontrollera att dubbelriktad skrivning i Finance and Operations-appar och Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Dataverse. Det beskriver särskilt hur du kan avgöra om dubbelriktad skrivning är konfigurerad i Finance and Operations-appar och i Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Kontrollera att dubbelriktad skrivning är konfigurerad i en Finance and Operations-app

För att avgöra om de fel som visas när du försöker spara rader för uppdatering kommer från dubbelriktad skrivning, ska du först kontrollera att dubbelriktad skrivning är konfigurerad.

+ Om du har administratörsbehörighet i Finance and Operations-appen, gå till **Arbetsytor \> Datahantering** och välj panelen **dubbelriktad skrivning**. Om information om de länkade miljöerna och listan över tabellmappningar som körs visas, konfigureras dubbelriktad skrivning.

    ![Verifiera Finance and Operations-appanslutningen när du har administratörsbehörighet](media/verify_fin_ops_1.png)

+ Om du inte har administratörsbehörighet visas ett felmeddelande *Det går inte att skriva data till entitet \<entity name\>*. I exemplet i följande bild kan du inte skapa en kundrad i Finance and Operations-appen eftersom dubbelriktad skrivning är konfigurerad men referensdata för kundgrupp och betalningsvillkor finns inte i Dataverse.

    ![Verifiera Finance and Operations-appanslutningen när du inte har administratörsbehörighet](media/verify_fin_ops_2.png)

Information om hur du åtgärdar problem när du skapar data i Finance and Operations-appar finns i [Felsöka problem med realtidssynkronisering](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Kontrollera att dubbelriktad skrivning är konfigurerad i Dataverse

När du skapar data, om du ser kolumnen **Företag** på sidor i Dataverse, är dubbelriktad skrivning konfigurerad.

![Verifierar Dataverse-anslutningen](media/verify_cds.png)

Information om hur du åtgärdar problem när du skapar data i Dataverse finns i [Felsöka problem med realtidssynkronisering](dual-write-troubleshooting-live-sync.md).

Information om hur du visar felinformation om du stöter på några fel medan du skapar data i Dataverse finns i [Aktivera och visa spårningslogg för plugin-program i Dataverse för att visa felinformation](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]