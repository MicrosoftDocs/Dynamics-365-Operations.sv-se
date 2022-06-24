---
title: Bokföring av produktionsorder
description: Det här ämnet innehåller information om andra typer av bokföringar i produktionsorder.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, ProjCategory, CostSheetDesigner
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: d41725325a82b24c1e5aa6bd2c1a5322f3078ace
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879636"
---
# <a name="production-postings"></a>Produktionsbokföringar

Det här ämnet innehåller information om andra typer av bokföring i produktionsorderprocessen.


## <a name="material-consumption"></a>Materialförbrukning

Material registreras som förbrukade under produktionen, när produktionens plocklistejournal bokförs. Detta skapar transaktioner som drar av lagerbehållningen. I **Produktionsparametrar** kan du ange om värdet av råmaterial som pågår produkter i arbete (kallad PIA), ska bokföras i redovisningen.

Värdet av råmaterial som pågår (PIA) bokförs på kontona **Uppskattad kostnad för förbrukat material** och **Uppskattad kostnad för förbrukat material, PIA**. Plocklisteprocessen för tillverkningsordern är en fysisk uppdatering av lagertransaktionerna som hör till tillverkningsordern. När en tillverkningsorder registreras som avslutad återförs de fysiska transaktionerna och relaterade lagertransaktioner uppdateras ekonomiskt. När slutjournalen bokförs används bokföringstyperna **Kostnad för förbrukat material** och **Kostnad för förbrukat material, PIA**.

Fliken **Produktion** på sidan **Lagerbokföringsprofiler** används för att styra hur produktionsorder bokförs i redovisningen. Detta används när fältet **Redovisning** ställs in på antingen **Artikel och resurs** eller **Artikel och kategori** på sidan **Produktionskontrollparametrar**. 

För att en plocklistejournal ska bokföras i redovisningen för en produktionsorder måste följande villkor uppfyllas:

-   Kryssrutan **Bokför plocklista i redovisningsmodulen** måste väljas på sidan **Produktionskontrollparametrar**. Den här inställningen kan åsidosättas för en specifik webbplats på sidan **Produktionskontrollparametrar per site**.
-   Kryssrutan **Bokför fysiskt lager** måste markeras på sidan **Artikelmodellgrupper** för den artikel som valts på inköpsorderraden.
-   Huvudkontona måste anges på sidan **Lagerbokföringsprofil** för följande bokföringstyper:
    -   **Uppskattad kostnad för förbrukat material**
    -   **Uppskattad kostnad för förbrukat material, PIA**

## <a name="time-consumption"></a>Tidsförbrukning

Den tid som arbetare spenderar på produktionsjobb registreras i **flödeskortjournalen** eller i **jobbkortjournalen**. När dessa journaler bokförs bearbetas redovisningsbokföringen till ett dedikerat konto för resurser som pågår (PIA). Denna bokföring representerar värdet av den tid som har använts för produktionsordern. När produktionsordern har registrerats som avslutad kvittas PIA-kontona.

Det finns tre sätt att bokföra tidsförbrukning beroende på alternativet som valts i fältet **Redovisningsbokföring** på sidan **Produktionskontrollparametrar**.

## <a name="reporting-finished-goods-and-error-quantities"></a>Rapportera färdiga varor och felkvantiteter

När en produktionsorder är **Rapporterat som färdigt**, de färdigvaror som är färdigställda uppdateras i inventariet genom journalen **Rapportera som avslutad**. Om du använder PIA-redovisning bokförs en redovisningsjournal för att minska PIA-kontona och öka lagret av färdiga varor. Journalen använder standardkostnaden som definierats för produkten. Om alternativet **Använd uppskattad självkostnad** har valts på sidan **Produktionskontrollparametrar** används den uppskattade kostnaden från tillverkningsordern.

