---
title: Återföra bokförda leasingtransaktioner
description: I det här ämnet beskrivs hur du återför en bokförd leasingtransaktion. Alla transaktioner som skapas via Leasing av tillgångar kan återföras.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseLeaseTransactions
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 4f23b6cca6ddf4da7a0232a5bc61785dbd451d55
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908079"
---
# <a name="reverse-posted-lease-transactions"></a>Återföra bokförda leasingtransaktioner

[!include [banner](../includes/banner.md)]

Alla transaktioner som skapas via Leasing av tillgångar kan återföras. Transaktioner som återförs via Leasing av tillgångar uppdaterar dina leasingdata. Det innebär att de också uppdaterar de redovisade värdena för leasingskulden och ROU-tillgången (tillgången med nyttjanderätt).

Om du vill skapa en återföringstransaktion för en leasing följer du stegen nedan.

1. På antingen sidan **Transaktioner för tillgångar** eller sidan **Skuldtransaktioner** väljer du transaktionen och väljer sedan **Återför transaktion**.
2. I dialogrutan som visas kan du redigera datumet när återföringsposten kommer att bokföras. Som standard är fältet **Datum** inställt på transaktionsbokföringsdatumet för den transaktion som du har valt. Återföringsposten kan inte bokföras tidigare än det ursprungliga bokföringsdatumet för den valda transaktionen.
3. Välj **OK**. En journalpost bokförs som återför den valda transaktionen. Återföringen visas på sidan **Transaktioner för tillgångar** eller sidan **Skuldtransaktioner** och nettosumman för det aktuella saldo som visas på sidan uppdateras.

När du väljer **Återförd spårning** visas en dialogruta där både de ursprungliga transaktionerna och de återförda transaktionerna visas, tillsammans med ett länkat nummer som kallas *spårningsnummer*. Om du vill göra återföringarna lättare att förstå och förbättra synligheten kan du spåra återföringar genom att använda leasingplanerna.

I fältet **Senaste journalnummer** på sidan **Tidsplanera** visas journalnumren för transaktionerna. När en transaktion återförs uppdateras det här fältet med journalnumret för en återföringstransaktion. Kryssrutan **Återförd** är dessutom markerad för att visa att transaktionen har återförts och fältet **Bokförd** markeras.

## <a name="revoke-a-reversed-transaction"></a>Återkalla en återförd transaktion

Om du vill återkalla en återförd transaktion följer du stegen nedan.

1. Välj den ursprungliga transaktionen på någon av sidorna **Tidsplanera** eller **Transaktioner**.
2. Gör något av följande:

    - Om du har valt transaktionen på sida **Tidsplanera** följer du stegen för att skapa en journal i [Skapa månadsvisa poster i redovisningsjournal i en batch](create-monthly-journals-batch.md). Du måste bokföra journalen manuellt.
    - Om du har valt transaktionen på sidan **Transaktioner** väljer du **Återför transaktion**. Du får ett meddelande om att denna återkallning är en återkallning av en tidigare återföring, och att du kan redigera bokföringsdatumet för återkallningen. Generella affärsvalideringar påverkar dock de datum som kan anges i fältet **Datum**. 

3. Välj **OK**. En journalpost bokförs som återför den valda transaktionen. Återföringen visas på sidan **Transaktioner** och nettosumman i det aktuella saldot återställs till det som ingick före den första återföringen. Därför är den inverkan som återföringen hade på saldona negerad.

När du väljer **Återförd spårning** visas en dialogruta där både de ursprungliga transaktionerna och de återförda transaktionerna visas, tillsammans med ett spårningsnummer.

Du kan också spåra återkallningarna med hjälp av lämplig sida för **planer**. Fältet **Återför** rensas och fältet **Journal bokförd** markeras. Dessutom uppdateras fältet **Senaste journalnummer** med journalnumret för återkallningstransaktionen och fältet **Journalnummer** uppdateras med numret på återföringsjournalen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
