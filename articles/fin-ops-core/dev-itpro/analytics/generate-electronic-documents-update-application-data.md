---
title: Generera elektroniska dokument och uppdatera programdata med hjälp av ER
description: Du kan utforma format för elektronisk rapportering (ER) som kan användas i programmet för att skapa utgående elektroniska dokument. Du kan också utforma ER-format som tolkar inkommande elektroniska dokument och som använder innehållet i dokumenten för att uppdatera programdata.
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 333f91cef12b6564ca9bc668732b4cc038f0fa7e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181874"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a>Generera elektroniska dokument och uppdatera programdata med hjälp av ER

[!include [banner](../includes/banner.md)]

Du kan utforma format för elektronisk rapportering (ER) som kan användas i programmet för att skapa utgående elektroniska dokument. Du kan också utforma ER-format som tolkar inkommande elektroniska dokument och som använder innehållet i dokumenten för att uppdatera programdata.

På så sätt kan ett enskilt ER-format användas för att skapa utgående elektroniska dokument och sedan uppdatera programdatan. Den här funktionen kan användas i följande scenarier:

- För att undvika upprepad användning av programdata i efterföljande processer kan du märka programdata omedelbart efter det att denna används för att skapa elektroniska dokument. Till exempel kan du markera betalningstransaktioner som "redan behandlade" så snart de har inkluderats i ett meddelande om skapad betalning.
- För att lagra behandlingsinformtionen för elektroniska dokument som har skapats med ER-logik. Till exempel en unik betalningsmeddelandeidentifiering som skapas med uttrycket ER. Uttrycket baseras på information som angetts i ER-dialogrutan när formatet ER körs för att skapa dokument.

Om du vill veta mer om den här funktionen kan du spela upp ER-uppgiftsguiderna för Skapa dokument med uppdatering av programdata (ingår i affärsprocessen 7.5.4.3 Införskaffa/utveckla komponenter för IT-tjänst/-lösning (10677) som vägleder dig genom informationen om Intrastat-rapportering och -arkivering. Följande filer krävs för att kunna utföra vissa åtgärder i dessa uppgiftsguider. Hämta och spara filerna på den lokala datorn.

- [Konfiguration av ER-datamodell: Intrastat (modell)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Mappningskonfiguration för ER-modell: Intrastat (mappning)](https://go.microsoft.com/fwlink/?linkid=849038)
- [ER-formatkonfiguration: Intrastat (format)](https://go.microsoft.com/fwlink/?linkid=849038)
