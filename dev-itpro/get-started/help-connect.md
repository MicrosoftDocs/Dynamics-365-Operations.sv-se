---
title: "Ansluta hjälpsystemet"
description: "Det här avsnittet innehåller en beskrivning av komponenterna i hjälpsystemet för Microsoft Dynamics 365 for Finance and Operations, en översikt över hur du ansluter dem samt en sammanfattning över hur du skapar anpassad hjälp."
author: margoc
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: acb832c422ccb5ddb98d6ddd6b69d2e2c3e11057
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

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
> Fliken **Uppgiftsguider** finns för närvarande inte i Microsoft Dynamics 365 for Talent eller Microsoft Dynamics 365 for Retail. Vi arbetar för närvarande med att aktivera den här funktionen i framtida versioner. Uppgiftsguiderna i Komma igång i Talent täcker fortsatt basfunktionerna. Procedurhjälp finns också på webbplatsen docs.microsoft.com ([docs.microsoft.com/dynamics365/operations](/dynamics365/unified-operations/fin-and-ops/index)) för både Retail och Talent.
 

Med hjälp av sidan **Systemparametrar** ansluter systemadministratörer delar av hjälpsystemet för en implementering [![Formulär för systemparametrar med hjälpinställningar](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) Gå till sidan **Systemparametrar** och följ dessa steg:

> [!IMPORTANT]
> Första gången du öppnar fliken **Hjälp** måste du ansluta till Lifecycle Services. Se till att klicka på länken i mitten av formuläret, vänta på anslutningen, stänga dialogrutan och klicka sedan på **OK** för att nå sidan **Systemparametrar**.[![Anslut till LCS](./media/connect-to-lcs-crop-1024x365.png "Connect to LCS")](./media/connect-to-lcs-crop.png)

1.  Välj Lifecycle Services-projektet att ansluta till.
2.  Välj BPM-biblioteken (inom det valda projektet) att hämta uppgiftsregistreringar från.
    - För Microsoft innehåll för Finance and Operations väljer du QPC Unified Library (februari 2017) för Microsoft Dynamics 365 for Finance and Operations. 
    - För Retail släpper vi ett bibliotek i juli. 
    - Du behöver inte välja ett bibliotek för Talent — anslutningen till rätt bibliotek sker automatiskt. 

3.  Välj BPM-bibliotekens visningsordning. Detta bestämmer i vilken ordning som uppgiftsregistreringar från biblioteken visas i fönstret **Hjälp**.

När du har slutfört de här stegen kan du öppna fönstret **Hjälp** och klicka på fliken **Uppgiftsguider**. Du ser nu de uppgiftsguider som gäller för den sida du för närvarande befinner dig på i Finance and Operations. Om inga uppgiftsguider hittas kan du ange nyckelord för att begränsa sökningen.

### <a name="showing-translated-task-guides"></a>Visa översatta uppgiftsguider

Översätta uppgiftsguider medföljde i för första gången i APQC Unified Library i maj 2016, samt i Komma igång-biblioteket. Om du vill se hjälpen för den lokaliserade uppgiftsguiden i Finance and Operations, se då till att du är ansluten till maj-biblioteket. Språket i uppgiftsguiden styrs av varje användare via språkinställningarna under **Alternativ** &gt; **Inställningar**. 

> [!NOTE]
> Även om många uppgiftsguider har översatts, visas för närvarande inte namnen på de översatta uppgiftsguiderna i Finance and Operations. Dessutom är enbart de uppgiftsguider som släpptes i februari 2016 tillgängliga i översättningen i maj-biblioteket. Vi kommer att släppa ett uppdaterat bibliotek med fler översättningar.
> -   Om en uppgiftsguide har översatts visas all text i guiden på det valda språket när du öppnar den.
> -   Om en uppgiftsguide ännu inte har översatts visas enbart en del text i guiden (text på reglage) på det valda språket när du öppnar den.

## <a name="creating-custom-help"></a>Skapa anpassad hjälp
Du kan skapa anpassad hjälp för Finance and Operations samt för Retail genom att skapa uppgiftsinspelningar som speglar din implementering och spara dessa i ett bibliotek för LCS-arbetsprocesser. Du kan inte skapa anpassade uppgiftsguider för Talent. 

För partners, om du främjar ett bibliotek som ett företagsbibliotek och inkluderar det i en lösning blir det tillgängligt även för dina kunder. Du kan också göra en kopia av det globala biblioteket APQC Unified och sedan öppna din kopia, öppna uppgiftsinspelningar från den, ändra dem och spara inspelningarna med dina ändringar. Mer information finns i avsnittet [Skapa en uppgiftsregistrering att använda som dokumentation eller utbildning](../user-interface/task-recorder.md).

<a name="see-also"></a>Se även
--------

[Hjälpöversikt](help-overview.md)

[Uppgiftsregistreringsöversikt](../user-interface/task-recorder.md)

[Skapa en uppgiftsinspelning som ska användas som dokumentation eller utbildning](../user-interface/task-recorder-training-docs.md)





