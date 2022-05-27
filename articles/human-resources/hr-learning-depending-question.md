---
title: Skapa en fråga beroende av svaret på den föregående frågan
description: Med villkorsstyrda frågor kan du ange vilken uppföljningsfråga som ska visas för en svarande, baserat på svaret på föregående fråga.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree, HcmLearningWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b2f7d55b577478f3156a8299fc2f827ab3bb60f1
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686094"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a>Skapa en fråga beroende av svaret på den föregående frågan


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Med villkorsstyrda frågor kan du ange vilken uppföljningsfråga som ska visas för en svarande, baserat på svaret på föregående fråga. Om du till exempel frågar "Föredrar du kaffe eller te”, kan en logisk uppföljningsfråga fastställas beroende på om den svarande väljer kaffe eller te som svar. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="find-the-existing-questionnaire"></a>Hitta den befintliga enkäten
1. Gå till **Enkät** > **Design** > **Enkäter**.
2. Välj enkäten WorkFH i listan.

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a>Lägg till alla frågor och underfrågor till enkäten
1. Klicka på **Frågor**.
2. Klicka på **Ny**.
3. I fältet **Fråga** väljer du fråga nummer 00016.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Klicka på **Spara**.
7. Stäng sidan.

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a>Ange enkätsekvensen till villkorsstyrd och gör frågan beroende av lämplig fråga
1. Klicka på **Redigera**.
2. Expandera avsnittet **Inställningar**.
3. I fältet **Frågeordning** väljer du "Villkor".
4. Klicka på frågan **Villkor**.
5. Välj ”Frågor\varför du besvarade föregående fråga sätt som du gjorde?" i trädet.
6. I fältet **Primär fråga** väljer du fråga 00009.
7. Klicka på länken på den valda raden i listan.
8. I fätlet **Svar** anger du ID för svarsserie för det svarsalternativ som du vill göra frågan beroende av. Ange till exempel 1 för det första svarsalternativet.
9. Klicka på **Spara**.
10. Välj "Frågor\Jag betalas rättvist för det arbete jag gör” i trädet.
    * Observera att frågeträdet har uppdateras för att visa beroendet.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
