---
title: Förbättringar i spårning av resultaten från genererade ER-rapporter och jämföra dem med baslinjevärden
description: Det här avsnittet innehåller information om hur funktionen ER-baslinje har förbättrats i Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (juni 2019).
author: NickSelin
manager: AnnBe
ms.date: 06/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 55e821b27f80383d8a8dc7a2d46f87e17c554078
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682857"
---
# <a name="improvements-in-tracing-the-results-of-generated-er-reports-and-comparing-them-with-baseline-values"></a>Förbättringar i spårning av resultaten från genererade ER-rapporter och jämföra dem med baslinjevärden

[!include[banner](../includes/banner.md)]

I det här avsnittet beskrivs den första uppsättningen med förbättringar av funktionen för baslinje i det elektroniska rapportramverket (ER). Dessa förbättringar finns i Microsoft Dynamics 365 for Finance and Operations version 10.0.3 (juni 2019) och senare.

## <a name="automate-the-setting-of-baseline-rules"></a>Automatisera inställningen av baslinjeregler

Ämnet [Spårningsgenererade rapportresultat och jämföra dem med baslinjevärden](er-trace-reports-compare-baseline.md) beskriver hur du konfigurerar ER-ramverket för insamling av information om ER-formatering och utvärdering av resultaten av dessa körningar. I exemplet i det här avsnittet visas de steg som måste utföras.

Här följer några steg:

- Kör ett ER-format för att skapa en utgående fil och spara filen lokalt.
- Lägg till den lokalt lagrade filen som en bilaga till den baslinje som lades till för ER-format.
- Konfigurera baslinjergeln för den tillagda baslinjen. Den här konfigurationen omfattar följande steg:

    - Ange ett ER-formatelement som används för att generera en utgående fil.
    - Markera den bilaga som refererar till den genererade utgående filen.

> [!NOTE]
> Du måste utföra dessa steg manuellt, även om de nya ER-funktionerna gör det möjligt att automatisera dem. Om du vill veta mer om den här funktionen fyller du i följande exempel.

## <a name="example-automate-the-setting-of-baseline-rules"></a>Exempel: Automatisera inställningen av baslinjeregler

Om du vill slutföra stegen i det här exemplet måste du först slutföra stegen i exemplet i [Spåra skapade rapportresultat och jämföra dem med baslinjevärden](er-trace-reports-compare-baseline.md) i avsnittet "lägga till en ny baslinjeplan för ett utformat ER-format".

### <a name="review-added-baseline"></a>Granska tillagda baslinjer

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. Välj **baslinjer**.

    > [!NOTE]
    > Knappen **baslinjer** i åtgärdsfönstret är bara tillgänglig om parametern **kör i felsökningsläge** ER-användarparameter är aktiverad för det aktuella företaget.

Baslinjen har lagts till för det valda formatet **Format för att lära ER-baslinjer** men baslinjereglerna har ännu inte lagts till för denna baslinje.

![Sidan Baslinjer med elektroniskt rapporteringsformat](media/GER-BaselineSample-AddBaseline2.PNG "Skärmbild av sidan Baslinjer med elektroniskt rapporteringsformat")

### <a name="make-a-new-baseline-rule"></a>Skapa en ny baslinjeregel

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. I trädet expanderar du **modell för att lära sig ER-baslinjer**.
3. Välj **modell för att lära dig ER-baslinjer\\format för att lära dig ER-baslinjer**.
4. Klicka på **Kör** på snabbfliken **Versioner**.
5. I fältet **Ange Id** anger du **1**.
6. Ställ in alternativet **gör baslinjefiler** till **Ja**.
7. Välj **OK**.
8. Välj **baslinjer**.

    ![Sidan Baslinjer med elektroniskt rapporteringsformat](media/GER-BaselineSample-ReviewAddedBaselineLine.PNG "Skärmbild av sidan Baslinjer med elektroniskt rapporteringsformat")

    Den genererade utgående filen har automatiskt kopplats till baslinjen för det körda ER-formatet. Baslinjeregeln läggs automatiskt till i denna baslinje och innehåller också referensen till den bifogade filen.

9. Skriv **Baslinje 1** i fältet **Namn**.
10. I fältet **Filnamnmask**, ange **.xml**.
11. Välj **Spara**.

### <a name="run-the-format"></a>Kör formatet

Du är nu redo att slutföra de återstående stegen i exemplet i [Spåra skapade rapportresultat och jämföra dem med baslinjevärden](er-trace-reports-compare-baseline.md) med hjälp av avsnittet "kör det utformade ER-formatet och granska loggen för analys av resultaten".

> [!NOTE]
> När du tar bort den automatiskt tillagda baslinjeregeln på snabbfliken **Baslinjer** tas refererade bifogade filer inte bort automatiskt.

