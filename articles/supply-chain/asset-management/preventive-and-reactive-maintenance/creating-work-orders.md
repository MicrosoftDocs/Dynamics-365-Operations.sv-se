---
title: Skapa arbetsorder
description: Det här avsnittet innehåller förklaringar av hur du skapar arbetsorder i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 6e910b2400106baf9f9dc06f6bc0d3daee8e4a43
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570086"
---
# <a name="creating-work-orders"></a>Skapa arbetsorder

[!include [banner](../../includes/banner.md)]

 

När du har schemalagt förebyggande underhållsjobb är nästa steg att skapa arbetsorder för jobben. Det gör du i ett av underhållsschemana. De schemalagda jobben i ett underhållsschema kan ha olika referenstyper:

| Referenstyp | Beskrivning                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| Underhållsplaner     | Förebyggande underhållsjobb baserade på underhållsplanens typer "Tid" eller "Räknare".                       |
| Underhållsomgångar    | Förebyggande underhållsjobb som innehåller flera tillgångar som kräver en liknande typ av underhåll.           |
| Underhållsbegäran   | Manuellt skapad begäran om underhåll eller reparation av en tillgång, som kan konverteras till en arbetsorder. |


1. Klicka på **Tillgångshantering** > **Allmänt** > **Alla underhållsscheman** eller **Öppna rader för underhållsschema** eller **Öppna pooler för underhållsschema**.

2. Välj de schemalagda underhållsjobb som du vill skapa en arbetsorder för och klicka på **Arbetsorder**. I dialogrutan **Skapa arbetsorder** visas det totala antalet prognostimmar för de valda raderna i fältet **Prognostimmar för underhåll**.

3. I avsnittet **Parametrar** väljer du hur många arbetsorder du vill skapa. Du kan skapa en arbetsorder per underhållsschemarad eller ett antal arbetsorder utifrån dina val i avsnittet **En arbetsorder per**.

4. Välj en **arbetsordertyp** som ska användas på alla arbetsorder som du skapar. Illustrationen nedan visar ett exempel på dialogrutan **Skapa arbetsorder**.

![Figur 1](media/18-preventive-maintenance.png)

5. Klicka på **OK**. En eller flera arbetsorder skapas.

