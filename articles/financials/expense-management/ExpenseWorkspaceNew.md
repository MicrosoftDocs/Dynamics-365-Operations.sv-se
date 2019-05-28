---
title: Utgiftsrapporter på nytt sätt
description: Det här ämnet ger information om den omdesignade och omarbetade upplevelsen för registrering av utgiftsrapport i Microsoft Dynamics 365 for Finance and Operations. Den nya upplevelsen förenklar processen för utgiftsrapporter som slutförs och minskar tiden som krävs.
author: ryansandness
manager: AnnBe
ms.date: 05/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: ryansand
ms.search.validFrom: 2019-6-30
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 3039cda3f2cf9259ca06207bdf941bc6b0fb28e1
ms.sourcegitcommit: be447fc81bc874982bc0185fcb4d87d99bd742c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538710"
---
# <a name="expense-reports-reimagined"></a>Utgiftsrapporter på nytt sätt

[!include[banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Registrering av utgiftsrapport har blivit omformad för att förenkla processen att fylla utgiftsrapporter och minska tiden som krävs. Här är de viktigaste komponenterna i den nya utgiftsupplevelsen:

- En ny arbetsyta för utgiftshantering som låter dig komma åt dina ombuds utgifter.
- En ny kvittomatchning som gör det enklare att visa kvitton på huvudnivå och förenkla processen att koppla kvitton till utgiftsrader.
- Ett nytt skrivskyddat rutnät där du kan visa många fler utgiftsrader och ytterligare kolumner med data. Nu kan du se alla specificerade och delade rader, tillsammans med deras överordnade utgifter.
- Ett förenklat fönster för redigering av utgifter.
- Omdefinierade fel, varningar och policymeddelanden för att garantera att du har rätt sammanhang för att förstå vad problemet är och hur du löser det. Microsoft har tagit bort många meddelanden som visades innan användarna hade möjlighet att slutföra sina uppgifter och åtgärdar problemen, t.ex. det ofullständiga specifikationsmeddelandet.
- En ny sida för att ange vilka fält som krävs av din organisation, vilka fält som är valfria och vilka fält som inte ska samlas in. På den här sidan kan du minska antalet fält som användarna måste ställa in.
- Ett nytt utseend och känsla för utgiftsrapporter så att rapporterna inte längre verkar vara som om de har utformats för redovisningspersonal.

Om du vill aktivera den nya upplevelsen använder du arbetsytan **Funktionshantering** för att aktivera för **Utgiftsrapporter på nytt sätt**. När du aktiverar den här funktionen utförs följande åtgärder:

- Den befintliga utgiftsarbets ytan ersätts med den nya arbetsytan.
- Ett nytt menyalternativ för utgiftsfältets synlighet läggs till.
- Inga befintliga meny alternativ för utgiftsrapporter (befintlig sida) eller utgiftsrapportfält tas bort.
- Arbetsflöden och eventuella godkännanden leder fortfarande till sidan för befintliga utgiftsrapporter.

## <a name="getting-started-video-for-new-users"></a>Komma igång-video för nya användare

Du kan titta på en kort video som visar huvudfunktionerna för utgiftsregistrering.

> [!NOTE]
> Videon är inte tillgänglig än. Det här avsnittet kommer att uppdateras när videon är tillgänglig.

## <a name="new-features"></a>Nya funktioner

| Ny funktion | Beskrivning |
|---|----|
| Synlighet för utgiftsfält | En ny installationssida låter dig ange vilka fält som ska inaktiveras för en organisation, vilka fält som ska fyllas i och vilka fält som rekommenderas. |
| Obligatoriska fält | Ny enkel konfiguration kan du göra några fält som krävs utan att behöva använda policyramen. |
| Valfria fält | En andra sida för valfria fält läggs till. På det här sättet känner inte medarbetarna att de måste ställa in fälten, men fälten är fortfarande lättillgängliga. |
| Lägg till ej bifogade kvitton | Möjligheten att lägga till ej bifogat kvitto till utgiftsrapport är mer synlig från arbetsytan och utgiftsrapporten. |
| Förbättrad meddelandehantering | Det finns bättre insyn i utgiftsrader som innehåller varningar eller fel. |
| Minska meddelanden i meddelandefältet| Antalet meddelanden i informationsloggen minskades och en ansträngning gjordes för att förhindra att dubbla meddelanden visas i många fall. |
| Gemensamma åtgärder grupperade tillsammans | Gränssnittet rensades med tillägget av en ny åtgärdsknapp för de flesta vanliga åtgärder på radnivå och tillägg av en ellips-knapp (...) för sidhuvud och andra mindre frekventa åtgärder. |
| Ny arbetsyta för att öka synligheten | En ny arbetsyta förenar funktioner och länkar som gör att användarna kan flytta till olika områden. |
| Lägg till befintliga utgifter och inleveranser under skapande av utgifter | När du skapar utgiftsrapporter kan du lägga till alla eller valda utgifter och kvitton. |
| Kalkylator för valutakurs | En kalylator för valutakurs läggs till där du kan beräkna valutakursen för kontanttransaktioner i flera valutor. |
| Spara och lägg till nya utgiftsrader | Knapparna **Spara** och **Ny** finns tillgängliga när nya utgifter anges, för att hjälpa dig att snabbt ange utgiftsrader. |
| Bättre synlighet i delade och specificerade rader | Specificerade och delade rader läggs direkt till i utgiftslistan för att öka synligheten och hjälpa dig att enkelt avgöra om det finns policyfel eller andra fel. |
| Visa inleveranser under specifikation | Inleveranser kan visas under specifikation. |

Den första versionen är inriktad på scenarier för utgiftsregistrering. Eventuell kostnadsrapportrapport eller godkännande scenario fortsätter att använda den existerande utgiftspostsidan.

Följande funktioner finns på den befintliga sidan men finns ännu inte på den nya sidan. De här funktionerna kommer att återinföras under de följande flera versionerna:

- Godkännanden
- Godkännande av leverantörsreskontra och möjligheten att redigera redovisningen
- Flera startpunkter
- Integrering av reserekvisition
- Dataenhet för synlighet för utgiftsfält
- Inmatning för traktamentsutgifter
- Arbetsflöde på radnivå
- Stöd för provisoriska godkännanden
- Avancerad specifikation
