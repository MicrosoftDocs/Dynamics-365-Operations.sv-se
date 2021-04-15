---
title: Generera elektroniska dokument och uppdatera programdata med hjälp av ER
description: Du kan utforma format för elektronisk rapportering (ER) som kan användas i programmet för att skapa utgående elektroniska dokument.
author: NickSelin
ms.date: 11/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 863c69446e9a7d447847483ec129788e85a8fd58
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750044"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a>Generera elektroniska dokument och uppdatera programdata genom att använda ER

[!include [banner](../includes/banner.md)]

Du kan utforma format för elektronisk rapportering (ER) som kan användas i programmet för att skapa utgående elektroniska dokument. Du kan också utforma ER-format som tolkar inkommande elektroniska dokument och som använder innehållet i dokumenten för att uppdatera programdata.

På så sätt kan ett enskilt ER-format användas för att skapa utgående elektroniska dokument och sedan uppdatera programdatan. Den här funktionen kan användas i följande scenarier:

- För att undvika upprepad användning av programdata i efterföljande processer kan du märka programdata omedelbart efter det att denna används för att skapa elektroniska dokument. Till exempel kan du markera betalningstransaktioner som "redan behandlade" så snart de har inkluderats i ett meddelande om skapad betalning.
- För att lagra behandlingsinformtionen för elektroniska dokument som har skapats med ER-logik. Till exempel en unik betalningsmeddelandeidentifiering som skapas med uttrycket ER. Uttrycket baseras på information som angetts i ER-dialogrutan när formatet ER körs för att skapa dokument.

Om du vill veta mer om den här funktionen kan du spela upp ER-uppgiftsguiderna för Skapa dokument med uppdatering av programdata (ingår i affärsprocessen 7.5.4.3 Införskaffa/utveckla komponenter för IT-tjänst/-lösning (10677) som vägleder dig genom informationen om Intrastat-rapportering och -arkivering). Följande filer krävs för att kunna utföra vissa åtgärder i dessa uppgiftsguider. Hämta och spara filerna på den lokala datorn.

- [Konfiguration av ER-datamodell: Intrastat (modell)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Mappningskonfiguration för ER-modell: Intrastat (mappning)](https://go.microsoft.com/fwlink/?linkid=849038)
- [ER-formatkonfiguration: Intrastat (format)](https://go.microsoft.com/fwlink/?linkid=849038)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]