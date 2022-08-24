---
title: Generera elektroniska dokument och uppdatera programdata med hjälp av ER
description: Du kan utforma format för elektronisk rapportering (ER) som kan användas i programmet för att skapa utgående elektroniska dokument.
author: kfend
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
ms.openlocfilehash: 1be618d16be2ce9e50c2a43864040dfd23a8ff69
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269674"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a>Generera elektroniska dokument och uppdatera programdata genom att använda ER

[!include [banner](../includes/banner.md)]

Du kan utforma format för elektronisk rapportering (ER) som kan användas i programmet för att skapa utgående elektroniska dokument. Du kan också utforma ER-format som tolkar inkommande elektroniska dokument och som använder innehållet i dokumenten för att uppdatera programdata.

På så sätt kan ett enskilt ER-format användas för att skapa utgående elektroniska dokument och sedan uppdatera programdatan. Den här funktionen kan användas i följande scenarier:

- För att undvika upprepad användning av programdata i efterföljande processer kan du märka programdata omedelbart efter det att denna används för att skapa elektroniska dokument. Till exempel kan du markera betalningstransaktioner som "redan behandlade" så snart de har inkluderats i ett meddelande om skapad betalning.
- För att lagra behandlingsinformtionen för elektroniska dokument som har skapats med ER-logik. Till exempel en unik betalningsmeddelandeidentifiering som skapas med uttrycket ER. Uttrycket baseras på information som angetts i ER-dialogrutan när formatet ER körs för att skapa dokument.

Om du vill veta mer om den här funktionen kan du spela upp ER-uppgiftsguiderna för Skapa dokument med uppdatering av programdata (ingår i affärsprocessen 7.5.4.3 Införskaffa/utveckla komponenter för IT-tjänst/-lösning (10677) som vägleder dig genom informationen om Intrastat-rapportering och -arkivering). Följande filer krävs för att kunna utföra vissa åtgärder i dessa uppgiftsguider. Hämta och spara filerna på den lokala datorn.

- [Konfiguration av ER-datamodell: Intrastat (modell)](https://download.microsoft.com/download/9/c/e/9ceeacbe-c13e-422e-96f2-594c4a6b45b7/Intrastatmodel.xml)
- [Mappningskonfiguration för ER-modell: Intrastat (mappning)](https://download.microsoft.com/download/2/1/d/21ddaaeb-64c5-4408-a35f-1ccb922d40a4/Intrastatmapping.xml)
- [ER-formatkonfiguration: Intrastat (format)](https://download.microsoft.com/download/8/b/b/8bbb8891-e88d-4739-b92a-2d1d2fffcb79/Intrastatformat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
