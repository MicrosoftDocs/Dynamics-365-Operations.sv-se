---
title: Skapa en fraktsedel
description: "I det här avsnittet beskrivs hur du skapar en fraktsedel när du använder lagerstyrningsprocesser."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: b88679f1be00d6a7168c8976f0d7db894c7e77fc
ms.lasthandoff: 03/31/2017


---

# <a name="create-a-bill-of-lading"></a>Skapa en fraktsedel

I det här avsnittet beskrivs hur du skapar en fraktsedel när du använder lagerstyrningsprocesser.  

En fraktsedel är ett juridiskt dokument mellan företaget som skeppar artiklarna och transportföretaget. Dokumentet medföljer de levererade artiklarna och fungerar som ett leveranskvitto när artiklarna levereras till målet. Om du använder lagerstyrning finns det två sätt att skapa en fraktsedel:

  -   Skapa rapporten manuellt med hjälp av sidan **Fraktsedel**.
  -   Generera rapporten från **Workbench för lastplanering**.

Om du genererar fraktsedeln från **Workbench för lastplanering** måste beläggningsstatusen vara **Levererad.** Om det finns mer än en leverans i belastningen, skapas en fraktsedel för varje leverans. När en fraktsedel skapats du kan göra ändringar i det på de **fraktsedel** sida.

## <a name="master-bill-of-lading"></a>Huvudfraktsedel
Om det finns mer än en leverans i en last kan du skapa en huvudfraktsedel. Denna har samma layout och information som en fraktsedel, men innehåller det sammanfattade innehållet för alla leveranser. Om alternativet **Skapa en huvudfraktsedel när det finns mer än en leverans på en beläggning** anges som **Ja** på sidan **Transportledningsparametrar**, genereras en huvudfraktsedel automatiskt om du skapar en fraktsedel från **Workbench för lastplanering** och det finns mer än en leverans. Du kan också få en lista över konossement genom att klicka på **relaterad information**&gt;**fraktsedel**. Om du skapar fraktsedlar manuellt kan du skapa en huvudfraktsedel på sidan **Fraktsedel**.


