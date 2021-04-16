---
title: Spåra skapade rapportresultat och jämföra dem med baslinjevärden
description: Det här avsnittet förklarar hur du kan jämföra resultaten av skapade ER-rapporter (elektronisk rapportering) med baslinjerapportvärden.
author: NickSelin
ms.date: 06/17/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: a8609cb026e7738eab96980bc9fe4a53340272eb
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5743591"
---
# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>Spåra skapade rapportresultat och jämföra dem med baslinjevärden

[!include[banner](../includes/banner.md)]

Du kan spåra resultatet av ER-format (lektronisk rapportering) som skapar utgående elektroniska dokument. När genereringen av spårning är aktiverad (genom att använda ER-användarparametrar **Kör i felsökningsläge**), skapas en ny spårningspost i körningslogg för ER-format varje gång en ER-rapport körs. Följande information lagras i respektive spår som skapas:

- Alla varningar som skapades av valideringsregler
- Alla fel som skapades av valideringsregler
- Alla skapade filer som lagras som bilagor till spårningsposten

Du kan lagra enskilda baslinjeprogramfiler för alla ER-format. Filer betraktas som baslinjefiler när de beskriver de förväntade resultaten av rapporterna som körs. Om det finns en baslinjefil för ett ER-format som kördes när spårgenereringen aktiverades, kommer spårningen, utöver informationen som nämndes tidigare, att lagra resultatet av jämförelsen av det skapade elektroniska dokumentet tillbaslinjefilen. Med ett klick kan du också få det skapade elektroniska dokumentet och dess baslinjefil i en enda zip-fil. Sedan kan du göra detaljerad jämförelse med hjälp av ett externt verktyg såsom Windiff.

Du kan utvärdera spårningen för att analysera om elektroniska dokument som skapas innehåller förväntade innehåll. Du kan göra en sådan utvärdering i ett acceptanstestet för användare (UAT) – när kodbasen har ändrats (till exempel när du migrerar till en ny instans av programmet, installerar snabbkorrigeringspaket eller distribuerar kodändringar). På så sätt kan se du till att utvärderingen inte påverkar genomförandet av ER-rapporter som används. Utvärderingen för många ER rapporter kan göras i obevakat läge.

Om du vill veta mer om den här funktionen kan du spela upp ER-uppgiftsguiderna **ER Skapa rapporter och jämföra resultat (del 1)** och **ER Skapa rapporter och jämföra resultat (del 2)** som ingår i affärsprocessen **7.5.4.3 Testa IT-lösningar och tjänster (10679)** och kan hämtas från [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684). Dessa uppgiftsguider går igenom processen att konfigurera ER-ramverket för att använda basfiler till att utvärdera skapade elektroniska dokument.

## <a name="example-trace-generated-report-results-and-compare-them-with-baseline-values"></a>Exempel: Spåra genererade rapportresultat och jämför dem med baslinjevärden

Den här proceduren förklarar hur du konfigurerar ER-ramverket för insamling av information om körningar av ER-format och sedan utvärdera resultaten av dessa körningar. Som en del av utvärderingen jämförs genererade dokument med baslinjefilerna. I det här exemplet ska du skapa erforderliga ER-konfigurationer för exempelföretaget Litware, Inc. Den här proceduren är avsedd för användare med rollen Systemadministratör eller Utvecklare för elektronisk rapportering. Stegen kan utföras med hjälp av valfri datauppsättning.

