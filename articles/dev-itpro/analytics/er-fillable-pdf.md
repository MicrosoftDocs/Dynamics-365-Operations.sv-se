---
title: Utforma ER-konfigurationer för att fylla i PDF-mallar
description: Det här avsnittet innehåller information om hur du utformar ett ER-format (elektronisk rapportering) för att fylla i en PDF-mall.
author: NickSelin
manager: AnnBe
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1ab6b6ae8a301e24751653dd74fad66417723360
ms.sourcegitcommit: 0400bfd66e98af50e64444a1c102575099a9312f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/09/2019
ms.locfileid: "1539190"
---
# <a name="design-er-configurations-to-fill-in-pdf-templates"></a>Utforma ER-konfigurationer för att fylla i PDF-mallar

[!include[banner](../includes/banner.md)]

Procedurerna i det här avsnittet är exempel som visar hur en användare i någon av rollerna **Systemadministratör** eller **Utvecklare för elektronisk rapportering** kan konfigurera ett ER-format (elektronisk rapportering) som genererar rapporter som PDF-filer genom att använda ifyllbara PDF-dokument som rapportmallar. Dessa steg kan utföras i alla företag med Microsoft Dynamics 365 for Finance and Operations eller som RCS (Regulatory Configuration Services).

## <a name="prerequisites"></a>Förutsättningar

Innan du börjar måste du ha någon av följande typer av åtkomst, beroende på vilken tjänst du använder för att slutföra procedurerna i det här avsnittet:

- Gå till Finance and Operation för någon av följande roller:

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

- Gå till RCS för någon av följande roller:

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

Du måste också slutföra processen [skapa en konfigurationsleverantör och markera den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md).

