---
title: Prissimulering
description: Det här avsnittet innehåller information om prissimulering för offerter. Prissimulering hjälper dig att utvärdera effekten av avdrag på det framtida försäljningspriset under offertprocessen innan du på fastställer ett specifikt pris.
author: omulvad
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesQuotationPriceSimulation
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 12254
ms.assetid: 92be7c85-73cf-4f77-833c-d37ce779a031
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fe8c4bc8f2efb06de4cb6fd727df93ba1a5d14bf
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251361"
---
# <a name="price-simulation"></a>Prissimulering

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om prissimulering för offerter. Prissimulering hjälper dig att utvärdera effekten av avdrag på det framtida försäljningspriset under offertprocessen innan du på fastställer ett specifikt pris.

En prissimulering för en offert visar ett nytt totalbelopp baserat på ett föreslaget nytt pris. En prissimulering kan också visa ett nytt belopp för en specifik rad som skapas i en befintlig offert. Du kan ange en prissimulering och använda den senare. Du kan också använda den ursprungliga offerten utan en prissimulering och göra fler ändringar när du går igenom försäljningsprocessen med din kund.  

En prissimulering ändrar inte priset i offerten. Om prissimuleringen används på en hel offert behandlas den som en särskild rabatt i offerthuvudet. Om prissimuleringen används på specifika artiklar behandlas den som en särskild rabatt på offertraderna. Enhetsförsäljningspriset på offertraden som skapas ändrar inte när en prissimulering används. I stället används en rabattprocent som motsvarar prisminskningen för offertraden. När en prissimulering används överförs enhetsförsäljningspriset och rabattprocenten till offertraden eller offerthuvudet.  

>Obs! När du kör en prissimulering används bara den aktuella försäljningsvalutan för att skapa simuleringen. Du kan emellertid visa en kombination av företagsvalutan och försäljningsvalutan när du visar offertsummorna.  

Fyllnadsartiklar som läggs till på offertrader kan utlösa radrabatter och flerradsrabatter. De kan också utlösa totala rabatter som ändrar täckningsbidraget och täckningsgraden på offertraderna och hela rabatten.  

Du kan köra flera prissimuleringar om du vill följa upp effekterna av prisjusteringar på offertens mål. Om du kör dessa simuleringar kan du justera det generella priset för offerten eller priset på en eller flera specifika rader i offerten, och sedan använda den lämpligaste prissimuleringen.  

Du kan ställa in en notifiering när du skapar en offert. Här är exempel på hur aviseringar används:

-   De kan hålla dig informerad om statusen för offerter i organisationen.
-   De kan utlösa en granskning av en viss offert eller informera dig när rabattgränserna överskrids.

## <a name="price-simulation-and-discounts"></a>Prissimulering och rabatter
Var försiktig när du kör prissimuleringar på offerter som har rabatter så att priser och rabatter beräknas korrekt. Eftersom alla prissimuleringar behandlas som specialrabatter på den aktiva offertraden eller på hela offerten är det viktigt att spåra skillnaderna för rabatterna.

### <a name="types-of-discounts-in-trade-agreements"></a>Typer av rabatter i handelsavtal

Handelsavtalen i Supply Chain Management kan ha fyra typer av prisrabatter. Rabatterna kan anges för olika artiklar, kunder eller prisgrupper och de kan begränsas efter datum. För att undvika felberäkningar måste du ta hänsyn till handelsavtal när du kör prissimuleringar. Här är de fyra rabattyperna i handelsavtal:

