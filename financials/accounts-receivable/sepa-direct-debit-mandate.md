---
title: "Ställa in SEPA Autogiromedgivande"
description: 
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 59491
ms.assetid: 653a135f-c515-4ae3-9da2-82b5e1f103b5
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 114dee90b0fe525f0b3efabbf651d2804a22dd7d
ms.openlocfilehash: bb835f8dad16938b56365c7b06d4a0228f9aba66
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-sepa-direct-debit-mandate"></a>Ställa in SEPA Autogiromedgivande



Ett SEPA-autogiro låter en fordringshavare ta ut medel från en kunds bankkonto, förutsatt att kunden har gett fordringshavaren en undertecknad fullmakt. Kunden undertecknar en fullmakt som auktoriserar fordringsägaren till att inkassera en betalning och instruerar kundens bank att betala inkasseringen. Det här avsnittet är ordnade till att visa processen för att skapa SEPA direktdebitering uppdrag.

## <a name="prerequisites"></a>Förutsättningar
Följande tabell visar förutsättningarna som krävs och måste finnas på plats innan du startar

| Kategori       | Förutsättning                                                                                                                                              |
|----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| Land/region | Den primära adressen för den juridiska personen måste vara i följande länder/regioner: Österrike, Belgien, Tyskland, Spanien, Frankrike, Italien eller Nederländerna. |

1. Ställ in en nummerserie för direktdebitering uppdrag varje uppdrag för direktdebitering måste ha ett unikt nummer. Använd sidan **Nummersekvenser** om du vill skapa en nummerserie för autogiromedgivanden. Du använder den här identifieraren för att tilldela nummerserien till systemet för autogiromedgivande på sidan **Parametrar för kundreskontra**.

2. Ställ in parametrar för kundreskontra för direktdebitering uppdrag används den **parametrar för kundreskontra** sidan om du vill ställa in parametrar för direktdebitering uppdrag. Du ställer in dessa parametrar i den **direktdebitering** ändra standardparametrar som du behöver. Klicka sedan på den **nummerserier** fliken och uppdatera de **ID för direktdebitering uppdrag** med den nummerserie som du skapade tidigare.

3. Ställa in en betalningsmetod för direktdebitering anger du måste ställa in en betalningsmetod för direktdebitering uppdrag. Du använder den här betalningsmetoden om du vill fråga efter fakturor som du vill generera autogirobetalningar för. Betalningsmetoden måste ställas in på sidan **Betalningsmetoder**. Om du vill ställa in en betalningsmetod för autogiromedgivanden måste du följa följande ytterligare steg för en betalningsmetod:

-   Välj **Elektronisk betalning** i fältet **Betalningstyp**.
-   Valfritt: Om du tror att var och en av dina kunder har flera anger, i den **Period** väljer **fakturan**. Skapas en separat betalning för varje faktura och varje betalning används uppdraget som angetts för fakturan.
-   Välj alternativet **Kräv medgivande** för att skapa betalningar genom att använda autogiromedgivanden. Alternativet **Kräv medgivande** är endast tillgängligt om du väljer **Elektronisk betalning** i fältet **Betalningstyp**.

Se även [översikt direktdebitering](sepa-direct-debit-overview.md) 

