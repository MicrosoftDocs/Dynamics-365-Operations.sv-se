---
title: Hantering av kredit och inkasso Power BI-innehåll
description: Det här avsnittet beskriver vad som ingår i Power BI-innehållet för kredit- och inkassohantering. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som används för att skapa innehållet.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 5ac47ee086569cdaaa3c30f76435432e64f8fac6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189118"
---
# <a name="credit-and-collections-management-power-bi-content"></a>Hantering av kredit och inkasso Power BI-innehåll

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver vad som ingår i Power BI-innehållet för **kredit- och inkassohantering**. Det förklarar hur du öppnar Power BI-rapporter, och ger information om den datamodell och de enheter som användes för att skapa innehållet.

## <a name="overview"></a>Översikt

Power BI-innehållet för **kredit- och inkassohantering** har skapats för kredit- och inkassochefer och inkassopersonal. Det ger viktiga mått för kredit och inkasso som t.ex. dagar för dagar för utestående betalning, förfallet saldo, kreditexponering och kunder som överskrider sin kreditgräns. Det använder transaktionsdata och ger aggregerade vyer av kredit och inkasso över alla företag. Det innehåller även en uppdelning per kund, kundgrupp och företag.

Detta Power BI-innehåll består av 10 rapportsidor:

- Två översiktssidor (en sida för en kreditöversikt) och en sida för en inkassoöversikt
- Åtta detaljsidor ger information om kredit- och inkassomått är vrids och vänds över flera olika dimensioner.

Alla belopp i visas i systemvalutan. Du kan ange systemvalutan på sidan **Systemparametrar**.

Som standard visas kredit- och inkassodata för det aktuella företaget. Om du vill visa data för alla företag, tilldelar du programbehörigheten **CustCollectionsBICrossCompany** till rollen.

## <a name="setup-needed-to-view-power-bi-content"></a>Installationen som behövs för att visa Power BI-innehåll

Följande inställningar måste slutföras för att data ska visas i **Kundkredit och inkasso**Power BI-visualiseringar.

1. Gå till **systemadministrations > inställningar > systemparametrar** för att ställa in **Systemvaluta** och **Systemets valutakurs**.
2. Gå till **redovisning > Inställningar > redovisning** och ange **redovisningsvaluta** och **valutakurstyp**.
3. Definiera valutakurser mellan transaktionsvalutor och redovisningsvaluta, redovisningsvaluta och systemvaluta. Det gör du genom att gå till **redovisning > valutor > valutakurser**.
4. Gå till **Systemadministration > Inställningar > Enhetslagring** för att uppdatera sammanlagda måtten **CustCollectionsBIMeasurements**.

## <a name="accessing-the-power-bi-content"></a>Komma åt Power BI-innehåll

Power BI-innehållet för **Kredit- och inkassohantering** visas i arbetsytan **Kundkredit och kundinkasso**.

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

Diagrammen och rutorna i samtliga dessa rapporter kan filtreras och fästas på instrumentpanelen. Mer information om hur du filtrerar och fäster i Power BI, se [Skapa och konfigurera en instrumentpanel](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). Du kan också använda funktionen Exportera underliggande data för att exportera underliggande data som summerats i en visualisering.
