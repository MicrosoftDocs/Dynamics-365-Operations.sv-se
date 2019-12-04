---
title: Ansluta hjälpsystemet
description: Det här avsnittet innehåller en beskrivning av komponenterna i hjälpsystemet för Finance and Operations och ger en översikt över hur du kopplar dem och en sammanfattning av hur du skapar anpassad hjälp.
author: margoc
manager: AnnBe
ms.date: 10/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2955464aa8a220563db1b9ebbb348be52f520659
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812590"
---
# <a name="connect-the-help-system"></a>Ansluta hjälpsystemet

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs komponenterna i hjälpsystemet för Finance and Operations-appar, till exempel Dynamics 365 Finance, Supply Chain Management, Retail och Talent. Det ger en översikt över hur du skapar ansluter dessa komponenter en sammanfattning av hur du skapar anpassad hjälp.

## <a name="help-architecture"></a>Hjälparkitektur

Följande bild visar delarna i hjälpsystemet. Produktens interna hjälpsystem hämtar artiklar från webbplatsen på https://docs.microsoft.com, samt på uppgiftsguider som lagras i Affärsprocessmodelleraren i Lifecycle Services (LCS).

> [!NOTE]
> Funktionerna som anges med en asterisk (\*) i diagrammet planeras, men är ännu inte tillgängliga.

[![Hjälparkitektur](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Ansluta hjälpsystemet

> [!NOTE]
> Fliken **uppgiftsguide** finns för närvarande inte i Dynamics 365 Talent eller Retail. Vi arbetar för närvarande med att aktivera den här funktionen i framtida versioner. Uppgiftsguiderna i Komma igång i Talent täcker fortsatt basfunktionerna. Procedurhjälp finns också på webbplatsen docs.microsoft.com för både Retail och Talent.

Med hjälp av sidan **Systemparametrar** ansluter systemadministratörer delar av hjälpsystemet för en implementering

[![Formulär för systemparametrar med hjälpinställningar](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png)

Gå till sidan **Systemparametrar** och följ dessa steg:

> [!IMPORTANT]
> Första gången du öppnar fliken **Hjälp** måste du ansluta till Lifecycle Services. Se till att klicka på länken i mitten av formuläret, vänta på anslutningen, stäng dialogrutan och klicka sedan på **OK** för att komma till sidan **Systemparametrar**.
>
> [![Anslut till LCS](./media/connect-to-lcs-crop-1024x365.png "Anslut till LCS")](./media/connect-to-lcs-crop.png)

1. Välj Lifecycle Services-projektet att ansluta till.
2. Välj BPM-biblioteken (inom det valda projektet) att hämta uppgiftsregistreringar från.
3. Välj BPM-bibliotekens visningsordning. Detta bestämmer i vilken ordning som uppgiftsregistreringar från biblioteken visas i fönstret **Hjälp**.

När du har slutfört dessa steg kan du öppna fönstret **Hjälp** och klicka på fliken **Uppgiftsguider**. Du kan nu se de uppgiftsguider som gäller den sida som du för tillfället befinner dig på i Finance and Operations-appar. Om inga uppgiftsguider hittas kan du ange nyckelord för att begränsa sökningen.

### <a name="showing-translated-task-guides"></a>Visa översatta uppgiftsguider

Översätta uppgiftsguider medföljde i för första gången i APQC Unified Library i maj 2016, samt i Komma igång-biblioteket. Om du vill se hjälpen för den lokaliserade uppgiftsguiden i Finance and Operations-appar, se då till att du är ansluten till maj-biblioteket. Språket i uppgiftsguiden styrs av varje användare via språkinställningarna under **Alternativ** &gt; **Inställningar**.

> [!NOTE]
> Även om många uppgiftsguider har översatts visas inte de översatta uppgiftsguiderna för närvarande i klienten. Dessutom är enbart de uppgiftsguider som släpptes i februari 2016 tillgängliga i översättningen i maj-biblioteket. Vi kommer att släppa ett uppdaterat bibliotek med fler översättningar.
>
> - Om en uppgiftsguide har översatts visas all text i guiden på det valda språket när du öppnar den.
> - Om en uppgiftsguide ännu inte har översatts visas enbart en del text i guiden (text på reglage) på det valda språket när du öppnar den.

## <a name="creating-custom-help"></a>Skapa anpassad hjälp

Du kan använda uppgiftsguiderna för att skapa anpassad hjälp eller ansluta en webbplats till hjälpfönstret.

### <a name="create-custom-help-with-task-guides"></a>Skapa anpassad hjälp med uppgiftsguider

Du kan skapa anpassad hjälp för Finance and Operations, Supply Chain Management samt Retail genom att skapa uppgiftsinspelningar som speglar din implementering och spara dessa i ett bibliotek för LCS-arbetsprocesser. Du kan inte skapa anpassade uppgiftsguider för Talent.

För partners, om du främjar ett bibliotek som ett företagsbibliotek och inkluderar det i en lösning blir det tillgängligt även för dina kunder. Du kan också göra en kopia av det globala biblioteket APQC Unified och sedan öppna din kopia, öppna uppgiftsinspelningar från den, ändra dem och spara inspelningarna med dina ändringar. Mer information finns i [Uppgiftsinspelarresurser](../../dev-itpro/user-interface/task-recorder.md).

### <a name="connect-a-custom-site"></a>Ansluta en anpassad webbplats

Microsoft tillhandahåller en vitbok och exempelkod som beskriver hur du skapar och ansluter en anpassad hjälpwebbplats till hjälpfönstret. Mer information finns i:

- [Skapa egen hjälp för Finance and Operations-appar (vitbok)](https://go.microsoft.com/fwlink/?linkid=2041185)
- [Anpassad hjälp GitHub-databasen](https://github.com/microsoft/dynamics356f-o-custom-help)

## <a name="additional-resources"></a>Ytterligare resurser

[Hjälpsystem](help-overview.md)

[Uppgiftsinspelarresurser](../../dev-itpro/user-interface/task-recorder.md)

[Skapa dokumentation eller utbildning med Uppgiftsinspelare](../../dev-itpro/user-interface/task-recorder-training-docs.md)
