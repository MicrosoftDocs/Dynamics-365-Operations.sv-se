---
title: Skapa enkäter
description: Den här artikeln beskriver processen för att skapa en enkät. Det första steget är att utforma enkäten. Om du utformar en enkät skapar du inte bara frågorna och svaren, utan även strukturen som gör det möjligt att registrera och ordna svar i tabeller.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KCMCollectionType, KMAnswerCollection, KMCollection, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 17341
ms.assetid: b27e2f12-c7a0-4a54-b8d8-17819f8a1c72
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 3f7f7d68caf12c33059d2f871fe3f4a036c89f35
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115136"
---
# <a name="create-questionnaires"></a>Skapa enkäter

Den här artikeln beskriver processen för att skapa en enkät. Det första steget är att utforma enkäten. Om du utformar en enkät skapar du inte bara frågorna och svaren, utan även strukturen som gör det möjligt att registrera och ordna svar i tabeller. 

En noggrant utformad enkät ökar kvaliteten på informationen som du samlar in. Med noggrann utformning är det lättare att du välja lämpliga alternativ vid en lämplig tidpunkt för en enkät. Följande punkter kan hjälpa dig att planera en effektiv enkät:

-   Definierar tydligt syftet med enkäten för att garantera att frågorna stöder syftet.
-   Bestäm vilken person eller vilken grupp personer som du vill ska fylla i enkäten.
-   Skriv frågor som visas i enkäten och inkludera svarsalternativ om tillämpligt.
-   Kontrollera att enkäten är logiskt så att svarande förblir engagerade.
-   Ordna frågor och svar i den ordning som de visas för svarande.
-   Bestäm hur resultatet utvärderas, om tillämpligt.
-   Välj om du behöver ytterligare funktioner. Bestäm till exempel om och hur resultat kategoriseras, om det krävs en tidsgräns eller om alla frågor ska vara obligatoriska.

Designfasen innehåller fyra uppgiftskategorier du måste slutföra i följande ordning:

1.  Nödvändiga inställningar efter behov.
2.  Skapa svarsgrupper och svar, om tillämpligt.
3.  Skapa frågor och deras koppling till svarsgrupperna.
4.  Skapa själva enkäten och koppla frågor till den.

## <a name="prerequisites"></a>Krav
Vissa förutsättningar måste vara finnas innan du kan skapa enkäter, frågor och svar. Dock krävs inte alla förutsättningar för fullständig funktionalitet.

### <a name="required"></a>Obligatoriskt

| Förutsättning        | Beskrivning                |
|---------------------|----------------------------|
| Enkättyper | Kategorisera enkäter. |
| Frågetyper      | Kategorisera frågor.      |

### <a name="optional"></a>Valfri

| Förutsättning             | Beskrivning                                                    |
|--------------------------|----------------------------------------------------------------|
| Enkätparametrar | Ändra grundläggande kontroller och standardinställningar för enkäter. |

### <a name="questionnaire-types"></a>Enkättyper

Enkättyper krävs och måste ha tilldelats när du skapar en enkät. Enkättyper hjälpa dig att hantera och klassificera enkäter enklare. Använd enkättyper för att klassificera enkäter och skilja dem från varandra. Om du till exempel har flera enkäter att välja bland, kan du filtrera dem efter typ för att göra det enklare att hitta en viss enkät. Här följer några exempel på enkättyper:

-   Personalutveckling
-   Kundenkäter
-   Granska process

### <a name="question-types"></a>Frågetyper

Frågetyper krävs och måste ha tilldelats när du skapar en fråga. 

Använd frågetyper om du vill kategorisera frågor för rapportering. Frågetyper gör det även enklare att hitta frågor, eftersom du kan använda typer som filter på sidan **Frågor**. Här följer några exempel på frågetyper:

-   Personal
-   Hantera affärer
-   Kursutvärdering

### <a name="questionnaire-parameters"></a>Enkätparametrar

Enkätparametrar är valfria. Du kanske inte använder dem, beroende på företagets behov. 

Enkätparametrar definierar anonymitet, nummerseriekoder och referenstyperna för en enkät. När en organisation distribuerar en enkät kan alternativet att låta svarande förbli anonyma vara viktigt. 

Nummerseriekoderna används för att ordna frågor och svar. Baserat på nummerserierkoderna tilldelas värden automatiskt till objekt. 

Du bör definiera alla parametrar innan du börjar skapa dina data. Du kan ändra enkätparameterinställningarna när som helst.

## <a name="questionnaire-components"></a>Enkätkomponenter
Frågeformulär består av tre huvuddelar: svarsgrupper som innehåller svaren på en flervalsfråga frågor, frågor i enkäten samt själva enkäten. Du kan även gruppera frågorna i en enkät i resultatgrupper. Resultatgrupper låter dig kategorisera frågor och tillhandahåller ytterligare analys i enkäten. 

[![QuestionnaireComponents](./media/questionnairecomponents-1024x615.png)](./media/questionnairecomponents.png)

