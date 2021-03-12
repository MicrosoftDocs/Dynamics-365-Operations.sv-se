---
title: Felsöka lageråtgärder
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med lageråtgärder.
author: sherry-zheng
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 3a22229106753d265a90f0ef05f5ac82dc745bbd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967165"
---
# <a name="troubleshoot-inventory-operations"></a>Felsöka lageråtgärder

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med lageråtgärder.

## <a name="i-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a>Jag hittar inte listrutan "Arbetsflöde" för lagerjournaler.

### <a name="issue-description"></a>Problembeskrivning

Du hittar inte listrutan **Arbetsflöde** på journalsidan, eller att relaterade arbetsflödesåtgärder inte är tillgängliga.

Det här problemet kan uppstå av tre orsaker, som beskrivs i följande underavsnitt.

### <a name="issue-resolution-1"></a>Problemlösning 1

Om problemet gäller för alla användare kan det bero på att arbetsflödet för godkännande inte har tilldelats journalnamnet. Gör så här om du vill åtgärda problemet.

1. Gå till **Lagerhantering &gt; Inställningar &gt; Journalnamn &gt; Lager**.
1. Välj ett journalnamn i listfönstret för att öppna inställningarna.
1. På snabbfliken **allmänt** anger du alternativet **Godkännandearbetsflöde** till *Ja*. Om du uppmanas att bekräfta ändringen väljer du **Ja**.
1. I fältet **Arbetsflöde** välj det arbetsflöde du vill använda för det valda journalnamnet.

### <a name="issue-resolution-2"></a>Problemlösning 2

Om det används anpassad kod i arbetsflödet kan problem uppstå när du har uppgraderat systemet. I journalarbetsflödet kan till exempel knappen **Skicka** vara gråtonad så att du inte kan välja den för att godkänna en överföring.

Om knappen **Skicka** är gråtonad kanske arbetsflödet har anpassats, vilket innebär att metoden för arbetsflödet, `canSubmitToWorkflow()` i `FormDataUtil`, utökats. Du åtgärdar problemet genom att ändra sättet som du utökar metoden för `canSubmitToWorkflow()` för att använda strukturen i följande exempel.

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

### <a name="issue-resolution-3"></a>Problemlösning 3

Om problemet endast gäller ett fåtal specifika användare kanske dessa användare inte har de säkerhetsprivilegier som krävs för att köra arbetsflödesåtgärder på lagerjournaler. Kontrollera att varje berörd användare har säkerhetsprivilegiet *Underhåll arbetsflöde för lagerjournal*. Som standard tilldelas det här privilegiet ett uppdrag som har samma namn och uppdraget tillämpas rollerna *Lagerarbetare* och *Lagerchef*.

## <a name="my-inventory-journal-remains-in-system-locked-status-and-the-workflow-batch-job-doesnt-work"></a>Min lagerjournal förblir i systemlåst status och batchjobbet för arbetsflödet fungerar inte.

### <a name="issue-description"></a>Problembeskrivning

En av dina lagerjournaler är låst av någon operation och släpps inte. Om ett okänt fel till exempel inträffar under bokföringen (vilket är en systemlåsoperation) kan journalen finnas kvar i systemlåst status. I det här fallet arbetsflödet arbetsobjekt hanterare kommer att kasta ett fel medan den gör låsvalidering.

### <a name="issue-resolution"></a>Problemlösning

Logga in på SQL Server-instansen för Supply Chain Management, och kontrollera om **InventJournalTable.SystemBlocked** är inställt på *1*. Om det är det, se till att journalen inte ska vara i låst status och återställ sedan **InventJournalTable.SystemBlocked** till *0*.

## <a name="my-inventory-journal-workflow-is-never-completed-and-the-journal-cant-be-edited-or-posted"></a>Mitt arbetsflöde för lagerjournalen har aldrig slutförts och journalen kan inte redigeras eller bokföras.

### <a name="issue-description"></a>Problembeskrivning

När du har skickat ett arbetsflöde för godkännande av journaler slutar arbetsflödesbearbetningen att svara och du kan inte redigera eller bearbeta dina journaler.

### <a name="issue-resolution"></a>Problemlösning

Det finns flera orsaker till att arbetsflödesbearbetningen kanske inte har slutförts. Kontrollera om följande problem:

- Gå till **Lagerhantering &gt; Inställningar &gt; Arbetsflöden för lagerhantering** och granska konfigurationen av det berörda arbetsflödet. Mer information finns i [Godkännandearbetsflöden för lagerjournal](inventory-journal-workflow.md).
- Arbetsflödet kanske stöter på ett undantag eller ett fel. Granska arbetsobjektshistoriken för det berörda arbetsflödet för att se om det inkluderar ett programfel som avslutar arbetsflödet.
- Lagerjournalen kan bara uppdateras eller redigeras om den är godkänd. Om återkallande är aktivt kan du försöka återkalla journalen. Körning av batchjobbet för arbetsflöde kanske stängs av på grund av flera skäl. Vissa av dessa orsaker kan bero på problemet med arbetsflödesramverket.

## <a name="inventory-journal-workflow-conditions-apply-only-at-the-journal-level-not-at-the-line-level"></a>Arbetsflödesvillkor för lagerjournal gäller endast på journalnivå, inte på radnivå