Värdet av råmaterial som pågår (PIA) bokförs på kontona **Uppskattad tillverkningskostnad** och **Uppskattad tillverkningskostnad, PIA**. Processen **Rapportera som avslutad** för tillverkningsordern är en fysisk uppdatering av lagertransaktionerna som hör till tillverkningsordern. När en tillverkningsorder avslutas återförs de fysiska transaktionerna och relaterade lagertransaktioner uppdateras ekonomiskt. När slutjournalen bokförs används bokföringstyperna **Tillverkningskostnad** och **Tillverkningskostnad, PIA**.

Fliken **Produktion** på sidan **Lagerbokföringsprofiler** används för att styra hur produktionsorder bokförs i redovisningen. Detta används när fältet **Redovisning** ställs in på antingen **Artikel och resurs** eller **Artikel och kategori** på sidan **Produktionskontrollparametrar**. På snabbflikarna **Redovisningsartiklar** på sidan **Produktionsgrupper** kan du också kontrollera bokföringen av tillverkningsorder när fältet är inställt på **Produktionsgrupper**.

För att en journal för **Rapportera som slutförd** ska bokföras i redovisningen för en produktionsorder måste följande villkor uppfyllas:
-   Kryssrutan **Bokför rapport som klar i redovisningen** måste väljas på sidan **Produktionskontrollparametrar**. Den här inställningen kan åsidosättas för en specifik webbplats på sidan **Produktionskontrollparametrar per site**.
-   Kryssrutan **Bokför fysiskt lager** måste markeras på sidan **Artikelmodellgrupper** för den artikel som valts på inköpsorderraden.
-   Huvudkontona måste anges på sidan **Lagerbokföringsprofil** för följande bokföringstyper:
    -   **Uppskattad tillverkningskostnad**
    -   **Uppskattad tillverkningskostnad, PIA**

## <a name="ending-the-production-order"></a>Avsluta produktionsordern

Innan en produktionsorder avslutas beräknas faktiska kostnader för den kvantitet som producerats. Alla uppskattade kostnader för material, arbete och omkostnader återställs och ersätts med faktiska kostnader. Den sammanlagda kostnaden för den färdiga artikeln debiteras kontot **Tillverkningskostnad** och krediteras kontot **Tillverkningskostnad, PIA**. Materialet som förbrukades under produktionsordern krediteras till **Kostnad för förbrukat material** och debiteras kontot **Kostnad för material, PIA**.

Om du markerar kryssrutan **Avsluta jobb** när du kör kostnadsberäkningen, ändras produktionsorderns status till **Avslutad**. Denna status förhindrar att ytterligare kostnader oavsiktligt bokförs på en slutförd produktionsorder. Du kan ange att värdet för antal fel som rapporteras som färdigt ska fördelas till de goda kvantiteterna som rapporteras som färdiga. Alternativt kan du ange att värdet av felkvantiteter ska bokföras på ett dedikerat kassationskonto. 

Följ dessa steg för att ange ett specifikt kassationskonto:
1.  Gå till **Produktionskontroll** > **Inställningar** > **Produktionskontrollparametrar**.
2.  Välj fliken **Standarduppdatering**.
3.  I fältet **Kassationsmetod**, välj **Kassationskonto**.
4.  Välj huvudkontot i fältet **Kassationskonto** där kassation för felkvantitet ska bokföras när tillverkningsordern avslutas. Välj till exempel ett utgiftskonto som 510380: Kassationsmetod.

För att en slutjournal ska bokföras i redovisningen för en produktionsorder måste följande villkor uppfyllas:
-   Huvudkontona måste anges på sidan **Lagerbokföringsprofil** eller **Produktionsgrupper** för följande bokföringstyper:
    -   **Kostnad för förbrukat material**
    -   **Kostnad för förbrukat material, PIA**
    -   **Tillverkningskostnad**
    -   **Tillverkningskostnad, PIA**
