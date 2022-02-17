---
title: Generera ACA-rapporter (Affordable Care Act)
description: Sjukförsäkringsrapportering genererar formulär 1095-B och 1095-C till stöd för delen **Arbetsgivarmandat** i sjukförsäkringen.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c8f336e31e77391ef7e2bc2dca901e6a78fbb914
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067011"
---
# <a name="generate-aca-reports"></a>Generera ACA-rapporter


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Sjukförsäkringsrapportering genererar formulär 1095-B och 1095-C till stöd för delen **Arbetsgivarmandat** i sjukförsäkringen.

> [!NOTE]
> Sjukförsäkringsrapportering är bara aktiverad för juridiska personer i USA.

## <a name="getting-started"></a>Komma igång

Om du vill spåra information för formulären 1095-B och 1095-C måste du först skapa en eller flera disponeringsgrupper för sjukförsäkring. Disponeringsgrupper för sjukförsäkring indikerar:

- Täckningserbjudande för en medarbetare
- Medarbetarens andel av den lägsta månadspremien, om kostnaden överstiger den federala fattigdomsgränsen
- Skyddsramar som används av arbetsgivaren, om tillämpligt

Med täckningsgrupper för sjukförsäkring kan du hantera information för dessa fält utan att behöva ändra varje enskild medarbetarpost där villkoren är desamma. Du kan enkelt tilldela sjukförsäkringsskyddsgrupper till en eller flera anställda med hjälp av funktionen för **masstilldelning** på sidan.

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a>Underhålla flera versioner av en försäkringsskyddsgrupp

Du kan underhålla flera versioner av valfri försäkringsskyddsgrupp. Med den här funktionen kan du göra ändringar utan att behöva skapa en ny grupp och tilldela om medarbetare till den. 

När du har skapat täckningsgrupper för sjukförsäkring kan du masstilldela grupperna till medarbetare med alternativet **Masstilldelning**. Du kan också enskilt ange om du vill spåra och rapportera sjukförsäkringsinformation, samt tilldela en medarbetare till en disponeringsgrupp för sjukförsäkring.

Du behöver inte spåra viss täckningsinformation för sjukförsäkring, till exempel för deltidsanställda. Ange i det här fallet fältet **Rapportomfattning** som **Nej**. Även om du måste tilldela varje enskild medarbetare spårbar sjukförsäkringsinformation till en täckningsgrupp för sjukförsäkring, kan du ändå ändra följande alternativ för månader med olika värden:

- **Erbjudande om försäkringsskydd**
- **Medarbetarens del av kostnaden**
- **Safe Harbor**

Om du vill ange undantag för värden för täckningsgrupper för sjukförsäkring väljer du länken **Sjukförsäkringstäckning** på sidan **Medarbetardetaljer** under avsnittet **Ytterligare information** på **Anställningsfliken**.

## <a name="reporting-health-care-coverage"></a>Rapportering av hälsovårdstäckning

Förutom att spåra vad händer om någon sjukförsäkringstäckning erbjudits till heltidsanställda, måste ytterligare information redovisas på 1095-C om arbetsgivaren erbjuder arbetsgivarsponsrad, självförsäkrad hälsotäckning som medarbetaren är anmäld för (oavsett om deras anställningsstatus är heltid eller deltid). Varje medarbetare (inklusive beroende) som omfattas av arbetsgivarsponsrade förmånsplaner måste inkluderas i rapporten för de månader som de omfattades. 

Du kan ange huruvida varje förmånsplan måste rapporteras genom att välja kryssrutan **Rapportera till sjukförsäkring**.

Om medarbetare har valt att låta något beroende omfattas av en förmån anger du dessutom de datum då beroendet omfattades för samtliga anställda på sidan **Underhåll förmåner**. Om du vill indikera att beroendet täcks av förmånen väljer du knappen **Redigera** i åtgärdsfönstret på snabbfliken **Beroenden**.

På sidan **Datumhanterare för beroendetäckning** anger du de datum då beroenden omfattades av förmånen. Om du anger datum på den här sidan kommer kryssrutan **Täckning** automatiskt att markeras på sidan **Bibehåll förmåner**.

## <a name="generate-1095-b-and-1095-c-forms"></a>Generera 1095-B- och 1095-C-formulär

Du kan också skapa 1095-B- och 1095-C-formulär inifrån själva produkten och distribuera dessa till var och en av dina medarbetare. Systemet kan också elektroniskt generera 1095-C-formulär och överföringsfilerna för 1094-C IRS.  

När du genererar formuläret 1095-C anger du lämpligt taxeringsår och om personnummer ska döljas. Om du skriver ut formulär 1095-C till mer än 500 anställda får du mer än en PDF-fil. Det’s rekommenderas att du ökar **Största filstorlek** i fönstret **Dokumenthanteringsparametrar** till 150 MB.

## <a name="viewing-information"></a>Visa information

Du kan använda sidan **Affordable Care-täckning för arbetstagare** om du vill se vilka medarbetare som har tilldelats respektive försäkringsskyddsgrupp, vilka medarbetare som inte behöver ingå i en rapport, samt vilka medarbetare som inte har tilldelats.

Om något av standardvärdena från täckningsgruppen för sjukförsäkring har åsidosatts, visas en asterisk bredvid värdet som har ändrats. Om värdena för alla 12 månader är desamma och inte har åsidosatts, anges värdet i kolumnen **Samtliga 12 månader**.

Du kan också använda förfrågningsfönstret för att förstå vilka medarbetare som har flaggats som icke-pliktiga för sjukförsäkring. Du behöver inte spåra huruvida täckning erbjudits dem, och du behöver heller inte utfärda 1095-C till dem vid årets slut. Välj **Icke-pliktig för sjukförsäkring** i fältet **Filtrera efter** om du vill generera en lista över alla anställda som inte får ett 1095-C.

Du kan dessutom visa de anställda som inte har tilldelats (fältet **Rapporttäckning för sjukförsäkring** är tomt) eller de som har tilldelats till en täckningsgrupp för sjukförsäkring som har löpt ut för året som valts i fältet **År**.

Du kan exportera listor över medarbetare som har skapats med något av filtreringsalternativen till Excel.

Om du behöver rapportera täckta personer eftersom du tillhandahåller självförsäkrad täckning, kan du visa alla beroende personer som omfattas av förmånsplaner och som har markerats som **pliktiga för sjukförsäkring**. Välj **Visa beroendetäckning** i åtgärdsfältet.

> [!NOTE]
> Endast förmånsplaner markerade som **sjukförsäkringspliktiga** visas i förfrågningsfönstret.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
