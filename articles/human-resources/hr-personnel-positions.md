---
title: Befattningar
description: Detta ämne beskriver de begreppsmässiga element som kan ingå i en befattning. Här finns också exempel som visar hur du kan använda dessa element i organisationen.
author: andreabichsel
ms.date: 06/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: anbichse
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 269054
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c8311df31326faeadd280585115338317b19125d54f3a526b4ccc6ef6684ad2c
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754762"
---
# <a name="positions"></a>Befattningar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver de begreppsmässiga element som kan ingå i en befattning. Här finns också exempel som visar hur du kan använda dessa element i organisationen.

Innan du kan skapa en befattning måste du konfigurera ett jobb. Vissa befattningsuppgifter, till exempel kompensationsregion, medarbetartilldelning, befattningsperiod och rapporteringsrelation, gäller från angivet datum.

## <a name="general-information"></a>Allmän information

När du skapar en befattning måste du välja ett jobb. Följande information fylls i automatiskt från det jobb som du väljer:

- beskrivning
- Befattning
- Heltidslön
- Jobbgrupp

Befattningstiteln används för att referera till en medarbetares titel. (Titeln som listas på medarbetaren används inte.) Därför bör befattningstitlar standardiseras så mycket som möjligt.

> [!NOTE]
> En medarbetare kan inte tilldelas en befattning på ett datum som ligger före möjligt tilldelningsdatumet.
>
> En parameter på fliken **Befattningar** på sidan **Gemensamma parametrar för Personal** styr hur medarbetartilldelningen fungerar. Välj ett av följande värden:
>
> - **Alltid** – Du kan tilldela arbetstagare till nya positioner när positioner skapas. När befattningar skapas kommer datum och tid för **Tillgänglig för tilldelningar** på fliken **Allmänt** på sidan **Position** anges automatiskt till skapandedatum och -tid.
> - **Aldrig** – Du kan inte tilldela arbetstagare till nya positioner när positioner skapas. Om du väljer det här alternativet måste du öppna sidan **Befattning** för varje ny befattning som blir tillgänglig. På fliken **Allmänt** anger du sedan datum för **Tillgänglig för tilldelning** för att aktivera medarbetstilldelningen. Om du väljer det här alternativet ställs tilldelningsdatum för medarbetare som standard in på **Aldrig** när du försöker tilldela medarbetaren.

## <a name="position-duration"></a>Befattningstidslängd

Varje befattning gäller för en viss tidsperiod, kallad "varaktighet". Sommarbefattningar kan exempelvis ha varaktigheten 1 maj 2021 till 31 augusti 2021. Aktiveringsdatumet är det datum då befattningen blir aktiv i systemet. Utrangeringsdatumet är det datum då befattningen inte längre är aktiv i systemet.

Observera att varken datum för tillgänglig tilldelning eller tilldelningsdatum för medarbetare kan infalla före aktiveringsdatumet. En befattning anses inte vara aktiv förrän aktiveringsdatumet har in uppnåtts. Dessutom kan en medarbetartilldelning inte sträckas tidigare än till och med befattningens utrangeringsdatum.

## <a name="reports-to-position"></a>Rapportering till befattning

Befattningar är ett viktigt element i den lägre nivån i en organisationshierarki. På sidan **Befattning** kan du ange den befattning som en befattning rapporterar till. När du tilldelar en medarbetare till en befattning som rapporterar till en annan befattning, skapar du en rapporteringsrelation mellan medarbetarna som tilldelas dessa två befattningar. Befattning 000220 kan exempelvis rapportera till befattning 000300. Kim Akers tilldelas befattning 000220, medan Sanjay Patel tilldelas befattningen 000300. Därför rapporterar Kim Akers till Sanjay Patel.

> [!TIP]
> Rapportering till befattning används i hela systemet för att bestämma vem som är en viss medarbetares överordnade. Om chefsrollen i föregående exempel tilldelas Sanjay Patel i systemet, ser han Kim Akers som en direktrapport i Självbetjäning för chef. Rapporteringsrelationen kan också användas när du skapar arbetsflödesregler och checklisteuppgifter.

## <a name="relationships"></a>Relationer

Om din organisation använder en matrishierarki eller någon annan anpassad hierarki, kan du konfigurera typer av befattningshierarki. Du kan sedan lägga till rapporteringsrelationer till befattningar för respektive hierarkityp som du konfigurerar. Exempelvis är Lori Penor verkställande direktör på Adventure Works och tilldelas befattningen **verkställande direktör**. Lori hanterar utvecklingen av en produkt som används för att rena gränssnittskomponenter. Hon behöver en revisor som hjälper henne med ekonomin. Därför hon har rekryterat Kim Akers som sin revisor. Kim rapporterar direkt till Sanjay Patel, men arbetar också med Lori Penor rörande frågor som är relaterade till finanserna för att utveckla rengöringsmedlet för widgeten.

För det föregående exemplet måste du utföra följande uppgifter om du vill konfigurera arbetsrelationen mellan Kim Akers och Lori Penor:

1. Skapa en anpassad befattningshierarkityp kallad **Widget** för att skapa en hierarki som inkluderar befattningar som ansvarar för arbete med rengöringsmedelprodukten för widgets.
2. Ange befattningen **Chef** som den befattning som Kims befattning rapporterar till i hierarkin för **Widget**.
3. Använd befattninghierarkin om du vill visa rapporteringstrukturen av befattningar. Om du har flera befattninghierarkier, kan du visa hierarkin för varje hierarki i befattninghierarkin. Du kan även söka efter en befattning efter befattnings-ID eller efter namnet på den medarbetare som tilldelats befattningen. Befattninghierarkin är en organisationshierarki.

## <a name="labor-union"></a>Fackförening

Du kan registrera om det krävs ett fackföreningsavtal för befattningen samt vilken fackförening som används. Du kan även associera avtalet med en juridisk person.

## <a name="financial-dimensions"></a>Ekonomiska dimensioner

När du skapar den ekonomiska dimensionen för en befattning måste du ange en juridisk person. Du kan välja standarddimensioner individuellt för varje dimension. Du kan också välja en distributionsmall om du automatiskt vill fylla i standarddimensioner. En fördelningsmall ger också möjlighet att tilldela belopp över flera dimensionsvärden.
