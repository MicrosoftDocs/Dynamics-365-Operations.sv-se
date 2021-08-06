---
title: Alternativ för transaktion för anläggningstillgång
description: Det här avsnittet innehåller en beskrivning av andra tillgängliga metoder för att skapa transaktioner för anläggningstillgångar.
author: ShylaThompson
ms.date: 02/07/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, PurchCreateOrder
audience: Application User
ms.reviewer: roschlom
ms.custom: 23061
ms.assetid: 338c495b-a4d8-461e-b85b-a83faf673730
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f9cd8846688e6b70f3ac2034caa1a9e3015355e
ms.sourcegitcommit: f9b40df70a77136529fbc790325ed657eb203731
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/20/2021
ms.locfileid: "6645382"
---
# <a name="fixed-asset-transaction-options"></a>Alternativ för transaktion för anläggningstillgång

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en beskrivning av andra tillgängliga metoder för att skapa transaktioner för anläggningstillgångar.

Du kan ställa in Anläggningstillgångar för integrering med Leverantörsreskontra, Kundreskontra, Anskaffning och källa, samt Redovisning. Du kan även överföra artiklar i Lager till Anläggningstillgångar för intern användning.

## <a name="accounts-payable"></a>Leverantörsreskontra
Du kan ange transaktioner för anläggningstillgångar på sidan Bokföringsorder. Denna sida kan öppnas från sidan Invoice journal. Du kan också öppna sidan Bokföringsorder på sidan Fakturagodkännandejournal. Välj Anläggningstillgångar i fältet Motkontotyp. Välj sedan ett Anläggningstillgångsnummer i fältet Motkonto. På fliken Anläggningstillgångar anger du värden i fälten Transaction type och Book.

## <a name="accounts-receivable"></a>Kundreskontra
Du kan ange transaktioner för anläggningstillgångar på sidan Fritextfaktura.  Välj en radartikel i rutnätet Fakturarader på sidan Fritextfaktura. Klicka på snabbfältet Radinformation. Ange Anläggningstillgångsnumret och boken för avyttringstransaktionen. För fritextfakturor är transaktionstypen för anläggningstillgångar alltid Avyttrande försäljning.

## <a name="procurement-and-sourcing"></a>Anskaffning och källa
Du kan ange transaktioner för anläggningstillgångar på sidan Inköpsorder. Ange nödvändig information för att skapa en inköpsorder och klicka sedan på OK. Klicka på snabbfliken Radinformation på sidan Inköpsorder. Ange sedan information om anläggningstillgången på fliken Anläggningstillgångar. 

Om du vill bokföra en anskaffningstransaktion för en befintlig anläggningstillgång anger du Anläggningstillgångsnumret, boken samt transaktionstypen. Anläggningstillgången kan inte bokföras om en del av den här informationen saknas. Om du vill bokföra en anskaffningstransaktion för en ny anläggningstillgång markerar du alternativet Ny anläggningstillgång? och väljer Anläggningstillgångsgruppen som den nya tillgången ska tilldelas till. Inget Anläggningstillgångsfält är emellertid tillgängligt för en rad om artikeln finns i en lagermodellgrupp som använder lagermodellen Standardkostnad. Alternativen som definierats på parametersidan Anläggningstillgångar bestämmer om du kan bokföra anskaffningstransaktioner från inköpsmodulerna. 

När inköpsorderjournalen eller journalen för lager till anläggningstillgångar används för anskaffning av anläggningstillgångar påverkas lagervärdet.

## <a name="general-ledger"></a>Huvudbok
Alla transaktionstyper för anläggningstillgångar kan bokföras på sidan Allmän journal. Du kan också använda journaler i Anläggningstillgångar för att bokföra transaktioner för anläggningstillgångar.

### <a name="options-for-entering-fixed-asset-transaction-types"></a>Alternativ för att ange transaktionstyper för anläggningstillgångar


| transaktionstyp                    | Modul                   | Alternativ                                   |
|-------------------------------------|--------------------------|-------------------------------------------|
| Anskaffning, Anskaffningsjustering | Anläggningstillgångar             | Anläggningstillgångar, Lager till anläggningstillgångar   |
|                                     | Huvudbok           | Allmän journal                           |
|                                     | Leverantörsreskontra         | Fakturajournalen, Fakturagodkännandejournal. |
|                                     | Anskaffning och källa | Inköpsorder                            |
| Avskrivning                        | Anläggningstillgångar             | Anläggningstillgångar                              |
|                                     | Huvudbok           | Allmän journal                           |
| Avyttrande                            | Anläggningstillgångar             | Anläggningstillgångar                              |
| ** **                               | Huvudbok           | Allmän journal                           |
| ** **                               | Kundreskontra      | Fritextfaktura                         |

Avskrivningsperiodernas återstående värde av anläggningstillgången uppdateras inte när en journalrad för avskrivningstransaktionstyp skapas manuellt eller importeras via en datatabell. Detta värde uppdateras när avskrivningsförslagsprocessen används till att skapa journalraden.

Mer information finns i [Integrering av anläggningstillgångar](fixed-asset-integration.md).

### <a name="transactions-that-require-different-voucher-numbers"></a>Transaktioner som kräver olika verifikationsnummer

Följande transaktioner för anläggningstillgångar kommer att använda olika verifikationsnummer:

- Ett ytterligare förvärv görs på en tillgång och "catch-up”-avskrivning beräknas.
- En tillgång delas upp.
- En parameter för att beräkna avskrivning vid avyttring aktiveras och sedan avyttras tillgången.
- En tillgångs servicedatum infaller före anskaffningsdatumet. Dörför bokförs en avskrivningsjustering.

> [!NOTE]
> När du registrerar transaktioner ska du se till att alla transaktionerna gäller för samma anläggningstillgång. Verifikationen bokförs inte om den innehåller fler än en anläggningstillgång, även om fältet **Ny verifikation** anges till bara **Ett verifikationsnummer** på sidan **Journalnamn** i redovisningen. Om du inkluderar fler än en anläggningstillgång i verifikationen kan meddelandet Den kan bara finnas en transaktion för anläggningstillgång per verifikation och du kan inte bokföra verifikationen.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
