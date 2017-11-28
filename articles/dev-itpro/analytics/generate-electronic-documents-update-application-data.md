---
title: "Skapa elektroniska dokument och uppdatera programdata med hjälp av verktyget för elektronisk rapportering"
description: "Du kan utforma format för elektronisk rapportering (ER) som kan användas i programmet Finance and Operations för att generera utgående elektroniska dokument. Du kan också utforma ER-format som tolkar inkommande elektroniska dokument och som använder innehållet i dokumenten för att uppdatera programdata."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7378c1d205b9a9cd61044dc33fc52ff75c6b94b7
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="generate-electronic-documents-and-update-application-data-using-the-electronic-reporting-tool"></a>Skapa elektroniska dokument och uppdatera programdata med hjälp av verktyget för elektronisk rapportering

Du kan utforma format för elektronisk rapportering (ER) som kan användas i programmet Finance and Operations för att generera utgående elektroniska dokument. Du kan också utforma ER-format som tolkar inkommande elektroniska dokument och som använder innehållet i dokumenten för att uppdatera programdata. 

På så sätt kan ett enskilt ER-format användas för att generera utgående elektroniska dokument och sedan uppdatera programdatan. Den här funktionen kan användas i följande scenarier:

- För att undvika upprepad användning av programdata i efterföljande processer kan du märka programdata omedelbart efter det att denna används för att generera elektroniska dokument. Till exempel kan du markera betalningstransaktioner som "redan behandlade" så snart de har inkluderats i ett meddelande om genererad betalning.
- För att lagra behandlingsinformtionen för elektroniska dokument som har skapats med ER-logik. Till exempel en unik betalningsmeddelandeidentifiering som genereras med uttrycket ER. Uttrycket baseras på information som angetts i ER-dialogrutan när formatet ER körs för att skapa dokument.

Om du vill veta mer om den här funktionen kan du spela upp ER-uppgiftsguiderna för Generera dokument med uppdatering av programdata (ingår i affärsprocessen 7.5.4.3 Införskaffa/utveckla komponenter för IT-tjänst/-lösning (10677) som vägleder dig genom informationen om Intrastat-rapportering och -arkivering. Följande filer krävs för att kunna utföra vissa åtgärder i dessa uppgiftsguider. Hämta och spara filerna på den lokala datorn.

- [Konfiguration av ER-datamodell: Intrastat (modell)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Mappningskonfiguration för ER-modell: Intrastat (mappning)](https://go.microsoft.com/fwlink/?linkid=849038)
- [ER-formatkonfiguration: Intrastat (format)](https://go.microsoft.com/fwlink/?linkid=849038)