-   Huvudkontona måste anges på sidan **Kostnadskategorier**, **Resurser** eller **Resursgrupper** för följande typer:
    -   **Tillverkningskostnad som förbrukats**
    -   **Kostnad för förbrukad tillverkning, PIA**

## <a name="indirect-costs-for-production-orders"></a>Indirekta kostnader för tillverkningsorder

När du bearbetar transaktioner för en tillverkningsorder kan du konfigurera indirekta kostnader så att du kan fånga in omkostnader eller ytterligare avgifter i redovisningen. Fysiska transaktioner för indirekta kostnader redovisas i lagret när du bokför en plocklistejournal eller rapporterar som färdig journal. Ekonomiska transaktioner för indirekta kostnader redovisas i lagret när du bokför slutjournalen.

Du kan känna igen indirekta kostnader på tidsförbrukningen som är relaterad till journaler för **Flödeskort** eller journaler för **Jobbkort**. Dessa transaktioner återförs och bokförs till de ekonomiska kontona när du avslutar tillverkningsordern. Mer information finns i [Kostnadsredovisningar](/supply-chain/cost-management/costing-sheets.md).

## <a name="controlling-the-level-of-ledger-posting"></a>Kontrollera nivån för redovisningsbokföring

På sidan **Produktionkontrollparametrar** kan du använda fältet **Redovisningsbokföring** för att ange nivån för redovisningsbokföring för produktionsprocesserna. 

Följande fält är tillgängliga:

### <a name="item-and-resource"></a>Artikel och resurs

När du väljer alternativet **Artikel och resurs** i fältet **Redovisningsbokföring** kommer bokföringskontona från resursen eller resursgruppen som finns i operationen i flödet. Konton för den specifika resursen är det första bokföringsalternativet. Om en konto inte angetts kommer de konton som angetts för resursgruppen att användas. Varje operationsrad i ett flöde kan ha en resurs angiven som **kostnadsredovisningsresurs**. Den här resursen används för att avgöra vilket konto som ska användas. Det här alternativet används ofta när en organisation tilldelar driftskostnader till resurserna. Kostnaderna är ofta högre för resurserna och används för att fatta beslut om att "göra eller köpa". Detta är den mest detaljerade bokföringskonfigurationen och gör det möjligt att styra bokföringarna och göra mycket detaljerade analyser av produktionsprocessen.

### <a name="item-and-category"></a>Artikel och kategori

När du väljer alternativet **Artikel och kategori** i fältet **Redovisningsbokföring** kommer bokföringskontona från sidan **kostnadskategori** som hör till respektive rad i flödet. Varje operationsrad i flödet kan ha tre kostnadskategorier: **Konfigurera** tid, **Kör** tid och **Kvantitet**. Det här alternativet används vanligtvis när företagets huvudfokus ligger på processeffektivitet och tidslängd för aktiviteten. Det här alternativet är en mer sammanfattad bokföringsväg och utgör fortfarande ett sätt att gruppera kostnader i kategorier.

### <a name="production-group"></a>Produktionsgrupp

När du väljer alternativet **Produktionsgrupper** i fältet **Redovisningsbokföring** kommer bokföringskontona från sidan **Produktionsgrupper**. **Produktionsgrupper** används vanligtvis när fler än en produktionsrad kör liknande produkter eller har liknande utrustning. Du kan använda det här alternativet för att jämföra kostnaderna mellan två olika produktionsgrupper.  
  
> [!NOTE]
> Om standardmetoden för att beräkna kostnaden för den färdiga artikeln användes reflekterar de slutliga transaktionerna denna fakta. Om de faktiska kostnaderna och de kostnader som beräknas med hjälp av standardmetoden skiljer sig, kommer mellanskillnaden att bokföras på det konto som visar vinst eller förlust.

### <a name="route-groups-and-ledger-posting"></a>Flödesgrupper och redovisning

