---
title: Vanliga frågor och svar om försäljningsorder
description: Den här sidan behandlar vanliga frågor som kommer upp när du arbetar med försäljningsorder i Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 3cee75b1d740e7cb414c674157dde0146e8faa50
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571627"
---
# <a name="sales-order-faqs"></a>Vanliga frågor och svar om försäljningsorder

Den här sidan behandlar vanliga frågor som kommer upp när du arbetar med försäljningsorder i Dynamics 365 Supply Chain Management.

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a>Kan jag koppla en inköpsorder till en försäljningsorder för att tillfredsställa efterfrågan?

Du kan skapa en inköpsorder från en försäljningsorder. För mer information, se [Skapa en inköpsorder från en försäljningsorder](/dynamics365/supply-chain/sales-marketing/tasks/create-purchase-order-sales-order).

## <a name="can-i-cancel-or-delete-a-sales-order-or-return-order"></a>Kan jag avbryta eller ta bort en försäljningsorder eller returorder?

Du kan endast annullera försäljningsorder och returorder som har statusen *skapad*. Mer information finns i [Avbryt returorder](/dynamics365/supply-chain/service-management/cancel-return-order).

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a>Kan jag återställa en fakturerad försäljningsorder som har tagits bort?

Om en fakturerad försäljningsorder har tagits bort av misstag kan du återställa den eller visa information om den.

Gå till **Kundkonto \> Transaktioner \> Ursprungsdokument \> Visa detaljer**. Hitta den faktura du söker och markera den om du vill visa information om den. Informationen omfattar försäljningsorder referensen. Du bör också kunna komma åt försäljningsorder information från den sidan.

## <a name="how-do-i-delete-orphaned-sales-order-records"></a>Hur tar jag bort överblivna försäljningsorderposter?

Om du vill rensa överblivna försäljningsorder poster kör du det *periodiska jobbet för borttagning av försäljningsorder* genom att gå till någon av följande platser:

- Försäljning och marknadsföring \> Periodiska uppgifter \> Rensa \> Ta bort försäljningsorder
- Butik och handel \> Butik och handels-IT \> Rensa \> Ta bort försäljningsorder

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a>Finns det något sätt att beräkna provisioner på fakturor som redan har bokförts?

Supply Chain Management stöder för närvarande inte beräkningen av provisioner för bokförda fakturor.
