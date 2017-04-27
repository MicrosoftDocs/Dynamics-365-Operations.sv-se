---
title: "Skapa ett arbetsflöde"
description: "Det här avsnittet innehåller information om hur du skapar ett arbetsflöde."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Core
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 1255cf90498f1968568dd2fa5a1377d989f40182
ms.lasthandoff: 03/31/2017


---

# <a name="create-a-workflow"></a>Skapa ett arbetsflöde

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller information om hur du skapar ett arbetsflöde.

<a name="open-the-workflow-editor"></a>Öppna arbetsflödesredigeraren
------------------------

Den Microsoft Dynamics 365 for Operations-modul som du arbetar i bestämmer vilka typer av arbetsflöden som du kan skapa. Gör på följande sätt för att välja vilken typ av arbetsflöden du vill skapa, och öppna arbetsflödesredigeraren.

1.  Öppna den modul som du vill skapa ett nytt arbetsflöde för. Om du till exempel vill skapa ett arbetsflöde för inköpsrekvisitioner, klicka då på **Procurement and sourcing**.
2.  Klicka på **Inställningar** &gt; **\[Modulnamn\] arbetsflöden**.
3.  Klicka på **New** i åtgärdsfönstret på den listsida som visas.
4.  På sidan **Create workflow** väljer du den typ av arbetsflöde som du vill skapa, och klickar sedan på **Create workflow**. Arbetsflödesredigeraren visas. Du kan nu använda följande procedurer när du skapar arbetsflödet.

## <a name="drag-workflow-elements-onto-the-canvas"></a>Dra arbetsflödeselementen till arbetsytan
Området **Workflow elements** i arbetsflödesredigeraren innehåller de element som du kan lägga till i ditt arbetsflöde. Dra element till arbetsflödet om du vill lägga till dem i arbetsflödet.

## <a name="connect-the-elements"></a>Anslut elementen
Om du vill koppla ett arbetsflödeselement till ett annat håller du pekaren över elementet tills kopplingspekaren visas. Klicka på en kopplingspunkt och dra den till det andra elementet. Kontrollera att du ansluter alla element.

## <a name="configure-the-properties-of-the-workflow"></a>Konfigurera egenskaperna för arbetsflödet
Använd följande steg när du vill konfigurera egenskaperna för arbetsflödet.

1.  Klicka på arbetsytan för att försäkra dig om att inget arbetsflödeselement är markerat.
2.  Klicka på **Properties** för att öppna sidan **Properties** för arbetsflödet.
3.  Följ procedurerna i ämnet [Configure the properties of a workflow](configure-workflow-properties.md).

## <a name="configure-the-elements-of-the-workflow"></a>Konfigurera elementen i arbetsflödet
Konfigurera varje element som du har dragit till arbetsytan. För information om hur du konfigurerar respektive arbetsflödeselement, se följande ämnen:

-   [Konfigurera en manuell uppgift](configure-manual-task-workflow.md)
-   [Konfigurera en automatisk uppgift](configure-automated-task-workflow.md)
-   [Konfigurera en godkännandeprocess](configure-approval-process-workflow.md)
-   [Konfigurera ett godkännandesteg](configure-approval-step-workflow.md)
-   [Konfigurera ett manuellt beslut](configure-manual-decision-workflow.md)
-   [Konfigurera ett villkorsbeslut](configure-conditional-decision-workflow.md)
-   [Konfigurera en parallell aktivitet](configure-parallel-activity-workflow.md)
-   [Konfigurera en parallell gren](configure-parallel-branch-workflow.md)
-   [Konfigurera ett arbetsflöde för radartiklar](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a>Lösa eventuella fel eller varningar
Fönstret **Errors and warning** i nedre delen av arbetsflödesredigeraren visar meddelanden som har skapats för arbetsflödet. Dubbelklicka på felet eller varningsmeddelandet för att hitta det element där en varning eller ett fel har inträffat. Du måste åtgärda alla fel och varningar innan du kan aktivera arbetsflödet.

## <a name="save-and-activate-the-workflow"></a>Spara och aktivera arbetsflödet
Följ dessa steg när du är redo att spara och aktivera arbetsflödet.

1.  Klicka på **Save and close** för att stänga redigeraren för arbetsflöde och öppna sidan **Save workflow**.
2.  Ange kommentarer om de ändringar som du har genomfört på arbetsflödet, och klicka sedan på **OK**.
3.  Om alla fel och varningar har lösts, visas sidan **Activate workflow**. Välj ett av följande alternativ:
    -   Klicka på **Activate the new version** för att aktivera denna version av arbetsflödet. När ett arbetsflöde är aktivt kan användare skicka dokument till det för bearbetning.
    -   Klicka på **Do not activate the new version** om du inte vill aktivera denna version. Du kan aktivera arbetsflödet senare.