### <a name="issue-description"></a>Problembeskrivning

Det här problemet kan du uppleva om du till exempel försöker ställa in ett arbetsflödesvillkor för lagerjournal på kostnadsbeloppet. Du ställer in villkoret så att steg 1 endast körs när kostnadsbeloppet är mindre än 100. Du ställer in ett annat villkor så att steg 2 endast körs när kostnadsbeloppet är mer än eller lika med 100. När arbetsflödet körs visar sedan arbetsflödeshistoriken bara en rad, och det första villkoret utvärderas alltid som *sant*, oavsett vilket värde som skickas.

### <a name="issue-workaround"></a>Problemlösning

I aktuella versionen gäller endast arbetsflödesvillkor för lagerjournal på journalnivå, inte på radnivå. Detta beteende är av design. Vi rekommenderar att du anger dina villkor endast på journalnivåattribut.

## <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-filter-results-as-i-expect"></a>Filterfönstret på sidan Behållningslista filtrerar inte resultat som jag förväntar mig.

### <a name="issue-description"></a>Problembeskrivning

Filter i filterfönstret på sidan **Behållningslista** filtrerar inte resultat som du förväntar dig.

### <a name="issue-resolution"></a>Problemlösning

Detta beteende är av design.

Sidan  **Behållningslista** är monterad i en detaljerad lagerbehållning som inkluderar alla tillgängliga dimensioner. Listan på den här sidan är dock en sammanfattning. Därför kan det hända att rader kombineras från källtabellen genom att värdena aggregeras enligt de dimensioner som visas.

Filtren som anges i filterfönstret gäller för källtabellen, inte den aggregerade listan. Det här beteendet kan ibland ge oväntade resultat, vilket visas i [dessa exempel](inventory-on-hand-list.md#examples).

Men [filtren som finns i rutnätet](inventory-on-hand-list.md#grid-filters) *gäller* för den aggregerade listan. Dessa filter inkluderar både snabbfilter överst i rutnätet och filtret för varje kolumnrubrik.

## <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a>Enhets- och enhetskvantiteten fungerar inte korrekt i lagerjournalen.

### <a name="issue-description"></a>Problembeskrivning

Du kanske stöter på ett eller båda av följande problem när du arbetar med enheter och kvantiteter i en lagerjournal:

- Du ser inte enheter eller enhetskvantiteter i lagerjournalen medan en enhet med konvertering ställs in för den frisläppta produkten och du kan inte ändra enheten i lagerjournalen.
- Du ser fälten **Antal** och **Enhet** i lagerjournalen, men du ser inte fältet **enhetskvantitet**. Om du ändrar enheten, anger ett antal och bokför journalen, visar journalen fortfarande den ursprungliga måttenheten för den kvantiteten.

### <a name="issue-resolution"></a>Problemlösning

Gör så här om du vill åtgärda problemet.

1. I arbetsytan **Funktionshantering** se till att funktionen *Använda måttenhet och kvantitet i lagerjournaler* är aktiverad. Den här funktionen lägger till fälten **Enhet** och **Enhetskvantitet** i journalen.
1. När funktionen har aktiverats använder du fälten **Antal**, **Enhetskvantitet** och **Enhet** på följande sätt:

    - **Antal** – Ange kvantiteten med hjälp av standardenheten som har definierats för den frisläppta produkten. Standardenheten i sig visas dock inte här. Om en konvertering ställs in mellan standardenheten och den enhet som är markerad i fältet **Enhet** uppdateras fältet **Antal** automatiskt, baserat på valen i fälten **Enhetskvantitet** och **Enhet**.
    - **Enhetskvantitet** – Ange mängden i den enhet som har valts i fältet **Enhet**.
    - **Enhet** – Välj den enhet som ska kopplas till värdet i fältet **Enhetskvantitet**.

## <a name="i-receive-the-following-error-message-maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a>Följande felmeddelande visas: "Maximalt antal decimaler för lagerhållningsenheten är 0."

### <a name="issue-description"></a>Problembeskrivning

När du försöker bokföra en lagertransaktion eller en lagerreservation visas följande felmeddelande: "Maximalt antal decimaler för lagerhållningsenheten är 0."

Det här problemet uppstår när lagertransaktionskvantiteten anges som ett decimalvärde som är under den nivå av precision som fältet stöder. En kvantitet på *0,5* har till exempel angetts för en lagertransaktion, men endast heltalskvantiteter stöds. Därför bör värdet vara *1* i stället för *0,5*.

### <a name="issue-resolution"></a>Problemlösning

1. Kör följande skript på din SQL Server-instans för att avrunda kvantiteter i lagertransaktionerna. Det här skriptet kommer att korrigera värden i tabellen **inventTrans**.

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. Kör en konsekvenskontroll där alternativet **åtgärda fel** är aktiverat. Denna kontroll kommer att korrigera värden i tabellen **inventSum**.

> [!IMPORTANT]
> Vi rekommenderar starkt att du noggrant redigerar skriptet som krävs för din miljö, testar den i en testmiljö och sedan kontrollerar resulterande data innan du kör skriptet i en produktionsmiljö.
