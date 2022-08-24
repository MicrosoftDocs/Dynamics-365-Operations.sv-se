---
title: Hantera flera härledda mappningar för en enskild modellrot
description: I den här artikeln beskrivs hur du hanterar flera härledda mappningar som har konfigurerats för en enskild modellrot.
author: kfend
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERSolutionTable, ERModelMappingTable
ms.openlocfilehash: 868d47ccfebb9a9753d93344c72b10ae4353b0e6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277521"
---
# <a name="manage-several-derived-mappings-for-a-single-model-root"></a>Hantera flera härledda mappningar för en enskild modellrot

[!include [banner](../includes/banner.md)]

En [Elektronisk rapportering (ER)](general-electronic-reporting.md) data modell komponent används i alla konfigurerade ER format komponent som datakälla för att generera utgående dokument. Om du vill beskriva en enskild affärsdomän konfigurerar du en datamodellkomponent som har många rotdefinitioner. 

I varje rotdefinition kan du representera data i domänen på det sätt som passar bäst för en viss rapportering. För varje rotdefinition kan du konfigurera en ER modellmappning komponent som Microsoft Dynamics 365 Finance-specifik implementeringen av din datamodell. På det här sättet beskriver du hur datamodellen fylls i när den körs.

Komponenter för ER-modellmappning kan finnas i ER-datamodell [konfigurationer](general-electronic-reporting.md#Configuration) och ER-modellmappningskonfigurationer. En enstaka ER-konfiguration kan innehålla många mappningskomponenter, som var och en är konfigurerad för en enda rotdefinition. Alternativt kan en enstaka ER-konfiguration innehålla bara en mappningskomponent som är konfigurerad för en enda rotdefinition.

Många konfigurationsleverantörer kan erbjuda ER-modellmappningskonfigurationer för samma ER-datamodell. Dessa modellmappningskonfigurationer kan innehålla mappningskomponenter för olika rotdefinitioner. Du kan använda en modellmappning för en rotdefinition som erbjuds av en [leverantör](general-electronic-reporting.md#Provider) och använda en modellmappning för en annan rotdefinition som erbjuds av en annan leverantör.

Procedurerna i den här artikeln förklarar hur du hanterar flera ER-modellmappningskonfigurationer för en ER-datamodell när de innehåller olika modellmappningskomponenter som konfigurerats för samma rotdefinition. 

För att slutföra procedurerna i detta ämne måste du tilldelas rollen Systemadministratör eller utvecklare av elektronisk rapportering.

Alla följande procedurer kan göras i USMF företaget. Ingen kod behövs.

## <a name="configure-the-er-framework"></a>Konfigurera ER-ramverket

Som användare i rollen Utvecklare för elektronisk rapportering [konfigurerar du den minsta uppsättningen](er-quick-start2-customize-report.md#ConfigureFramework) av ER-parametrar innan du använder ER-ramverket för att designa din nya ER-lösning.

## <a name="import-the-standard-er-format-configurations"></a>Importera standardkonfiguration av ER-format

Om du vill lägga till standard-ER-konfigurationer i din aktuella Finance-instansen måste du importera dem från databasen som har konfigurerats för den instansen. Följ stegen i [Hämta ER-konfigurationer från den globala konfigurationsdatabasen för konfigurationstjänster](er-download-configurations-global-repo.md) för att importera följande ER-formatkonfigurationer:

- **Fritextfaktura (Excel)**, version 220.106
- **Projektfaktura (Excel)**, version 226.27

## <a name="review-the-imported-er-configurations"></a>Granska importerade ER-konfigurationer

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **Lokaliseringskonfiguration** i avsnittet **Konfigurationer** väljer du panelen **Rapporteringskonfiguration**.
3. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **Fakturamodell**.

    ![Granska de importerade konfigurationerna på sidan Konfigurationer.](./media/er-multiple-model-mappings-image1.png)

4. Granska formatet **Fritextfaktura (Excel)**:

    1. I konfigurationsträdet i det vänstra fönstret, välj **Fritextfaktura (Excel)**.
    2. Klicka på **Designer** i åtgärdsfönstret.
    3. På sidan **Formatdesigner** på fliken **Mappning** i listan för datakällor, välj **Modell**.
    4. Välj **Vy**.
    
       Det aktuella ER-formatet är konfigurerat till att använda rotdefinitionen **InvoiceCustomer** för **Fakturamodell**. När detta format körs och datakällan **Modell** anropas, används den modellmappning som konfigurerats för rotdefinitionen **InvoiceCustomer** för åtkomst till programdata och ifyllnad av datamodellen.

        ![Granska modelldatakällan på sidan Formatdesigner.](./media/er-multiple-model-mappings-image2.png)

    6. Stäng sidan **Formatdesigner**.

5. Granska innehållet i konfigurationen för **fakturamodellmappning**:

    1. I konfigurationsträdet i det vänstra fönstret, välj **Fakturamodellmappning**.
    2. Klicka på **Designer** i åtgärdsfönstret.
    3. På sidan **Modell till mappning av datakälla** page, observera att den nuvarande konfigurationen av ER-modellmappning innehåller flera komponenter för modellmappning:

        + Modellmappningen **Kundfaktura** konfigureras för rotdefinitionen **InvoiceCustomer** för **Fakturamodellen**. När ER-formatet för **Fritextfaktura (Excel)** körs modellmappningen **Kundfaktura** av den här ER-konfigurationen väljas för åtkomst till programdata och fyll i datamodellen.
        + Modellmappningen **Projektfaktura** konfigureras för rotdefinitionen **InvoiceProject** för **Fakturamodellen**. När ER-formatet för **Projektfaktura (Excel)** körs modellmappningen **Projektfaktura** av den här ER-konfigurationen väljas för åtkomst till programdata och fyll i datamodellen.

        ![Fakturamodellmappning på mappningssidan för Modell till datakälla.](./media/er-multiple-model-mappings-image3.png)

    4. Stäng sidan **modell till mappning av datakälla**.
    5. På snabbfliken **Versioner**, välj **Ta bort** om du vill ta bort alla versioner av denna ER-konfigurationen som är senare än den version 240.175.

6. Granska innehållet i konfigurationen för **Fakturamodellmappning för projekt (RDP)**:

    1. I konfigurationsträdet i det vänstra fönstret, välj **Fakturamodellmappning för projekt (RDP)**.
    2. Klicka på **Designer** i åtgärdsfönstret.
    3. På sidan **Modell till mappning av datakälla** observera att den aktuella ER-modellmappningskonfigurationen innehåller modellmappningen **InvoiceProject** och att denna modellmappning är konfigurerad för rotdefinitionen **InvoiceProject** för **fakturamodell**. När ER-formatet för **Projektfaktura (Excel)** körs, välj modellmappningen **InvoiceProject** för denna ER-konfigurationen för åtkomst till programdata och fyll i datamodellen.

        ![Fakturamodellmappning för projekt på mappningssidan Modell till datakälla.](./media/er-multiple-model-mappings-image4.png)

    4. Stäng sidan **modell till mappning av datakälla**.
    5. På snabbfliken **Versioner**, välj **Ta bort** om du vill ta bort alla versioner av denna ER-konfigurationen som är senare än den version 226.35.

## <a name="customize-the-imported-er-configurations"></a>Anpassa importerade ER-konfigurationer

I det här avsnittet beskrivs hur du anpassar [anpassar](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration) modellmappningarna som tillhandahålls av Microsoft. Anpassning kan till exempel krävas för att implementera din anpassade logik eller lägga till bindande som saknas.

### <a name="customize-the-invoice-model-mapping-configuration"></a>Anpassa konfigurationen av fakturamodellmappning

1. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster väljer du **Fakturamodellmappning**.
2. Klicka på **Skapa konfiguration** i åtgärdsfönstret.
3. I listrutan **Skapa konfiguration** i fältet **Ny** välj **Härled från namn: fakturamodellmappning, Microsoft**.
4. I fältet **Namn** ange **mappning av fakturamodell (Litware)**.
5. Välj **Skapa konfiguration**.
6. [Markera](er-quick-start2-customize-report.md#MarkFormatRunnable) versionen [utkast](general-electronic-reporting.md) av den härledda mappningen som tillgänglig för användning vid körning:

    1. I Åtgärdsfönstret, på fliken **Konfigurationer**, i gruppen **Avancerade inställningar**, markerar du **Användarparametrar**.
    2. I dialogrutan **Användarparametrar** ange alternativet **Kör inställningar** till **Ja** och väljer sedan **OK**.
    3. Välj **redigera** för att göra sidan klar för redigering.
    4. För konfigurationen av **mappning av fakturamodell (Litware)** som för närvarande valts i konfigurationsträdet, ange alternativet **Kör utkast** till **Ja**.

7. I åtgärdsfönstret, välj **Designer** för att granska modellmappningarna för den här konfigurationen.

    ![Granska fakturamodellmappning för projekt på mappningssidan Modell till datakälla.](./media/er-multiple-model-mappings-image5.png)

    > [!TIP]
    > Du kan nu öppna någon av ER-modellmappningskomponenterna i den här ER-konfigurationen i designern för att konfigurera din anpassade logik. Mer information finns i [Anpassa modellmappningskonfigurationen](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration).

8. Stäng sidan **modell till mappning av datakälla**.

Du har nu konfigurationer **Fakturamodellmappning** och **Fakturamodellmappning (Litware)** som alla har en modellmappning som är konfigurerad för rotdefinitionen **InvoiceCustomer**. Tilldela explicit en av modellmappningarna som standardmodellmappning som används i något av ER-formaten, till exempel formatet **Fritextfaktura (Excel)** som innehåller en modelldatakälla som har rotdefinitionen **InvoiceCustomer**. Om du kör, redigerar eller validerar ett av ER-formaten är följande undantag ett meddelande om att ingen standardmodellmappning har tilldelats explicit:
 
> Det finns fler än en modellmappning för '\<model name\> (\<root descriptor\>)' datamodellen i konfigurationerna \<configuration names separated by commas\>. Ställ in en av konfigurationerna som standard.

![Öppna formatet för redigering på sidan Konfigurationer.](./media/er-multiple-model-mappings-image6.gif)

### <a name="customize-the-project-invoice-model-mapping-rdp-configuration"></a>Anpassa konfigurationen av Fakturamodellmappning för projekt (RDP)

1. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster väljer du **Fakturamodellmappning för projekt (RDP)**.
2. Klicka på **Skapa konfiguration** i åtgärdsfönstret.
3. I dialogrutan **Skapa konfiguration** i fältet **Ny** välj **Härled från namn: Fakturamodellmappning för projekt (RDP), Microsoft**.
4. I fältet **Namn** ange **Fakturamodellmappning för projekt (Litware)**.
5. Välj **Skapa konfiguration**.
6. För konfigurationen av **Fakturamodellmappning för projekt (Litware)** som för närvarande valts i konfigurationsträdet, ange alternativet **Kör utkast** till **Ja**.
7. I åtgärdsfönstret, välj **Designer** för att granska modellmappningarna för den här konfigurationen.

    ![Granska den anpassade fakturamodellmappningen för projekt på mappningssidan Modell till datakälla.](./media/er-multiple-model-mappings-image7.png)

8. Stäng sidan **modell till mappning av datakälla**.

Du har nu konfigurationer **Fakturamodellmappning**, **Fakturamodellmappning för projekt (RDP)** och **Fakturamodellmappning för projekt (Litware)**. För var och en av dessa konfigurationer finns en modellmappning konfigurerad för rotdefinitionen **InvoiceProject**. Tilldela explicit en av modellmappningarna som standardmodellmappning som används i något av ER-formaten. Använd till exempel formatet **Projektfaktura (Excel)** som innehåller en modelldatakälla som har rotdefinitionen **InvoiceProject**. Om du kör eller redigerar ett av ER-formaten erhålls ett undantag för att meddelande om att ingen standardmodellmappning har tilldelats explicit.

## <a name="select-the-derived-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>Välj den härledda konfigurationen av fakturamodellmappning, som konfiguration som innehåller standardmodellmappningar

1. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster väljer du **Fakturamodellmappning Litware**.
2. Ange alternativet **standard för modellmappning** till **Ja**.

    ![Ange modellmappningen som standardmodellmappning på sidan Konfigurationer.](./media/er-multiple-model-mappings-image8.png)

    På grund av den här inställningen används modellmappningen för **kundfakturakopia** används när du kör **fritextfaktura (Excel)** eller när du redigerar eller validerar den. Modellmappning **Kundfaktura** från konfigurationen **Fakturamodellmappning** ignoreras.

    Du kan nu öppna formatet **fritextfaktura (Excel)** för granskning i formatdesignern.

## <a name="select-the-derived-project-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>Välj den härledda konfigurationen av Fakturamodellmappning för projekt (Litware), som konfiguration som innehåller standardmodellmappningar

1. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster väljer du **Fakturamodellmappning för projekt Litware**.
2. Ange alternativet **standard för modellmappning** till **Ja**.

    I det här fallet, till skillnad från det fall som beskrivs för konfigurationen **Fakturamodellmappning för projekt Litware** i föregående avsnitt, kan du inte börja använda modellmappningen **InvoiceProject Copy** från konfigurationen **Fakturamodellmappning för projekt Litware**. Två konfigurationer som innehåller en modellmappning för rotdefinitionen **InvoiceProject** markeras för närvarande som standardkonfiguration. Därför har de samma prioritet som används. Du löser det här problemet genom att utföra resten av stegen i den här proceduren.

3. I konfigurationsträdet i det vänstra fönstret, välj **Fakturamodellmappning Litware**.
4. Klicka på **Designer** i åtgärdsfönstret.
5. På sidan **Modell till mappning av datakälla** välj **Redigera** om du vill göra sidan redigerbar, efter behov.
6. Markera modellmappningen **Projektfakturakopia** och markera kryssrutan **Är borttagen** för det.

    ![Ställa in modellmappningen som praktiskt taget borttagen på mappningssidan för Modell till datakälla.](./media/er-multiple-model-mappings-image9.png)

    På grund av denna inställning behandlas konfigurationen för **mappning av fakturamodell (Litware)** som om den inte har någon modellmappning för rotdefinitionen **InvoiceProject**. Modelmappningen **InvoiceProject Copy** utfärdas som standard. Den här konfigurationen, **Fakturamodellmappning för projekt (Litware)**, som innehåller denna modellmappning är markerad som standardmodellmappningar. Eftersom den är markerad som standard har den högre prioritet än modellmappningen **InvoiceProject** från konfigurationen **Fakturamodellmappning för projekt (RDP)**.

## <a name="other-considerations"></a>Övriga beaktanden

Modellmappningen **InvoiceProject Copy** för konfiguration **Fakturamodellmappning för projekt (Litware)** har utformats för att använda datakällan **ReportDataProvider**. Datakällan är en del av typen *Objekt* som refererar till programklassen **PsaProjInvoiceDP**. Den här klassen implementeras som dataprovider för projektfakturan för rapporten SQL Server Reporting Services (SSRS) i ramverket Utskriftshantering. Välj den här datakällan som [ER-integrationspunkt](er-apis-app10-0-11.md#api-to-run-a-format-mapping-for-the-generation-of-outbound-documents). Den här inställningen beaktas när ER-implementeringen för utskriftshanteringsrapporter skrivs ut. Mer information finns i källkoden för programklassen **ERPrintMgmtDataProviderReport**. Vid körning innebär tilldelningen av datakällan **ReportDataProvider** som modellmappningens integrationspunkt tvingar Finance att behandla denna mappningskomponent med en högre prioritet än mappningskomponent **InvoiceProject** från konfigurationen **Fakturamodellmappning för projekt (RDP)**.

## <a name="see-also"></a>Se även

- [Hantera ER-modellmappning i separata ER-konfigurationer](./tasks/er-manage-model-mapping-configurations-july-2017.md)
- [Konfigurera ER-modellmappningar som är beroende av landssammanhang](er-country-dependent-model-mapping.md)
- [Ändringar i ramverks-API för elektroniskt rapportering](er-apis-app10-0-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