-   **Försäljningspris** – Olika försäljningspriser kan anges för artiklar. När offertrader skapas söker programmet efter rätt försäljningspris för en artikel och överför det till offertraderna. Därför påverkar ett handelsavtal som har den här typen av rabatt inte prissimuleringen. Försäljningspriset som används på offertraden återspeglar handelsavtalet.
-   **Radrabatt** – Särskilda rabatter anges för artiklar, beroende på den beställda kvantiteten. Radbelopp reduceras normalt med radrabatten innan en prissimulering körs. Därför påverkar ett handelsavtal som har den här typen av rabatt prissimuleringen.
-   **Samköpsrabatt** – Om de kombinerade summorna överskrider den gräns som du har definierat, utlöser fördefinierade kombinationer av beställda artiklar en rabatt för hela ordern. Radbelopp reduceras normalt med radrabatten innan en prissimulering körs. Därför påverkar ett handelsavtal som har den här typen av rabatt prissimuleringen.
-   **Total rabatt** – Om de kombinerade summorna överskrider den gräns som du har definierat, utlöser fördefinierade beställda artiklar en rabatt för hela ordern. Totalrabatten genereras via offertraderna. Men eftersom den totala rabatten tillämpas på offertsumman som en rabatt minskar den det totala beloppet för offerten. Därför påverkar ett handelsavtal som har den här typen av rabatt prissimuleringen.

### <a name="quotation-lines-and-trade-agreements"></a>Offertrader och handelsavtal

När du skapar eller anpassar en offertrad beräknas radrabatterna automatiskt. Det relevanta försäljningspriset hittas för artikeln, baserat på handelsavtalet.

## <a name="price-simulation-examples"></a>Prissimuleringsexempel
I följande exempel används prissimulering för offerthuvuden och artiklar på enskilda rader.

### <a name="price-simulation-for-quotation-headers"></a>Prissimulering för offerthuvuden

Du skapar en offert med följande rader:

-   10 enheter av artikel BR-12 (kostnadspris per enhet: 9,52 USD och försäljningspris per enhet: 15,32 USD).
-   12 enheter av artikel BR-14 (kostnadspris per enhet: 7,48 USD och försäljningspris per enhet: 13,75 USD).

Följande tabell visar offertraderna.

|                            | Beräkning                          | Resultat   |
|----------------------------|--------------------------------------|----------|
| Försäljningskvantitet             | 10 enheter + 12 enheter                  | 22 enheter |
| Försäljningsvärde i USD         | (10 × 15,32) + (12 × 13,75)          | 318,20   |
| Kostnadsvärde i USD          | (10 × 9,52) + (12 × 7,48)            | 184,96   |
| Täckningsbidrag i USD | 318,20 – 184,96                      | 133,24   |
| Täckningsgrad         | (\[318.20 – 184.96\] ÷ 318.20) × 100 | 41,87 %   |

Du kör en prissimulering och tillämpar en totalrabatt på 15 procent för hela offerten eller offerthuvudet. Följande tabell visar de nya totalsummorna för offerten, efter prissimuleringen har körts.

|                                                      | Beräkning                               | Resultat   |
|------------------------------------------------------|-------------------------------------------|----------|
| Försäljningskvantitet                                       | 10 enheter + 12 enheter                       | 22 enheter |
| Gammalt försäljningsvärde i USD                               | (10 × 15,32) + (12 × 13,75)               | 318,20   |
| Gammalt kostnadsvärde i USD                                | (10 × 9,52) + (12 × 7,48)                 | 184,96   |
| Gammalt täckningsbidrag i USD                       | 318,20 – 184,96                           | 133,24   |
| Gammal täckningsgrad                               | (\[318.20 – (10 × 9.52)\] ÷ 318.20) × 100 | 41,87 %   |
| Prissimulering med 15 % total rabatt i USD | (15 × 318,2) ÷ 100                        | 47,73    |
| Nytt försäljningsvärde i USD                               | 318,20 – 47,73                            | 270,47   |
| Nytt täckningsbidrag i USD                       | 270,47 – 184,96                           | 85,51    |
| Ny täckningsgrad                               | \[(270.47 – 184.96) ÷ 270.47\] × 100      | 31,61 %   |

### <a name="price-simulation-for-single-line-items"></a>Prissimulering av artikel på enskild rad

Du skapar en offert med följande rader:

