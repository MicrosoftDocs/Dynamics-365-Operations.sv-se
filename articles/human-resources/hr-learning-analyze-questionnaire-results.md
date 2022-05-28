---
title: Analysera enkätresultat
description: Enkätstatistiken kan användas för att beräkna medelvärde, summor och procentsatser som baseras på en uppsättning demografiska data.
author: twheeloc
ms.date: 08/26/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMQuestionnaireStatistics, KMQuestionnaireStatisticsLine, HcmLearningWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1da18dd32363308438b7f9da5b2e04e119e840cb
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692931"
---
# <a name="analyzing-questionnaire-results"></a>Analysera enkätresultat


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Enkätstatistiken kan användas för att beräkna medelvärde, summor och procentsatser som baseras på en uppsättning demografiska data. Starta proceduren genom att gå till **Enkät** > **Visa och analysera resultat** > **Enkätstatistik**. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-a-questionnaire-statistics-record"></a>Skapa en enkätstatistikpost
1. Gå till **Enkätsstatistik**.
2. Klicka på **Ny**.
3. Markera vald rad i listan.
4. Skriv ett värde i fältet **Statistik**.
5. I fältet **Beskrivning** anger du ett värde.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet **Enkät**.
7. Klicka på länken på den valda raden i listan.
8. Klicka på fliken **Allmänt**.
    * Välj om du vill inkludera anonyma resultat eller resultat från arbetare, kontakter och sökande.  
9. Markera eller avmarkera kryssrutan **Arbetare**.
    * Om du ska visa resultaten efter tjänsteålder eller ålder, anger du de intervall som du vill använda för att gruppera resultatet.  
    * Om du anger 5 för åldersintervallet grupperas resultaten baserat på femårsintervall.  
10. Ange ett nummer i fältet **Ålder**.
    * Välj om du vill köra beräkningen mot hela enkäten, för varje resultatgrupp, för varje fråga eller för varje frågerad.  
    * Välj hur du vill gruppera resultaten.  
    * Om du till exempel beräknar medelpoäng per fråga kanske du vill se frågorna grupperade efter resultatgrupp.  
    * Välj de data som beräkningen ska baseras på.  
    * Om du till exempel vill se den genomsnittsprocent som har tagits emot i enkäten hos dina arbetare kontra det genomsnittliga antal poäng som har tagits emot hos dina arbetare.  
11. Klicka på fliken **Sortiment**.
    * Använd intervall för att begränsa resultatuppsättningen till endast de som uppfyller intervallkriterierna.  
12. Klicka på fliken **Gruppera efter**.
    * Använd grupperingarna för att ange hur resultatet ska visas.  
    * Du kan till exempel gruppera resultaten först efter kön och sedan efter ålder.  
13. Hitta och markera önskad post i listan.
    * Flytta grupperingarna till sidan **Valda** och placera dem i önskad ordning.  

## <a name="execute-the-statistics-calculation"></a>Utför statistikberäkningen
1. Klicka på **Kör**.
    * Välj vilken beräkningsfunktion som du vill utföra på resultaten.  
    * Beräkna till exempel genomsnittsprocent för enkäten för de valda grupperingarna eller summera poängen över resultatgrupper för de valda grupperingarna.  
2. Markera eller avmarkera kryssrutan **Radera tidigare sökningar**.
3. Klicka på **OK**.

## <a name="view-the-results-of-the-questionnaire-statistics-run"></a>Visa resultaten av enkätstatistikkörningen.
1. Klicka på **Resultat**.
2. Klicka på **Resultat**.
3. Stäng sidan.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
