---
title: "Dela genererade filer utifrån storlek och innehållskvantitet"
description: "Det här avsnittet innehåller information om hur du delar genererade filer baserat på filstorlek och innehållartikelkvantitet."
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: 2fc887668171175d436b9eb281a35c1c9d089591
ms.openlocfilehash: afdf5b2596af7641182be50ced8159967164b115
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2018

---

# <a name="split-generated-xml-files-based-on-file-size-and-content-quantity"></a>Dela genererade XML-filer utifrån filstorlek och innehållskvantitet

[!include[banner](../includes/banner.md)]

Du kan utforma elektronisk rapportering (ER)-format som genererar utgående dokument i XML-format. Ibland kan dessa dokument endast godkännas om de uppfyller vissa kriterier såsom maximal filstorlek eller maximalt antal för vissa XML-noder. Du kan skapa ER-format för att generera elektroniska dokument som uppfyller de krav som anger mottagare av dessa dokument.

- För elementet FIL-format kan du definiera en gräns på storleken som ett ER-uttryck. Om den definierade gränsen överskrids när en ER-rapport genereras, slutför ER att skapa den aktuella filen och går sedan vidare till nästa fil.
- För alla XML ELEMENT-format kan du definiera en gräns på antalet element som ett ER-uttryck. Om antalet XML-noder i filen som genereras överstiger gränsen när en ER-rapport körs, slutför ER att skapa den aktuella filen och går sedan vidare till nästa fil.
- För alla XML SEQUENCE-formatelement kan du definiera en gräns på antalet underordnade element som ett ER-uttryck. Om antalet kapslade XML-noder av formatelement i den genererade filen överstiger gränsen när en ER-rapport körs, slutför ER att skapa den aktuella filen och går sedan vidare till nästa fil.
- Du kan markera XML ELEMENT-formatet som fasta På så sätt kan du behålla de kapslade artiklarna med XML-noder som genereras under formatelementet i en enkel genererad fil.

Utöver att använda XML ELEMENT- och XML SEQUENCE-formatelement för att lägga till XML-noder till den skapade filen kan du använda RAW XML-formatelementet. Noder som du lägger till med hjälp av RAW XML formatelementet beaktas inte när antalet noder beräknas för att utvärdera gränserna för antalet element.

Om du har konfigurerat filmålet för ett FILE formatelement som har konfigurerats för att dela genererade utdata när specifika gränser överskrids skickas varje del av genererade utdata till det konfigurerade filmålet som en individuell fil. För att unikt namnge filerna som skapas genom att dela upp utdata, måste du konfigurera ER-uttryck för FILE-formatelementet. Om du anger en ER-datakälla för NUMMERSERIE-typen ökas nummerserien för varje typ av delad utdata.

Om du vill veta mer om den här funktionen kan du spela upp uppgiftsguiden **ER dela XML-filerna baserat på filstorlek eller innehållsartikelkvantiteten** som är en del av affärsprocessen **7.5.4.3 hämta/utveckla fram IT-tjänst/komponenter (10677)** och kan hämtas från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684). Uppgiftsguiden ger dig information om processen att konfigurera ett ER-format för att dela genererade filer utifrån gränser om filstorlek och innehållsartikelkvantiteten. För att slutföra uppgiftsguiden måste du hämta följande filer:

- [Konfiguration av ER-datamodell - XmlFilesSplittingModel.xml](https://go.microsoft.com/fwlink/?linkid=874111)
- [ER-formatkonfiguration - XmlFilesSplittingFormat.xml](https://go.microsoft.com/fwlink/?linkid=874111)

## <a name="additional-resources"></a>Ytterligare resurser
[Destinationer för elektronisk rapportering](electronic-reporting-destinations.md)

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)


