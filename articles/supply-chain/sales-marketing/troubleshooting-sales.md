---
title: Felsök försäljningsorder
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med försäljningsorder.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTable, SalesTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 6e51723915892f465ce09d09ee9ed622bab9451e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437625"
---
# <a name="troubleshoot-sales-orders"></a>Felsök försäljningsorder

I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med försäljningsorder.

## <a name="the-tax-information-isnt-updated-if-i-change-the-location-on-a-sales-order-header"></a>Skatteinformationen uppdateras inte om jag ändrar en plats i en försäljningsorderrubrik.

### <a name="issue-description"></a>Problembeskrivning

Om webbplatsen, lagerstället eller leveransadressen ändras antingen i ett försäljningsorderrubrik eller på radnivå uppdateras inte fall skatteinformationen för raderna automatiskt.

### <a name="issue-resolution"></a>Problemlösning

Detta beteende är av design. Problemet beror på att leveransadressen, webbplatsen och lagerstället inte ändras automatiskt på radnivå. Du måste uppdatera dem manuellt.

## <a name="if-there-are-two-trade-agreements-for-the-same-period-or-overlapping-periods-the-same-agreement-line-is-always-selected"></a>Om det finns två handelsavtal för samma period eller överlappande perioder väljs alltid samma avtalsrad.

### <a name="issue-description"></a>Problembeskrivning

Om två handelsavtal har definierats för samma period eller överlappande perioder verkar samma handelsavtal väljas varje gång du skapar försäljningsorderrader som innehåller dessa artiklar.

### <a name="issue-resolution"></a>Problemlösning

Om det finns fler än ett handelsavtal för ett givet datum väljs alltid handelsavtalet med det lägsta priset. Om du vill ha mer information hämtar du följande faktablad: [handelsavtal i Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>Kan jag koppla en inköpsorder till en försäljningsorder för att tillfredsställa efterfrågan?

Du kan skapa en inköpsorder från en försäljningsorder. För mer information, se [Skapa en inköpsorder från en försäljningsorder](tasks/create-purchase-order-sales-order.md).

## <a name="i-cant-cancel-or-delete-a-return-order-or-a-sales-order"></a>Jag kan inte avbryta eller ta bort en returorder eller en försäljningsorder.

Du kan endast annullera försäljningsorder och returorder som har statusen *skapad*. Mer information finns i [Avbryt returorder](../service-management/cancel-return-order.md).

## <a name="when-i-try-to-cancel-a-sales-order-i-receive-a-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations-error"></a>När jag försöker annullera en försäljningsorder får jag felet "reservationer kan inte tas bort eftersom det finns ett arbete skapat som använder reservationerna".

Om arbete associeras med en försäljningsorder kan du inte annullera försäljningsordern förrän arbetet har annullerats och återförts. Detta krav gäller även om det arbete som är kopplat till försäljningsordern stängs.

Gör så här om du vill åtgärda problemet.

1. Avbryt arbetet och sätt tillbaka lagret på önskad plats. Gå till relevant inläsning av försäljningsordern och välj antingen **minska plockad kvantitet** på lastraden eller **återför arbete** i åtgärdsfönstret.

    Arbetet har nu statusen *Annullerat* och nytt lagerrörelsearbete skapas och bearbetas automatiskt för att placera lagret på den plats som beskrivs vid tidpunkten för återföringen.

2. Ta bort lasten. Även leveransen tas bort.
3. Du bör nu kunna gå till försäljningsordern och annullera den.

## <a name="i-cant-cancel-an-intercompany-purchase-order-that-is-linked-to-a-sales-order"></a>Jag kan inte annullera en koncernintern inköpsorder som är kopplad till en försäljningsorder.

### <a name="issue-description"></a>Problembeskrivning

Om du försöker avbryta en koncernintern inköpsorder som är kopplad till en försäljningsorder, kan det hända att följande felmeddelande visas: "kvantiteten kan inte minskas eftersom återstående uppdateringsantal ändrar tecken."

### <a name="issue-resolution"></a>Problemlösning

Det här problemet har åtgärdats i Microsoft Dynamics 365 Supply Chain Management version 10.0.13. I den versionen och senare versioner kan du nu avbryta en koncernintern inköpsorder som är kopplad till en försäljningsorder.

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>Kan jag återställa en fakturerad försäljningsorder som har tagits bort?

### <a name="issue-description"></a>Problembeskrivning

En fakturerad försäljningsorder har tagits bort av misstag och du vill återställa den eller visa information om den.

### <a name="issue-resolution"></a>Problemlösning

Om den borttagna försäljningsordern redan har fakturerats går du till **kundkonto \> transaktioner \> originaldokument \> visningsinformation**. Hitta den faktura du söker och markera den om du vill visa information om den. Informationen omfattar försäljningsorder referensen. Du bör också kunna komma åt försäljningsorder information från den sidan.

## <a name="the-deadline-of-a-sales-order-header-cant-be-found-in-the-salesorderheaderv2entity-data-entity"></a>Det går inte att hitta en deadline för en försäljningsorderrubrik i dataentiteten SalesOrderHeaderV2Entity.

Fältet för tidsgräns finns inte i entiteten *SalesOrderHeaderV2Entity*.

## <a name="i-must-delete-orphaned-sales-order-records"></a>Jag måste ta bort överblivna försäljningsorderposter.

Om du vill rensa överblivna försäljningsorder poster kör du det *periodiska jobbet för borttagning av försäljningsorder* genom att gå till någon av följande platser:

- Försäljning och marknadsföring \> Periodiska uppgifter \> Rensa \> Ta bort försäljningsorder
- Butik och handel \> Butik och handels-IT \> Rensa \> Ta bort försäljningsorder

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>Finns det något sätt att beräkna provisioner på fakturor som redan har bokförts?

Supply Chain Management stöder för närvarande inte beräkningen av provisioner för bokförda fakturor.

## <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a>En buntad artikel stöds inte i en koncernintern process.

Buntad artikel är inte tillgänglig för inköpsordern eftersom du, om du granskar försäljningsorderraderna för buntad artikel ser du att kvantiteten är *0* (noll) och statusvärdet *annullerad*. Detta beteende är av design. Försäljningsordern köper endast komponenterna i buntad artikel. Den handlar inte om själva buntade artikeln.

Om du måste köpa en buntad bör du fundera över om du måste markera det som buntad artikel, eftersom denna funktion verkligen är utformad för scenarier för intäktsredovisning. Mer information om buntad artikel, se [buntade](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]