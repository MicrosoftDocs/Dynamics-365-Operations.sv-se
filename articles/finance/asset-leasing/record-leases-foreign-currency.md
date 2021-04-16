---
title: Registrera leasing i utländsk valuta
description: I det här ämnet beskrivs hur du registrerar leasing i andra valutor än redovisnings- eller rapporteringsvalutan.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7f1f9153d627eba4c3c79a764cffec6a2f008818
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5819756"
---
# <a name="record-leases-in-foreign-currencies"></a>Registrera leasing i utländsk valuta

[!include [banner](../includes/banner.md)]

Leasingkonton för tillgångar för leasingar i andra valutor än redovisningsvalutan eller rapporteringsvalutan fastställs på sidan **Redovisningsinställningar**. Alla leasingar ska anges i sin transaktionsvaluta. Med andra ord ska de anges i den valuta som är angiven i leasingavtalet. I det här ämnet beskrivs hur du registrerar leasing i andra valutor än redovisnings- eller rapporteringsvalutan.

Om du anger en leasing i en utländsk valuta avskrivs ROU-tillgången i både redovisningsvalutan och rapporteringsvalutan. Dessa valutor konfigureras på sidan **Redovisningsinställningar**. Det här beteendet används också i Anläggningstillgångar. När du skapar en leasing i en utländsk valuta väljer du transaktionsvalutan i fältet **Valuta**.

Valutakursen för redovisningsvalutan är standardvärdet i fältet **Redovisningsvalutans valutakurs**. Valutakursen för rapporteringsvalutan är standardvärdet i fältet **Rapporteringsvalutans valutakurs**. Dessa valutakurser gällde vid den tidpunkt då leasingen påbörjades. Fälten **Redovisningsvalutans valutakurs** och **Rapporteringsvalutans valutakurs** finns på snabbfliken **Information om ekonomi- och rapporteringsvalutakurs** på sidan **Leasingdetaljer**.

1. Markera kryssrutan **Fast kurs** om du vill åsidosätta den valutakurs som angavs automatiskt och ange sedan den nya kursen.
2. Ange den information som krävs för leasingen i de andra fälten och välj sedan **Skapa scheman**.
3. Välj **Böcker** på sidan **Leasingdetaljer**.
4. På sidan **Leasingbok**, på fliken **Information om ekonomi- och rapporteringsvalutakurs**, kontrollerar du värdena i fälten **Redovisningsvaluta för initial tillgång med nyttjanderätt** och **Rapporteringsvaluta för initial tillgång med nyttjanderätt**. Vart och ett av fälten visar det översatta ROU-tillgångsvärdet i den motsvarande valutan. Dessa fält uppdateras varje gång du ändrar ekonomisk information. Välj **Skapa scheman** innan du bekräftar betalningsplanen.

    Den ursprungliga redovisningsjournalposten registrerar den ROU-tillgång som använder valutakurserna som listas i leasingen. Journalposten inkluderar även värdena i fälten **Redovisningsvaluta för initial tillgång med nyttjanderätt** och **Rapporteringsvaluta för initial tillgång med nyttjanderätt**.

## <a name="subsequent-measurement-for-foreign-currency-leases"></a>Efterföljande mått för leasing i utländsk valuta

Avskrivningsplanen visar de förväntade utgifterna för avskrivning i rapporteringsvalutan, redovisningsvalutan och transaktionsvalutan.

Om du vill visa ROU-tillgångssaldon och avskrivningsbelopp i antingen rapporteringsvalutan eller redovisningsvalutan öppnar du sidan **Avskrivningsplan för tillgången** och markerar kryssrutan **Visa belopp i redovisningsvaluta** eller **Visa belopp i rapporteringsvaluta**.

När du skapar avskrivningsjournalposterna mot en leasing som uttrycks i en utländsk valuta, använder posten de valutakurser som anges i leasingen. Den använder också värdena i fälten **Redovisningsvaluta för initial tillgång med nyttjanderätt** och **Rapporteringsvaluta för initial tillgång med nyttjanderätt**.

Det slutliga utgiftsbeloppet för avskrivning kan beräknas med en något annorlunda valutakurs, så att ROU-tillgången är helt avskriven i både redovisningsvalutan och rapporteringsvalutan.

Om leasingen har omklassificerats som **Uppskov av leasingavgift** rensar systemet automatiskt redovisnings- och rapporteringsvalutorna, om de redan har definierats.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]