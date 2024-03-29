---
title: Kvittningöversikt
description: Den här artikeln innehåller allmän information om kvittningsprocessen. Den beskriver vilka transaktionstyper som kan kvittas samt tid och process för kvittning av dem. Här beskrivs även resultat av kvittningsprocessen.
author: angelad116
ms.date: 07/30/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14551"
- intro-internal
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: angelading
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 343802b409363f2698f857f3fc0e2682b48fec92
ms.sourcegitcommit: 0b7a034e644f4d93fe55c7baca5a3f89dbe56898
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151235"
---
# <a name="settlement-overview"></a>Kvittningsöversikt

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Den här artikeln innehåller allmän information om kvittningsprocessen. Den beskriver vilka transaktionstyper som kan kvittas samt tid och process för kvittning av dem. Här beskrivs även resultat av kvittningsprocessen.

Under kvittning tillämpas transaktionerna för ett dokument till transaktioner på ett annat dokument för att minska eller öka saldot för varje dokument. Exempelvis kan en betalning tillämpas till en faktura. Olika typer av transaktioner kan kvittas vid olika tidpunkter och genom olika metoder. Kvittningen kan även generera nya transaktioner.

## <a name="what-transactions-can-be-settled"></a>Vilka transaktioner kan kvittas

Kvittning i Leverantörsreskontra och Kundreskontra kan inträffar mellan alla transaktionstyper som påverkar leverantörssaldot eller kundsaldot, till exempel fakturor, betalningar, kreditfakturor och avgifter. Dessa transaktionstyper kan omfatta fakturor, betalningar, kreditnotor och avgifter. Alla transaktionstyper kan kvittas mot någon annan transaktionstyp. Du kan till exempel kvitta en betalning mot en faktura, en kreditfaktura mot en faktura, en faktura mot en faktura och en betalning mot en annan betalning.

Du kan kvitta betalningar mot en transaktion i samma juridiska person eller i en annan juridisk person. I organisationer som använder en centraliserad betalningmodell kan [centraliserade betalningar](set-up-centralized-payments.md) förenkla betalningsprocessen.

## <a name="when-to-settle-transactions"></a>När du ska kvitta transaktioner

Transaktioner kan kvittas när betalningar registreras. Till exempel när du gör betalningar till en leverantör, väljer du vanligtvis vilka fakturor som ska betalas. Genom att välja fakturor kan markera du dem för kvittning mot betalningen. När ansvariga för kundreskontrabetalningar registrerar kundbetalningar, kan användaren välja lämpliga fakturor för kvittning som baseras på informationen som inkluderas med varje kunds betalning. Använd sidan **Kvitta transaktioner** för att markera transaktioner för kvittning. Den här sidan kan öppnas från en ej bokförd faktura eller betalning. När transaktionen bokförs, bokförs även kvittningen. 

Transaktioner kan också kvittas, när de har bokförts. Du kan ange och bokföra en kundbetalning, utan att kvitta den mot eventuella fakturor. Du kanske först vill kontrollera att betalningen kvittas mot den korrekta fakturan innan kvittningen bokförs. Sidan **Kvitta transaktioner** kan öppnas från sidan **Alla kunder** eller **Alla leverantörer** eller från sidan **Transaktioner** för alla kunder eller leverantörer.

Du kan också reservera bokförda förskottsbetalningar för en faktura, genom att välja betalningen för kvittning mot en inköpsorder eller försäljningsorder. I det här fallet har betalningen fortfarande en ingående balans, men kan inte kvittas mot en annan faktura. Betalningen kvittas automatiskt mot den faktura som skapas från en inköpsorder eller försäljningsorder.

## <a name="how-to-settle-transactions"></a>Så här kvittar du transaktioner

Transaktioner kan kvittas manuellt, automatiskt, eller genom att använda en kombination av de två metoderna. Valet av kvittningsmetod beror på dina affärsprocesser. På sidorna **Parametrar för leverantörsreskontra** och **Parametrar för kundreskontra** kan du konfigurera kvittnings processen så att den justeras efter affärsprocesserna.

