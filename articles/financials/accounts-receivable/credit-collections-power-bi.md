---
title: "Power BI innehållspaket för kredit- och inkassohantering"
description: "Det här avsnittet beskriver vad som ingår i Power BI-innehållet för kredit- och inkassohantering. Det förklarar hur du öppnar Power BI-rapporter och ger information datamodellen och de enheter som används för att skapa innehållet."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations. Core
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 6e64337f19600b18320550d91c134949c33af7b0
ms.openlocfilehash: 536ebae3ec44954aba314a966c9b0d2dabef45d1
ms.contentlocale: sv-se
ms.lasthandoff: 12/01/2017

---

# <a name="credit-and-collections-management-power-bi-content"></a>Power BI innehållspaket för kredit- och inkassohantering

Det här avsnittet beskriver vad som ingår i Power BI-innehållet för **kredit- och inkassohantering**. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.

## <a name="overview"></a>Översikt

Power BI-innehållet för **kredit- och inkassohantering** har skapats för kredit- och inkassochefer och inkassopersonal. Det ger viktiga mått för kredit och inkasso som t.ex. dagar för dagar för utestående betalning, förfallet saldo, kreditexponering och kunder som överskrider sin kreditgräns. Det använder transaktionsdata och ger aggregerade vyer av kredit och inkasso över alla företag. Det innehåller även en uppdelning per kund, kundgrupp och företag.

Detta Power BI-innehåll består av 10 rapportsidor:

- Två översiktssidor (en sida för en kreditöversikt) och en sida för en inkassoöversikt
- Åtta detaljsidor ger information om kredit- och inkassomått är vrids och vänds över flera olika dimensioner.

Alla belopp i visas i systemvalutan. Du kan ange systemvalutan på sidan **Systemparametrar**.

Som standard visas kredit- och inkassodata för det aktuella företaget. Om du vill visa data för alla företag, tilldelar du programbehörigheten **CustCollectionsBICrossCompany** till rollen.

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll
Power BI-innehållet **Kredit- och inkassohantering** visas i arbetsytan **Kundkredit och kundinkasso**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet

Power BI-innehållet **CustCollectionsBICrossCompany** innehåller ofta en rapport som består av en uppsättning mått. De här måtten visas som diagram, paneler och tabeller. Följande register ger en översikt över de visuella effekterna i Power BI-innehållet **CustCollectionsBICrossCompany**.

