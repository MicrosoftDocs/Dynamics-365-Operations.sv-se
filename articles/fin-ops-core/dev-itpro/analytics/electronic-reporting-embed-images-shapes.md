---
title: Bädda in bilder och former i dokument som du skapar med ER
description: I detta ämne beskrivs hur du använder verktyget Elektronisk rapportering (ER) för att generera affärsdokument som har inbäddade bilder och former.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: bfa8137de7b782ba80a0d80c987a96c37b3a7d86
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6361425"
---
# <a name="embed-images-and-shapes-in-documents-that-you-generate-by-using-er"></a>Bädda in bilder och former i dokument som du skapar med ER

[!include [banner](../includes/banner.md)]

Med verktyget Elektronisk rapportering (ER) kan du designa rapporter som du kan köra för att generera erforderliga elektroniska dokument. Du kan använda Microsoft Excel- eller Microsoft Word-dokument för att ange layouten för en rapport. Med ER Operations-designern kan du bifoga Excel- eller Word-dokumentet som en mall för rapporten. Följande namngivna element i den kopplade mallen associeras med formatelementen i ER-rapporten. Rapportens formatelement är bundna till datakällor. Dessa element anger de data som ska anges i genererade dokument under körning.

Denna nya funktion går utöver befintliga ER-funktioner för att skapa dokument i Microsoft Office-format. Spela upp följande uppgiftsguider för mer information: Dessa uppgiftsguider finns under affärsprocess 7.5.4.3 Skaffa/utveckla IT-tjänster/lösningskomponenter (10677).

- ER utformar en konfiguration för rapportgenerering i OPENXML-format
- ER Utforma en konfiguration för rapportgenerering i Microsoft WORD-format

## <a name="embed-an-image-in-an-excel-document"></a>Infoga en bild i ett Excel-dokument

### <a name="embed-an-image-in-an-excel-worksheet"></a>Infoga en bild i ett Excel-kalkylblad

Först måste du lägga till en platshållare för bilden i ett Excel-dokument. Öppna en Excel-arbetsbok och lägg till en bild som en platshållare för den bild du ska lägga till senare. Använd sedan ER-verktyget för att lägga till en ny ER-formatkonfiguration om du vill inkludera den rapport du designar. Koppla Excel-arbetsboken som en mall för rapportens format och importera sedan innehållet i arbetsboken till ER-formatet. Formatdefinitionen skapas automatiskt. Bildplatshållaren som du lägger till tas med i ER-formatdefinitionen som ett **CELL**-element.

> [!NOTE]
> Du kan ange formatdefinitionen manuellt istället för att importera den. När du sparar ändringarna valideras formatet.

