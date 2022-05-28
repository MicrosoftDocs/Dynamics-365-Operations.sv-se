---
title: Rekommenderade metoder för bokföringsprofiler
description: I det här avsnittet beskrivs rekommenderade metoder för att konfigurera bokföringsprofiler.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, MainAccount, SysDatabaseLogSetup, CustGroup, VendGroup, InventItemGroup
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 211dc42b80089eb1f59a435f09d6e9d9f956736b
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734287"
---
# <a name="recommended-practices-for-posting-profiles"></a>Rekommenderade metoder för bokföringsprofiler

Det finns flera rekommenderade metoder som du bör följa när du konfigurerar bokföringsprofiler i hela systemet. I det här avsnittet beskrivs olika scenarier och motsvarande rekommenderade metoder.

## <a name="setting-the-do-not-allow-manual-entry-flag"></a>Ange flaggan Tillåt inte manuell inmatning

På sidan **Huvudkonton** bör kryssrutan **Tillåt inte manuell inmatning** vara markerad för något huvudkonto som används för en bokföringsprofil. Den här inställningen förhindrar att användarna manuellt bokför en journalpost till huvudkontot. Därför hjälper det till att säkerställa att redovisningen förblir i balans med redovisningen och gör avstämningsprocessen enklare.

Om du behöver justeringar för ett konto som styrs av systemet och bokförs automatiskt, kan du göra något av följande:

- Skapa ett sekundärt huvudkonto där justeringarna kan bokföras. Använd sedan ett totalkonto eller en särskild rad i dina ekonomiska rapporter för att gruppera och summera kontona tillsammans.
- Återför de ursprungliga transaktionerna i rätt delmall, gör de ändringar som behövs och bokförda sedan transaktionen på samma sätt på samma nivå.

## <a name="changing-posting-profiles-after-transactions-exist"></a>Ändra bokföringsprofiler efter det att det finns transaktioner

Om du ändrar en bokföringsprofil efter det att det finns transaktioner kan avstämningen misslyckas och redovisningen kan bli ur balans. I allmänhet rekommenderar vi att du **inte** ändrar bokföringsprofilen efter det att det finns transaktioner.

Om du behöver göra ändringar använder du följande riktlinjer för att säkerställa systemets integritet:

- Gör ändringarna under en periodslut.
- Gör ändringarna när inga andra transaktioner sker i systemet.
- Validera redovisningen och stäm av den mot redovisningen innan och efter att du har gjort ändringarna.
- Bokförda transaktioner uppdateras inte om du ändrar bokföringsprofilen. Tänk noggrant igenom om det behövs några justeringsposter för ändringen.
- Om du ändrar lagerbokföringsprofiler bör du överväga hur ändringarna påverkar lagerbehållningen och redovisningssaldona. För en del ändringar kanske du måste ta med lagret till 0 (noll), stänga lagret och sedan föra tillbaka lagret när ändringarna har gjorts.
- Testa alltid dina ändringar i en icke-produktionsmiljö innan du gör dem i produktionen.

## <a name="using-database-logging-to-audit-changes-to-posting-profiles"></a>Använda databasloggning för att granska ändringar av bokföringsprofiler

Du kan konfigurera databasloggning för varje bokföringsprofil och parameterregister som styr bokföringen. Om en parameter eller profil sedan ändras får du en fullständig verifieringspost över vilket värde som ändrades, vem som ändrade den, när den ändrades och vilket tidigare värde som var det. Denna information kan vara viktig under avstämningen, och din revisor kanske kräver den dokumentation som stöder det.

Mer information finns i [Konfigurera databasloggning](../../fin-ops-core/dev-itpro/sysadmin/configure-manage-database-log.md).

Använd tabellen nedan som referens för vanliga registernamn som är relaterade till bokföringsprofiler och relaterade bokföringsparametrar.

