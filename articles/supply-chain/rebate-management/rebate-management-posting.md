---
title: Bokföringsinställningar för rabatthantering
description: I det här avsnittet beskrivs hur du ställer in bokföringsprofiler. Bokföringsprofiler används för att bestämma bokföringsposter för beräkningsrader för rabatthantering.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: edffccfec552d90ce704190b4be0b4594964fa81
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574339"
---
# <a name="rebate-management-posting-setup"></a>Bokföringsinställningar för rabatthantering

[!include [banner](../includes/banner.md)]

Bokföringsprofiler för rabatthantering används för att bestämma bokföringsposter för beräkningsrader för rabatthantering. När en bokföringsprofil har valts i affärens huvud, gäller detta för alla avtalsrader.

Den här funktionen fungerar i flera företag (juridiska personer). Du kan ange vilket företag som belopp ska periodiseras och att anspråken ska betalas av. Du kan även ställa in olika debetkonton för reservering och bortskrivning av kreditkonton per källbokföringsföretag.

Om du vill ställa in bokföringsprofiler för rabatthantering för kunder och leverantörer går du **Rabatthantering \> Bokföringsinställningar för rabatthantering \> Bokföringsprofiler för rabatthantering**. Sidan **Bokföringsprofiler för rabatthantering** innehåller ett listfönster som visar alla befintliga profiler. Du kan använda knapparna i åtgärdsfönstret för att lägga till profiler i listan eller ta bort dem.

De återstående avsnitten i det här avsnittet beskriver hur du använder de tillgängliga fälten när du skapar eller redigerar en profil.

## <a name="posting-profile-header"></a>Bokföra profilrubrik

I tabellen nedan beskrivs de inställningar som är tillgängliga i rubrikavsnittet för alla bokföringsprofiler för rabatthantering.

