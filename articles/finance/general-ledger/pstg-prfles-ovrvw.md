---
title: Översikt över bokföringsprofiler
description: Det här ämnet beskriver hur bokföringsprofiler används i Microsoft Dynamics 365 program.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4c29597155e525638e7c2ded7d641017f2189c49
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734588"
---
# <a name="posting-profiles-overview"></a>Översikt över bokföringsprofiler

I Ekonomi och Drift-appar används termen *bokföringsprofiler* för att beskriva konfigurationerna som styr hur redovisningskonton konverteras till huvudkonton så att de kan användas i transaktioner som bokförs i redovisningen. De kontrollerar till exempel hur kunden konverteras till ett huvudkonto i Kundreskontra när en faktura bokförs.

I vissa moduler och funktioner finns en sida som innehåller orden "bokföringsprofil" i namnet (till exempel **kundbokföringsprofil** eller **leverantörsbokföringsprofil**).  Dessutom har vissa moduler flera alternativ för att konfigurera redovisningsbokföring för transaktioner som genereras från redovisningen. I modulen **Produktionskontroll** kan du till exempel ställa in bokföringen efter produktionsgrupp, resurs eller resursgrupp.

Observera att det för många typer av transaktioner finns ett alternativ till bokföringsprofiler: bokföringsdefinitioner. För dokument som stöds kan du använda bokföringsdefinitioner i stället för bokföringsprofiler för att klassificera huvudkontona och ekonomiska dimensioner på redovisningsposter. Om du tänker använda inteckning eller förinteckningar måste en bokföringsdefinition definiera kontona för redovisningsposterna.

Innan du kan konfigurera bokföringsprofiler, bokföringsdefinitioner eller sidan **Konton för automatiska transaktioner** måste du konfigurera kontoplanen på sidan **Redovisning** i den juridiska person som du vill konfigurera.

## <a name="posting-types"></a>Bokföringstyper

I Ekonomi och Drift-appar används en bokföringstyp för att definiera en allmän kategori för debet eller kredit. Denna kategori är oberoende av huvudkontot i redovisningen. Det finns bokföringstyper för varje debet eller kredit i redovisningen.

En och samma verifikation kan ha en eller flera bokföringstyper. En transaktion som till exempel bokförs via en allmän journal där kontot och motkontot är inställt på **Redovisning** kommer att ha bokföringstypen **Redovisningsjournal** för både debet och kredit. En leverantörsfaktura kommer däremot att ha flera bokföringstyper. Dessa bokföringstyper kommer att innehålla en rad för leverantörssaldot och ytterligare rader för motposten, t.ex. **redovisningsjournal**.

Du kan visa bokföringstypen i fältet **Bokföringstyp** på fliken **Allmänt** på sidan **Verifikationstransaktioner**.

> [!TIP]
> Med verktygsfältet **Personanpassning** kan du lägga till fältet **Bokföringstyp** i rutnätet på fliken **Översikt**, eller flytta det. På det här sättet kan du göra det här fältet enklare att komma åt eller visa när du visar verifikationer.

## <a name="detail-settings-for-a-posting-profile"></a>Detaljinställningar för en inläggsprofil 

När du konfigurerar bokföringsprofiler definierar fältet **kontokod** nivån på inställningen. Följande alternativ är tillgängliga: **Tabell**, **Grupp** och **Alla**. Matchningen avslutas efter den första matchningen och ordern kommer från den mest specifika nivån till den minst specifika nivån. Även om fältet **kontokod** har något andra namn är det i vissa fall fortfarande fältets beteende och funktion. Lagerbokföringsprofilen innehåller till exempel ett fält för **artikelkod** och ett fält för **kontokod**. Båda fälten har **Tabell**, **Grupp** och **All** värden.

Om fältet **huvudkonto** lämnas tomt för en bokföringsprofil och du inte har konfigurerat ett huvudkonto på sidan **konton för automatisk transaktion** eller på en modulspecifik eller funktionsspecifik sida visas ett felmeddelande när du bokför en transaktion som använder bokföringstypen.  Vanligtvis visas meddelandet "Kontot för \[bokföringstyp\] går inte att hitta."

### <a name="table-value"></a>Registervärde

Värdet **Tabell** hänvisar till huvudposten som är kopplad till bokföringsprofilen. Varje registerpost är specifik för ett värde. Du anger det värdet i fältet som visas efter fältet **kontokod**. Det här fältet kallas vanligtvis **konto** eller **konto/gruppnummer**. Det exakta namnet varierar beroende på vilken sida där det visas.

Om du till exempel arbetar med en kundbokföringsprofil representerar värdet **tabell** en viss kund. Om du väljer **Tabell** i fältet **Kontokod** ska du markera kundnumret i fältet **Konto/gruppnummer**.

Värdet **Tabell** representerar den mest specifika posttypen. Systemet använder alltid det här värdet, även om du har konfigurerat en annan post där värdet **Grupp** eller **Alla** har valts. Det här värdet åsidosätter även eventuella värden som du skapat som standardvärden på sidan **Konton för automatiska transaktioner**.

Du bör inte använda värdet **Tabell** som primär mekanism för hantering av bokföringsprofiler, eftersom datakvalitetsproblem kan uppstå om en separat bokföringsprofil underhålls för varje huvuddatapost. Det är också svårt att underhålla och stämma av en separat bokföringsprofil för varje huvuddatapost. Istället ska detta värde användas för att hantera undantag i dina bokföringsprofiler.

### <a name="group-value"></a>Gruppvärde

Värdet **Grupp** hänvisar till grupperingsposten som stöds av masterposten som är associerad med bokföringsprofilen. Varje gruppost är specifik för ett värde. Du anger det värdet i fältet som visas efter fältet **kontokod**. Det här fältet kallas vanligtvis **konto** eller **konto/gruppnummer**. Det exakta namnet varierar beroende på vilken sida där det visas.

