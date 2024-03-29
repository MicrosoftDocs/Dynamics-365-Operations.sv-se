---
title: Skapa en fraktsedel
description: I denna artikel beskrivs hur du skapar en fraktsedel när du använder lagerstyrningsprocesser (WMS).
author: Weijiesa
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench, WHSBillOfLadingCarrier, WHSBillOfLadingOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 68a703475191255ff6ceaee25ef8e2bdf33ba0c2
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069709"
---
# <a name="create-a-bill-of-lading"></a>Skapa en fraktsedel

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du skapar en fraktsedel när du använder lagerstyrningsprocesser (WMS).  

En fraktsedel är ett juridiskt dokument mellan företaget som skeppar artiklarna och transportföretaget. Dokumentet medföljer de levererade artiklarna och fungerar som ett leveranskvitto när artiklarna levereras till målet. Om du använder lagerstyrning finns det två sätt att skapa en fraktsedel:

  -   Skapa rapporten manuellt med hjälp av sidan **Fraktsedel**.
  -   Generera rapporten från **Workbench för lastplanering**.

Om du genererar fraktsedeln från **Workbench för lastplanering** måste beläggningsstatusen vara **Levererad.** Om det finns mer än en leverans i beläggningen, skapas en fraktsedel för varje leverans. När en fraktsedel skapats kan du ändra den på sidan **Ffraktsedel**.

## <a name="master-bill-of-lading"></a>Huvudfraktsedel
Om det finns mer än en leverans i en last kan du skapa en huvudfraktsedel. Denna har samma layout och information som en fraktsedel, men innehåller det sammanfattade innehållet för alla leveranser. Om alternativet **Skapa en huvudfraktsedel när det finns mer än en leverans på en beläggning** anges som **Ja** på sidan **Transportledningsparametrar**, genereras en huvudfraktsedel automatiskt om du skapar en fraktsedel från **Workbench för lastplanering** och det finns mer än en leverans. Du kan också få en lista över fraktsedlarna genom att klicka på **Relaterad information** &gt; **Fraktsedel**. Om du skapar fraktsedlar manuellt kan du skapa en huvudfraktsedel på sidan **Fraktsedel**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]