### <a name="answer-groups-and-answers"></a>Svarsgrupper och svar

Svarande kan besvara en fråga på två sätt beroende på frågans ämne:

-   Öppna frågor kräver inte svar i ett specifikt format. Svarande svara med text, ett tal, ett datum eller en tid. Dessa frågor kräver vanligen att de svarande tillhandahåller subjektiv information i sina svar, till exempel en åsikt, en beskrivning, en värdering eller en uppskattning.
-   Stänga frågor kräver att den svarande väljer ett svar på en lista över möjliga svar.

Om du vill ge en lista med svar på stängda frågor kan du skapa svar på sidan **Svarsgrupper**. 

Svarsgrupper och svar är komponenter som utgör det huvudsakliga informationsmaterialet som frågor skapas från. När du har skapat en svarsgrupp kan du koppla svarsgruppen till en fråga i fältet **Svarsgrupp** på sidan **Frågor**. 

Samma svarsgrupp kan användas för flera frågor i samma enkät och kan också användas i flera enkäter. 

> [!NOTE]
> Om du ändrar svarstext i svarsgrupper som redan har använts i ifyllda enkäter, kan data bli svåra att utvärdera och enkätresultaten kanske inte gäller längre. Om du måste ändra en svarsgrupp bör du överväga att skapa en ny svarsgrupp i stället för att ändra en befintlig. Du kan inte radera svarsgrupper som har kopplats till en fråga eller ett svar eller som har besvarats.

### <a name="questions"></a>Frågor

En enkät måste innehålla frågor. Frågor kan vara antingen öppna eller stängda.

-   Svaren för öppna frågor kontrolleras inte och svarande kan skriva in sina svar.
-   Stängda frågor kräver en lista med fördefinierade svarsalternativ, och frågorna kan struktureras för att tillåta att svaranden väljer flera svar. Frågor bör utformas för att få fram specifik information från en svarande och måste vara länkade till en svarsgrupp som innehåller svarsalternativen för varje stängd fråga. 

    > [!NOTE]
    > Innan du kan skapa stängda frågor måste du skapa svarsgrupper och svar.

Frågor kan grupperas i en villkorsstyrd frågehierarki så att sekundära frågor beror på svaren som den svarande valde för föregående fråga. Du kan skriva frågorna först och sedan flytta ordna dem till en hierarki senare.

## <a name="setting-up-questionnaires"></a>Ställa in enkäter

> [!NOTE]
> Innan du kan ställa in en enkät måste du skapa frågor, svar och förutsättningar. 

För varje enkät kan du ange följande information:

-   Den totala tiden eller tidsgränsen för svar på obligatoriska frågor.
-   Om alla frågor är obligatoriska.
-   Att beräkna poäng i en enkät eller inte.
-   Hur du kategoriserar resultat.
-   Om enkäten ska vara tillgänglig för en begränsad grupp svarande.
-   Om en formulärmall visas som en bakgrund bakom varje sida i enkäten.
-   Ytterligare kommentarer som krävs för att klargöra avsikten med enkäten för de svarande.
-   Om du vill visa frågor i en viss ordningsföljd eller välja dem slumpvis från en pool.
-   Om frågor ställs endast om specifika svar har angetts för tidigare svar.

### <a name="set-up-a-questionnaire"></a>Ställ in en enkät

Den primära sidan som du använder för att ställa in en enkät är **Enkäter**. Ställ in en enkät genom att slutföra följande uppgifter i ordningsföljd:

1.  Skapa en enkät.
2.  Följ ett av dessa steg i för att koppla frågor till enkäten:
    -   Om du använder resultatgrupper kan du koppla frågor till en enkät genom att använda resultatgrupper. Ställ först in resultatgrupper för enkäten och lägg sedan till frågor till resultatgrupperna.
    -   Om du inte använder resultatgrupper kan du koppla frågor direkt till enkäten.

3.  Ställ in en hierarki för villkorsfrågor om en sådan krävs.
4.  Testa enkäten.

Klicka på **Validera** på sidan **Enkäter** för att testa om enkäten är korrekt sammanställd. Det är dock också praktiskt att fylla i enkäten och testa den själv innan du distribuerar den.

### <a name="modify-a-questionnaire"></a>Ändra en enkät

På sidan **Enkäter** kan du utföra följande uppgifter:

-   Redigera informationen i enkäten, inklusive resultatgrupper och frågor.
-   Radera och lägga till frågor.
-   Göra ändringar i resultgrupperna och sekvensnummer. 

> [!CAUTION]
> Var försiktig när du ändrar enkäter som redan har besvarats. Ändringar kan minska den statistiska noggrannheten och därigenom göra denna till en dålig grund för utvärdering. Överväg att hellre skapa en ny fråga istället för att ändra en fråga som redan har besvarats.

I en enkät kan du inte ta bort följande typer av frågor:

-   Frågor som har kopplats till en enkät
-   Frågor som har besvarats och därför redan visas i dialogrutan **Svar**.

### <a name="result-groups"></a>Resultatgrupper

