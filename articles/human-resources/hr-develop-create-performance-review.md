---
title: Skapa resultatöversyner
description: I det här avsnittet förklarar vi hur du skapar en resultatöversyn och beskriver syftet för varje del av granskningen.
author: twheeloc
ms.date: 08/26/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EssWorkspace, HcmDiscussionNewDialog, HcmDiscussion, HcmDiscussionChangeSettings, HcmDiscussionAddGoalDialog, HcmTopicCreate, HcmMeasurementDetailDialog, HcmPerfJournalAdd, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1340653c1e9a21d41743b8e3c0b81a4285245d5a
ms.sourcegitcommit: a8ac6d9b63eb67d14dd17a086ef4f1eccd7f9fc1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2021
ms.locfileid: "7431170"
---
# <a name="create-performance-reviews"></a>Skapa resultatöversyner

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]


I det här avsnittet förklarar vi hur du skapar en resultatöversyn och beskriver syftet för varje del av granskningen. Denna procedur skapades med demodataföretaget USMF.

1. På startsidan väljer du arbetsytan **Självbetjäning för medarbetare**.
2. Välj **Ny granskning** för att skapa en ny granskning.
3. Ange eller välj ett värde i fältet **Typ av granskning**.
4. Ange eller välj ett värde i fältet **Prestationsperiod**.
5. Ange ett datum i fältet **Slutdatum**.
6. Välj **OK**. Du kan även skapa en granskning från en mall. Detta är bästa sättet att skapa en granskning, detta eftersom varje avsnitt innehåller den information du behöver för att initiera en granskning.  
7. Du kan visa eller dölja flikar som t.ex. fliken bifogade filer:

    1. I åtgärdsfönstret väljer du **Visa avsnitt** för att öppna dialogmenyn.
    1. Välj **Ja** eller **Nej** i fältet **Visa bifogade filer** om du vill visa eller dölja fliken bifogade filer.
    1. Välj **Spara**.

8. Välj **Lägg till mål för granskning** om du vill lägga till ett mål. Välj **OK** när du är klar.
9. Välj **Lägg till kompetens** för att öppna dialogrutan.
10. Ange ett värde i fältet **Rubrik**.
11. Ange `Increase customer skills by working with the support team` i fältet **Beskrivning**.
12. Välj **OK**.
13. Välj **Dölj alla**.
14. Välj **Expandera alla**.
15. Välj **Lägg till kommentar**.
16. Vald **bokföring**
17. Välj fliken **Mått**.
18. Välj **Lägg till mått** för att öppna dialogmenyn.
19. Ange eller välj ett värde i fältet **Mått**.
26. Ange en siffra i fältet **Målbelopp**.
20. Välj **OK**.
21. Välj fliken **Aktiviteter**.
22. Markera **Lägg till**.
23. Ange ett värde i fältet **Rubrik**.
24. I fältet **Beskrivning** anger du ett värde.
25. Ange ett datum i fältet **Startdatum**.
26. Ange ett datum i fältet **Slutfört den**.
27. Välj **Ja** i fältet **Utvecklingsplan**.
28. Ange ett värde i fältet **Nyckelord**.
29. Välj **Spara**.
30. Välj fliken **Värderingar**.  

    - Snabbfliken för **Bedömningsinformation** låter medarbetarna bedöma sig själva och chefen bedöma medarbetaren. Om vikter används kommer det viktade värdet av poängen att beräknas automatiskt.  
    - Om du vill visa det här avsnittet aktiverar du parameterinställningarna för visning av medarbetaromdömen på sidan **Delade personalparametrar**.  

31. Välj fliken **Godkännanden**. Om granskningen använder arbetsflöden kommer godkännandena att visas först när arbetsflödet är färdigt. Om ingen arbetsflöde används kommer både arbetaren och chefen att anges här. Kryssrutan **Obligatoriskt** för **Godkännanden** väljs utifrån inställningarna för granskningstypen.  
32. Välj fliken **Allmänt**.

    - Resultatperioden skapar förvalda start- och slutdatum. Dessa datum kan redigeras.  
    - Statusen reglerar åtkomsten till granskningen. Statusen **Inte startad** låter alla redigera granskningen. Statusen **Pågår** låter endast medarbetaren granska och redigera granskningen. **Klar för granskning** tillåter endast chefen att visa och redigera granskningen. Status för **Slutlig granskning** ger både medarbetaren och chefen möjlighet att visa och redigera granskningen om alternativet **Tillåt redigering i slutgiltig granskning** har valts i granskningstypen. Statusen **Slutförd** och **Avbruten** skrivskyddar granskningen. Om en granskning är **Avvisad** och skickas tillbaka till medarbetaren kan både medarbetaren och chefen göra nödvändiga ändringar så att medarbetaren kan skicka in på nytt.

33. Ange ett värde i fältet **Översikt**.
34. Välj fliken **Granska**. I takt med att granskningen fortskrider genom de olika stadierna, kan medarbetaren och chefen lägga till kommentarer för respektive mål eller kompetens.  
35. Välj fliken **Godkännanden**. Arbetaren och chefen kan godkänna granskningen. När alla erforderliga godkännanden har slutförts ändras statusen till **Slutfört**, och inga fler ändringar kan genomföras.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
