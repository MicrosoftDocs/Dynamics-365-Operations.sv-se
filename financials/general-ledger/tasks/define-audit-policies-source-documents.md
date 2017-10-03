--- 
title: "Definiera granskningspolicyer för källdokument"
description: "I den här proceduren visar vi hur du ställer in och kör granskningsprincipregler."
author: ryansandness
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ca4c8735258170c41dc907ed0ef8afca250ea9dd
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="define-audit-policies-for-source-documents"></a>Definiera granskningspolicyer för källdokument

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visar vi hur du ställer in och kör granskningsprincipregler. I exemplet används utgiftsrapporter av typen hotellutgift. I den här proceduren används demonstrationsföretaget USMF. Revisorrollen har rätt behörighet för att utföra dessa uppgifter.

1. Gå till Revision > Inställningar > Policyregeltyp.
2. Klicka på Ny.
3. I fältet Regelnamn, skriv ett värde.
4. Ange ett värde i fältet Beskrivning.
5. I frågenamnfältet, välj raden Utgiftsrapport
6. Välj Sammansättning i frågetypsfältet
7. Välj Juridisk person i fältet Juridisk person
8. Välj Datum och tid för ändring i dokumentdatumreferensfältet
9. Klicka på Spara.
10. Gå till revision workbench > Installation > Revision policy.
11. Klicka på Ny.
12. Skriv ett värde i fältet Namn.
13. Expandera avsnittet Policyorganisationer.
14. Välj det ”Contoso Entertainment System USA" i trädet..
15. Klicka på Lägg till.
16. Välj ”Contoso Consulting USA" i trädet.
17. Klicka på Lägg till.
18. Välj ”Contoso Retail USA" i trädet.
19. Klicka på Lägg till.
20. Komprimera avsnittet Policyorganisationer.
21. Expandera avsnittet Policyregler.
22. I listan söker du efter och väljer den policyregel som tidigare har skapats.
23. Klicka på Skapa policyregel.
24. Ange datum och tid i fältet Giltighetsdatum.
25. Klicka på Filter.
26. Markera raden för utgiftskategori i listan och ange Hotell
27. Ange eller välj ett värde i fältet Kriterier.
28. Klicka på fliken Sammansättning.
29. Klicka på Lägg till.
30. Välj ett fältvärde för transaktionsbelopp
31. Ange eller välj ett värde i fältet Fält.
32. Välj ”Summa” i fältet AggregateFunction.
33. Klicka på fliken Gruppera efter.
34. Klicka på Lägg till.
35. I listan väljer du ett värde av anställd  
36. Klicka på Lägg till.
37. Välj ett värde för Utgiftskategori i listan
38. Ange eller välj ett värde i fältet Fält.
39. Klicka på fliken Har.
40. Klicka på Lägg till.
41. Välj transaktionsbelopp
42. Ange eller välj ett värde i fältet Fält.
43. Välj ”Summa” i fältet AggregateFunction.
44. I fältet skriver du ">2000".
45. Klicka på OK.
46. Klicka på Ja.
47. I fältet Startdatum för dokumenturval, ange datum och tid.
48. I fältet Slutdatum för dokumenturval, ange datum och tid.
49. Klicka på Kör test.
50. Klicka på Granskningspolicy i åtgärdsfönstret.
51. Klicka på ytterligare alternativ.
52. Ange datum och tid i fältet Startdatum.
53. I fältet Slutdatum, ange datum och tid.
54. Klicka på Batch.
55. Expandera avsnittet Kör i bakgrunden.
56. Välj Ja i fältet Batchbearbetning.
57. Klicka på OK.
58. Gå till revision workbench > revision.
59. Hitta och markera önskad post i listan.
60. Klicka på länken på den valda raden i listan.
61. Expandera avsnittet Associationer.
62. Hitta och markera önskad post i listan.
63. Klicka på länken på den valda raden i listan.


