---
title: Verifiera konfiguration av dubbelriktad skrivning i appar för ekonomi och drift samt Dataverse
description: I den här artikeln beskrivs hur du kan avgöra huruvida dubbelriktad skrivning har konfigurerats i apper för ekonomi och drift samt i Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: d5191f5dd9c3a286abac622aede07d04fb72a8f7
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111405"
---
# <a name="verify-dual-write-configuration-in-finance-and-operations-apps-and-dataverse"></a>Verifiera konfiguration av dubbelriktad skrivning i appar för ekonomi och drift samt Dataverse

[!include [banner](../../includes/banner.md)]





Den här artikeln innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan appar för ekonomi och drift och Dataverse. Den beskriver särskilt hur du kan avgöra huruvida dubbelriktad skrivning har konfigurerats i appar för ekonomi och drift samt i Dataverse.

## <a name="verify-that-dual-write-is-configured-in-a-finance-and-operations-app"></a>Verifiera att dubbelriktad skrivning har konfigurerats i en app för ekonomi och drift

För att avgöra om de fel som visas när du försöker spara rader för uppdatering kommer från dubbelriktad skrivning, ska du först kontrollera att dubbelriktad skrivning är konfigurerad.

+ Om du har administratörsbehörighet i appen för ekonomi och drift går du till **Arbetsytor \> Datahantering** och väljer panelen **Dubbelriktad skrivning**. Om information om de länkade miljöerna och listan över tabellmappningar som körs visas, konfigureras dubbelriktad skrivning.

    ![Verifiera anslutningen till appen för ekonomi och drift när du har administratörsbehörigheter.](media/verify_fin_ops_1.png)

+ Om du inte har administratörsbehörighet visas ett felmeddelande *Det går inte att skriva data till entitet \<entity name\>*. I exemplet i följande bild kan du inte skapa en kundrad i appen för ekonomi och drift, detta eftersom dubbelriktad skrivning har konfigurerats men referensdata för kundgrupp och betalningsvillkor inte finns i Dataverse.

    ![Verifiera anslutningen till appen för ekonomi och drift när du inte har administratörsbehörigheter.](media/verify_fin_ops_2.png)

Information om hur du åtgärdar problem när du skapar data i appar för ekonomi och drift finns i [Felsöka problem med realtidssynkronisering](dual-write-troubleshooting-live-sync.md).

## <a name="verify-that-dual-write-is-configured-in-dataverse"></a>Kontrollera att dubbelriktad skrivning är konfigurerad i Dataverse

När du skapar data, om du ser kolumnen **Företag** på sidor i Dataverse, är dubbelriktad skrivning konfigurerad.

![Verifiera Dataverse-anslutningen.](media/verify_cds.png)

Information om hur du åtgärdar problem när du skapar data i Dataverse finns i [Felsöka problem med realtidssynkronisering](dual-write-troubleshooting-live-sync.md).

Information om hur du visar felinformation om du stöter på några fel medan du skapar data i Dataverse finns i [Aktivera och visa spårningslogg för plugin-program i Dataverse för att visa felinformation](dual-write-troubleshooting.md#enable-view-trace).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