## <a name="configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>Konfigurera baslinjen så att den ignorerar konstant ändring av delar av ER-resultat

När ett ER-format har utformats för att innehålla information som ändras när formatet körs måste formatet vara obligatoriskt för användning av funktionen ER-baslinje för att jämföra genererade resultat med baslinjevärden. Informationen kan till exempel vara bearbetningsdatum och -tid eller en unik identifierare för ett genererat dokument i olika format (globala unika identifieraren\[GUID\] och så vidare). Med de nya ER-funktionerna kan du konfigurera baslijeregler så att den ignorerar ändringsbara element i ett ER- format när formatet körs med syftet att jämföra baslinjevärden med resultatet av formatets körning. Om du vill veta mer om den här funktionen fyller du i följande exempel.

## <a name="example-configure-the-baseline-so-that-it-ignores-constantly-changing-parts-of-the-er-output"></a>Exempel: Konfigurera baslinjen så att den ignorerar konstant ändring av delar av ER-resultat

Om du vill slutföra stegen i det här exemplet måste du först slutföra stegen i exemplet i [Spåra skapade rapportresultat och jämföra dem med baslinjevärden](er-trace-reports-compare-baseline.md).

### <a name="modify-a-configured-er-format"></a>Ändra ett konfigurerat ER-format

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. I trädet expanderar du **modell för att lära sig ER-baslinjer**.
3. Välj **modell för att lära dig ER-baslinjer\\format för att lära dig ER-baslinjer**.
4. Välj **Designer**.
5. I trädet, välj **Utdata\\Dokument**.
6. Markera **Lägg till**.
7. I listrutan i trädet väljer du **XML\\Attribut**.
8. I fältet **Namn** anger du **ProcessingDateTime**.
9. Välj **OK**.
10. På fliken **Mappning** i trädet väljer du **Resultat\\Dokument\\ProcessingDateTime**.
11. Välj **Redigera recept**.
12. I fältet **Formel** anger du följande uttryck: **DATETIMEFORMAT(NOW(), "O")**
13. Välj **spara** och välj sedan **test**.
14. Välj **test** igen om du vill testa om det konfigurerade uttrycket.

    ![Sidan Formeldesigner](media/GER-BaselineSample-DefineProcessingDTExpression.PNG "Skärmbild av sidan Formeldesigner")

    > [!NOTE]
    > På fliken **testresultat** visas att det konfigurerade uttrycket returnerar ett annat datum- och tidsvärde när det anropas.

15. Stäng sidan **Formeldesigner** och välj sedan **Spara**.

    ![Formatdesignersida](media/GER-BaselineSample-FormatMappingDesign2.PNG "Skärmbild av sidan Formatdesigner")

16. Stäng sidan **Formatdesigner**.

### <a name="remove-an-existing-baseline-rule"></a>Ta bort en befintlig baslinjeregel

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. Välj **baslinjer**.
3. I listan över baslinjer väljer du den baslinje som har konfigurerats för formatet **Format för att lära sig ER-baslinjer**.
4. På snabbfliken **baslinjer** väljer du **ta bort** för att ta bort den baslinjeregel som du konfigurerade tidigare.

![Sidan Baslinjer med elektroniskt rapporteringsformat](media/GER-BaselineSample-AddBaseline3.PNG "Skärmbild av sidan Baslinjer med elektroniskt rapporteringsformat")

### <a name="define-replacements-for-bindings-of-designed-er-format"></a>Definiera ersättningar för bindningar av utformade ER-format

1. På sidan **konfigurationer** på snabbfliken **ersättningar**, välj **välj komponenter**.
2. I trädet formatkomponenter expanderar du **Utdata**, expanderar **Utdata\\dokument** och markerar sedan kryssrutan **Utdata\\dokument\\ProcessingDateTime**.
3. Välj **OK**.

![Sidan Baslinjer med elektroniskt rapporteringsformat](media/GER-BaselineSample-AddBaseline4.PNG "Skärmbild av sidan Baslinjer med elektroniskt rapporteringsformat")

Den valda ER-formatkomponenten har lagts till i listan över komponenter på snabbfliken **ersättningar**. När bas-ER-formatet körs i felsökningsläge ersätts formatets bindning för varje komponent med bindningen som visas i kolumnen **bindning**. Om du vill ändra standardbindningen för en komponent som visas på snabbfliken **ersättningar** väljer du **redigera**.

### <a name="make-a-new-baseline-rule"></a>Skapa en ny baslinjeregel

Följ stegen i avsnittet "exempel: automatisera inställningen av baslinjeregler" ovan i det här avsnittet. Ett meddelande visas med en varning om att den utgående filen har genererats med hjälp av inställningar för baslinje och att formatbindningarna har bytts ut.