| Sidnamn | Navigeringssökväg | Tabellnamn |
|-----------|-----------------|------------|
| Parametrar för leverantörsreskontra | Leverantörsreskontra &gt; Inställningar &gt; Parametrar för leverantörsreskontra. | VendParm |
| Bokföringsprofil för leverantör | Leverantörsreskontra &gt; Inställningar &gt; Leverantörsbokföringsprofil | VendPosting |
| Kod för avgifter | Leverantörsreskontra &gt; Ställa in avgifter &gt; Avgiftskod eller Leverantörsreskontra &gt; Ställa in avgifter &gt; Avgiftskod | MarkupTable |
| Betalningsmetoder | Leverantörsreskontra &gt; Betalningsinställning &gt; Betalningsmetoder | VendPaymMode |
| Kassarabatter | Leverantörsreskontra &gt; Betalningsinställningar &gt; Kassarabatter eller Leverantörsreskontra &gt; Betalningsinställningar &gt; Kassarabatter | CashDisc |
| Betalningsavgift (leverantör) | Leverantörsreskontra &gt; Betalningsinställning &gt; Betalningsavgift | VendPaymFee |
| Parametrar för kundreskontra | Kundreskontra &gt; Inställningar &gt; Parametrar för kundreskontra | CustParm |
| Kundbokföringsprofiler | Kundreskontra &gt; Inställningar &gt; Kundbokföringsprofil | CustPosting |
| Betalningsmetoder | Kundreskontra &gt; Betalningsinställning &gt; Betalningsmetoder | CustPaymMode |
| Betalningsavgift (Kund) | Kundreskontra &gt; Betalningsinställning &gt; Betalningsmetoder | CustPaymFee |
| Parametrar för tillgångsleasing | Leasing av tillgångar &gt; Konfigurera &gt; Parametrar för tillgångsleasing | AssetLeasePostingAccounts<br>AssetLeaseJournalParameters<br>AssetLeaseExecutoryCostPostingAccounts |
| Bankkonton | Kassa- och bankhantering &gt; Bankkonton &gt; Bankkonton | BankAccountsTable |
| Banktransaktionstyper | Kassa- och bankhantering &gt; Inställningar &gt; Banktransaktionstyper | BankTransType |
| Elimineringsregler | Konsolideringar &gt; Inställningar &gt; Elimineringsregel | LedgerEliminationRule<br>LedgerEliminationRuleLines |
| Utgiftskategorier | Utgiftshantering &gt; Inställningar &gt; Allmänt &gt; Utgiftskategorier | ProjCategories |
| Parametrar för anläggningstillgångar | Anläggningstillgångar &gt; Inställning &gt; Parametrar för anläggningstillgångar | AssetParameters |
| Bokföringsprofiler för anläggningstillgångar | Anläggningstillgångar &gt; Inställning &gt; Bokföringsprofiler för anläggningstillgångar | AssetLedgerAccounts<br>AssetDisposalParameters |
| Valutaomvärderingskonton | Redovisning &gt; Valutor &gt; Valutaombedömningskonton | CurrencyLedgerGainLossAccount |
| Konton för automatiska transaktioner | Redovisning &gt; Bokföringsinställningar &gt; Konton för automatiska transaktioner | LedgerSystemAccounts |
| Koncernintern redovisning | Redovisning &gt; Bokföringsinställningar &gt; Koncerninterna konton | LedgerIntercompany |
| Bokföringsdefinitioner för transaktioner | Redovisning &gt; Bokföringsinställningar &gt; Bokföringsdefinitioner för transaktioner | JournalizingDefinitionTrans |
| Bokföringsdefinitioner | Redovisning &gt; Bokföringsinställningar &gt; Bokföringsdefinitioner | JournalizingDefintion |
| Bokföring (lager) | Lagerhantering &gt; Inställningar &gt; Bokföring &gt; Bokföring | InventPosting |
| Koder för kostnadstyp | Hemtagningskostnad &gt; Inställning av kostnadsredovisning &gt; Kostnadstypskoder | ITMCostTypeTable |
| Resurser | Produktionsstyrning &gt; Inställningar &gt; Resurser &gt; Resurser | WrkCtrTable |
| Resursgrupper | Produktionsstyrning &gt; Inställningar &gt; Resurser &gt; Resursgrupper | WrkCtrResourceGroup |
| Produktionsgrupper | Produktionskontroll &gt; Inställningar &gt; Produktion &gt; Produktionsgrupp | ProdGroup |
| Kostnadskategorier | Produktionskontroll &gt; Inställningar &gt; Rutter &gt; Kostnadskategorier | ProjCategory |
| Projektgrupper | Projekthantering och redovisning &gt; Inställningar &gt; Bokföring &gt; Projektgrupper | ProjGroup |
| Inställning av redovisningsbokföring (projekt) | Gå till Projekthantering och redovisning &gt; Inställningar &gt; Bokföra &gt; Inställning av redovisningsbokföring | ProjPosting |
| Standardmotkonton för utgifter | Projekthantering och redovisning &gt; Setup &gt; Inställningar &gt; Standardmotkonton för utgifter | ProjDefaultOffsetSetup |
| Bokföringsprofiler för rabatthantering | Rabatthantering &gt; Bokföringsinställningar för rabatthantering &gt; Bokföringsprofiler för rabatthantering | TAMRebatePosting |
| Redovisningsbokföringsgrupp (moms) | Skatt &gt; Inställningar &gt; Moms &gt; Redovisningsbokföringsgrupp | TaxAccountGroup |

