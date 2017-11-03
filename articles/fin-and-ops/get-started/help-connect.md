---
title: "Ansluta hjälpsystemet"
description: "Det här avsnittet innehåller en beskrivning av komponenterna i hjälpsystemet för Microsoft Dynamics 365 for Finance and Operations, en översikt över hur du ansluter dem samt en sammanfattning över hur du skapar anpassad hjälp."
author: margoc
manager: AnnBe
ms.date: 09/11/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d67ad79c068651f32ce7dc776bc460698557bc29
ms.openlocfilehash: a27b21ffcde9bfbb7e6276ef35b2e48bd23af70d
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="connect-the-help-system"></a>Ansluta hjälpsystemet

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller komponenten för hjälpsystemet för Microsoft Dynamics 365 for Finance and Operations. Det ger en översikt över hur du skapar ansluter dessa komponenter en sammanfattning av hur du skapar anpassad hjälp. 

## <a name="help-architecture"></a>Hjälparkitektur
Följande bild visar delarna i hjälpsystemet för Finance and Operations. Produktens interna hjälpsystem hämtar artiklar från Finance and Operations-webbplatsen på https://docs.microsoft.com, samt på uppgiftsguider som lagras i Affärsprocessmodelleraren i Lifecycle Services (LCS). 
> [!NOTE]
> Funktionerna som anges med en asterisk (\*) i diagrammet planeras, men är ännu inte tillgängliga. [![Hjälparkitektur](./media/help-architecture.png)](./media/help-architecture.png)


## <a name="connecting-the-help-system"></a>Ansluta hjälpsystemet
> [!NOTE]
> Fliken **Uppgiftsguider** finns för närvarande inte i Microsoft Dynamics 365 for Talent eller Microsoft Dynamics 365 for Retail. Vi arbetar för närvarande med att aktivera den här funktionen i framtida versioner. Uppgiftsguiderna i Komma igång i Talent täcker fortsatt basfunktionerna. Procedurhjälp finns även att få via webbplatsen docs.microsoft.com site ([docs.microsoft.com/dynamics365/unified-operations](../../index.md)) för såväl Retail som Talent.
 

Med hjälp av sidan **Systemparametrar** ansluter systemadministratörer delar av hjälpsystemet för en implementering [![Formulär för systemparametrar med hjälpinställningar](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Gå till sidan **Systemparametrar** och följ dessa steg:

> [!IMPORTANT]
> Första gången du öppnar fliken **Hjälp** måste du ansluta till Lifecycle Services. Se till att klicka på länken i mitten av formuläret, vänta på anslutningen, stäng dialogrutan och klicka sedan på **OK** för att nå sidan **Systemparametrar**.[![Anslut till LCS](./media/connect-to-lcs-crop-1024x365.png "Anslut till LCS")](./media/connect-to-lcs-crop.png)

1.  Välj Lifecycle Services-projektet att ansluta till.
2.  Välj BPM-biblioteken (inom det valda projektet) att hämta uppgiftsregistreringar från.
    - Välj det nyaste förenade APQC-biblioteket för Finance and Operations om du vill ha Microsoft-innehåll. 
    - För Retail släpps snart ett eget bibliotek. 
    - Du behöver inte välja ett bibliotek för Talent — anslutningen till rätt bibliotek sker automatiskt. 

3.  Välj BPM-bibliotekens visningsordning. Detta bestämmer i vilken ordning som uppgiftsregistreringar från biblioteken visas i fönstret **Hjälp**.

När du har slutfört dessa steg kan du öppna fönstret **Hjälp** och klicka på fliken **Uppgiftsguider**. Du kan nu se de uppgiftsguider som gäller den sida som du för tillfället befinner dig på i Finance and Operations. Om inga uppgiftsguider hittas kan du ange nyckelord för att begränsa sökningen.

### <a name="showing-translated-task-guides"></a>Visa översatta uppgiftsguider

Översätta uppgiftsguider medföljde i för första gången i APQC Unified Library i maj 2016, samt i Komma igång-biblioteket. Om du vill se hjälpen för den lokaliserade uppgiftsguiden i Finance and Operations, se då till att du är ansluten till maj-biblioteket. Språket i uppgiftsguiden styrs av varje användare via språkinställningarna under **Alternativ** &gt; **Inställningar**. 

> [!NOTE]
> Även om många uppgiftsguider har översatts, visas för närvarande inte namnen på de översatta uppgiftsguiderna i Finance and Operations. Dessutom är enbart de uppgiftsguider som släpptes i februari 2016 tillgängliga i översättningen i maj-biblioteket. Vi kommer att släppa ett uppdaterat bibliotek med fler översättningar.
> -   Om en uppgiftsguide har översatts visas all text i guiden på det valda språket när du öppnar den.
> -   Om en uppgiftsguide ännu inte har översatts visas enbart en del text i guiden (text på reglage) på det valda språket när du öppnar den.

## <a name="creating-custom-help"></a>Skapa anpassad hjälp
Du kan skapa anpassad hjälp för Finance and Operations samt för Retail genom att skapa uppgiftsinspelningar som speglar din implementering och spara dessa i ett bibliotek för LCS-arbetsprocesser. Du kan inte skapa anpassade uppgiftsguider för Talent. 

För partners, om du främjar ett bibliotek som ett företagsbibliotek och inkluderar det i en lösning blir det tillgängligt även för dina kunder. Du kan också göra en kopia av det globala biblioteket APQC Unified och sedan öppna din kopia, öppna uppgiftsinspelningar från den, ändra dem och spara inspelningarna med dina ändringar. Mer information finns i avsnittet [Skapa en uppgiftsregistrering att använda som dokumentation eller utbildning](../../dev-itpro/user-interface/task-recorder.md).

<a name="see-also"></a>Se även
--------

[Hjälpöversikt](help-overview.md)

[Uppgiftsregistreringsöversikt](../../dev-itpro/user-interface/task-recorder.md)

[Skapa en uppgiftsinspelning som ska användas som dokumentation eller utbildning](../../dev-itpro/user-interface/task-recorder-training-docs.md)





