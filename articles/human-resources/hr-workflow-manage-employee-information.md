---
title: Använd arbetsflöden för att hantera medarbetarinformation
description: Det här avsnittet beskriver hur du kan använda arbetsflödeskapacitet för personal får att hantera medarbetarinformation. Exempelvis kan du koppla ett arbetsflöde till en befattning och konfigurera ett godkännandearbetsflöde som startas när en medarbetare har ändrat deras post.
author: andreabichsel
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: aba7627877cd9b79dce5930e528f892e2d80baac
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058762"
---
# <a name="use-workflows-to-manage-employee-information"></a>Använd arbetsflöden för att hantera medarbetarinformation

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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

## <a name="additional-resources"></a>Ytterligare resurser

[Visa och hantera adressändringar](hr-personnel-view-address-changes.md) 





[!INCLUDE[footer-include](../includes/footer-banner.md)]