## <a name="changing-groups-after-transactions-exist"></a>Ändra grupper efter det att det finns transaktioner

Var försiktig när du ändrar grupper i huvuddata. Om du använder grupper för att definiera bokföringsprofilerna kan en ändring i en grupp för en huvudpost påverka möjligheten att stämma av redovisningen mot redovisningen med redovisningen. Du kan till exempel konfigurera lagerbokföringsprofilen för försäljningsorderintäkt så att ett annat intäktskonto används för varje artikelgrupp. Om du ändrar artikelgruppen som tilldelas en artikel efter det att det finns transaktioner, bokförs intäkten för nya transaktioner på det uppdaterade kontot. Alla intäkter som bokfördes före ändringen kommer dock att ligga kvar på det ursprungliga kontot.

## <a name="testing-posting-profiles"></a>Bokföringsprofiler för test

Innan du går direkt och sedan har gjort ändringar i eller tillägg till bokföringsprofilerna eller relaterade parametrar, måste du testa alla scenarion. Du bör minst testa varje bokföringstyp för att validera att bokföringen fungerar som den ska. Vi rekommenderar dock att du testar varje bokföringsprofiltransaktion och kombination.

Du har till exempel två kundbokföringsprofiler, som vart och ett har tre poster som är specifika för kundgrupper. I detta fall ska du testa varje transaktionstyp.

**Bokföringsprofiler:**

- **GEN** – Den allmänna postningsprofilen som har en grupp för anställda, en för kunder och en för koncernintern. Varje grupp pekar till olika kundreskontra handelskonton.
- **PRE** – Den bokföringsprofil för förskottsbetalning som har en post för alla förskottsbetalningar som pekar på kundens förutbetalda konton.

### <a name="testing-scenarios"></a>Testscenarier

- Fritextfaktura för en kund i gruppen **Medarbetare** som använder bokföringsprofilen **GEN**
- Fritextfaktura för en kund i gruppen **Medarbetare** som använder bokföringsprofilen **PRE**
- Försäljningsorderfaktura för en kund i gruppen **Medarbetare** som använder bokföringsprofilen **GEN**
- Försäljningsorderfaktura för en kund i gruppen **Medarbetare** som använder bokföringsprofilen **PRE**
- Kundbetalningsjournal för en kund i gruppen **Medarbetare** som använder bokföringsprofilen **GEN**
- Kundbetalningsjournal för en kund i gruppen **Medarbetare** som använder bokföringsprofilen **PRE**

Upprepa i föregående exempel ett testscenario för varje kundgrupp och upprepa varje grupp av testscenarier för varje ytterligare transaktionstyp (till exempel projektfakturor och servicehantering).

## <a name="reconciling-the-ledger-to-the-subledger"></a>Avstämning av redovisning till reskontra

Redovisningen ska stämmas av mot reskontra varje period. Många moduler innehåller "färdiga"-rapporter som kan användas för att göra avstämningen. Beroende på dina lokala krav kanske du emellertid måste ta fram anpassade rapporter eller utöka de befintliga rapporterna så att de uppfyller dina rapporteringskrav.

Vi rekommenderar att du gör en låtsasperiod och stänger och stämmer av var och en av dina reskontra med redovisningen innan din start. Vi rekommenderar även att du gör en låtsasövergång av alla öppna saldon och öppna transaktioner innan du gör din ursprungliga start. Som en del av den här processen bör du köra en fullständig avstämning för att säkerställa att migreringen av saldon och öppna transaktioner balanserar med det äldre systemet och att alla redovisningssaldon med redovisningen innan nya transaktioner skapas.