Värdet **Grupp** kräver att du först konfigurerar en grupp och länkar den till en eller flera poster för kontot. Värdet **Grupp** är mindre specifikt än värdet **Tabell** men mer specifikt än värdet **Alla**. Om ingen post har konfigurerats för en tabell görs ett försök i systemet att hitta en post för den grupp som posten tillhör.

Om du till exempel arbetar med en kundbokföringsprofil och väljer **Grupp** i fältet **Kontokod** måste du välja en kundgrupp i fältet **Konto-/gruppnummer**. Du måste fördefiniera kundgrupperna på sidan **Kundgrupp**, och du måste ange en kundgrupp när du skapar en kund.

Om du måste spåra flera huvudkonton för en viss bokföringstyp rekommenderar vi att du använder värdet **Grupp**. Du har till exempel tre huvudkonton för kundreskontra: en för vanliga kunder, en för anställda och en för koncernintern försäljning. I detta fall rekommenderar vi att du skapar tre kundgrupper för att segmentera kunderna. Mappa sedan varje kundgrupp till rätt huvudkonto i kundbokföringsprofilen. Följande tabell visar de tre kundgrupperna för detta exempel.

| Kundgrupp | Namn | Beskrivning |
|----------------|------|-------------|
| EXT | Extern kund | Denna grupp används för alla externa standardkunder. |
| EMP | Medarbetare | Denna grupp används för alla medarbetare som gör inköp från din organisation. |
| INT | Koncernintern försäljning | Denna grupp används för alla koncerninterna kundkonton som används med integration av försäljnings- och inköpsorder. |

I bokföringsprofilen kommer du sedan att ställa in tre rader. På varje rad väljer du värdet **grupp** och relaterat huvudkonto.

### <a name="all-value"></a>Alla värden

**Alla** värden anger att inställningarna gäller för alla poster. Om du väljer värdet **Alla** i fältet **Kontokod** är fältet **Konto/Gruppnummer** inte tillgängligt och du kan inte välja en specifik post som konfigurationen ska tillämpas på.

Värdet **Alla** är det minst specifika värdet. Den används bara om systemet inte kan hitta en matchning av värdet **tabell** eller **grupp**. Du bör välja värdet **Alla** om du bara har ett huvudkonto för en viss bokföringstyp.

När du till exempel arbetar med en kundbokföringsprofil, gäller de huvudkonton som du anger för alla andra kunder och kundgrupper som inte har någon post för ett specifikt register (kund) eller grupp (kundgrupp).

### <a name="category"></a>Kategori

Lagerbokföringsprofiler har ett extra värde som är specifikt för försäljningskategorin eller anskaffningskategorin. Det här värdet liknar värdet **tabell** så att det bara gäller en viss försäljnings- eller anskaffningskategori.

### <a name="default-value"></a>Standardvärde

Om du inte skapar en post för en bokföringstyp i en bokföringsprofil där fältet **kontokod** fältet är inställt på **Alla** och systemet inte kan hitta en matchande bokföringsprofilpost för värdet för **Grupp** eller **Tabell**, återgår systemet till standardvärdet som kan anges på sidan **Konton för automatisk transaktion**. Mer information finns i [Konton för automatiska transaktioner](accounts-for-auto-transactions.md).

## <a name="clearing-accounts"></a>Clearingkonton

Termen *clearingkonto* används ofta i redovisningen. Vissa bokföringstyper i Microsoft Dynamics 365-program är clearingkonton. Med andra ord raderas eller återförs saldot på kontot när en annan transaktion bokförs. När du till exempel bokför en inleverans av en inköpsorderprodukt bokförs summan av de uppskattade kostnaderna för produkterna plus moms och eventuella tillägg på inköpsorderraderna i bokföringstypen för inköps periodisering som en skuld. När du senare fakturerar inköpsordern återförs saldot från bokföringstypen för inköpsperiodisering och flyttas till leverantörsreskontrakontot.

## <a name="additional-resources"></a>Ytterligare resurser

Många moduler i Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce och Dynamics 365 Project Operations har en bokföringsprofil eller ytterligare konfigurationer som styr hur bokföring i redovisningen fungerar. Använd följande avsnitt om du vill veta mer om bokföringsprofiler och bokföringsinställningar i varje modul:

- [Konton för automatiska transaktioner](accounts-for-auto-transactions.md)
- [Bokföring av leverantörsreskontra](accts-payble-posting.md)
- [Bokföring av kundreskontra](accts-recvble-posting.md)
- [Bokföring av tillgångsleasing](../asset-leasing/set-up-lease-posting-accts.md)
- Bokföring av tillgångshantering (kommer snart)
- Parametrar för kassa- och bankhantering (kommer snart)
- Bokföringskonton för valutaomvärdering (kommer snart)
- Bokföring av utläggshantering (kommer snart)
- [Bokföringsprofil för anläggningstillgång](../fixed-assets/tasks/set-up-fixed-asset-posting-profiles.md)
- Bokföring av koncernintern redovisning (kommer snart)
- Bokföringsprofil för lager (kommer snart)
- [Bokföring av hemtagningskostnader](../../supply-chain/landed-cost/costing-parameters-setup.md)
- [Översikt av bokföringsdefinitioner](posting-definitions.md)
- Bokföring av produktionskontroll (kommer snart)
- Bokföring av projekthantering och redovisning (kommer snart)
- Bokföring av tjänsthantering (kommer snart)
- Momsbokföring (kommer snart)
- Tids- och närvarobokföring (kommer snart)
- Bokföring av transporthantering (kommer snart)
- Bokföringsprofiler för rabatthantering (kommer snart)