Varje operationsrad i ett flöde har en **flödesgrupp** angiven. Fälten **Ställtid**, **Körtid** och **Kvantitet** i **Flödesgrupp** i gruppen **Uppskattning och kostnadsredovisning** används för att styra om tiden kommer att användas för beräkning vid bokföring **Jobbkort** eller **Flödeskortjournal** på tillverkningsordern. Om alternativen är inaktiverade, skapas ingen verifikation i redovisningen för tidsförbrukningen.

För en **Flödeskort** eller **Jobbkortjournal** för att bokföra till huvudboken för en produktionsorder måste följande villkor vara uppfyllda:

-   Fältet **Ställtid**, **Körtid** eller **Kvantitet** måste väljas i gruppen **Uppskattning och kostnadsredovisning** på sidan **Flödesgrupp**.
-   Huvudkontona måste anges i antingen **Kostnadskategori**, **Flöde**, **Flödesgrupp** eller **Produktionsgrupper** för följande bokföringstyper:
    -   Beräknad tillverkningskostnad som förbrukats
    -   Uppskattad kostnad för förbrukad tillverkning, PIA

I bilden nedan visas flödesgruppens relation till beräkningen av den totala kostnaden för varje operation (flödesrad) i ett givet flöde. Varje flödesrad har en flödesgrupp. Flödesgruppen kontrollerar parametrar för ställt tid, körtid och kvantitet. Fliken **Kostnadskategori** har tre alternativ för **Inställningar**, **Kör** och **Kvantitet** som är aktiverade baserat på inställningen för flödesgrupper. På snabbfliken **Tidsinställning** finns tre fält som baseras på flödesgruppen.

Formeln som används baseras på om alternativet är aktiverat i flödesgruppen. Kostnaden från den valda kostnadskategorin multipliceras med den kvantitet som angavs i tidmätningarna för att beräkna den totala kostnaden.

:::image type="complex" source="media/RouteGroupRelationship.png" alt-text="Flödesgruppernas relation till den totala beräknade kostnaden.":::
Flödesgruppernas relation till den totala beräknade kostnaden. Varje flödesrad har en flödesgrupp. Flödesgruppen kontrollerar parametrar för ställt tid, körtid och kvantitet. Fliken Kostnadskategori har tre alternativ för Inställningar, Kör och Kvantitet som är aktiverade baserat på inställningen för flödesgrupper. På snabbfliken Tidsinställning finns tre fält som är aktiverade och kostnadsberäknade baserade på flödesgruppen. Formeln som används baseras på om alternativet är aktiverat i flödesgruppen. Kostnaden från den valda kostnadskategorin multipliceras med den kvantitet som angavs i tidmätningarna för att beräkna den totala kostnaden.
:::image-end:::

## <a name="sample-posting-profile-configuration"></a>Exempel på konfiguration av bokföringsprofil

Följande tabell innehåller exempel på standardbokföringstyper med exempelhuvudkonton och beskrivningar. 

 - **Debet/kredit**-kolumnen anger om transaktionen vanligtvis debet- eller kredit, eller i vissa fall kan bokföra. 
 - Kolumnen **Clearingkonto** visar att bokföringstypen är ett clearingkonto. Beloppet som bokförs på detta konto återförs automatiskt när en senare transaktion bokförs. 
 - Kolumnen **P/F** (F/E) anger **P** för fysisk bokföring och **F** för ekonomisk bokföring. 
 - Kolumnen **Följ** visar om huvudkontot för en viss bokföringstyp normalt är samma som en annan bokföringstyp. Värdet i kolumnen visar den bokföringstyp som följs vanligtvis.

> [!NOTE]
> De föreslagna huvudkontona och huvudkontonamnen är bara förslag. Vi rekommenderar att du arbetar med revisorn för att avgöra vilken konfiguration som passar bäst för verksamheten.