-   10 enheter av artikel BR-12 (kostnadspris per enhet: 9,52 USD och försäljningspris per enhet: 15,32 USD).
-   12 enheter av artikel BR-14 (kostnadspris per enhet: 7,48 USD och försäljningspris per enhet: 13,75 USD).

Följande tabell visar offertraderna.

|                                      | Beräkning                          | Resultat   |
|--------------------------------------|--------------------------------------|----------|
| Försäljningskvantitet                       | 10 enheter + 12 enheter                  | 22 enheter |
| Försäljningsvärde i USD för BR-12         | 10 × 15,32                           | 153,20   |
| Försäljningsvärde i USD för BR-14         | 12 × 13,75                           | 165,00   |
| Kostnadsvärde i USD för BR-12          | 10 × 9,52                            | 95,20    |
| Kostnadsvärde i USD för BR-14          | 12 × 7,48                            | 89,76    |
| Täckningsbidrag i USD för BR-12 | 153,20 – 95,20                       | 58,00    |
| Täckningsbidrag i USD för BR-14 | 165,00 – 89,76                       | 75,24    |
| Täckningsgrad i USD för BR-12  | \[(153.20 – 95.20) ÷ 153.20\] × 100  | 37,86    |
| Täckningsgrad i USD för BR-14  | \[(165.00 – 89.76) ÷ 165.00\] × 100  | 45,60    |
| Totalt försäljningsvärde i USD             | (10 × 15,32) + (12 × 13,75)          | 318,20   |
| Totalt kostnadsvärde i USD              | (10 × 9,52) + (12 × 7,48)            | 184,96   |
| Totalt täckningsbidrag i USD     | 318,20 – 184,96                      | 133,24   |
| Total täckningsgrad             | \[(318.20 – 184.96) ÷ 318.20\] × 100 | 41,87 %   |

Du kör en prissimulering och tillämpar en 10 procent totalrabatt till enheter BR-12. Följande tabell visar de nya totalsummorna för offerten, efter prissimuleringen har körts för artikel på enskild rad.

|                                                   | Beräkning                             | Resultat   |
|---------------------------------------------------|-----------------------------------------|----------|
| Försäljningskvantitet                                    | 10 enheter + 12 enheter                     | 22 enheter |
| Gammalt försäljningsvärde i USD för BR-12                  | 10 × 15,32                              | 153,20   |
| Prissimulering med 10 % rabatt för BR-12 | (10 × 153,2) ÷ 100                      | 15,32    |
| Nytt försäljningsvärde i USD för BR-12                  | (10 × 15,32) – 15,32                    | 137,88   |
| Försäljningsvärde i USD för BR-14                      | 12 × 13,75                              | 165,00   |
| Kostnadsvärde i USD för BR-12                       | 10 × 9,52                               | 95,20    |
| Kostnadsvärde i USD för BR-14                       | 12 × 7,48                               | 89,76    |
| Nytt täckningsbidrag i USD för BR-12          | 137,88 – 95,20                          | 42,68    |
| Täckningsbidrag i USD för BR-14              | 165,00 – 89,76                          | 75,24    |
| Ny täckningsgrad i USD för BR-12           | \[(137.88 – 95.20) ÷ 137.88\] × 100     | 30,95    |
| Täckningsgrad i USD för BR-14               | \[(165.00 – 89.76) ÷ 165.00\] × 100     | 45,60    |
| Nytt totalt försäljningsvärde i USD                      | \[(10 × 15.32) – 15.32\] + (12 × 13.75) | 302,88   |
| Totalt kostnadsvärde i USD                           | (10 × 9,52) + (12 × 7,48)               | 184,96   |
| Nytt totalt täckningsbidrag i USD              | 302,88 – 184,96                         | 117,92   |
| Ny total täckningsgrad                      | \[(302.88 – 184.96) ÷ 302.88\] × 100    | 38,93 %   |

Prissimuleringen påverkar enbart raden som den tillämpas på och minskar summan för den raden.



