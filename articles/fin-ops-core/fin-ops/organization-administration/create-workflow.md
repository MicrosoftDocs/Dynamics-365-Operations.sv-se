---
title: Skapa arbetsflöden – översikt
description: Det här ämnet förklarar hur du skapar ett arbetsflöde.
author: ChrisGarty
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom:
- "195583"
- intro-internal
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: 1343061ba06d13e68a98b05c013867af0a4d07a6
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864498"
---
# <a name="create-workflows-overview"></a>Skapa arbetsflöden – översikt

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Det här ämnet förklarar hur du skapar ett arbetsflöde.

## <a name="open-the-workflow-editor"></a>Öppna arbetsflödesredigeraren

Den modul som du arbetar i bestämmer vilka typer av arbetsflöden som du kan skapa. Gör på följande sätt för att välja vilken typ av arbetsflöden du vill skapa, och öppna arbetsflödesredigeraren.

1. Öppna den modul som du vill skapa ett nytt arbetsflöde för. Om du till exempel vill skapa ett arbetsflöde för inköpsrekvisitioner, klicka då på **Anskaffning och källa**.
2. Klicka på **Inställningar** &gt; **\[Modulnamn\] arbetsflöden**.
3. Klicka på **Nytt** i åtgärdsfönstret på den listsida som visas.
4. På sidan **Skapa arbetsflöde** väljer du den typ av arbetsflöde som du vill skapa, och klickar sedan på **Skapa arbetsflöde**. Arbetsflödesredigeraren visas. Du kan nu använda följande procedurer när du skapar arbetsflödet.

## <a name="drag-workflow-elements-onto-the-canvas"></a>Dra arbetsflödeselementen till arbetsytan

Området **Arbetsflödeselement** i arbetsflödesredigeraren innehåller de element som du kan lägga till i ditt arbetsflöde. Dra element till arbetsflödet om du vill lägga till dem i arbetsflödet.

## <a name="connect-the-elements"></a>Anslut elementen

Om du vill koppla ett arbetsflödeselement till ett annat håller du pekaren över elementet tills kopplingspekaren visas. Klicka på en kopplingspunkt och dra den till det andra elementet. Kontrollera att du ansluter alla element.

## <a name="configure-the-properties-of-the-workflow"></a>Konfigurera egenskaperna för arbetsflödet

Använd följande steg när du vill konfigurera egenskaperna för arbetsflödet.

1. Klicka på arbetsytan för att försäkra dig om att inget arbetsflödeselement är markerat.
2. Klicka på **Properties** för att öppna sidan **Properties** för arbetsflödet.
3. Följ procedurerna i ämnet [Konfigurera egenskaper för arbetsflöde](configure-workflow-properties.md).

## <a name="configure-the-elements-of-the-workflow"></a>Konfigurera elementen i arbetsflödet

Konfigurera varje element som du har dragit till arbetsytan. För information om hur du konfigurerar respektive arbetsflödeselement, se följande ämnen:

- [Konfigurera manuella uppgifter i ett arbetsflöde](configure-manual-task-workflow.md)
- [Konfigurera automatiska uppgifter i ett arbetsflöde](configure-automated-task-workflow.md)
- [Konfigurera godkännandeprocesser i ett arbetsflöde](configure-approval-process-workflow.md)
- [Konfigurera godkännandesteg i ett arbetsflöde](configure-approval-step-workflow.md)
- [Konfigurera manuella beslut i ett arbetsflöde](configure-manual-decision-workflow.md)
- [Konfigurera villkorsbeslut i ett arbetsflöde](configure-conditional-decision-workflow.md)
- [Konfigurera parallella grenar i ett arbetsflöde](configure-parallel-activity-workflow.md)
- [Konfigurera en parallell gren](configure-parallel-branch-workflow.md)
- [Konfigurera arbetsflöden för radartiklar](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a>Lösa eventuella fel eller varningar

Fönstret **Errors and warning** i nedre delen av arbetsflödesredigeraren visar meddelanden som har skapats för arbetsflödet. Dubbelklicka på felet eller varningsmeddelandet för att hitta det element där en varning eller ett fel har inträffat. Du måste åtgärda alla fel och varningar innan du kan aktivera arbetsflödet.

## <a name="save-and-activate-the-workflow"></a>Spara och aktivera arbetsflödet

Följ dessa steg när du är redo att spara och aktivera arbetsflödet.

1. Klicka på **Spara och stäng** för att stänga redigeraren för arbetsflöde och öppna sidan **Spara arbetsflöde**.
2. Ange kommentarer om de ändringar som du har genomfört på arbetsflödet, och klicka sedan på **OK**.
3. Om alla fel och varningar har lösts, visas sidan **Aktivera arbetsflöde**. Välj ett av följande alternativ:

    - Klicka på **Aktivera den nya versionen** för att aktivera denna version av arbetsflödet. När ett arbetsflöde är aktivt kan användare skicka dokument till det för bearbetning.
    - Klicka på **Aktivera inte den nya versionen** om du inte vill aktivera denna version. Du kan aktivera arbetsflödet senare.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]