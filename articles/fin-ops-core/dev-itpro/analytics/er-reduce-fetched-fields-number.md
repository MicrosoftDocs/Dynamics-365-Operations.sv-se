---
title: Förbättra prestandan för ER-lösningar genom att minska antalet registerfält som hämtas under körning
description: Det här ämnet förklarar hur du kan hjälpa till att förbättra prestandan för ER-lösningar genom att minska antalet registerfält som hämtas under körning.
author: NickSelin
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: eb76c415da87d421b8135a93b84f4e905f01e70d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847463"
---
# <a name="improve-performance-of-er-solutions-by-reducing-the-number-of-table-fields-that-are-fetched-at-runtime"></a>Förbättra prestandan för ER-lösningar genom att minska antalet registerfält som hämtas under körning

[!include[banner](../includes/banner.md)]

Du kan designa [elektronisk rapportering](general-electronic-reporting.md) (ER) [format](er-overview-components.md#format-components-for-outgoing-electronic-documents) som skapar utgående dokument i olika format. När ett dokument skapas anropar ett ER-format datakällor som har konfigurerats i en motsvarande [ER-modellmappning](er-overview-components.md#model-mapping-component). Om du vill konfigurera åtkomst till programregister, frågor eller entiteter för att hämta poster kan du använda ER-datakällor av typen *Registerposter*. Datakällan i typen *registerpost* hämtar som standardvärdena för alla fält i de begärda posterna. Du kan dock konfigurera den här typen av datakälla så att den bara hämtar de fältvärden som krävs för det körande ER-formatet. Den här konfigurationen minskar minnesförbrukningen på programservern som utför datahämtning och ytterligare post cachelagring.

Slutför exemplet i den här artikeln om du vill veta mer om hur du begränsar listan med hämtade fält med datakällor för *registerposter*.

## <a name="example-reduce-the-number-of-table-fields-that-are-fetched-at-runtime"></a>Exempel: Minska antalet registerfält som hämtas vid körning

Följande procedurer visar hur en användare med rollen Systemadministratör eller Elektronisk rapporteringsutvecklare kan konfigurera en ER-modellmappning så att den bara hämtar de fält som krävs för att köra ER-formatet, för att minska förbrukningen av programserverminnet.

Dessa procedurer kan slutföras i **USMF**-företaget i Microsoft Dynamics 365 Finance. Ingen kod behövs.

För att slutföra detta exempel måste du ha åtkomst till **USMF** företag för en av följande roller:

- Konsult för funktionen för elektronisk rapportering
- Systemadministratör

I det här exemplet ska du använda ER-[konfigurationer](general-electronic-reporting.md#Configuration) som tillhandahålls för exempelföretaget **Litware, Inc.**. Se till att konfigurationsprovidern för exempelföretaget **Litware, Inc.** (`http://www.litware.com`) har listats för ER-ramverket samt att det har markerats som **Aktivt**. Om denna konfigurationsleverantör inte finns med i listan, eller om den inte är markerad som **Aktiv**, följer du stegen i [Skapa en konfigurationsleverantör och markera den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="configure-the-er-framework"></a>Konfigurera ER-ramverket

Följ stegen i [Konfigurera ER-ramverket](er-quick-start2-customize-report.md#ConfigureFramework) för att ställa in den minimala uppsättningen ER-parametrar. Du måste slutföra dessa inställningar innan du börjar använda ER-ramverket för att ändra datakällor för den tillhandahållna ER-lösningen.

### <a name="import-the-sample-er-configurations"></a>Importera ER-exempelkonfigurationer

Om du ännu inte har slutfört exemplet i ämnet [Designa en ny ER-lösning för att skriva ut en anpassad rapport](er-quick-start1-new-solution.md) ladda ner och lagra XML-filerna lokalt för följande konfigurationer av den medföljande ER-lösningen.

| Beskrivning av innehåll            | Filnamn |
|--------------------------------|-----------|
| Exempel på konfiguration av ER-datamodell.    | [Questionnaires model.version.1.xml](https://download.microsoft.com/download/b/6/3/b633bd34-d200-4422-96d9-8f62eb5218f8/Questionnaires_model.version.1.xml) |
| Konfiguration och ER-modellmappning | [Questionnaires mapping.version.1.1.xml](https://download.microsoft.com/download/7/b/2/7b258e4e-4bd5-46a4-8114-27419ae4acd8/Questionnaires_mapping.version.1.1.xml) |
| Konfiguration för ER-fomat        | [Questionnaires format.version.1.1.xml](https://download.microsoft.com/download/1/b/a/1ba39ec2-257a-44d8-972f-25bf7d18fb41/Questionnaires_format.version.1.1.xml) |

Följ sedan de här stegen när du vill överföra konfigurationerna för den angivna ER-lösningen till din ekonomiinstans.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. Välj **rapporteringskonfigurationer**.
3. På sidan **Konfigurationer**, importera ER-datamodellens konfiguration.

    1. Välj **Växel** och välj **Läs in från XML-fil**.
    2. Välj **Bläddra**, leta och välj filen **Questionnaires model.version.1.xml** och välj **OK**.

4. Importera ER-konfiguration för modellmappning.

    1. Välj **Växel** och välj **Läs in från XML-fil**.
    2. Välj **Bläddra** och markera filen **Questionnaires mapping.1.1.xml** och sedan **OK**.

5. Importera ER-formatkonfiguration.

    1. Välj **Växel** och välj **Läs in från XML-fil**.
    2. Välj **Bläddra** och markera filen **Questionnaires format.1.1.xml** och sedan **OK**.

6. I konfigurationsträdet expanderar du **enkätmodell**.
7. Granska listan över importerade ER-konfigurationer i konfigurationsträdet.

    ![Granska lista över importerade ER-konfigurationerna på sidan Konfigurationer.](./media/er-reduce-fetched-fields-number-configurations.png)

### <a name="review-the-provided-er-model-mapping"></a>Granska den ER-modellmappning som tillhandahålls

1. På sidan **Konfigurationer**, välj **enkätmappning**.
2. Klicka på **Designer** i åtgärdsfönstret.
3. På sidan **Modell för mappning av datakälla** väljer du **Designer**.
4. På sidan **Modellmappningsdesigner** i åtgärdsfönstret väljer du **Gruppvy** om du vill aktivera vyn **Grupp**.
5. I fönstret **Datamodell** expandera **Enkät**.

    Observera datakällan **Enkät** datakällan har konfigurerats för att komma åt `KMCollection` apptabell.

6. I fönstret **Datakällor** expandera **Registerposter** \> **Enkät** \> **Fält**.

    Lägg märke till hur många fält från `KMCollection` programregistret som visas av datakällan **Enkät** för typen *Registerpost*.

    ![Granskning av den angivna modellmappningen på sidan Modellmappningsdesigner när gruppvyn aktiveras.](./media/er-reduce-fetched-fields-number-mapping1.png)

7. I åtgärdsfönstret väljer du **Gruppvy** igen för att stänga av **Gruppvyn**, och välj sedan **Visa alla** \> **Visa bara mappade**.

    Lägg märke till att några fält i programregistret `KMCollection` används för att fylla i postlistan **Enkät** i ER-datamodellen:

    - `Active`
    - `Description`
    - `questionMode`
    - `kmCollectionId`

    ![Granskning av den angivna modellmappningen på sidan Modellmappningsdesigner när gruppvyn inaktiveras.](./media/er-reduce-fetched-fields-number-mapping2.png)

### <a name="turn-on-the-er-performance-trace"></a>Aktivera ER-prestandaspårning

Följ stegen i [Aktivera ER-prestandaspårning](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) för att ställa in ER-användarparametrarna som gör att körning av ER-komponenter kan spåras.

### <a name="run-the-provided-er-format-by-using-the-provided-model-mapping"></a>Kör det angivna ER-formatet genom att använda den angivna modellmappningen

Följ anvisningarna i [Kör ett utformat format från ER](er-quick-start1-new-solution.md#RunFormatFromER) för att köra det angivna ER-formatet för en enkät från sidan **Konfigurationer**.

### <a name="review-the-execution-trace-of-the-first-run"></a>Granska körningsspårningen av första körningen

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering \> Konfigurationer**.
2. På sidan **Konfigurationer**, expandera **Enkätmodell** och välj **Enkätmappning**.

    > [!NOTE]
    > Informationen på snabbflikarna **versioner** visar att du har valt utkastversionen för konfigurationen **Enkätmappning**. Därför kan du ändra innehållet i modellmappningen.

3. Klicka på **Designer** i åtgärdsfönstret.
4. På sidan **Modell för mappning av datakälla** väljer du **Designer**.
5. På snabbfliken **Modellmappningsdesigner** på åtgärdsfönstret väljer du **Prestandaspårningsformat**.
6. I dialogrutan **Resultatinställningar för resultatspårning** välj spåret som genererades under den senaste formatkörningen.

    ![Välja spåret i dialogrutan Resultatinställningar för resultatspårning.](./media/er-reduce-fetched-fields-number-select-trace-1.png)

7. Välj **OK**. 
8. På snabbfliken **Detaljer**, filtrera sökvägen **Enkät** som pekar på datakällan **Enkät**.
9. Granska informationen om databasfrågan som genererades när datakällan **Enkät** anropades.

    Lägg märke till att alla fält i `KMCollection` programregistret hämtades vid körning när datakällan **enkät** anropades.

    ![Granska informationen om databasfrågan på sidan Modellmappningsdesigner.](./media/er-reduce-fetched-fields-number-query1.png)

### <a name="modify-the-provided-er-model-mapping"></a>Ändra den ER-modellmappning som tillhandahålls

1. På sidan **Modellmappingsdesigner** i fönstret **Datakällor** väljer du datakällan **Enkät**.
2. I fönstret **Datakällor**, välj **Redigera**.
3. I dialogrutan **Egenskaper för datakälla**, välj **Välj fält** för att ange listan över fält för den refererade `KMCollection` programtabell som kommer att hämtas vid körning när den redigerbara datakällan **Enkät** anropas.

    ![Välj fält i dialogrutan Datakällaegenskaper för att börja konfigurera listan över fält som kommer att hämtas från programtabellen med hjälp av den redigerbara datakällan.](./media/er-reduce-fetched-fields-number-select-fields1.png)

4. På sidan **Välj fält**, välj **Fylla i automatiskt**.

    Listan **Valda fält** fylls i automatiskt utifrån förkonfigurerade artefakter för modellmappningen. Alla fält och relationer i det refererade registret som nämns i någon bindande, formel eller datakälla för modellmappningen läggs till i listan.

    ![Konfigurera listan med fält som ska hämtas från programregistret på sidan Välj fält.](./media/er-reduce-fetched-fields-number-select-fields2.png)

5. Välj **Spara** och stäng sidan **Välj fält**.
6. Välj **OK** om du vill lagra de ändringar du har gjort i datakällsinställningarna.
7. Klicka på **Visa alla** i åtgärdsfönstret.

    Lägg märke till att datakällan **Enkät** visar nu texten **\<Fields are filtered\>**. Den här texten visar att datakällan har konfigurerats för hämtning av ett begränsat antal fält från det refererade programregistret.

    ![Granska den uppdaterade modellmappningen på sidan Modellmappningsdesigner.](./media/er-reduce-fetched-fields-number-mapping3.png)

8. Välj **Spara** om du vill lagra de ändringar du har gjort i redigerbar modellmappning.

    > [!NOTE]
    > Vid körning analyserar ER de tillagda relationerna och lägger till alla fält som används i dem i databasfrågan, även om dessa fält inte explicit läggs till i listan med hämtade fält vid designtid.

### <a name="run-the-provided-er-format-by-using-the-updated-model-mapping"></a>Kör det angivna ER-formatet genom att använda den uppdaterade modellmappningen

Följ anvisningarna i [Kör ett utformat format från ER](er-quick-start1-new-solution.md#RunFormatFromER) för att köra det angivna ER-formatet för en enkät från sidan **Konfigurationer**.

### <a name="review-the-execution-trace-of-the-second-run"></a>Granska körningsspårningen av andra körningen

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **Konfigurationer**, expandera **Enkätmodell** och välj **Enkätmappning**.
3. Klicka på **Designer** i åtgärdsfönstret.
4. På sidan **Modell för mappning av datakälla** väljer du **Designer**.
5. På snabbfliken **Modellmappningsdesigner** på åtgärdsfönstret väljer du **Prestandaspårningsformat**.
6. I dialogrutan **Resultatinställningar för resultatspårning** välj spåret som genererades under den senaste formatkörningen.
7. Välj **OK**.
8. På snabbfliken **Detaljer**, filtrera sökvägen **Enkät** som pekar på datakällan **Enkät**.
9. Granska informationen om databasfrågan som genererades när datakällan **Enkät** anropades.

    Observera att endast de fält som krävs för att fylla i datakällan hämtades under körningen från `KMCollection` programregistret när datakällan **Enkät** anropades.

    > [!NOTE]
    > En del fält, som fälten för partitions-ID, dataområdes-ID och post-ID, läggs automatiskt till i datahanteringsramverket i programmet Ekonomi.

    ![Granska informationen om databasfrågan för den uppdaterade modellmappning på sidan Modellmappningsdesigner.](./media/er-reduce-fetched-fields-number-query2.png)

Du kan använda den här metoden om du vill minska antalet hämtade poster när du måste minska minnesförbrukningen genom att köra ER-modellmappning och ER-format.

## <a name="limitations"></a>Begränsningar

När du begränsar antalet hämtade fält för en datakälla av typen *Registerposter* kan du inte använda metoderna i ett programregister som datakällan refererar till, eftersom programmetadata inte innehåller information om registerfält som krävs för att anropa dessa metoder.

## <a name="usage-notes"></a>Användningsanteckningar

Även om kommandot **fylla i automatiskt** lägger till fält, raderar det inte automatiskt fält som har lagts till tidigare, även om de inte längre används i bindande, formler och datakällor för den redigerbara modellmappningen.

När du väljer **fylla i automatiskt** analyserar ER bindande, formler och datakällorna som den redigerbara modellmappningen hade när du öppnade den för redigering. Om du ändrar bindande, formler och datakällor för den redigerbara modellmappningen och vill använda kommandot **fylla i automatiskt**, stänger du modellmappningsdesignern och öppnar den igen för att redigera modellmappningen. 

## <a name="additional-resources"></a>Ytterligare resurser

- [Spåra körningen av ER-format för att felsöka prestandaproblem](trace-execution-er-troubleshoot-perf.md)
- [Felsöka prestandaproblem i ER-konfigurationer](er-troubleshoot-perf-issues-in-configurations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
