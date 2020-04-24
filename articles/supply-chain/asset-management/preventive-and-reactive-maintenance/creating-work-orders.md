---
title: Skapa arbetsorder
description: Det här avsnittet innehåller förklaringar av hur du skapar arbetsorder i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f94f8bc20753e38ce1cb6eccdfbc85c2e491ffad
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206137"
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

