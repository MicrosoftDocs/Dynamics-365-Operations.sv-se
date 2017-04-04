---
title: "Ansluta hjälpsystemet"
description: "Det här avsnittet innehåller en beskrivning av komponenterna i hjälpsystemet för Microsoft Dynamics 365 for Operations, en översikt över hur du ansluter dem samt en sammanfattning över hur du skapar anpassad hjälp."
author: margoc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SystemParameters
audience: Application User, Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16141
ms.assetid: 0b9c8630-9474-4473-80fd-7db5d54b2275
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 5ac5e30cff2239f601778001368fa7aaba478f5c
ms.lasthandoff: 03/31/2017


---

# <a name="connect-the-help-system"></a>Ansluta hjälpsystemet

Det här avsnittet beskrivs komponenterna i hjälpsystemet för Microsoft Dynamics 365 för operationer. En översikt över hur du skapar anpassade hjälpen och den ger en översikt över hur du ansluter komponenterna. 

<a name="help-architecture"></a>Hjälparkitektur
-----------------

Följande illustration visar delarna i Dynamics 365 för operationer i hjälpen för. Hjälpsystemet i produkten hämtar artiklarna från Dynamics 365 för operationer på https://docs.microsoft.com samt uppgift guider lagras i Affärsmodelleraren processen Lifecycle Services (LCS). 
**Anmärkning:** funktionerna visas i bilden med en asterisk (\*) är planerade men ännu inte är tillgängliga. [![Help architecture](./media/help-architecture.png)](./media/help-architecture.png)

## <a name="connecting-the-help-system"></a>Ansluta hjälpsystemet
Med hjälp av den **systemparametrar** kan administratörer ansluta de olika delarna i hjälpsystemet för en implementering. [![Systemparameterformuläret med hjälp inställningar](./media/system-parameters_ops-1024x437.png)](./media/system-parameters_ops.png) på de **systemparametrar** sidan, gör du följande:

1.  **Viktigt:** första gången du öppnar den **hjälp** fliken måste du ansluta till Lifecycle Services. Du klickar du på länken mitt i formuläret vänta tills anslutningen, Stäng dialogrutan och klicka sedan på **OK** till den **systemparametrar** sida. [![Når LCS](./media/connect-to-lcs-crop-1024x365.png "når LCS")](./media/connect-to-lcs-crop.png)
2.  Välj Lifecycle Services-projektet att ansluta till.
3.  Välj BPM-biblioteken (inom det valda projektet) att hämta uppgiftsregistreringar från.
4.  Välj BPM-bibliotekens visningsordning. Detta bestämmer i vilken ordning som uppgiftsregistreringar från biblioteken visas i fönstret **Hjälp**.

När du har slutfört de här stegen kan du öppna fönstret **Hjälp** och klicka på fliken **Uppgiftsguider**. Du ser nu uppgiftsguiderna som gäller för den sida du för närvarande befinner dig på i Dynamics 365 for Operations. Om inga uppgiftsguider hittas kan du ange nyckelord för att begränsa sökningen.

### <a name="showing-translated-task-guides"></a>Visa översatta uppgiftsguider

Översatta aktiviteter stödlinjerna levererades först i maj 2016 APQC enhetliga bibliotek och komma igång-biblioteket. Om du vill se hjälpen för den lokaliserade uppgiftsguiden i Dynamics 365 for Operations ska du se till att är ansluten till maj-biblioteket. Det språk som utgångspunkt för aktiviteten visas i kontrolleras för varje användare av språkinställningar under **alternativ**&gt;**inställningar**. **Obs!** Även om många uppgiftsguider har översatts, visas inte namnen på de översatta uppgiftsguiderna i Dynamics 365 for Operations-klienten för närvarande. Dessutom finns bara som gavs ut i februari 2016 guiderna uppgiften i översättning i maj biblioteket. Vi kommer att släppa ett uppdaterat bibliotek med fler översättningar.

-   Om en uppgiftsguide har översatts visas all text i guiden på det valda språket när du öppnar den.
-   Om en uppgiftsguide ännu inte har översatts visas enbart en del text i guiden (text på reglage) på det valda språket när du öppnar den.

## <a name="creating-custom-help"></a>Skapa anpassad hjälp
Du kan skapa anpassad hjälp för din Dynamics 365 for Operations-implementering genom att skapa uppgiftsinspelningar som speglar din implementering och spara dem i ett bibliotek för LCS-arbetsprocesser. För partners, om du främjar ett bibliotek som ett företagsbibliotek och inkluderar det i en lösning blir det tillgängligt även för dina kunder. Du kan också göra en kopia av det globala biblioteket APQC Unified och sedan öppna din kopia, öppna uppgiftsinspelningar från den, ändra dem och spara inspelningarna med dina ändringar. Mer information finns i [hur du skapar en uppgift inspelning ska användas som dokumentation och utbildning](../user-interface/task-recorder.md).

<a name="see-also"></a>Se även
--------

[Help overview](help-overview.md)

[Översikt över registrerade uppgifter](../user-interface/task-recorder.md)

[Skapa en uppgiftsinspelning som ska användas som dokumentation eller utbildning](../user-interface/task-recorder-training-docs.md)

[Skapa nya bibliotek utbildning för Dynamics 365 för operationer inom Lifecycle Services med Uppgiftsregistering (extern länk)](https://docs.com/mufife/163372c6-f366-4c5a-94fa-93e2c25f878a/creating-new-training-libraries-for-dynamics-ax)