![Meddelande på sidan Konfigurationer](media/GER-BaselineSample-FormatRunToMakeBaselineFile4.PNG "Skärmbild av meddelande på sidan Konfigurationer")

### <a name="suppress-warnings-about-the-replacement-of-format-bindings"></a>Ignorera varningar om byte av formatbindningar

Genom att ställa in specifika ER-parametrar kan du utelämna meddelanden som varnar vid byte av formatbindningar. Denna undertryckning kan vara användbar när formatbindningar ersätts i obevakat läge med hjälp av Regression Suite Automation Tool. I det här fallet kan varningen betraktas som ett fel i testfallet som körs.

1. På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **Konfigurationer** markerar du **Använd parametrar**.
2. Ange alternativet **Undertryck baslinjevarningar** till **Ja** och välj sedan **OK**.

### <a name="review-the-generated-baseline-file"></a>Granska den skapade baslinjefilen.

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. Välj **baslinjer**.
3. Välj **bilagor**.
    > [!NOTE]
    > Den genererade filen innehåller bearbetningsdatumet och tidstexten (**"#"**) från bindningen som konfigurerats i den tillagda baslinjeregeln, inte från formatets bindning.
    
4. Stäng sidan **Bilagor**.

### <a name="run-the-designed-er-format-and-review-the-log-to-analyze-the-results"></a>Kör det utformade ER-formatet och granska loggen för att analysera resultaten

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. I trädet expanderar du **modell för att lära sig ER-baslinjer**.
3. Välj **modell för att lära dig ER-baslinjer\\format för att lära dig ER-baslinjer**.
4. Klicka på **Kör** på snabbfliken **Versioner**.
5. I fältet **Ange Id** anger du **1**.
6. Välj **OK**.
7. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfiguration av felsökningsloggar**.

Körningsloggen innehåller information om resultaten av jämförelsen mellan den genererade filen och den konfigurerade baslinjen. Loggen anger att den genererade filen och baslinjen är lika även om det körda formatet innehåller bindningen för att ange ett konstant värde för datum och tid i den utgående filen.

> [!NOTE]
> Även om den utgående filen har genererats med hjälp av inställningar för baslinje som tvingar fram bindningar av formatets bindningar, får du inga varningar om ersättningen.

## <a name="exchange-baseline-settings-between-environments"></a>Inställningar för byte av baslinjeinstllningar mellan miljöer

### <a name="export-baseline-settings"></a>Exportera baslinjeinställningar

Med de nya ER-funktionerna kan du exportera baslinjeinställningar för det valda ER-formatet från den aktuella miljön och lagra dem som XML-filer. 

Om du vill exportera inställningar väljer du på sidan **Baslinjer med elektroniskt rapporteringsformat** **Exportera**.

### <a name="import-baseline-settings"></a>Importera baslinjeinställningar

Exporterade baslinjeinställningar kan importeras till en annan miljö. Miljön måste först importeras som ett ER-format. Du kan sedan importera baslinjeinställningarna.

Om du vill importera baslinjeinställningar från en lokalt lagrad XML-fil väljer du **Baslinjer med elektroniskt rapporteringsformat** och **Importera** och sedan **bläddra** för att välja XML-filen.

![Dialogrutan Importera baslinjeinställningar](media/GER-BaselineSample-ImportBaseline1.PNG "Skärmbild av dialogrutan Importera baslinjeinställningar")

Om du vill importera baslinjeinställningar från en XML-fil som är lagrad på Microsoft SharePoint-servern, baserat på de aktuella dokumenthanteringsinställningarna och den valda dokumenttypen väljer du sidan **Baslinjer med elektroniskt rapporteringsformat** och sedan **Importera från källa**. Välj sedan dokumenttyp och XML-fil. Den dokumenttyp som krävs för åtkomst SharePoint-mappen måste konfigureras i förväg.

![Dialogrutan Importera från källa](media/GER-BaselineSample-ImportBaseline2.PNG "Skärmbild av dialogrutan Importera från källa")

> [!NOTE]
> Du kan använda uppgiftsregistrering för att registrera stegen för att välja önskad dokumenttyp och filnamnet i dialogrutan **importera från källa**. På det här sättet kan du behålla de nödvändiga baslinjeinställningarna på SharePoint-servern och sedan automatiskt importera dem genom att spela upp en uppgiftsinspelning när du kör automatiserade tester med hjälp av Regression Suite Automation Tool.

## <a name="additional-resources"></a>Ytterligare resurser

- [Spåra genererade rapportresultat och jämför dem med baslinjevärden](er-trace-reports-compare-baseline.md)
- [Uppgiftsinspelarresurser](../user-interface/task-recorder.md)