Du kan skapa leverantörsbetalningar och autogirobetalningar för kunder genom att använda ett betalningsförslag. Ett betalningsförslag används för att välja fakturor som ska betalas. Betalningsförslaget startas manuellt men sedan väljer systemet automatiskt de utvalda fakturorna för kvittning när betalningarna skapas.

Om betalningarna skapas manuellt kan du använda **Kvitta transaktioner** för att välja fakturor för kvittning. Du kan manuellt välja fakturorna, eller använda alternativet **Markera efter prioritet** om du vill att fakturor ska väljas automatiskt för kvittning. Alternativet **Markera efter prioritet** är bara tillgängligt för kundreskontra. Du kan aktivera det här alternativet på fliken **Kvittningsprioritet** på sidan **Parametrar för kundreskontra**.

Om en betalningsansvarig registrerar en betalning, men inte kvittar betalningen innan den bokförs kan betalningen kvittas automatiskt. Du kan slå på automatisk kvittning på sidorna **Parametrar för kundreskontra** och **Parametrar för leverantörsreskontra**. Automatisk kvittning kvittar endast transaktioner för samma juridiska person. Det går inte att kvitta transaktioner mellan flera juridiska personer.

När du använder automatisk kvittning kan du använda fördefinierad kvittningsprioritet eller definiera din egen prioritetsordning för kvittning på sidan **Parametrar för kundreskontra**. Den här funktionen är bara tillgänglig för kundreskontra.

## <a name="results-of-settlement"></a>Resultat från kvittningen

Allt eftersom transaktioner kvittas, ökas eller minskas det utestående saldot för respektive transaktion. Vanligtvis när en faktura och en betalning kvittas, uppdateras status och saldo för respektive transaktion enligt följande regler:

- Om betalningsbeloppet är mer än fakturabeloppet, reduceras fakturasaldot till 0,00 och fakturan stängs. Betalningen förblir öppen och saldot är skillnaden mellan betalningsbeloppet och fakturabeloppet.
- Om betalningsbeloppet är mindre än fakturabeloppet, reduceras betalningssaldot till 0,00 och betalningen stängs. Fakturan förblir öppen och saldot är skillnaden mellan fakturabeloppet och betalningsbeloppet.
- Om betalningsbeloppet är lika med fakturabeloppet, stängs både betalningen och fakturan och saldo för båda minskas till 0,00.

Om [betalningsbeloppet är mindre än fakturabeloppet](../accounts-payable/vendor-payments-partial-amount.md) på grund av kassarabatt, avskrivning, eller underbetalning, kan faktura och betalning fortfarande stängas beroende på hur kvittningar är konfigurerade på sidorna **Parametrar för leverantörsreskontra** och **Parametrar för kundreskontra**.

Kvittningar kan även generera transaktioner. Till exempel kan kvittning av en faktura och en betalning ge en kassarabatt, realiserad vinst eller förlust, momsjusteringar, avskrivningar, eller öresutjämning.

## <a name="identifying-marked-transactions-during-settlement"></a>Identifiera markerade transaktioner under kvittning

När du försöker kvitta en transaktion kan det hända att en symbol visas som anger att transaktionen har markerats på en annan plats. I detta fall kan du välja transaktionen på sidan **Kvitta transaktioner** och sedan välja **Fråga \> Kvittning i fönstret kvittning**. Vyn för den här frågan visar journaler, försäljningsorder, fakturor, betalningsförslag och kundplatser som eventuellt blockerar transaktionen från kvittning. Du kan lösa problemet genom att välja länken för att gå direkt från frågan till den spärrade platsen. Du kan sedan uppdatera dokumentet med de justeringar som krävs för kvittning. Du kan också använda indikatorn **Märkt** för att identifiera andra dokument som finns på samma blockeringsplats.

## <a name="resolve-issues-with-transactions-that-cant-be-settled"></a>Lös utsproblem med transaktioner som inte kan kvittas

