---
title: Skapa en konfiguration för att generera dokument i Excel-format
description: Det här avsnittet beskriver hur du utformar ett elektroniskt rapporteringsformat (ER) för att fylla i en Excel-mall och sedan generera utgående dokument i Excelformat.
author: NickSelin
manager: AnnBe
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c8d6a18741d57829d1929fb8362dc4ba8e03a1bd
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094039"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>Skapa en konfiguration för att generera dokument i Excel-format

[!include[banner](../includes/banner.md)]

Du kan utforma en konfiguration för [elektroniskt rapporteringsformat (ER)](general-electronic-reporting.md) som har en ER-[formatkomponent](general-electronic-reporting.md#FormatComponentOutbound) som du kan konfigurera för att generera ett utgående dokument i ett Microsoft Excel-arbetsboksformat. Specifika komponenter i ER-format måste användas för detta syfte.

Om du vill veta mer om den här funktionen följer du stegen i avsnittet [utforma en konfiguration för generering av rapporter i OpenXML-format](tasks/er-design-reports-openxml-2016-11.md).

## <a name="add-a-new-er-format"></a>Lägg till ett nytt ER-format

När du lägger till en ny konfiguration för ER-format i syfte att generera ett utgående dokument i ett Excel-format, måste du antingen välja **Excel**-värdet för attributet **Formattyp** för formatet eller lämna attributet **Formattyp** tomt.

- Om du väljer **Excel** kan du konfigurera formatet så att ett utgående dokument endast skapas i Excel-format.
- Om du lämnar attributet tomt kan du konfigurera formatet så att ett utgående dokument skapas i ett format som stöds av ER-ramverket.

Om du vill konfigurera ER-formatkomponenten för konfigurationen väljer du **Designer** i åtgärdsfönstret och öppnar ER-formatkomponenten för redigering i ER-åtgärdersdesignern.

![Sidan Konfigurationer](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Excel-filkomponent

### <a name="manual-entry"></a>Manuell registrering

Du måste lägga till en **Excel\\fil**-komponent i det konfigurerade ER-formatet för att kunna generera ett utgående dokument i Excel-format.

![Excel-\filkomponent](./media/er-excel-format-add-file-component.png)

Om du vill ange layouten för det utgående dokumentet bifogar du en Excel-arbetsbok med filnamnstillägget .xlsx till komponenten **Excel\\fil** som mall för utgående dokument.

> [!NOTE]
> När du bifogar en mall manuellt måste du använda en [dokumenttyp](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) som har konfigurerats för detta syfte i [ER-parametrarna](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

![Lägga till en bilaga i Excel\fil-komponenten](./media/er-excel-format-add-file-component2.png)

Om du vill ange hur den bifogade mallen ska fyllas i när du kör det konfigurerade ER-formatet måste du lägga till kapslade **Ark-**, **Intervall-** och **Cell-** komponenter i **Excel\\fil**-komponenten. Varje kapslad komponent måste associeras med ett namngivet Excel-objekt.

### <a name="template-import"></a>Mallimport

Du kan välja **Importera från Excel** på fliken **Importera** i åtgärds fönstret för att importera en ny mall till ett tomt ER-format. I det här exemplet skapas en **Excel\\-fil** komponent automatiskt, och den importerade mallen kopplas till den. Alla obligatoriska ER-komponenter skapas också automatiskt, baserat på listan med Excel-objekt som upptäcks.

![Välja Importera från Excel](./media/er-excel-format-import-template.png)

> [!NOTE]
> Om du vill skapa det valfria **Ark**-elementet i det redigerbara ER-formatet ställer du in alternativet **Skapa formatelement för Excel-ark** som **Ja**.

## <a name="sheet-component"></a>Ark-komponent

Komponenten **Ark** anger ett kalkylblad tillhörande den bifogade Excel-arbetsbok som måste fyllas i. Namnet på kalkylbladet i en Excel-mall definieras i egenskapen **Ark** för den här komponenten.

> [!NOTE]
> Denna komponent är valfri för Excel-arbetsböcker som innehåller ett enda kalkylblad.

På fliken **Mappning** i ER-åtgärdsdesignern kan du konfigurera egenskapen **Aktiverad** för en **ark**-komponent i syfte att ange om komponenten ska placeras i ett genererat dokument:

- Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **True** vid körning, eller om inget uttryck har konfigurerats alls, infogas lämpligt kalkylblad i det genererade dokumentet.
- Om ett uttryck för egenskapen **Aktiverad** har konfigurerATS att returnera **False** vid körning kommer det genererade dokumentet inte att innehålla något kalkylblad.

![Exempel på en ark-komponent](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>Intervall-komponent

**Intervall**-komponenten anger ett Excel-intervall som måste kontrolleras av denna ER-komponent. Namnet på intervallet definieras i egenskapen **Excel-intervall** för den här komponenten.

Egenskapen **Replikeringsriktning** anger om och hur intervallet ska upprepas i ett genererat dokument:

- Om egenskapen **Replikeringsriktning** anges som **Ingen replikering** upprepas inte det aktuella Excel-intervallet i det genererade dokumentet.
- Om egenskapen **Replikeringsriktning** anges som **Lodrät** upprepas lämpligt Excel-intervall i det genererade dokumentet. Varje replikerat intervall placeras under det ursprungliga intervallet i en Excel-mall. Antalet upprepningar definieras av antalet poster i en data källa för den typ av **Postlista** som är bunden till den här ER-komponenten.
- Om egenskapen **Replikeringsriktning** anges som **Horisontell** upprepas lämpligt Excel-intervall i det genererade dokumentet. Varje replikerat intervall placeras till höger om det ursprungliga intervallet i en Excel-mall. Antalet upprepningar definieras av antalet poster i en data källa för den typ av **Postlista** som är bunden till den här ER-komponenten.

Om du vill veta mer om vågrät replikering följer du stegen i [Använd vågrätt expanderbara intervall för att dynamiskt lägga till kolumner i Excel-rapporter](tasks/er-horizontal-1.md).

**Intervall**-komponenten kan ha andra kapslade ER-komponenter som används för att ange värden i lämpliga Excel-namngivna intervall.

- Om en komponent i **Text**-gruppen används för att ange värden, anges värdet i ett Excel-intervall som ett textvärde.

    > [!NOTE]
    > Använd det här mönstret om du vill formatera angivna värden baserat på de språk som har definierats i programmet.

- Om en **Cell**-komponent tillhörande gruppen **Excel** används för att ange värden, anges värdet i ett Excel-intervall som värde för den datatyp som definieras av bindningen för den **Cell**-komponenten (t.ex. **Sträng**, **Verklig** eller **Heltal**).

    > [!NOTE]
    > Använd det här mönstret om du vill göra det möjligt för Excel-programmet att formatera angivna värden baserat på språkinställningen för den lokala dator som öppnar det utgående dokumentet.

På fliken **Mappning** i ER-åtgärdsdesignern kan du konfigurera egenskapen **Aktiverad** för en **Intervall**-komponent i syfte att ange om komponenten ska placeras i ett genererat dokument:

- Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **True** vid körning, eller om inget uttryck har konfigurerats alls, ifylles lämpligt intervall i det genererade dokumentet.
- Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **False** vid körning, och om detta intervall inte representerar hela raderna eller kolumnerna, kommer lämpligt intervall inte att ifyllas i det genererade dokumentet.
- Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **False** vid körning, och om detta intervall representerar hela raderna eller kolumnerna, kommer det genererade dokumentet att omfatta dessa rader och kolumner som dolda radera och kolumner.

## <a name="cell-component"></a>Cellkomponent

**Cell**-komponenten används för att fylla i Excel-betitlade celler, figurer och bilder. Om du vill ange ett Excel-namngivet objekt som måste fyllas i av en ER-komponent för en **Cell**, måste du ange namnet på objektet i egenskapen **Excel-intervall** för komponenten **Cell**.

På fliken **Mappning** i ER-åtgärdsdesignern kan du konfigurera egenskapen **Aktiverad** för en **Cell**-komponent i syfte att ange om objektet måste ifyllas i ett genererat dokument:

- Om ett uttryck för egenskapen **Aktiverad** har konfigurerats att returnera **True** vid körning, eller om inget uttryck har konfigurerats alls, ifylles lämpligt objekt i det genererade dokumentet. Bindningen för denna **cell**-komponent anger ett värde som placeras i lämpligt objekt.
- Om ett uttryck för egenskapen **Aktiverad** konfigureras i syfte att returnera **False** vid körning, kommer lämpligt objekt inte att ifyllas i det genererade dokumentet.

När en **cell**-komponent konfigureras för att ange ett värde i en cell, kan den bindas till en datakälla som returnerar värdet för en primitiv datatyp (t.ex. **sträng**, **verklig** eller **heltal**). I det här fallet anges värdet i cellen som ett värde av samma datatyp.

När en **cell**-komponent konfigureras för att ange ett värde i en Excel-figur kan den bindas till en datakälla som returnerar ett värde för en primitiv datatyp (t.ex. **sträng**, **verklig** eller **heltal**). I det här fallet anges värdet i Excel-figuren som figurens text. För värden med datatyper som inte är **strängar** sker konverteringen till text automatiskt.

> [!NOTE]
> Du kan konfigurera en **cell**-komponent så att den fyller i en form endast om en formegenskap för text stöds.

När en **Cell**-komponent konfigureras för att ange ett värde i Excel-bild kan den bindas till en datakälla som returnerar ett värde av datatypen **Behållare** som representerar en bild i ett binärt format. I det här fallet anges värdet i Excel-bilden som en bild.

> [!NOTE]
> Alla Excel-bilder och -former betraktas som förankrade med sitt övre vänstra hörn till en viss Excel-cell eller ett visst Excel-intervall. Om du vill replikera en Excel-bild eller -form måste du konfigurera cellen eller intervallet som den är fäst till som en replikerad cell eller ett cellområde.

Mer information om hur du bäddar in bilder och former finns i [Bädda in bilder och former i dokument som du skapar med hjälp av ER](electronic-reporting-embed-images-shapes.md).

## <a name="page-break-component"></a>Komponenten PageBreak

Komponenten **PageBreak** tvingar Excel att påbörja en ny sida. Den här komponenten behövs inte om du vill använda Excels standardsidindelning, men du bör använda den när du vill att Excel följer ditt ER-format för att strukturera sidindelning.

## <a name="edit-an-added-er-format"></a>Redigera ett tillagt ER-format

### <a name="update-a-template"></a>Uppdatera en mall

Du kan välja **Uppdatera från Excel** på fliken **Importera** i åtgärdsfönstret för att importera en uppdaterad mall till ett redigerbart ER-format. Under den här processen ersätts en mall för den valda **Excel\\-filkomponenten** med en ny mall. Innehållet i det redigerbara ER-formatet synkroniseras med innehållet i den uppdaterade ER-mallen.

- En ny komponent för ER-format kommer att skapas automatiskt för alla Excel-namn om komponenten i ER-format inte hittas i det redigerbara formatet.
- Alla ER-formatkomponenter tas bort från det redigerbara ER-formatet om det inte finns något korrekt Excel-namn.

> [!NOTE]
> Ange alternativet **Skapa formatelement för Excel-kalkylblad** som **Ja** om du vill skapa det valfria elementet **Ark** i det redigerbara ER-formatet.
>
> Om det redigerbara ER-formatet ursprungligen innehöll **ark**-element rekommenderar vi att du ställer in alternativet **Skapa formatelement för Excel-kalkylblad** som **Ja** när du importerar en uppdaterad mall. I annat fall kommer alla kapslade element i det ursprungliga **ark**-elementet att skapas från grunden. Därför kommer också alla bindningar för de återskapade formatelementen att gå förlorade i det uppdaterade ER-formatet.

![Alternativet Skapa formatelement för Excel-ark i dialogrutan Uppdatera från Excel](./media/er-excel-format-update-template.png)

Om du vill veta mer om den här funktionen följer du stegen i [Ändra format för elektronisk rapportering genom att återanvända Excel-mallar](modify-electronic-reporting-format-reapply-excel-template.md).

## <a name="validate-an-er-format"></a>Validera ett ER-format

När du validerar ett ER-format som kan redigeras görs en konsekvenskontroll för att säkerställa att Excel-namnet finns i den Excel-mall som används för närvarande. Du får ett meddelande om eventuella inkonsekvenser. För vissa inkonsekvenser kommer alternativet att åtgärda problem automatiskt att erbjudas.

![Meddelande om felvalidering](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>Kontrollera beräkning av Excel-formler

När ett utgående dokument i ett Microsoft Excel arbetsboksformat genereras, kan vissa celler i det här dokumentet innehålla Excel-formler. När funktionen **Aktivera användning av EPPlus bibliotek i ramverket för elektronisk rapportering** är aktiverad kan du styra när formlerna beräknas genom att ändra värdet för **Beräkningsalternativ**-[parametern](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows) i Excel-mallen som används:

- Välj **Automatisk** för att beräkna om alla beroende formler varje gång som ett genererat dokument läggs till av nya områden, celler osv.
    >[!NOTE]
    > Det kan orsaka ett prestandaproblem för Excel-mallar som innehåller många relaterade formler.
- Välj **Manuell** för att undvika omberäkningar av formler när ett dokument genereras.
    >[!NOTE]
    > Omräkning av formel utförs påtvingat manuellt när ett genererat dokument öppnas för förhandsgranskning med Excel.
    > Använd inte det här alternativet om du konfigurerar en ER-destination som förutsätter användning av ett genererat dokument utan förhandsgranskning i Excel (PDF-konvertering, e-post osv.) eftersom det genererade dokumentet kanske inte innehåller värden i celler med formler.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering](general-electronic-reporting.md)

[Utforma en konfiguration för rapportgenerering i OPENXML-format](tasks\er-design-reports-openxml-2016-11.md)

[Ändra format för elektronisk rapportering genom att tillämpa mallar från Excel igen](modify-electronic-reporting-format-reapply-excel-template.md)

[Använd horisontellt expanderbara intervall för att dynamiskt lägga till kolumner i Excel-rapporter](tasks/er-horizontal-1.md)

[Bädda in bilder och former i dokument som du skapar med ER](electronic-reporting-embed-images-shapes.md)

[Konfigurera elektronisk rapportering (ER) för att hämta data till Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)
