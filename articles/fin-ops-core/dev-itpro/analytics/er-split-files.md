---
title: Dela skapade XML-filer utifrån filstorlek och innehållskvantitet
description: Den här artikeln innehåller information om hur du delar skapade filer baserat på filstorlek och innehållartikelkvantitet.
author: kfend
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.openlocfilehash: 5347d4e85198893dd94f14508176db93ccd47c22
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280108"
---
# <a name="split-generated-xml-files-based-on-file-size-and-content-quantity"></a>Dela skapade XML-filer utifrån filstorlek och innehållskvantitet

[!include[banner](../includes/banner.md)]

Du kan utforma elektronisk rapportering (ER)-format som skapar utgående dokument i XML-format. Ibland kan dessa dokument endast godkännas om de uppfyller vissa kriterier såsom maximal filstorlek eller maximalt antal för vissa XML-noder. Du kan skapa ER-format för att skapa elektroniska dokument som uppfyller de krav som anger mottagare av dessa dokument.

- För elementet FIL-format kan du definiera en gräns på storleken som ett ER-uttryck. Om den definierade gränsen överskrids när en ER-rapport skapas, slutför ER att skapa den aktuella filen och går sedan vidare till nästa fil.
- För alla XML ELEMENT-format kan du definiera en gräns på antalet element som ett ER-uttryck. Om antalet XML-noder i filen som skapas överstiger gränsen när en ER-rapport körs, slutför ER att skapa den aktuella filen och går sedan vidare till nästa fil.
- För alla XML SEQUENCE-formatelement kan du definiera en gräns på antalet underordnade element som ett ER-uttryck. Om antalet kapslade XML-noder av formatelement i den skapade filen överstiger gränsen när en ER-rapport körs, slutför ER att skapa den aktuella filen och går sedan vidare till nästa fil.
- Du kan markera XML ELEMENT-formatet som fasta På så sätt kan du behålla de kapslade artiklarna med XML-noder som skapas under formatelementet i en enkel skapad fil.

Utöver att använda XML ELEMENT- och XML SEQUENCE-formatelement för att lägga till XML-noder till den skapade filen kan du använda RAW XML-formatelementet. Noder som du lägger till med hjälp av RAW XML formatelementet beaktas inte när antalet noder beräknas för att utvärdera gränserna för antalet element.

Om du har konfigurerat filmålet för ett FILE formatelement som har konfigurerats för att dela skapade utdata när specifika gränser överskrids skickas varje del av skapade utdata till det konfigurerade filmålet som en individuell fil. För att unikt namnge filerna som skapas genom att dela upp utdata, måste du konfigurera ER-uttryck för FILE-formatelementet. Om du anger en ER-datakälla för NUMMERSERIE-typen ökas nummerserien för varje typ av delad utdata.

Om du vill veta mer om den här funktionen kan du spela upp uppgiftsguiden **ER dela XML-filerna baserat på filstorlek eller innehållsartikelkvantiteten** som är en del av affärsprocessen **7.5.4.3 hämta/utveckla fram IT-tjänst/komponenter (10677)** och kan hämtas från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684). Uppgiftsguiden ger dig information om processen att konfigurera ett ER-format för att dela skapade filer utifrån gränser om filstorlek och innehållsartikelkvantiteten. För att slutföra uppgiftsguiden måste du hämta följande filer:

- [Konfiguration av ER-datamodell – XmlFilesSplittingModel.xml](https://download.microsoft.com/download/e/a/f/eaffe96a-22ec-4a32-898a-f4328c91c387/XmlFilesSplittingModel.xml)
- [ER-formatkonfiguration – XmlFilesSplittingFormat.xml](https://download.microsoft.com/download/e/9/c/e9c5849b-8254-4cdf-bb00-4c2ebc72ddec/XmlFilesSplittingFormat.xml)

## <a name="additional-resources"></a>Ytterligare resurser
[Destinationer för elektronisk rapportering (ER)](electronic-reporting-destinations.md)

[Formeldesigner i elektronisk rapportering (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
