---
title: "Använda arbetsflöden för att hantera medarbetarinformation"
description: "Det här avsnittet beskrivs hur du kan använda arbetsflödet möjligheten för personal kan du hantera medarbetarinformation. Exempelvis kan du koppla ett arbetsflöde till en befattning konfigurera ett arbetsflöde startas när en medarbetare har ändrat deras posten"
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: a76ec0cd86bcc810b42ae3cd8efd8a584e6c4da3
ms.openlocfilehash: f286436aa4833babaeb3de875ee393d18e5f8eea
ms.lasthandoff: 03/31/2017


---

# <a name="use-workflows-to-manage-employee-information"></a>Använda arbetsflöden för att hantera medarbetarinformation

Det här avsnittet beskrivs hur du kan använda arbetsflödet möjligheten för personal kan du hantera medarbetarinformation. Exempelvis kan du koppla ett arbetsflöde till en befattning konfigurera ett arbetsflöde startas när en medarbetare har ändrat deras posten

Arbetsflödet möjligheten för personal innehåller flera arbetsflöden för hantering av Personalaktiviteter. Dessutom finns många alternativ så att du kan ändra särskilda arbetsflöden och koppla dem till företagets hierarki. Arbetsflöden är tillgängliga för att hantera ändringar i flera olika typer av medarbetarinformation som standard. Du kan koppla ett arbetsflöde till en befattning. Sedan om medarbetare ändrar deras medarbetarposten, har ett arbetsflöde startats som måste godkännas innan den nya informationen sparas. Arbetsflöden är fördefinierade för följande typer av information som kan hjälpa dig att effektivt hantera ändringar och behålla de anställdas data korrekt:

-   Identifieringsnummer
-   Kurser
-   Utbildning
-   Bild
-   Lånade objekt
-   Yrkeserfarenhet
-   Projekterfarenhet
-   Kompetenser
-   Förtroendeuppdrag
-   Åtgärder för personal
-   Kursregistrering

När medarbetare anställs, överförs eller upphävs, kan arbetsflödet innehålla en granskningsprocess. Ett dokument kan ändras på det här sättet eller villkoren för en åtgärd kan definieras som en del av arbetsflödet. När granskningen är klar, dokumentet eller åtgärden slutförs och arbetsflödet fortsätter till steg ett slutligt godkännande.

## <a name="associate-a-workflow-with-a-position-hierarchy"></a>Koppla ett arbetsflöde till en Befattningshierarki
Du kan koppla ett arbetsflöde till vilken hierarki som helst som du konfigurerar. Om en befattning som är kopplad till matris företagets hierarki, kan du konfigurera ett arbetsflöde som vidarebefordrar utgifter för ett visst projekt till project lead i stället för chef för medarbetare som är kopplad till befattningen. Om du vill skapa ett nytt arbetsflöde eller ändra ett befintligt arbetsflöde på den **personal arbetsflöde** klickar du på **New**. Markera ett arbetsflöde i listan Starta Workflow designer. Du kan använda designer för att skapa ett nytt arbetsflöde eller ändra stegen i ett befintligt arbetsflöde. När du ändrar ett befintligt arbetsflöde, spara ändringarna som en ny version. Därför kan kan du alltid gå tillbaka till en tidigare version om du behöver.

## <a name="configure-a-human-resources-workflow"></a>Konfigurera ett arbetsflöde för personal
Så här konfigurerar du en grundläggande arbetsflöde startas när anställda gör ändringar i sin personliga kod.

1.  I den **Personalarbetsflöden** klickar du på **New**.
2.  Välj i listan över tillgängliga arbetsflöden **ID-nummer**.
3.  Klicka på **kör** starta Workflow designer och ange ditt användarnamn och lösenord när du uppmanas.
4.  Dra den **godkänna identifieringsnummer** element i listan med de arbetsflödeselement som designer arbetsytan.
5.  Godkännandeelement att ansluta **starta** och **Slutför**.
6.  Dubbelklicka på **Godkänn elementet**, och sedan högerklicka och välj **egenskaper**.
7.  Så här lägger du till artikel arbetsinstruktionerna:
    1.  Välj **tilldelning av**, och välj sedan **hierarki** under Tilldelningstypen.
    2.  Under den **hierarki** val väljer **hierarki konfigurerbara**.
    3.  Lägg till ett stoppvillkor och Stäng sidan.

8.  Slutför eventuella ytterligare instruktioner (inga fler varningar inte bör finnas).
9.  Klicka på **Spara och stäng**. Aktivera det nya arbetsflödet när dialogrutan öppnas och välj **aktivera**.
10. Gå till **personal**&gt;**positioner**&gt;**placerar hierarkiska typer**.
11. Välj **matris**.
12. Lägg till de **arbetare identifieringsnummer** arbetsflöde i listan.



