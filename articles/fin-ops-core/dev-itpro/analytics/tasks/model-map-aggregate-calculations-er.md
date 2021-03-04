---
title: Använd konfigurationer för modellmappning för att sammanställa beräkningar på databasnivå
description: Denna procedur ger information för att skapa en ny elektronisk rapportering (ER)-modellmappningskonfiguration och använda inbyggda funktioner för ER för effektiv aggregerade beräkningar.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f1c4ddf0fac5ba962c3dab545bfa7e0df4afa948
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684126"
---
# <a name="use-model-mapping-configurations-for-aggregate-calculations-at-the-database-level"></a>Använd konfigurationer för modellmappning för att sammanställa beräkningar på databasnivå

[!include [banner](../../includes/banner.md)]

Denna procedur ger information för att skapa en ny elektronisk rapportering (ER)-modellmappningskonfiguration och använda inbyggda funktioner för ER för effektiv aggregerade beräkningar. I det här exemplet ska du skapa en konfiguration för exempelföretaget, Litware, Inc. 

Den här proceduren har skapats för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Stegen kan utföras med hjälp av valfri datauppsättning.

 För att slutföra stegen måste du först slutföra stegen i proceduren ”ER förbättrar effektiviteten av aggregerade beräkningar genom att utföra dem på databasnivå (del 1: förbereda konfigurationer)”.

1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Expandera "Intrastat model" i trädet.
3. Välj "Intrastat model\Intrastat sample mapping" i trädet.
4. Klicka på Designer.
5. Klicka på Designer.
6. Välj "Dynamics 365 for Operations\Table records" i trädet.
7. Klicka på Lägg till rot.
    * Lägg till en ny datakälla som representerar poster som du vill gruppera.  
8. Skriv "Transaktioner" i fältet Namn.
    * Transaktioner  
9. Skriv "Intrastat" i fältet Tabell.
    * Intrastat  
10. Klicka på OK.
11. Välj alternativet för metadata för "Funktioner\gruppera efter" i trädet.
    * Denna typ av datakälla används för att presentera en ny datakälla under körning för att gruppera poster och beräkna aggregeringar som krävs.  
12. Klicka på Lägg till rot.
13. I namnfältet anger du "TransactionsGroups".
    * TransactionsGroups  
14. Klicka på Redigera grupp efter.
15. Välj "Transaktioner" i trädet.
    * Välj den tillagda datakällan av typen "Postlista" som motsvarar de poster som du vill gruppera.  
16. Klicka på Lägg till fält i.
17. Klicka på Vad ska grupperas.
18. Expandera "Transaktioner" i trädet.
19. Välj "Transactions\Direction" i trädet.
20. Klicka på Lägg till fält i.
21. Klicka på Grupperade fält.
    * Välj fältet för att ange grupperingsnivån. Baserat på detta val returnerar datakällan vid körning så många grupper för transaktionerna som det finns riktningskoder som ska uppfyllas i Intrastat-registret.  
22. Välj "Transactions\Invoice amount(AmountMST)" i trädet.
    * Välj fältet för att ange källan för beräkningen av aggregering.  
23. Klicka på Lägg till fält i.
24. Klicka på Sammansättningsfält.
25. Markera vald rad i listan.
26. I fältet Metod väljer du Summa.
    * Välj aggregeringstyp.  
27. I namnfältet anger du "SumOfAmountMST".
    * Ange namnet på denna aggregering i konfigurerade datakällan.  
28. Klicka på Spara.
    * Observera att fältet "körning på" anger att grupperingen ska utföras vid körning i SQL-databasen.  
29. Stäng sidan.
30. Klicka på OK.
31. Expandera "Totaler" i trädet.
32. Expandera "TransactionsGroups" i trädet.
33. Expandera "TransactionsGroups\aggregated" i trädet.
34. Välj "TransactionsGroups\aggregated\SumOfAmountMST" i trädet.
35. Välj "Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')" i trädet.
36. Klicka på Bind.
    * Baserat på denna inställning beräknar datakällan summan av värdena i fältet "AmountMST" för varje grupp av transaktioner. Denna aggregeringsberäkning blir tillgängliga som TransactionsGroups.aggregated.TotalAmount-objekt.  
37. Expandera "TransactionsGroups" i trädet.
38. Välj "TransactionsGroups" i trädet.
39. Klicka på Redigera.
40. Klicka på Redigera grupp efter.
41. Expandera "Transaktioner" i trädet.
42. Välj "Transactions\Invoice amount(AmountMST)" i trädet.
43. Klicka på Lägg till fält i.
44. Klicka på Sammansättningsfält.
45. Markera vald rad i listan.
46. I fältet Metod väljer du Max.
47. I namnfältet anger du "MaxOfAmountMST".
48. Klicka på Spara.
    * För närvarande kan utförandet av GROUPBY-datakällor översättas till nivån för SQL-databasen med vissa begränsningar. Översättningen kan göras antingen datakällor av typen "Postlista" eller datakällor som representeras av ett uttryck som använder FILTER-funktionen. Det kan också göras när endast en aggregering konfigureras för ett enskilt fält av grupperingsposter.  
    * Observera att även om mer än en aggregering konfigurerades för fältet AmountMST, kommer fältet "körning på" fortfarande ange att denna gruppering ska utföras vid körning i SQL-databasen. Detta beror på att endast en aggregering är bunden till datamodellobjektet och används vid körning så att data hämtas från datakällan.  
49. Stäng sidan.
50. Klicka på OK.
51. Expandera "TransactionsGroups" i trädet.
52. Expandera "TransactionsGroups\aggregated" i trädet.
53. Välj "TransactionsGroups\aggregated\MaxOfAmountMST" i trädet.
54. Välj "Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')" i trädet.
55. Klicka på Bind.
56. Expandera "TransactionsGroups" i trädet.
57. Välj "TransactionsGroups" i trädet.
58. Klicka på Redigera.
59. Klicka på Redigera grupp efter.
    * Observera att fältet "körning på" anger att grupperingen ska utföras vid körning i minnet eftersom båda aggregeringarna med samma fält är bundna till datamodellelement.   
60. Markera eller avmarkera alla rader i listan.
61. Klicka på Ta bort.
62. Klicka på Ja.
63. Klicka på Ta bort.
64. Klicka på Ja.
65. Klicka på Lägg till fält i.
66. Klicka på Vad ska grupperas.
67. Expandera "Commodity record(Intrastat)" i trädet.
68. Klicka på Spara.
    * Observera att fältet "körning på" anger att grupperingen ska utföras vid körning i minnet även om det inte finns några aggregeringar definierade och den valda datakällan av typen ”registerposter” refererar till samma Intrastat-tabell. Detta beror på att datakällan innehåller vissa beräknade fält som ännu inte kan konverteras till SQL-databasnivå.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]