Bind sedan **CELL**-elementet för ER-formatet till fältet från formatets datakälla som visar bildens data i binärt format vid körning. När en ER-datamodell används som datakälla för ett format måste datatypen för fältet vara [Behållare](er-formula-supported-data-types-composite.md#container). För närvarande kan ett ER-datamodellfält av typen [Behållare](er-formula-supported-data-types-composite.md#container) vara bundet till ett flertal olika typer av datakällor som returnerar bilder i binärt format. Via ramverket för dokumenthantering kan du öppna ett fält i ett dataregister och en fil som är kopplad till datatabellens post.

> [!IMPORTANT]
> - Om du vill fylla bildplatshållaren i dokumentet du skapar med hjälp av Excel-mallen måste ER-formatet innehålla det **CELL**-element som refererar till det namngivna bildelementet i Excel-mallen. Annars visas ingen bildplatshållare i rapportens utdata. Om bindandet av ett **CELL**-element inte returnerar några data i samband med körning kommer det dokument som genereras att visa bildplatshållaren från mallen. Om du vill dölja en bild i dokumentet som du genererar definierar du ett **CELL**-element och anger att uttrycket **Aktiverar** ska returnera värdet **FALSE**.
> - Använd ett unikt namn för alla element i Excel-mallen. Dessa element inkluderar bilder och celler. Om du kopierar ett elementnamn kommer innehållet i rapporten som genereras att vara tvetydigt och förvirrande.

### <a name="embed-images-in-the-header-and-footer-of-an-excel-worksheet"></a>Bädda in bilder i sidhuvudet och sidfoten i ett Excel-kalkylblad

Använd Excel-arbetsbokens dokument som en mall för att ange en layouten för en rapport. Arbetsboken kan innehålla flera kalkylblad som vart och ett kan utformas så att det har ett sidhuvud och en sidfot. Excel har stöd för upp till tre bilder i sidhuvud och sidfot i varje kalkylblad. Bilderna kan justeras åt vänster, höger eller centrerat.

I Finance-version 10.0.21 kan du hantera de sidhuvud- och sidfotsbilder som genereras av en ER-lösning som har en Excel-mall.

Om du vill att en standardbild ska visas i sidhuvudet eller sidfoten i ett genererat dokument kan du lägga till en bild i sidhuvudet eller sidfoten i ett kalkylblad i en ER-mall. Om du vill komma åt bilden i ditt ER-format måste du lägga till komponenten **Bild** under komponenten [Sidhuvud](er-fillable-excel.md#header-component) eller [Sidfot](er-fillable-excel.md#footer-component) för formatet. Konfigurera justeringen för komponenten **Bild** efter behov. 

Du kan också använda komponenten **Bild** om du vill placera en bild i sidhuvudet eller sidfoten i ett genererat dokument under körning, även om mallen inte innehåller någon standardbild. Om du vill ange det medieinnehåll som ska placeras i sidhuvudet eller sidfoten på ett genererat dokument som antingen en ny bild eller en ersättning för en standardbild, måste du binda komponenten **Bild** till en datakälla av typen [Behållare](er-formula-supported-data-types-composite.md#container) som representerar en bild i ett binärt format.

Varje **Sidhuvud**- eller **Sidfot** skomponent kan innehålla en (1) **Bild**-komponent för respektive justering som stöds: **Vänster**, **Mitten** och **Höger**.

Med egenskapen **Anpassa höjd** för komponenten **Bild** kan du använda den konfigurerade bindande funktionen för att kontrollera en bilds storlek:

- Välj **Ursprunglig** om du vill behålla bildens ursprungliga storlek.
- Välj **Relativt** om du vill anpassa bildens höjd i förhållande till höjden på sidhuvudet eller sidfoten som innehar bilden.

    - I det här fallet måste höjden på bilden definieras som en procentandel av det överordnade sidhuvudet eller den överordnade sidfoten.
    - Om skalvärdet överstiger 100 procent kan bilden komma att överlappa dataområdet i motsvarande kalkylblad.
    - Om bildens höjd ändras när skalningen används, ändras även bredden så att bildens ursprungliga proportioner bibehålls.

- Välj **Absolut** om du vill ändra storleken på bilden enligt värdena för höjd och bredd (i pixlar) som anges vid designtidpunkten.

    - Om den angivna höjden överskrider höjden på det överordnade sidhuvudet eller den överordnade sidfoten, kan bilden komma att överlappa dataområdet i motsvarande kalkylblad.

Du kan även använda egenskapen **Aktiverad** för komponenten **Bild** för att kontrollera synligheten för en bild som placeras i ett genererat dokument med hjälp av denna komponent.

> [!NOTE]
> Du måste använda ER-formatdesignern om du vill lägga till en **Bild**-komponent i redigerbart ER-format. Du kan inte lägga till komponenten när du använder arbetsytan [Hantering av affärsdokument](er-business-document-management.md) för att redigera mallen för ett affärsdokument.

Om du vill veta mer om den här funktionen följer du stegen i [Designa ett ER-format för att generera en rapport i Excel med inbäddade bilder i sidhuvuden eller sidfötter](er-embed-images-header-footer-excel-reports.md).

## <a name="embed-a-shape-in-an-excel-document"></a>Bädda in en figur i ett Excel-dokument

Du måste först lägga till en platshållare för formen i ett Excel-dokument. Öppna en Excel-arbetsbok och välj **Figur**, **Textruta** eller **WordArt** som platshållare för figuren. Använd sedan ER-verktyget för att lägga till en ny ER-formatkonfiguration om du vill inkludera den rapport du designar. Koppla Excel-arbetsboken som en mall för rapportens format och importera sedan innehållet i arbetsboken till ER-formatet. Formatdefinitionen skapas automatiskt. Platshållaren som du lagt till inkluderas i ER-formatdefinitionen som ett **CELL**-element som refererar till namngivet Excel-figurelement.

> [!NOTE]
> Du kan ange formatdefinitionen manuellt istället för att importera den. När du sparar ändringarna valideras formatet.

Bind sedan **CELL**-elementet för ER-formatet till fältet från formatets datakälla som visar datan vid körning. Dessa data kan konverteras till en textsträng. När elementet **CELL** i ER-formatet refererar till ett figurelement i Excel-mallen som har stöd för text, visas den text som anges genom detta bindande under körning i en figur i det dokument som genereras.

> [!IMPORTANT]
> - Om du vill använda Excel-mallen där figurplatshållaren ingår för att skapa ett nytt dokument, måste ER-formatet innehålla ett **CELL**-element som refererar till Excel-figurelementet. I anat fall visas ingen figurplatshållare i rapportens utdata. Om bindningen av ett **CELL**-element som refererar till namngiven Excel-figur inte returnerar några data vid körning kommer det dokument som genereras att visa figurplatshållarens text från Excel-mallen. Om du vill dölja en figur i det dokument som du genererar definierar du ett **CELL**-element som refererar till angiven Excel-figur och anger att uttrycket **Aktiverar** ska returnera värdet **FALSE**.
> - Använd ett unikt namn för alla element i Excel-mallen. Dessa element inkluderar figurer och celler. Om du kopierar ett elementnamn kommer innehållet i rapporten som genereras att vara tvetydigt och förvirrande.

## <a name="embed-an-image-in-a-word-document"></a>Bädda in en bild i ett Word-dokument
> [!IMPORTANT]
> Du kan återanvända ER-formatet som använder en Excel-mall för att skapa dokument med inbäddade bilder. Kontrollera i ER-formatet att ett namn har angetts för det **CELL**-element som refererar till ett namngivet bildelement i Excel och som är bundet till en datakälla som returnerar en bild i samband med körning.

Först måste du konfigurera Word-dokumentets layout. Använd kontrollen **Bildinnehåll** om du vill skapa en platshållare för den inbäddade bilden. Om du vill komma åt den här kontrollen måste du först göra fliken **Utvecklare** synlig på Word-menyfliken.

Därefter tar du bort Excel-mallen från ER-formatet och kopplar Word-malldokumentet. Uppdatera referensen till mallen och spara ändringarna. Strukturen hos det aktuella ER-formatet sparas i Word-mallen som en ny, anpassad XML-del som kallas **Rapport**.

Spara sedan Word-mallen för det aktuella ER-formatet på din lokala dator. Öppna mallen och öppna fönstret **XML-mappning**. Hitta den anpassade XML-del som kallas **Rapport** och referera sedan till **CELL**-elementet i den ER-rapport som är bunden till en datakälla som returnerar en bild i binärt format. Mappa denna XML-dels artikel till den markerade kontrollen **Bildinnehåll** och spara ändringarna.

[![bädda in bilder.](./media/embed-images-shapes-01.png)](./media/embed-images-shapes-01.png)

Ta slutligen bort Word-mallen från ER-formatet och koppla Word-dokumentet som innehåller de mappade, anpassade XML-delarna. Uppdatera formatreferensen till mallen och spara de ändringar du har gjort i detta ER-format.

## <a name="more-information"></a>Mer information
Om du vill bekanta dig med informationen rörande den här funktionen spelar du upp en uppsättning uppgiftsguider, **ER Skapa rapporter i MS Office-format med inbäddade bilder**. I dessa uppgiftsguider visas hur du kan bädda in bilder av en företagslogotyp och en behörig persons signatur i de betalningskontroller som genereras med hjälp av ER-verktyget i Excel- och Worddokument.

I följande tabell visas de filer som krävs för att slutföra uppgiftsguiderna **ER Skapa rapporter i MS Office-format med inbäddade bilder**. Hämta och spara filerna på din lokala dator.

| beskrivning                                          | Filnamn                   |
|------------------------------------------------------|-----------------------------|
| Exempel på konfiguration av ER-datamodell.                          | [Modell för checkar.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| Konfiguration för ER-fomat                              | [Checkar utskriftsformat.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| Bild av företagslogotypen                                   | [Företagslogotyp.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| Signaturbild                                      | [Signaturbild.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| Alternativ signaturbild                          | [Signaturbild 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Microsoft Word-mall för utskrift av betalningscheckar  | [Checkmall Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |
| Microsoft Excel-mall för utskrift av betalningscheckar | [Checkmall.xlsx](https://download.microsoft.com/download/1/f/6/1f671963-73aa-48d5-ae69-45f21fe7dfb4/Cheque%20template.xlsx)        |

Bilden nedan visar ett exempel på testutskriften för en betalningskontroll som genereras från Excel-mallen.

[![Utskrift av betalningskontrolltest.](./media/embed-images-shapes-02.png)](./media/embed-images-shapes-02.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