För att slutföra stegen i detta exempel måste du i RCS först slutföra stegen i [Skapa konfigurationsleverantörer och välj dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md)

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet för **konfigurationsleverantörer** kontrollerar du att konfigurationsprovidern för exempelföretaget Litware, Inc. är listade och markerat som **aktivt**. Om du inte ser den här konfigurationsleverantören ska du följa stegen i [Skapa konfigurationsleverantörer och välj dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="configure-document-management-parameters"></a>Konfigurera dokumenthanteringsparametrar

1. Gå till **organisationsadministration** \> **dokumenthantering** \> **dokumenttyper** och skapa en ny dokumenttyp för att lagra baslinjefiler.
2. I fältet **klass** anger du **bifoga fil**.
3. I fältet **grupp** anger du **fil**.

![Sida för dokumenttyper](media/GER-BaselineSample-SetupDocumentType.PNG "Skärmbild av sidan dokumenttyper")

> [!NOTE]
> En ny dokumenttyp som har samma namn måste konfigureras för varje datauppsättning där du planerar att använda funktionen ER-baslinje.

### <a name="configure-er-parameters-to-start-to-use-the-baseline-feature"></a>Konfigurera ER-parametrar för att börja använda baslinjefunktionen

1. I arbetsytan **elektronisk rapportering** i avsnittet **Relaterade länkar** väljer du **parametrar för elektronisk rapportering**.

    ![Arbetsytan för elektronisk rapportering](media/GER-BaselineSample-ERWorkspace.PNG "Skärmbild av arbetsytan elektronisk rapportering")

2. På fliken **bifogade filer** i fältet **baslinje** anger du eller väljer den dokumenttyp som du just har skapat.

    ![Fliken bifogade filer på sidan parametrar för elektronisk rapport](media/GER-BaselineSample-ERParameters.PNG "Skärmbild av parametrar för elektronisk rapportering")

3. Välj **Spara** och stäng sidan **Parametrar för elektronisk rapportering**.

### <a name="add-a-new-er-model-configuration"></a>Lägg till en ny konfiguration för ER-modell

1. På arbetsytan **Elektronisk rapportering**, i avsnittet **Konfigurationer** väljer du panelen **Rapporteringskonfiguration**.
2. Klicka på **Skapa konfiguration** i åtgärdsfönstret.
3. I listrutan i fältet **namn** anger du **modell för att lära dig ER-baslinjer**.
4. Välj **skapa konfiguration** om du vill bekräfta att en ny post för ER-datamodell skapas.

![Den nedrullningsbara dialogrutan skapa konfiguration](media/GER-BaselineSample-ModelAdd.PNG "Skärmbild av den nedrullningsbara dialogrutan skapa konfiguration")

### <a name="design-a-data-model"></a>Designa en datamodell

1. På sidan **Konfigurationer** på åtgärdspanelen väljer du **Designer**.
2. Välj **Ny**.
3. Ange **Rot** i listrutan i fältet **namn**.
4. Markera **Lägg till**.
5. Välj **Rotreferens**.
6. Välj **OK** och välj sedan **spara**.
7. Stäng sidan **modelldesigner**.
8. Välj **Ändra status**.
9. Välj **Slutför** och välj sedan **OK**.

![Sidan Konfigurationer](media/GER-BaselineSample-ModelComplete.PNG "Skärmbild av sidan Konfigurationer")

### <a name="add-a-new-er-format-configuration"></a>Lägg till en ny konfiguration för ER-format

1. På sidan **Konfigurationer** på åtgärdspanelen väljer du **Skapa konfigurationer**.
2. I listrutan i fältgruppen **Ny**, väljer du alternativet **Format baserat på datamodell för att lära sig ER-baslinjer**.
3. I fältet **namn** anger du **format för att lära dig ER-baslinjer**.
4. Välj **skapa konfiguration** om du vill bekräfta att en ny post för ER-format skapas.

![Den nedrullningsbara dialogrutan skapa konfiguration](media/GER-BaselineSample-FormatAdd.PNG "Skärmbild av den nedrullningsbara dialogrutan skapa konfiguration")

### <a name="design-a-format"></a>Designa ett format

I det här exemplet ska du skapa ett enkelt ER-format för att generera XML-dokument.

1. På sidan **Konfigurationer** på åtgärdspanelen väljer du **Designer**.
2. Välj **Lägg till rot**.
2. Gör följande i listrutan:

    1. I trädet, välj **Allmänt\\Fil**.
    2. Skriv **Utdata** i fältet **Namn**.
    3. Välj **OK**.

3. Markera **Lägg till**.
4. Gör följande i listrutan:

    1. I trädet, välj **XML\\Element**.
    2. Skriv **Dokument** i fältet **Namn**.
    3. Välj **OK**.

5. I trädet, välj **Utdata\\Dokument**.
6. Markera **Lägg till**.
7. Gör följande i listrutan:

    1. I trädet välj **XML\\Attribut**.
    2. I fältet **Namn**, ange **ID**.
    3. Välj **OK**.

    ![Formatdesignersida](media/GER-BaselineSample-FormatLayoutDesign.PNG "Skärmbild av sidan Formatdesigner")

8. Välj **ta bort** på fliken **mappning**.
9. Välj **Lägg till rot**.
10. I listrutan i trädet väljer du **allmän\\parameter för användarindata** och följer sedan de här stegen:

    1. I fältet **Namn**, ange **ID**.
    2. I fältet **Etikett** anger du **Ange ID**.
    3. Välj **OK**.

11. I trädet, välj **Output\\Document\\Id**.
12. Välj **Bind** och välj sedan **Spara**.

![Formatdesignersida](media/GER-BaselineSample-FormatMappingDesign.PNG "Skärmbild av sidan Formatdesigner")

Baserat på den designade strukturen kommer det konfigurerade formatet att generera en XML-fil. Denna XML-kod innehåller elementet **Rot** som har attributet **ID** som är angivet med värdet som användaren anger i dialogrutan ER-körtid.

### <a name="generate-a-new-baseline-file-for-a-designed-er-format"></a>Generera en ny baslinjefil för ett utformat ER-format

1. På sidan **konfigurationer** på snabbfliken **versioner**, välj **kör**.
2. I fältet **Ange ID** anger du **1**.
3. Välj **OK**.

    ![Dialogrutan Elektroniska rapportparametrar](media/GER-BaselineSample-FormatRunToMakeBaselineFile1.PNG "Skärmbild av dialogrutan för parametrar för elektronisk rapportering")

4. Spara en lokal kopia av filen **out.Admin.xml** som genereras så att du kan använda den senare som en baslinje för det här ER-formatet.

    ![Meddelande om den genererade filen på sidan konfigurationer](media/GER-BaselineSample-FormatRunToMakeBaselineFile2.PNG "Skärmbild av meddelande om den genererade filen på sidan konfigurationer")

### <a name="configure-er-parameters-to-use-the-baseline-feature"></a>Konfigurera ER-parametrar för att använda baslinjefunktionen

1. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** markerar du **Använd parametrar**.
2. Ställ in alternativet **Kör i felsökningsläge** till **Ja**.
3. Välj **OK**.

![Dialogruta Användarparametrar](media/GER-BaselineSample-ERUserParameters.PNG "Skärmbild av dialogrutan användarparametrar")

### <a name="add-a-new-baseline-for-designed-er-format"></a>Lägg till en ny baslinje för ett utformat ER-format

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. Klicka på **Baslinjer** i åtgärdsfönstret.

    ![Knappen Baslinjer på sidan Konfigurationer](media/GER-BaselineSample-OpenBaselinePage.PNG "Skärmbild av knappen Baslinjer på sidan Konfigurationer")

3. Klicka på **Ny** i åtgärdsfönstret.
4. Välj **format för att lära dig ER-baslinjer** som du har utformat tidigare.
5. Välj **Spara**.

![Sidan Baslinjer med elektroniskt rapporteringsformat](media/GER-BaselineSample-AddBaseline.PNG "Skärmbild av sidan Baslinjer med elektroniskt rapporteringsformat")

Baslinjen läggs till i formatet **format för att lära dig ER-baslinjer**.

### <a name="configure-a-baseline-rule-for-the-added-baseline"></a>Konfigurera baslinjeregeln för den tillagda baslinjen.

1. På ssidan **Basliinjer för elektroniskt rapporteringsformat** i åtgärdfönstret, väljer du knappen **bifogade filer** (gemsymbolen).
2. I åtgärdsfönstret väljer du **Ny** \> **Fil**. I ER-parametrarna bör dokumenttypen **fil** ha valts tidgare som den dokumenttyp som används för att lagra baslinjefiler.
3. Välj **bläddra** och välj sedan filen **out. Admin.xml** som skapades när det konfigurerade ER-formatet kördes tidigare.

    ![Sidan Bilagor](media/GER-BaselineSample-UploadBaselineFile.PNG "Skärmbild av sidan Bilagor")

4. Stäng sidan **Bilagor**.
5. På snabbfliken **Baslinjer**, välj **Ny**.
6. Skriv **Baslinje 1** i fältet **Namn**.
7. I fältet **Filkomponentnamn** anger du eller väljer **Utdata**. Det här värdet anger att den konfigurerade baslinjen kommer att jämföras med en fil som genereras med formatelementet **Utdata**.
8. I fältet **Filnamnmask**, ange **\*.xml**.

    > [!NOTE]
    > Du kan definiera filnamnsmasken. När filnamnsmasken definieras kommer baslinjeposten att användas för att utvärdera genererade utdata först när namnet på utdatafilen som genereras uppfyller den masken.

9. Om den konfigurerade baslinjen endast ska användas när ER-formatet **när formatet för att lära dig ER-baslinjer-** körs av användare som är inloggade på specifika företag väljer du dessa företag i fältet **företag**.
10. I fältet **baslinje** anger eller väljer du bilagan **out.Admin**.
11. Välj **Spara**.

![Sidan Baslinjer med elektroniskt rapporteringsformat](media/GER-BaselineSample-SetupBaselineLine.PNG "Skärmbild av sidan Baslinjer med elektroniskt rapporteringsformat")

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Kör det utformade ER-formatet och granska loggen för att analysera resultaten

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. I trädet expanderar du **Modell för att ta reda på ER-baslinjer** och väljer sedan **Modell för att ta reda på ER-baslinjer\\Format för att ta reda på ER-baslinjer**.
3. Klicka på **Kör** på snabbfliken **Versioner**.
4. I fältet **Ange ID** anger du **1**.
5. Välj **OK**.
6. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfiguration av felsökningsloggar**.

    ![Sidan körningsloggar för elektronisk rapportering](media/GER-BaselineSample-ReviewBaselineComparison1.PNG "Skärmbild av sidan körningsloggar för elektronisk rapportering")

    > [!NOTE]
    > Körningsloggen innehåller information om resultaten av jämförelsen mellan den genererade filen och den konfigurerade baslinjen. I det här exemplet anger loggen att den genererade filen och baslinjen är lika.

7. Välj **Ta bort alla**.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Kör det utformade ER-formatet och granska loggen för att analysera resultaten

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. I trädet expanderar du **Modell för att ta reda på ER-baslinjer** och väljer sedan **Modell för att ta reda på ER-baslinjer\\Format för att ta reda på ER-baslinjer**.
3. Klicka på **Kör** på snabbfliken **Versioner**.
4. I fältet **Ange ID** anger du **2**.
5. Välj **OK**.
6. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfiguration av felsökningsloggar**.

    ![Sidan körningsloggar för elektronisk rapportering](media/GER-BaselineSample-ReviewBaselineComparison2.PNG "Skärmbild av sidan körningsloggar för elektronisk rapportering")

    > [!NOTE]
    > Körningsloggen innehåller information om resultaten av jämförelsen mellan den genererade filen och den konfigurerade baslinjen. I det här exemplet anger loggen att den genererade filen och baslinjen är olika.

7. Välj **Jämför**.

> [!NOTE]
> Den genererade filen och baslinjefilen tillhandahålls som en zip-fil. Du kan använda externa jämförelseverktyg, t.ex. WinDiff för att jämföra filerna och granska skillnaderna.

## <a name="additional-resources"></a>Ytterligare resurser

- [Konfigurera ramverket för elektronisk rapportering (ER)](electronic-reporting-er-configure-parameters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]