| Rapportsida                 | Visualisering |
|-----------------------------|---------------|
| Inkassoöversikt        | <ul><li>Förfallna kunder</li><li>Kundens över kreditgräns</li><li>DSO 30 dagar</li><li>Öppna ärenden</li><li>Genomsnittligt antal dagar till stängning av fall</li><li>Öppna aktiviteter</li><li>Genomsnittligt antal dagar till stängning av aktiviteter</li><li>Öppna räntefakturor</li><li>Öppna kravbrev</li><li>Kunden spärrad</li><li>Försäljning spärrad</li><li>Åldersfördelade saldon</li><li>Belopp för inkassostatus</li><li>Belopp för inkassokod</li><li>Orsak till avskrivning</li><li>Förfallet saldo efter region</li><li>Förväntad betalning</li></ul> |
| Kreditöversikt             | <ul><li>Förfallna kunder</li><li>Kreditgräns vs förfallet saldo</li><li>Rutnät för kunder över kreditgränsen</li><li>Kunder över kreditgräns per företag</li><li>Kredit som används kontra kreditgräns</li><li>Kreditgräns kontra kredit som används efter region</li><li>Kunder per kreditvärdighet</li></ul> |
| Kreditgräns                | <ul><li>Kreditgräns</li><li>Detaljer om kreditgräns</li><li>Kreditgräns per kund</li><li>Kreditgräns per kundgrupp</li><li>Kreditgräns per kreditvärdighet per företag</li><li>Kreditgräns kontra kredit som används efter region</li></ul> |
| Kundens över kreditgräns | <ul><li>Kundens över kreditgräns</li><li>Detaljer om kundens över kreditgräns</li><li>Kunder över kreditgräns per företag</li><li>Kunden över kreditgräns per kundgrupp</li><li>Kunder över kreditgräns efter region</li></ul> |
| Förfallna kunder          | <ul><li>Förfallna kunder</li><li>Detaljer om förfallna kunder</li><li>Förfallna kunder per företag</li><li>Förfallna kunder per kundgrupp</li><li>Förfallna kunder efter region</li></ul> |
| Åldersfördelade saldon               | <ul><li>Åldersfördelade saldon</li><li>Delajer för åldersfördelade kundsaldon</li><li>Åldersfördelade saldon per företag</li><li>Åldersfördelade saldon per kundgrupp</li></ul> |
| Förväntad betalning           | <ul><li>Förväntad betalning</li><li>Detaljer om förväntad betalning</li><li>Förväntade betalningar per företag</li><li>Förväntade betalningar per kundgrupp</li><li>Förväntade betalningar efter region</li></ul> |
| Avskrivningar                  | <ul><li>Avskrivningar per region</li><li>Detaljer om avskrivningar</li><li>Avskrivningar per huvudkonto</li><li>Avskrivningar per företag</li><li>Avskrivningar per kundgrupp</li><li>Avskrivningar per region</li></ul> |
| Kravstatus          | <ul><li>Omtvistat</li><li>Löfte om betalning brutet</li><li>Lova att betala</li><li>Detaljer om inkassostatus</li><li>Belopp för inkassostatus</li><li>Öppna ärenden</li><li>Öppna aktiviteter</li></ul> |
| Kravbrev         | <ul><li>Belopp för inkassokod</li><li>Detaljer om belopp för inkassokod</li><li>Belopp för kravbrev per företag</li><li>Belopp för kravbrev per kundgrupp</li><li>Belopp för kravbrev efter region</li></ul> |

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI finns i [Skapa och konfigurera en intrumentpanel](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Du kan också använda funktionen Exportera underliggande data för att exportera underliggande data som summerats i en visualisering.

## <a name="extending-the-power-bi-content"></a>Utöka Power BI-innehåll
Genom att använda innehållspaket som är tillgängliga i Microsoft Dynamics Lifecycle Services (LCS) kan du ge bra analyser till människor som inte är inloggade i Finance and Operations. Du kan ändra dessa innehållspaket så att de innehåller andra rapporter och modeller och publicera innehållspaket till din Power BI.com-innehavare för analys.

Du hittar Power BI-innehåll för **kredit- och inkassohantering** i det delade resursbiblioteket i LCS. Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](../../dev-itpro/analytics/power-bi-content-microsoft-partners.md). Om du vill se en demonstration som visar hur du implementerar Power BI-innehållet, se [Power BI-innehåll från Microsoft och dina samarbetspartners i Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office mix.

Hämta Power BI-innehållet för **kredit- och inkassohantering** som avser versionen av Finance and Operations som du använder.

## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

Följande data används för att fylla i rapportsidorna Power-Bi-innehållet **kredit- och inkassohantering**. Informationen visas som sammansatta mått som mellanlagras i Enhetslagring. Enhetslagring är en Microsoft SQL Server-databas som är optimerad för analys. Mer information finns i [Översikt för Power BI-integrering med enhetsarkiv](../../dev-itpro/analytics/power-bi-integration-entity-store.md).

| Enhet                                      | Sammanlagda huvudmått           | Datakälla                                 | Fält                                                      | beskrivning |
|---------------------------------------------|--------------------------------------|---------------------------------------------|------------------------------------------------------------|-------------|
| CustCollectionsBIActivitiesAverageCloseTime | NumOfActivities AveragecClosedTime  | smmActivities                               | AverageOfChildren(AverageClosedTime) Count(ActivityNumber) | Antal stängda aktiviteter och genomsnittlig tid för att avsluta dessa aktiviteter. |
| CustCollectionsBIActivitiesOpen             | ActivityNumber                       | smmActivities                               | Count(ActivityNumber)                                      | Antal öppna aktiviteter. |
| CustCollectionsBIAgedBalances               | AgedBalances                         | CustCollectionsBIAgedBalancesView           | Sum(SystemCurrencyBalance)                                 | Summan av förfallna saldon. |
| CustCollectionsBIBalancesDue                | SystemCurrencyAmount                 | CustCollectionsBIBalanceDueView             | Sum(SystemCurrencyAmount)                                  | De belopp som har förfallit. |
| CustCollectionsBICaseAverageCloseTIme       | NumOfCases, CaseAverageClosedTime    | CustCollectionsCaseDetail                   | AverageOfChildren(CaseAverageClosedTime) Count(NumOfCases) | Antal stängda fall och genomsnittlig tid för att avsluta dessa fall. |
| CustCollectionsBICasesOpen                  | CaseId                               | CustCollectionsCaseDetail                   | Count(CaseId)                                              | Antal öppna fall. |
| CustCollectionsBICollectionLetter           | CollectionLetterNum                  | CustCollectionLetterJour                    | Count(CollectionLetterNum)                                 | Antal öppna kravbrev. |
| CustCollectionsBICollectionLetterAmount     | CollectionLetterAmounts              | CustCollectionsBIAccountsReceivables        | Sum(SystemCurrencyAmount)                                  | Saldot på bokförda kravbrev. |
| CustCollectionsBICollectionStatus           | CollectionStatusAmounts              | CustCollectionsBIAccountsReceivables        | Sum(SystemCurrencyAmount)                                  | Saldot för transaktioner med kravbrevstatus. |
| CustCollectionsBICredit                     | CreditExposed AmountOverCreditLimit | CustCollectionsBICreditView                 | Sum(CreditExposed), Sum(AmountOverCreditLimit)             | Summan av kreditexponering och belopp som kunder överskridit kreditgränsen. |
| CustCollectionsBICustOnHold                 | Spärrad                              | CustCollectionsBICustTable                  | Count(Blocked)                                             | Antalet kunder som är spärrade. |
| CustCollectionsBIDSO                        | DSO30                                | CustCollectionsBIDSOView                    | AverageOfChildren(DSO30)                                   | Dagar för utestående försäljning för 30 dagar |
| CustCollectionsBIExpectedPayment            | ExpectedPayment                      | CustCollectionsBIExpectedPaymentView        | Sum(SystemCurrencyAmounts)                                 | Summan av förväntade betalningar inom ett år. |
| CustCollectionsBIInterestNote               | InterestNote                         | CustInterestJour                            | Count(InterestNote)                                        | Antalet räntefakturor som har skapats. |
| CustCollectionsBISalesOnHold                | SalesId                              | SalesTable                                  | Count(SalesId)                                             | Antalet totala försäljningsorder som är spärrade. |
| CustCollectionsBIWriteOff                   | WriteOffAmount                       | CustCollectionsBIWriteOffView               | Sum(SystemCurrencyAmount)                                  | Summan av transaktioner som har skrivits av. |

