---
title: "Arbetsflödeselement"
description: "Den här artikeln beskriver de olika elementen som utgör ett arbetsflöde."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 56441
ms.assetid: de740262-6ffd-42b9-a325-540eae5cec94
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 05a35e91d3e502309c42c85960b5b1e2025f0e6e
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="workflow-elements"></a>Arbetsflödeselement

[!include[banner](../includes/banner.md)]


Den här artikeln beskriver de olika elementen som utgör ett arbetsflöde.

Ett arbetsflöde består av olika element, t.ex. De olika avsnitten som följer beskriver varje typ av element.

## <a name="tasks"></a>Uppgifter
En *uppgift* är en arbetsenhet som måste utföras. Två typer av uppgifter kan läggas till i ett arbetsflöde: manuella uppgifter och automatiska uppgifter.

### <a name="manual-task"></a>Manuell uppgift

En *manuell uppgift* är en arbetsenhet som måste utföras av en användare. Till exempel kan en utgiftsrapport arbetsflöde ha manuella uppgifter som kräver att de tilldelade användarna utför följande åtgärder:

-   Granska de inleveranser som skickas in tillsammans med en utgiftsrapport.
-   Kontakta en medarbetares chef.

### <a name="automated-task"></a>Automatisk uppgift

En *automatisk uppgift* är en arbetsenhet som måste utföras av systemet. Ingen mänsklig interaktion krävs. Till exempel kan ett arbetsflöde med en försäljningsorder ha automatiska uppgifter som kräver att systemet utför följande åtgärder:

-   Utför en kreditkontroll.
-   Skapa en kundpost för kunden, om en post inte redan finns.

## <a name="approval-processes"></a>Godkännandeprocess
En *godkännandeprocess* är en process som består av separata steg. I varje godkännandesteg kan användaren utföra följande åtgärder:

-   Godkänna dokumentet.
-   Avvisa dokumentet.
-   Begära en ändring av dokumentet.
-   Tilldela en annan användare dokumentet för godkännande.

## <a name="lineitem-workflow-elements"></a>Arbetsflödeselement för radartikel
Ett arbetsflöde kan skapas för att bearbeta antingen dokument eller radartiklarna på ett dokument. Om du till exempel har skapat ett arbetsflöde för godkännande för tidrapporter. (Du refererar till arbetsflödet som *dokumentarbetsflöde*.) Du kan lägga till ett element för *arbetsflöde för radartikel* till det dokumentarbetsflödet. När elementet för radartikeln körs, skickas varje radartikel på dokumentet in för bearbetning. Du kan vilja att alla radartiklar bearbetas av samma radartikelarbetsflöde, eller du kanske vill att varje radartikel kan bearbetas i ett annat arbetsflöde för radartikel. Tänk dig att en medarbetare har skickat in en tidrapport som liknar följande bild. ![Arbetsflöde med radartiklar](./media/workflow_lineitemworkflow.gif) I detta scenario kanske du vill skapa följande rarbetsflöden för radartiklar:

-   **Arbetsflöde för radartikel 1** – Det här arbetsflödet används för att bearbeta artiklar där projekt-ID är 1111.
-   **Arbetsflöde för radartikel 2** – Det här arbetsflödet används för att bearbeta artiklar där projekt-ID är 2222.
-   **Arbetsflöde för radartikel 3** – Det här arbetsflödet används för att bearbeta artiklar där projekt-ID är 3333.

## <a name="flowcontrol-elements"></a>Flödeskontrollelement
Följande element låter dig designa arbetsflöden som har alternativa förgreningar eller förgreningar som körs samtidigt.

### <a name="manual-decision"></a>Manuellt beslut

Ett *manuellt beslut* är en punkt där ett arbetsflöde delas i två förgreningar. En användare måste ta ett beslut, och detta beslut bestämmer vilken förgrening som används för att bearbeta dokumentet som skickats in.

### <a name="conditional-decision"></a>Villkorligt beslut

Ett *villkorligt beslut* är också en punkt där ett arbetsflöde delas i två förgreningar. Men systemet bestämmer vilken förgrening som används för att bearbeta dokumentet som skickats in. För att fatta detta beslut utvärderar systemet dokumentet för att avgöra om det uppfyller angivna villkor.

### <a name="parallel-activity"></a>Parallell aktivitet

En *parallell aktivitet* är ett arbetsflödeselement som inkluderar två eller flera arbetsflödesgrenar som körs samtidigt.

### <a name="subworkflow"></a>Delarbetsflöde

Ett *delarbetsflöde* är ett arbetsflöde som körs i ett annat arbetsflödes sammanhang.




