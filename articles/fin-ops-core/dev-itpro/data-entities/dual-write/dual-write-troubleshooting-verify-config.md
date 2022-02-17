---
title: Verifiera konfiguration av dubbelriktad skrivning i Finance and Operations-appar och Dataverse
description: I det här avsnittet beskrivs hur du kan avgöra om dubbelriktad skrivning är konfigurerad i Ekonomi och Drift-appar och i Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 3fa16a450032464e445ae166f0699fe0dc388071
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062810"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Verifiera konfiguration av dubbelriktad skrivning i Finance and Operations-appar och Dataverse

[!include [banner](../../includes/banner.md)]





Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Ekonomi och Drift-appar och Dataverse. Det beskriver särskilt hur du kan avgöra om dubbelriktad skrivning är konfigurerad i Ekonomi och Drift-appar och i Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Verifiera att dubbelriktad skrivning är konfigurerad i en Ekonomi och Drift-app

För att avgöra om de fel som visas när du försöker spara rader för uppdatering kommer från dubbelriktad skrivning, ska du först kontrollera att dubbelriktad skrivning är konfigurerad.

+ Om du har administratörsbehörighet i Ekonomi och Drift-appen, gå till **Arbetsytor \> Datahantering** och välj panelen **Dubbelriktad skrivning**. Om information om de länkade miljöerna och listan över tabellmappningar som körs visas, konfigureras dubbelriktad skrivning.

    ![Verifiera Ekonomi och Drift-appanslutningen när du inte har administratörsbehörigheter.](media/verify_fin_ops_1.png)

+ Om du inte har administratörsbehörighet visas ett felmeddelande *Det går inte att skriva data till entitet \<entity name\>*. I exemplet i följande bild kan du inte skapa en kundrad i Ekonomi och Drift-appen eftersom dubbelriktad skrivning är konfigurerad men referensdata för kundgrupp och betalningsvillkor finns inte i Dataverse.

    ![Verifiera Ekonomi och Drift-appanslutningen när du inte har administratörsbehörigheter.](media/verify_fin_ops_2.png)

Information om hur du åtgärdar problem när du skapar data i Ekonomi och Drift-appar finns i [Felsöka problem med realtidssynkronisering](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Kontrollera att dubbelriktad skrivning är konfigurerad i Dataverse

När du skapar data, om du ser kolumnen **Företag** på sidor i Dataverse, är dubbelriktad skrivning konfigurerad.

![Verifiera Dataverse-anslutningen.](media/verify_cds.png)

Information om hur du åtgärdar problem när du skapar data i Dataverse finns i [Felsöka problem med realtidssynkronisering](dual-write-troubleshooting-live-sync.md).

Information om hur du visar felinformation om du stöter på några fel medan du skapar data i Dataverse finns i [Aktivera och visa spårningslogg för plugin-program i Dataverse för att visa felinformation](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]