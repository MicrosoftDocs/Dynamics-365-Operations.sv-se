---
title: Använd arbetsflöden för att hantera medarbetarinformation
description: Det här avsnittet beskriver hur du kan använda arbetsflödeskapacitet för personal får att hantera medarbetarinformation. Exempelvis kan du koppla ett arbetsflöde till en befattning och konfigurera ett godkännandearbetsflöde som startas när en medarbetare har ändrat deras post.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: a159f5fd811ee80c0ac45ca1b582f2f46fcb2c61
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010560"
---
# <a name="use-workflows-to-manage-employee-information"></a>Använd arbetsflöden för att hantera medarbetarinformation

Det här avsnittet beskriver hur du kan använda arbetsflödeskapacitet för personal får att hantera medarbetarinformation. Exempelvis kan du koppla ett arbetsflöde till en befattning och konfigurera ett godkännandearbetsflöde som startas när en medarbetare har ändrat deras post.

Arbetsflödeskapaciteten för personal innehåller flera arbetsflöden för hantering av personalaktiviteter. Dessutom finns många alternativ så att du kan ändra särskilda arbetsflöden och koppla dem till en rapporthierarki. Arbetsflöden är tillgängliga för att hantera ändringar i flera olika standardtyper av medarbetarinformation. Du kan associera ett arbetsflöde med en befattning. Om sedan medarbetare ändrar sin medarbetarpost startas ett arbetsflöde som måste godkännas innan den nya informationen sparas. Arbetsflöden är fördefinierade för följande typer av information som kan hjälpa dig att effektivt hantera ändringar och behålla medarbetarnas data korrekt:

-   Identifieringsnummer
-   Kurser
-   Utbildning
-   Bild
-   Lånade objekt
-   Yrkeserfarenhet
-   Projekterfarenhet
-   Kompetenser
-   Förtroendeuppdrag
-   Personalåtgärder
-   Kursregistrering

När medarbetare anställs, överförs eller sägs upp kan arbetsflödet innehålla en granskningsprocess. På så sätt kan ett dokument ändras eller villkoren för en åtgärd kan definieras som en del av arbetsflödet. När granskningen är klar slutförs dokumentet eller åtgärden och arbetsflödet fortsätter till ett slutligt godkännandesteg.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Associera ett arbetsflöde med en befattningshierarki
Du kan associera ett arbetsflöde till vilken hierarki som helst som du konfigurerar. Om en befattning som är kopplad till en matrisrapporteringshierarki kan du konfigurera ett arbetsflöde som vidarebefordrar utgifter för ett specifikt projekt till projektledning i stället för chefen för den medarbetare som är kopplad till den befattningen. Om du vill skapa ett nytt arbetsflöde eller ändra ett befintligt arbetsflöde på sidan **Personalarbetsflöde** klickar du på **Ny**. Markera ett arbetsflöde i listan för att starta arbetsflödesdesignern. Du kan använda designern för att skapa ett nytt arbetsflöde eller för att ändra stegen i ett befintligt arbetsflöde. När du ändrar ett befintligt arbetsflöde, sparas dina ändringar som en ny version. Därför kan kan du alltid gå tillbaka till en tidigare version om du behöver.

## <a name="configure-a-human-resources-workflow"></a>Konfigurera personalåtgärdsarbetsflöden
Om du vill konfigurera ett grundläggande arbetsflöde som startas när anställda begär ändringar i sin personliga kod följer du dessa steg.

1.  Klicka på **Ny** på sidan **Personalarbetsflöden**.
2.  I listan över tillgängliga arbetsflöden väljer du **ID-nummer**.
3.  Klicka på **Kör** för att starta arbetsflödesdesignern och ange ditt användarnamn och lösenord när du uppmanas.
4.  Dra elementet **Godkänna identifieringsnummer** från listan med arbetsflödeselement till designerarbetsytan.
5.  Anslut godkännandeelement för **Starta** och **Slutföra**.
6.  Dubbelklicka på **Godkänn elementt** och högerklicka sedan och välj **Egenskaper**.
7.  Så här lägger du till arbetsuppgiftsinstruktioner:
    1.  Välj **Tilldelning** och välj sedan **Hierarki** under tilldelningstypen.
    2.  Under **Hierarki** väljer du **Konfigurerbar hierarki**.
    3.  Lägg till ett stoppvillkor och stäng sidan.

8.  Slutför eventuella ytterligare instruktioner (inga fler varningar bör finnas).
9.  Klicka på **Spara och stäng**. Aktivera det nya arbetsflödet när dialogrutan öppnas och välj **Aktivera**.
10. Gå till **Personal** &gt; **Befattningar** &gt; **Befattningshierarkityper**.
11. Välj **Matris**.
12. Lägg till arbetsflödet **Medarbetares ID-nummer** i listan.