| Fält | beskrivning |
|---|---|
| Bokföringsprofil | Ange ett unikt namn för profilen. |
| beskrivning | Ange en beskrivning av profilen. |
| Modul | Välj den modul som rabatter och royalties som profilen är associerad med ( *Kund* eller *Leverantör*). |
| Typ | Välj profiltyp ( *Rabatt* eller *Royalty*). |
| Betalningstyp | <p>Det här fältet bestämmer formatet för den bokförda rabattutleveransen.<p><p>När fältet **Typ** är inställt på *Rabatt* är följande värden tillgängliga:</p><ul><li>*Betala med leverantörsreskontra* – När du bokför en kundrabatt skapas en leverantörsfaktura för remissleverantören som ställs in för rabattkunden. När du bokför en leverantörsrabatt skapas en leverantörsfaktura för rabattens leverantörskonto.</li><li>*Kundavdrag* – När du bokför rabatten skapas en kundavdragsjournal för rabattkunden.</li><li>*Kundavdrag för momsfaktura* – När du bokför rabatten skapas en fritextfaktura för rabattkunden.</li><li>*Handelsutgift* – När du bokför rabatten skapas en kundavdragsjournal för rabattkunden.</li><li>*Rapportering* – När du bokför rabatten skapas en kundavdragsjournal för rabattkunden.</li></ul><p>När fältet **Typ** är inställt på *Royalty* är följande värden tillgängliga:</p><ul><li>*Betala med leverantörsreskontra* – När du bokför rabatten skapas en leverantörsfaktura för rabattens leverantörskonto.</li><li>*Rapportering* – När du bokför rabatten skapas en leverantörsfaktura för rabattens leverantörskonto.</li></ul><p>För mer information, se avsnittet [Betalningstyper](#payment-types) som följer. |
| Företag | Välj vilket företag (juridisk person) som provisioner ska periodiseras och att anspråken ska betalas av. |

### <a name="payment-types"></a>Betalningstyper

I tabellen nedan beskrivs hur de olika inställningarna i fältet **Betalningstyp** påverkar var betalningarna bokförs. Betalningar kan bokföras på ett kundkonto, leverantörskonto eller remancekonto, beroende på måltransaktion och rabattyp.

| Betalningstyp | Måltransaktionstyp | Rabattyp | Betalning till (fakturakonto) |
|---|---|---|---|
| Betala med leverantörsreskontra | Leverantörsfakturajournal | Kundrabatt | Kundens leverantörskonto för remittering |
| Betala med leverantörsreskontra | Leverantörsfakturajournal | Kundroyalty | Leverantörskonto |
| Betala med leverantörsreskontra | Leverantörsfakturajournal | Säljarrabatt | Leverantörskonto |
| Kundavdrag | Dagsjournal | Kundrabatt | Kund-ID |
| Momsfaktura och kundavdrag | Fritextfaktura | Kundrabatt | Kund-ID |
| Handelsutgift | Dagsjournal | Kundrabatt | Kund-ID |
| Rapportering | Dagsjournal | Kundrabatt | Kund-ID |
| Rapportering | Leverantörsfakturajournal | Kundroyalty | Leverantörskonto |
| Rapportering | Leverantörsfakturajournal | Säljarrabatt | Leverantörskonto |

> [!NOTE]
> Ta hänsyn till följande när du ställer in [rabatthanteringserbjudanden](rebate-management-deals.md):
>
> - För transaktioner där fältet **Stäm av efter** anges till *Erbjudande*, kan du inte använda det dynamiska erbjudandekontot vid bokföring. Du måste använda ett angivet kund- eller leverantörskonto.
> - För erbjudanden där fältet **Stäm av efter** anges till *Rad* kan du använda en bokföringsprofil som förskjuts till ett dynamiskt affärskonto på erbjudanderaden, eftersom kunden eller leverantören är inställd per transaktionsrad.

## <a name="posting-fasttab"></a>Snabbflik för bokföring

I tabellen nedan beskrivs de fält som är tillgängliga på snabbfliken **Bokföring** för alla bokföringsprofiler för rabatthantering.

| Fält | beskrivning |
|---|---|
| Kredittyp | Välj om du vill kreditera ett redovisningskonto eller en kund. Om fältet **Betalningstyp** i rubriken anges till *Momsfaktura och kundavdrag*, anges detta fält till *huvudbokskonto*. För leverantörsrabatter är det här fältet inställt på *huvudbokskonto*. |
| Kreditkonto | Välj det konto som kreditbeloppen bokförs på när rabattbeloppen förs in. Det här kontot kommer även att användas som motkonto när rabatten bokförs för att kreditera kunden eller debitera leverantören. |
| Journalnamn<br>(I avsnittet **Provision**) | Välj namnet på den journal som ska användas för att registrera den bokförda provisionen. |
| Typ | Välj om du vill bokföra rabatten till ett redovisningskonto eller till en kund eller leverantör. Om fältet **Betalningstyp** i rubriken anges till *Momsfaktura och kundavdrag*, anges detta fält till *Kund/leverantör*. |
| Använd kontokälla | <p>Välj ett av följande värden:</p><ul><li>*Fast konto* – Om du väljer det här värdet måste du ange ett konto i fältet **Rabattkonto**.</li><li>*Erbjudanderadkonto* – Använd kund- eller leverantörskontot som anges på rabattraden. Du kan bara välja detta värde för erbjudanden där fältet **Stäm av efter** anges till *Rad* och erbjudanderader där fältet **Kontokod** anges till *Tabell*. Den gäller inte för bokföringsprofiler för kund-/royaltybokföring eller leverantörsrabatter som baseras på försäljningsorder.</li></ul> |
| Rabattkonto | Kontot som faktiska rabatter bokförs på. |
| Journalnamn<br>(I Fältgrupp för **rabatthantering**) | Välj namnet på den journal som ska användas för att bokföra en kreditfaktura för rabattbeloppet till kunden eller leverantören. Det här fältet är inte tillgängligt när **Betalningstyp** anges till *Momsfaktura för kundavdrag*. För kundrabatter är journalnamn av typen *Daglig* journal tillgängliga. För kund- och leverantörsrabatter är journalnamnen för journaltypen *Leverantörsfakturaregistrering* tillgänglig. |
| Artikelmomsgrupp | Ange om rabatten är beskattningsbar. |
| Journalnamn<br>(I fältgrupp **Avskrivning**) | Om rabatten som bokförs inte är lika med provision kan skillnaden skrivas av. Välj namnet på den journal som ska användas för att registrera den bokförda avskrivningen. |

## <a name="posting-by-company-fasttab"></a>Snabbflik för bokföring efter företag

Snabbfliken **Bokföring per företag** för varje rabattadministrationsbokningsprofil kan du ange det bokningskonto som används av varje företag (juridisk enhet) i rutnätet.

Använd knapparna i verktygsfältet för att lägga till företag i rutnätet och ta bort dem. Varje gång du lägger till en rad i rutnätet använder du fältet **Företag** för att ange den juridiska personen för den raden. Fältet **Namn** ställs automatiskt in.

Markera raden för respektive företag och ange sedan följande information med hjälp av fälten under rutnätet:

- **Debettyp** – Välj om du vill debitera ett redovisningskonto eller leverantör. För kundrabatter och royalties är det här fältet inställt på *huvudbokskonto*.
- **Debetkonto** – Ange det konto som debetbeloppet bokförs på när rabattbeloppen tillämpas.
- **Huvudkonto** – Välj huvudkonto för avskrivning.