Ibland kan du inte kvitta transaktioner eftersom en annan aktivitet bearbetar dokumentet. Om du försöker kvitta transaktionerna uppstår ett fel eftersom dessa transaktioner används. För att lösa problemet kan du använda sidan **Markerade transaktionsdetaljer** för att hitta transaktioner som märkts för kvittning och identifiera eventuella ytterligare processer med åtkomst till dessa.

Transaktioner markeras för kvittning antingen när leverantörsfakturor betalas eller när kunder betalar sina öppna fakturor. Då och då kan dessa fakturor redan ha markerats för kvittning. Användarna kan därför inte välja dem för betalning. Fakturorna kan markeras av en annan kundbetalningsjournal, försäljningsorder, leverantörsbetalningsjournal eller inköpsorder i den aktuella juridiska personen eller någon annan juridisk person.

Om en transaktion är spärrad för kvittning när du för in en kundbetalning öppnar du sidan **Kundmärkta transaktionsdetaljer** (**Kundreskontra \> Periodiska uppgifter \> Kundmärkta transaktionsdetaljer**). Om du snabbt vill identifiera var en transaktion har spärrats kan du ställa in någon av följande urvalsparametrar: **Kundkonto**, **Verifikation**, **Datum** eller **Faktura**. Om du inte ställer in några urvalsparametrar visar systemet alla spärrade dokument från det aktuella företaget eller något annat företag som du väljer. När transaktionen som har spärrats för kvittning har identifierats kan du markera den och sedan välja **Avmarkera valda transaktioner**. Den valda transaktionen tas då bort från alla journaler som inkluderar den. Dokumentet tas dock inte bort från den andra platsen. Endast markeringsinformationen tas bort från journalen.

Om en transaktion är spärrad för kvittning när du för in en leverantörsbetalning öppnar du sidan **Leverantörsmärkta transaktionsdetaljer** (**Leverantörsreskontra \> Periodiska uppgifter \> Leverantörsmärkta transaktionsdetaljer**). Om du snabbt vill identifiera var en transaktion har spärrats kan du ställa in någon av följande urvalsparametrar: **Leverantörskonto**, **Verifikation**, **Datum** eller **Faktura**. Om du inte ställer in några urvalsparametrar visar systemet alla spärrade dokument från det aktuella företaget eller något annat företag som du väljer. När transaktionen har identifierats kan du markera den och sedan välja **Avmarkera valda transaktioner** för att åtgärda blockeringsproblemet. Den valda transaktionen tas då bort från alla journaler där den har valts. Dokumentet tas dock inte bort från den andra platsen. Endast markeringsinformationen tas bort från journalen.

Om du vill identifiera alla spärrade dokument öppnar du sidan **Alla markerade transaktionsdetaljer** (**Kundreskontra \> Periodiska uppgifter \> Alla markerade transaktionsdetaljer** eller **Leverantörsreskontra \> Periodiska uppgifter \> Alla markerade transaktionsdetaljer**). Om du snabbt vill identifiera var en transaktion har spärrats kan du ställa in någon av följande urvalsparametrar: **Kundkonto**, **LEverantörskonto**, **Verifikation**, **Datum** eller **Faktura**. Om du inte ställer in några urvalsparametrar visar systemet alla spärrade dokument från det aktuella företaget eller något annat företag som du väljer. När transaktionen har identifierats kan du markera den och sedan välja **Avmarkera valda transaktioner** för att åtgärda blockeringsproblemet. Den valda transaktionen tas då bort från alla journaler där den har valts. Dokumentet tas dock inte bort från den andra platsen. Endast markeringsinformationen tas bort från journalen.

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda arbetsytan **funktionshantering** för att kontrollera funktionens status och aktivera den om det behövs. Funktionen visas på följande sätt:

- **Modul:** Kassa- och bankhantering
- **Funktionsnamn:** Formuläret Markerade transaktionsdetaljer

## <a name="additional-resources"></a>Ytterligare resurser

- [Kvitta rest](settle-remainder.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