Slutligen måste du hämta följande filer från [CustomerSource](https://go.microsoft.com/fwlink/?linkid=874111).

| Beskrivning av innehåll                       | Filnamn                                     |
|-------------------------------------------|-----------------------------------------------|
| Mall för rapportens första sida | [IntrastatReportTemplate1.pdf](https://mbs.microsoft.com/Files/public/CS)                  |
| Mall för rapportens andra sidor    | [IntrastatReportTemplate2.pdf](https://mbs.microsoft.com/Files/public/CS/AX/IntrastatReportTemplate2.pdf)                  |
| ER-provformat - PDF                          | [Intrastat-rapport (PDF).version.1.1.xml](https://mbs.microsoft.com/Files/public/CS/AX/IntrastatreportPDFversion11.xml)        |
| ER-provformat - Excel                          | [Intrastat (import från Excel).version.1.1.xml](https://mbs.microsoft.com/Files/public/CS/AX/IntrastatimportfromExcelversion11.xml) |
| Provdatamängd                            | [Intrastat provdata.xlsx](https://mbs.microsoft.com/Files/public/CS/AX/Intrastatsampledata.xlsx)                    |

## <a name="design-the-format-configuration"></a>Designa formatkonfigurationen

### <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Få åtkomst till listan med konfigurationer som tillhandahålls av Microsoft

1. Gå till **Organisationsadministration \> Arbetsytor \> Elektronisk rapportering**.
2. Kontrollera att leverantören **Litware, Inc.** finns tillgänglig och har markerats som aktiv.
3. På panelen för **Microsoft**-leverantören väljer du **Databaser**.

    > [!NOTE]
    > Om det redan finns en databas av typen **LCS** hoppar du över de återstående stegen för den här proceduren.

4. Markera **Lägg till**.
5. I listrutan i fältgruppen **Typ av konfigurationsdatabas**, välj alternativet **LCS**.
6. Välj **Skapa databas**.
7. Välj **OK**.

### <a name="get-the-model-configurations-provided-by-microsoft"></a>Hämta modellkonfigurationerna som tillhandahålls av Microsoft

1. På vänster sida av **konfigurationsdatabaser** väljer du knappen **Visa filter** (trattsymbol).
2. Lägg till ett filter för ett värde av **LCS** i fältet **Typ** och använd operatorn **börjar med**.
3. Välj **Tillämpa**.
4. Välj **Öppen**.
5. I trädet väljer du **Intrastat-modell**.
6. På snabbfliken **Versioner**, välj version **1**.

    > [!NOTE]
    > Om knappen **importera** på snabbfliken **versioner** inte är tillgänglig, hoppar du över de återstående stegen för den här proceduren.

7. Välj **Importera**.
8. Välj **ja** om du vill bekräfta importen av den valda versionen av modellkonfigurationen **Intrastat-modellen**.

### <a name="create-a-new-format-configuration"></a>Skapa en ny formatkonfiguration

1. På arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.
2. I trädet väljer du **Intrastat-modell**.
3. Välj **Skapa konfiguration**.

    > [!NOTE]
    > Om knappen **skapa konfiguration** inte är tillgänglig måste du aktivera designläget på sidan **Parametrar för elektronisk rapportering** som kan öppnas från arbetsytan **elektronisk rapportering.**

4. I listrutan i fältgruppen **Ny**, väljer du alternativet **Format baserat på datamodell Intrastat**.
5. I fältet **namn** anger du **Intrastat-rapport (PDF)**.
6. I fältet **Beskrivning** anger du **Intrastat-rapport i PDF-format**.

    > [!NOTE]
    > Den aktiva konfigurationsleverantören anges automatiskt. Den här leverantören kommer att kunna underhålla konfigurationen. Även om andra leverantörer kan använda den här konfigurationen kommer de inte att underhålla den.

7. Valfritt: i fältet **formattyp** kan du välja ett specifikt format för elektroniskt dokument. Om du väljer **PDF**, vid designtiden kommer ER-verksamhetens designer att bara erbjuda de formatelement som endast gäller för dokument som genereras i PDF-format (**PDF\fil**, **PDF\PDF-sammanslagning**, etc.). Om du lämnar det här fältet tomt kommer ett format för det elektroniska dokumentet att anges i designtid i ER-verksamhetens designer när ett första formatelement läggs till. Om du till exempel lägger till **Excel\Fil** som första formatelement kommer ER-verksamhetens designer kommer bara att erbjuda formatelementen som bara gäller för dokument som genereras i Excel-format (**Excel\Cell**, **Excel\Intervall**, etc.). format.
8. Välj **Skapa konfiguration**.

En ny ER-formatkonfiguration har skapats. Du kan använda utkastversionen av den här konfigurationen för att lagra ER-formatkomponenten som är utformad för att generera elektroniska dokument i PDF-format.

### <a name="design-the-format-of-an-electronic-document"></a>Designa formatet för ett elektroniskt dokument

Därefter ska du i den konfiguration av ER-format som du har skapat utforma det ER-format som genererar rapporten **Intrastat-kontroll** i PDF-format. Den första sidan i rapporten måste visa en sammanfattning av rapporten och information om de utländska affärstransaktioner som rapporteras. Övriga sidor får bara visa information om de utländska affärstransaktioner som rapporteras. Eftersom rapportsidorna som genereras måste ha olika layouter, kommer två olika mallar i PDF-format att användas i ER-format.

Öppna PDF-mallarna som du har hämtat i ett PDF-visningsprogram. Lägg märke till att varje mall innehåller flera fält som måste fyllas i. I varje mall visas detaljer om transaktioner för utländsk handel som 42 rader, som var och en har nio fält. Radnumret visas i slutet av varje fältnamn (till exempel, **Datum 1**…**Datum 42** och **Artikel 1**…**Artikel 42**).

Följande bild visar PDF-mallen för rapportens första sida.

![Mall 1](media/rcs-ger-filloutpdf-template1.png)

Följande bild visar PDF-mallen för rapportens andra sidor.

![Mall 2](media/rcs-ger-filloutpdf-template2.png)

1. Välj **Designer** på sidan **Konfigurationer**.
2. Välj **Lägg till rot**.
3. I listrutan i trädet väljer du **PDF \> PDF sammanslagning**.

    När du väljer elementet **PDF sammanslagning** som rotelement för formatet, slås alla PDF-dokument som genereras under körning ihop till ett enda slutligt PDF-dokument. Om du bara behöver en PDF-mall för att skapa alla dokument som krävs genom att använda ER-formatet du designar kan du välja **PDF-fil** som rotelement.

4. Skriv **Utdata** i fältet **Namn**.
5. I fältet **Språkinställningar** väljer du **Användarinställningar**. Rapporten kommer att genereras på det språk som föredras för den användare som kör den.
6. I fältet **Kulturinställningar** väljer du **Användarinställningar**. Värden och datum som visas på sidorna i rapporten kommer att formateras med utgångspunkt på det föredragna användarspråket för den användare som kör rapporten.
7. Välj **OK**.
8. I åtgärdsfönstret, på fliken **IMport**, välj **Importera från PDF**.

    När ett ifyllbart PDF-dokument importeras som en mall för detta ER-format, skapas automatiskt alla nödvändiga formatelement (elementen **PDF-fil**, **Fältgrupp** och **Fält**) skapas automatiskt i det format som är utformad utifrån strukturen i det PDF-dokument som importeras.

9. Välj **bläddra**. Navigera till och markera filen **IntrastatReportTemplate1.pdf** som du laddade ned tidigare som en förutsättning.
10. Välj **OK**.

    Den valda filen läses in och fältet **Mall** i dialogrutan **importera från PDF** fylls i.

11. Ge alternativet **Gruppfält** värdet **Ja**. Om det markerade PDF-dokumentet innehåller några fältgrupper används de för att gruppera de ER-formatelement som skapas. Formatelementet **fälgrupp** skapas för det här syftet.

    Om det här alternativet är inställt på **Nej** kommer de obligatoriska formatelementen att skapas som en platt lista med element som är kapslade under formatelementet **PDF-fil** som skapas.

12. Välj **OK**.

    ![Importera från PDF dialogrutan](media/rcs-ger-filloutpdf-importtemplate.png)

13. Expandera **Utdata** i trädet.

    Observera att komponenten **PDF-fil** automatiskt har skapats för att hantera skapandet av den första sidan i den rapport som genereras vid körning.

14. Expandera **Utdata \> PDF-fil** i trädet.

    Observera att den strukturerade listan över formatelement har skapats automatiskt i det här ER-formatet, baserat på strukturen i det ifyllbara PDF-dokument som du importerade tidigare.

15. Välj **Utdata \> PDF-fil** i trädet.
16. Skriv **Sida 1** i fältet **Namn**.

    Det här formatelementet används för att generera den första sidan i rapporten **Intrastat-kontroll**. På den sidan visas en sammanfattning av rapporten och information om transaktioner i utländsk handel.

    Om du låter fältet **språkinställningar** vara tomt, kommer **språkinställningar** för det överordnade **PDF sammanslagning** att bestämma vilket språk som ska tillämpas på den rapport som genereras i formatetelementet. Du kan välja ett annat värde om du vill åsidosätta inställningen för det överordnade elementet.

    Om du låter fältet **Kulturinställningar** vara tomt, kommer **Kulturinställningar** för det överordnade **PDF sammanslagning** att bestämma vilket språk som ska tillämpas på den rapport som genereras i formatetelementet. Språket bestämmer format på värden och datum på rapportens sidor. Du kan välja ett annat värde om du vill åsidosätta inställningen för det överordnade elementet.

17. I åtgärdsfönstret väljer du fliken **Import**. Observera att knappen **uppdatera från PDF** har blivit tillgänglig för det valda formatelementet, **PDF-fil**.

    Du kan använda den här knappen om du vill importera den uppdaterade PDF-mallen till det redigerade formatet. När den uppdaterade PDF-mallen importeras ändras listan över formatelement enligt detta:

    - Nya formatelement skapas i det redigerade ER-formatet för nya fält i den uppdaterade PDF-mallen.
    - Om den uppdaterade PDF-mallen inte längre innehåller fält som motsvarar befintliga formatelement i det redigerade ER-formatet, tas dessa formatelement bort från ER-formatet.

18. Välj **bifogade filer** på fliken **format**.

    Lägg märke till att det importerade PDF-dokumentet är kopplat till det redigerade ER-formatet.

    ![Förhandsgranskning av PDF-bilaga](media/rcs-ger-filloutpdf-attachedtemplate.png)

19. Fortsätt att utforma det här formatet genom att importera den andra PDF-mallen, lägga till nödvändiga bindningar till data källor och så vidare.
20. Välj **Spara**.
21. Stäng sidan.
22. Välj **Ta bort**.
23. Välj **Ja**.

Om du vill veta hur nya formatelementetn **PDF sammanslagning**, **PDF-fil**, **Fälgrupp** och **Fält** kan användas för att generera dokument i PDF-format kan du importera och analysera exempel på ER-format.

### <a name="import-the-format-configuration"></a>Importera formatkonfiguration

Nu ska du importera det exempel på ER-format som du tidigare hämtade för att generera rapporten **Intrastat-kontroll** i PDF-format. Den första sidan i rapporten måste visa en sammanfattning av rapporten och information om de utländska affärstransaktioner som rapporteras. Övriga sidor får bara visa information om de utländska affärstransaktioner som rapporteras.

1. På sidan **konfigurationer** väljer du **växla\> last från XML-fil**.
2. Välj **bläddra**. Navigera till och markera filen **Intrastat-rapport (PDF).version.1.1.xml** som du laddade ned tidigare som en förutsättning.
3. Välj **OK**.

## <a name="analyze-the-format-configuration"></a>Analysera formatkonfiguration

### <a name="format-layout"></a>Formatlayout

1. På sidan the **konfigurationer** i trädet väljer du **Intrastat-modell \> Intrastat-rapport (PDF)**.
2. Välj **Designer**.
3. Välj **Visa detaljer**.
4. I trädet expandera **Utdata: PDF sammanfoga**.

    Observera att det här ER-formatet innehåller två **PDF-fil**-element där var och en av dem använder olika PDF-mallar. En mall används för att generera den första sidan i rapporten i PDF-format och den andra mallen används för att generera de andra sidorna.

5. I trädet, expandera **Utdata: PDF sammanslagning \> Sida 1: PDF-fil (IntrastatReportTemplate1)**.
6. I trädet, expandera **Utdata: PDF sammanslagning \> Sida N: PDF-fil (IntrastatReportTemplate2)**.

    Observera att eftersom innehållet i de båda PDF-mallarna skiljer sig åt, är även strukturen för de kapslade formatelementen för de två elementen **PDF-fil** olika.

### <a name="format-mapping"></a>Mappning av format

1. Välj fliken **Formatdesigner** välj fliken **Mappning**.
2. I trädet, expandera **Sidindelning \> Sidor**.

    ![Formeldesignersida där modellträdet är expanderat](media/rcs-ger-filloutpdf-reviewformat.png)

    Observera följande information:

    - Formatelementet **Utdata \> Sida 1** för typen **PDF-fil** är inte bundet till någon datakälla och uttrycket **Aktiverad** för det här formatelementet är tomt. Vid körning fylls därför PDF-mallen **IntrastatReportTemplate1** bara i en gång när ett individuellt PDF-dokument genereras.
    - Elementet **Utdata \> Sida N** formatelement för **PDF-fil** är bundet till **Paging.PageN** datakälla till uttrycken **Artikeltyp** och **Aktiverad** för detta formatelement är tomt. Vid körning fylls därför PDF-mallen **IntrastatReportTemplate2** för varje post från den bundna postlistan till ett individuellt PDF-dokument genereras.
    - Eftersom formatelementen **sidan 1: PDF-fil** och **sidan N: PDF-fil** är underordnade formatelementen **utdata: PDF sammanslagning** kommer alla PDF-dokument som är ifyllda att slås samman till ett enda slutligt PDF-dokument.
    - Datakällorna **Paging.Page1** och **Paging.PageN** datakällor är konfigurerade som filter av poster från datakällan **Paging.Pages**. Den här datakällan är konfigurerad för att dela upp hela uppsättningen utländska handelstransaktioner med batchar. Varje batch innehåller upp till 42 poster. Följande ER-uttryck används för att dela upp transaktionerna i batchar:

        SPLITLIST(Totals.CommodityRecord,42)

    - Datakällan **Paging.Pages** innehåller elementet **Paging.Pages.Enumerated** som returnerar information om varje post som ingår i en batch. Den här informationen inkluderar postens ordningsföljd i den aktuella batchen (fältet **Paging.Pages.Enumerated.Number**). Fältet **Paging.Pages.Enumerated.Number** används i uttrycket **Namn** för formatelementen **PDF-fält** för att dynamiskt generera ett fält namn som baseras på transaktionsnumret i en batch. Fältnamnet som skapas används sedan för att fylla i rätt PDF-fält i PDF-mallen som används.
    - Formatelementen **Utdata \> Sida N \> Detlajer 2** av typen **PDF-gruppen** är bunden till datakällan **Paging.PageN.Enumerated** för (eller **\@.Enumerated** om visningsläget **Relativa sökvägar** används) för typen **Postlista**. Det innebär att de kapslade elementen i den här PDF-gruppen fylls i för varje post i den bundna postlistan vid körning. På så sätt skapas enskilda PDF-rader praktiskt taget när för varje N:te av 42 poster i listan **Paging.PageN.Enumerated** följande PDF-fält fylls i: Datum N, Adress N, Artikel N, etc. I det här fallet liknar funktion för detta formatelement **Fältgrupp** funktionen för formatelementen **XML \> Sekvens** och **Text \> Sekvens**.

3. Expandera **Utdata \>sida N \> Detaljer2** i trädet.
4. I trädet, välj **Utdata \> Sida N \> Detaljer2 \> sidfot**.

    Oservera att attributet **Namn** av detta formatelement definieras som **sidfot**. Lägg också märke till att uttrycket **namn** för formatelementet är tomt.

5. I trädet, väljer du **Utdata \> Sida N \> Detaljer2 \> korrigering 1**.

    Oservera att attributet **Namn** av detta formatelement definieras som **korrigering 1**. Observera också att uttrycket **Namn** för formatelementet definieras som **Paging.FldName("Correction",\@.Number)**.

![Formatdesigner där en mappning har valts](media/rcs-ger-filloutpdf-reviewformat2.png)

Observera att formatelementet **fält** används för att fylla i ett enskilt fält i ett ifyllbart PDF-dokument som definieras som en mall för det överordnade **PDF-fil**formatet. Bindningen för **PDF-fil**formatet eller det inkapslade elementet, om det innehåller några kapslade element, anger värdet som anges i motsvarande PDF-fält. Olika egenskaper för formatelementet **fält** kan användas för att ange vilket PDF-fält som fylls i av ett enskilt formatelement:

- På fliken **format** är **Namn** attributet för formatelementet
- På fliken **Mappning** är **Namn** uttrycket för formatelementet

Eftersom båda egenskaperna är valfria för formatelementet **fält** används följande regler för att ange mål-PDF-fältet:

- Om attributet **Namn** är tomt och uttrycket **Namn** returnerar en tom sträng vid körning, genereras ett undantag vid körningen för att meddela användaren att ett PDF-fält inte kan hittas i PDF-mallen som används för att fylla i PDF-dokumentet.
- Om attributet **Namn** definieras, uttrycket **Namn** är tomt fylls det PDF-fält i som har samma namn som attributet **Namn** för formatelementet fylls i.
- Om attributet **Namn** definieras, uttrycket **Namn** är konfigurerat fylls det PDF-fält i som har samma namn som värdet som returneras av uttrycket **Namn** för formatelementet fylls i.

> [!NOTE]
> En PDF-kryss ruta kan fyllas i som valt på följande sätt:
>
> - När motsvarande formatelement **Fält** är bundet till ett datakällfält av datatypen **Boolesk** ahr värdet **True**
> - När motsvarande formatelementet **Fält** innehåller ett nästat formatelementet **Sträng** som är bundet till ett data käll fält som har ett text värde av **1**, **True**, eller **Ja**

## <a name="run-the-format-configuration"></a>Kör formatkonfigurationen

### <a name="import-the-format-configuration"></a>Importera formatkonfiguration

Nu ska du läsa in ER-format **Intrastat (import från Excel)**. Det här formatet är utformat för att analysera en användardefinierad Microsoft Excel arbetsbok som simulerar utländska handelstransaktioner.

1. På sidan **konfigurationer** väljer du **växla\> last från XML-fil**.
2. Välj **bläddra**. Navigera till och markera filen **Intrastat-rapport (import från Excel).version.1.1.xml** som du laddade ned tidigare som en förutsättning.
3. Välj **OK**.
4. I trädet, välj **Intrastat-modell \> Intrastat (import från Excel)**.
5. Välj **Redigera**.
6. Ange alternativet **standard för modellmappning** till **Ja**.

    > [!NOTE]
    > Om du tidigare har ställt **standard för modellmappning** till **Ja** för konfigurationen **Intrastat-modell** eller en annan konfiguration som är nästad konfiguration **Intrastat-modell** ställer du in alternativet till **Nej**.

    När alternativet **standard för modellmappning** anges till **Ja**, tilldelas det importerade ER-formatet **Intrastat (importera från Excel)** som standarddatakälla för formatkonfigurationen **Intrastat rappport (PDF)**. När formatkonfigurationen för **Intrastat-rapport (PDF**) körs, kommer innehållet i den Excel-arbetsbok som tolkas av formatet **Intrastat (import från Excel)** att simulera utländska handelstransaktioner som måste rapporteras. Illustrationen nedan visar ett exempel på en Excel-arbetsbok.

    ![Excel-arbetsbok med exempeldata](media/rcs-ger-filloutpdf-excelworkbook.png)

### <a name="run-the-format-configuration"></a>Kör formatkonfigurationen

1. På sidan the **konfigurationer** i trädet väljer du **Intrastat-modell \> Intrastat-rapport (PDF)**.
2. Välj **kör**.
3. Välj **bläddra**. Navigera till och markera filen **Intrastat exempeldata.xlsx** som du laddade ned tidigare som en förutsättning.
4. Välj **OK**.
5. I fältet **rapportriktning** väljer du **både** för att fylla i alla transaktioner från den importerade Excel-arbetsboken i den PDF-rapport som skapas.
6. Välj **OK**.
7. Granska det PDF-dokument som genereras.

Den följande bilden visar ett exempel på första sidan i den rapport som genereras.

![Första sidan i den genererade rapporten](media/rcs-ger-filloutpdf-generatedreport.png)

Den följande bilden visar ett exempel på en annan sida i den rapport som genereras.

![Annan sida i den genererade rapporten](media/rcs-ger-filloutpdf-generatedreport2.png)

## <a name="additional-resources"></a>Ytterligare resurser

- [ER utformar en konfiguration för rapportgenerering i OPENXML-format](tasks/er-design-reports-openxml-2016-11.md)
- [Utforma ER-konfigurationer för rapportgenerering i Microsoft Word-format](tasks/er-design-configuration-word-2016-11.md)