| Bokföringstyp  | Huvudkonto exempel | Huvudkonto namnexempel| Kontotyp | Debit/kredit? | Clearingkonto | Fysisk eller ekonomisk | Följ | Beskrivning |
|---------------|----------------------|--------------------------|--------------|----------------|------------------|-----------------------|--------|------------|
| Uppskattad kostnad för förbrukat material      | 140100               | Materiallager        | Tillgång        | Kredit         | Y                | P                     | Kostnad för förbrukat material                | Det här kontot används när du bokför en plocklistejournal för en tillverkningsorder. Motbokningen till detta konto är den uppskattade materialkostnaden, PIA. Beloppet på detta konto återförs automatiskt när produktionsordern avslutas. Detta konto representerar lagerkontot i balansräkningen.       |
| Uppskattad kostnad för förbrukat material, PIA | 150150               | Produktions-PIA – Material | Tillgång        | Debet          | Y                | P                     | Uppskattad tillverkningskostnad, PIA          | Det här kontot används när du bokför en plocklistejournal för en tillverkningsorder. Motbokningen till detta konto är den uppskattade kostnaden för förbrukade material. Beloppet på detta konto återförs automatiskt när produktionsordern avslutas. Detta konto representerar PIA i balansräkningen.                  |
| Uppskattad tillverkningskostnad               | 140200               | Inventering av färdiga varor   | Tillgång        | Debet          | Y                | P                     | Tillverkningskostnad                         | Det här kontot används när du bokför en rapport som avslutad journal för en tillverkningsorder. Motbokningen till detta konto är Uppskattad tillverkningskostnad, PIA. Beloppet på detta konto återförs automatiskt när produktionsordern avslutas. Detta konto representerar lagerkontot i balansräkningen. |
| Uppskattad tillverkningskostnad, PIA          | 150150               | Produktions-PIA – Material | Tillgång        | Kredit         | Y                | P                     | Tillverkningskostnad, PIA                    | Det här kontot används när du bokför en rapport som avslutad journal för en tillverkningsorder. Motbokningen till detta konto är Uppskattad tillverkningskostnad. Beloppet på detta konto återförs automatiskt när produktionsordern avslutas. Detta konto representerar PIA i balansräkningen.                     |
| Kostnad för förbrukat material                | 140100               | Materiallager        | Tillgång        | Kredit         | N                 | F                     | Uppskattad kostnad för förbrukat material      | Detta konto används för att känna igen materialen som förbrukas på tillverkningsordern under slutprocessen. Motbokningen till detta konto är Kostnad för förbrukat material, PIA.                                                                                                    |
| Kostnad för förbrukat material, PIA           | 150150               | Produktions-PIA – Material | Tillgång        | Debet          | N                 | F                     | Uppskattad kostnad för förbrukat material, PIA | Detta konto används för att känna igen materialen i PIA som förbrukas på tillverkningsordern under slutprocessen. Motbokningen till detta konto är Kostnad för förbrukat material.                                                |
| Tillverkningskostnad                         | 140200               | Inventering av färdiga varor   | Tillgång        | Debet          | N                 | F                     | Uppskattad tillverkningskostnad               | Detta konto används för att redovisa kostnaden för den färdiga varan som produceras av en tillverkningsorder när du avslutar tillverkningsordern. Motbokningen till detta konto är tillverkningskostnad, PIA-konto.                                                                  |
| Tillverkningskostnad, PIA                    | 150150               | Produktions-PIA – Material | Tillgång        | Kredit         | N                 | F                     | Uppskattad tillverkningskostnad, PIA          | Detta konto används för att redovisa kostnaden för den färdiga varan i PIA som produceras av en tillverkningsorder när du avslutar tillverkningsordern. Motbokningen till detta konto är tillverkningskostnadskonto.                                     |

> [!NOTE]
> **PIA-inleverans Lean-tjänst** och **Lean-tjänst, PIA clearingkonto** används med kostnadskalkylering med automatisk lageravräkning för lean manufacturing. Mer information finns i [kostnadskalkylering med automatisk lageravräkning](/supply-chain/cost-management/backflush-costing.md).