Resultatgrupper är valfria när du kopplar frågor till en enkät. 

En resultatgrupp används för att beräkna poäng och kategorisera resultaten för en enkät. Om du använder resultatgrupper kan du utföra följande uppgifter:

-   Utvärdera enkätresultat baserat på poängstatistik.
-   Utvärdera den svarandes poäng för varje den resultatgrupp du ställer in.
-   Skapa statistik för varje resultatgrupp som hjälper dig att analysera resultaten.
-   Skriv ut en rapport som visar resultat för varje resultatgrupp och valfria poäng/texter som baseras på poäng som erhållits i varje resultatgrupp.

> [!NOTE]
> Innan du kan ställa in resultatgrupper måste du utföra följande uppgifter:

-   Skapa stängda frågor. För stängd fråga måste ange indatatypen på sidan **Frågor** vara **Kryssruta**, **Alternativknapp** eller **Kombinationsruta**.
-   Definiera poäng för svaren i svarsgrupperna som är tilldelade till varje fråga.
-   Ställ in en enkät.

Bifoga frågor till en enkät genom att använda resultatgrupper, genom att först lägga till resultatgrupper för enkäten och sedan lägga till frågor till resultatgrupperna. Om du inte använder resultatgrupper kan du koppla frågor direkt till enkäten. 

Du kan skapa flera resultatgrupper för att bedöma hur många poäng som en svarande har i respektive kategori. När en enkät har slutförts kan du visa hur många poäng som har uppnåtts för varje resultatgrupp. 

> [!TIP]
> Om du vill utvärdera en enkät genom att använda poäng men inte separata kategorier, kan du lägga till alla frågor i en enskild resultatgrupp. 

För varje resultatgrupp kan du även skapa en eller flera poängbaserade meddelanden som svaranden får när denne har fyllt i en enkät. Texten som visas kan variera beroende på poängen som en svarande får i en resultatgrupp. Använd poängbaserade meddelanden genom att definiera poängintervall och en beskrivning av varje intervall. När en svarande uppnår en poäng i ett speciellt intervall inkluderas texten för det intervallet i resultatrapporten. 

Eftersom en resultatgrupp är relaterad till de poäng som är kopplade till specifika frågeuppsättningar i en enkät, kan du endast använda en viss resultatgrupp för en enkät.

#### <a name="example-pointstexts-for-result-group-3"></a>Exempel: Poäng/texter för resultatgrupp 3

Du använder en enkät för ett ledarskapstest som har 15 frågor i tre kategorier. Du skapar tre resultatgrupper och lägger till fem frågor till varje resultatgrupp. Poängen räknas sedan samman i de tre grupperna. De tre resultatgrupper är följande:

-   Kreativa förmågor
-   Ledarskapsförmågor
-   Tekniska förmågor

Om du vill använda poängbaserade meddelanden, ställer du in textintervall för varje resultatgrupp. Varje fråga tilldelas två poäng. Därför är 10 den maximala poängsumman i respektive resultatgrupp. 

Följande tabell visar de poängbaserade meddelanden som du definierar i resultatgruppen "ledarskapsförmågor".

| Poängintervall | Text                                       |
|----------------|--------------------------------------------|
| 1 till 3         | Du har genomsnittliga ledarskapförmågor.     |
| 4 till 7         | Du har goda ledarskapförmågor.        |
| 8 till 10        | Du har utmärkta ledarskapförmågor. |

Du kan ställa in poängintervall och texter för varje resultatgrupp i en enkät. Texter som motsvarar respektive svarandes poäng visas för varje resultatgrupp. 

> [!NOTE]
> Du kan ändra intervall och texter. Om en enkät har fyllts i kan dock ändringar orsaka skillnader mellan föregående och nya resultatrapporter.

### <a name="conditional-question-hierarchies"></a>Hierarkier med villkorsfrågor

Hierarkier med villkorsfrågor är valfria när du skapar en enkät. 

> [!NOTE]
> Innan du kan skapa en hierarki för villkorsfrågor måste du koppla frågor som har tilldelade svarsgrupper till enkäten. 

Villkorsfrågor gör det möjligt att skapa en frågehierarki i en enkät och att skapa en ordningsföljd för hur frågorna presenteras beroende på svaret den svarande valde för respektive fråga. Genom att på detta sätt basera frågesekvensen på svaren kan du ändra enkäten medan den svarande svarar på den.

#### <a name="examples"></a>Exempel

En juridisk person erbjuder både artiklar och tjänster till sina kunder. Såsom inträffar normalt i sådana fall köper en del kunder endast artiklar, andra bara tjänster, och en del köper både artiklar och tjänster. Om företaget skickar ut en enkät om kundnöjdhet, använder det en villkorsstruktur i enkäten så att kunder som endast köper tjänster slipper att svara på frågor om artiklar. 

Alternativt kan du skapa en enkät så att om den svarande väljer Svar A på fråga 1 är fråga 2 är nästa fråga i frågesekvensen. Om svarande väljer svar B på fråga 1 följs den av fråga 5.