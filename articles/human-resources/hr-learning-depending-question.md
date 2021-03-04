---
title: Skapa en fråga beroende av svaret på den föregående frågan
description: Med villkorsstyrda frågor kan du ange vilken uppföljningsfråga som ska visas för en svarande, baserat på svaret på föregående fråga.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMCollection, KMCollectionQuestion, KMCollectionQuestionTree, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4295b49336ec7ac3cff4deba675bc63511be48de
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420659"
---
# <a name="make-a-question-dependent-on-the-answer-of-the-previous-question"></a>Skapa en fråga beroende av svaret på den föregående frågan



Med villkorsstyrda frågor kan du ange vilken uppföljningsfråga som ska visas för en svarande, baserat på svaret på föregående fråga. Om du till exempel frågar "Föredrar du kaffe eller te”, kan en logisk uppföljningsfråga fastställas beroende på om den svarande väljer kaffe eller te som svar. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="find-the-existing-questionnaire"></a>Hitta den befintliga enkäten
1. Gå till Enkät > Design > Enkäter.
2. Välj enkäten WorkFH i listan.

## <a name="add-all-questions-and-sub-questions-to-the-questionnaire"></a>Lägg till alla frågor och underfrågor till enkäten
1. Klicka på Frågor.
2. Klicka på Ny.
3. Välj fråga nummer 00016 i fältet Fråga.
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
6. Klicka på Spara.
7. Stäng sidan.

## <a name="set-the-questionnaire-sequence-to-conditional-and-make-the-question-dependent-on-the-appropriate-question"></a>Ange enkätsekvensen till villkorsstyrd och gör frågan beroende av lämplig fråga
1. Klicka på Redigera.
2. Expandera avsnittet Inställningar.
3. Välj "Villkor" i fältet Frågeordning.
4. Klicka på Villkorsfråga.
5. Välj ”Frågor\varför du besvarade föregående fråga sätt som du gjorde?" i trädet.
6. Välj fråga 00009 i fältet Primär fråga
7. Klicka på länken på den valda raden i listan.
8. Ange svarssekvens-ID för det svarsalternativ som du vill göra frågan beroende av i fältet Svar. Ange till exempel 1 för det första svarsalternativet.
9. Klicka på Spara.
10. Välj "Frågor\Jag betalas rättvist för det arbete jag gör” i trädet.
    * Observera att frågeträdet har uppdateras för att visa beroendet.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]