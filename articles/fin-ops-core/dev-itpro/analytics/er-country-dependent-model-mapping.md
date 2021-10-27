---
title: Konfigurera ER-modellmappningar som är beroende av landkontext
description: I det här avsnittet beskrivs hur du kan ställa in ER-modellmappningar så att de är beroende av land/region i den juridiska personen som styr deras användning.
author: NickSelin
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.2
ms.openlocfilehash: 5b26c605bd64b8d8e5a90f4389261e8e56825111
ms.sourcegitcommit: 25b3dd639e41d040c2714f56deadaa0906e4b493
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605381"
---
# <a name="configure-country-context-dependent-er-model-mappings"></a>Konfigurera ER-modellmappningar som är beroende av landkontext

[!include[banner](../includes/banner.md)]

Du kan konfigurera ER-modellmappningar (elektronisk rapportering) så att de implementerar en allmän ER-datamodell men är specifik för Dynamics 365 Finance. Det här avsnittet innehåller information om hur du utformar flera ER-modellmappningar för en ER-datamodell som kontrollerar hur de används i motsvarande ER-format som körs från företag med olika lands- eller regionskontexter.

## <a name="prerequisites"></a>Förutsättningar

För att slutföra exemplet i det här avsnittet måste du ha följande åtkomst:

- Gå till Finance för någon av följande roller:
    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

- Åtkomst till den instans av Regulatory Configuration Services (RCS) som har etablerats för samma innehavare som ekonomi för en av följande roller:
    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

Vissa steg i det här avsnittet kräver att du kör ett ER-format. I vissa fall påverkas körningen av ett ER-format av land- eller regionskontexten för det företag som du för närvarande är inloggad på. Du kan köra ett återställningsformat i den aktuella RCS-instansen om företaget som har den obligatoriska lands-/regionskontexten är tillgängligt i RCS. I annat fall måste du överföra en slutförd version av ER-modellmappningen och ER-format som använder ER-datamodellen till din ekonomiinstans och sedan köra ER-formatet i ekonomiinstansen. Mer information om hur du importerar konfigurationer som finns i RCS till en ekonomiinstans finns i [Importera konfigurationer från RCS](rcs-download-configurations.md).

## <a name="single-model-mapping-case"></a>Enstaka modellmappningsfall

Följ instruktionerna i [tillägg 1](#appendix1) i det här avsnittet för att designa de nödvändiga ER-komponenterna. Du har nu modellmappningskonfigurationen **Mappning (allmänt)** som innehåller modellmappningen för definitionen **startpunkt 1**.

![ER-konfigurationssida, Format för inlärning av mappningskonfiguration.](./media/RCS-Context-specific-mapping-Tree.PNG)

### <a name="run-the-configured-format"></a>Kör det konfigurerade formatet

1.  På sidan **konfigurationer** på snabbfliken **versioner**, välj **kör**.
2.  Välj **OK**.

Lägg märke till att webbläsaren kan hämta textfilen som genererades i ER-format. Eftersom det här formatet har konfigurerats för att använda definitionen **startpunkt 1** och endast en enda modellmappning är tillgänglig för den basmodell som innehåller en mappning för den här definitionen använde det körda ER-formatet modellmappningen **Mappning (allmänt)** för konfigurationen **Mappning (allmänt)** som en datakälla. Därför innehåller den hämtade filen texten **generisk funktion 1**.

## <a name="multiple-shared-model-mappings-case"></a>Flera delade modellmappningsfall

Följ instruktionerna i [tillägg 2](#appendix2) i det här avsnittet för att designa de nödvändiga ER-komponenterna. Du har nu modellmappningskonfigurationen **Mappning (allmänt)** och **Mappning (allmänt) anpassa** som var och en innehåller modellmappningen för definitionen **startpunkt 1**.

![ER-konfigurationssida, Mappa allmän anpassad konfiguration.](./media/RCS-Context-specific-mapping-TreeCustom.PNG)

### <a name="run-the-configured-format"></a>Kör det konfigurerade formatet

1.  På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Format för att lära mappningar**.
2.  Klicka på **Kör** på snabbfliken **Versioner**.
3.  Välj **OK**.

Observera att körningen av det valda återställningsformatet misslyckas. Ett felmeddelande informerar om att det finns fler än en modellmappning för modellen **modell för att lära sig mappning** och definitionen **startpunkt 1** i modellmappningskonfigurationerna **Mappning (allmänt)** och **Mappning (allmänt) anpassa**. Meddelandet rekommenderar också att du väljer en av dessa konfigurationer som standardkonfiguration.

![ER-konfigurationssida med felmeddelande.](./media/RCS-Context-specific-mapping-FormatRunCustomFailed.PNG)

### <a name="define-a-default-mapping-configuration"></a>Definiera en standardkonfiguration för mappningar

Följ dessa steg för att definiera konfiguration av modellmappning **Mappning (allmänt) - anpassa** som standardkonfiguration, så att dess mappningar kan användas som datakällor för ER-formatet **Format för att lära sig mappningar**.

1.  På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Mappning (allmänt) - anpassa**.
2.  Om det behövs väljer du **redigera** för att göra den aktuella sidan klar för redigering.
3.  Ange alternativet **standard för modellmappning** till **Ja**.
4.  Välj **Spara**.

![ER-konfigurationssida, Standard för modellmappningsskjutreglage inställt på Ja.](./media/RCS-Context-specific-mapping-MappingsCustomDefault.PNG)

### <a name="run-the-configured-format"></a>Kör det konfigurerade formatet

1.  På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Format för att lära mappningar**.
2.  Klicka på **Kör** på snabbfliken **Versioner**.
3.  Välj **OK**.

Observera att körningen av det valda återställningsformatet lyckas. Webbläsaren kan hämta textfilen som genererades i ER-format. Eftersom det här formatet har konfigurerats för att använda definitionen **startpunkt 1** och konfiguration av modellmappning **Mappning (allmänt) - anpassa** valdes som standardkonfiguration använde det körda ER-formatet modellmappningen **Mappning (allmänt) - anpassa** för konfigurationen **Mappning (allmänt) - anpassa** som en datakälla. Därför innehåller den hämtade filen texten **generisk funktion 1 - anpassa**.

> [!NOTE]
> Om du ändrar det företag som du för närvarande är inloggad på och kör detta ER-format igen får du samma innehåll i den genererade filen, eftersom standardkonfigurationen för ER-modellmappning inte innehåller några företagsspecifika begränsningar.

## <a name="multiple-mixed-model-mappings-case"></a>Flera blandade modellmappningsfall

Följ instruktionerna i [tillägg 3](#appendix3) i det här avsnittet för att designa de nödvändiga ER-komponenterna. Du har nu konfigurationen **Mappning (allmänt)**, **Mappning (allmänt) - anpassa** och **Mappning (FR) modellmappning** som innehåller modellmappningen för definitionen **startpunkt 1**.

Observera att version 1 av konfiguration av modellmappning **Mappning (FR)** är konfigurerad så att den bara gäller för ER-format för modellen **modell för att lära mappningar** som körs i ekonomiföretag med franskt land/region-sammanhang.

![ER-konfigurationssida, Modellmappningskonfiguration (FR).](./media/RCS-Context-specific-mapping-TreeFR.PNG)

### <a name="run-the-configured-format"></a>Kör det konfigurerade formatet

1.  Ändra företag till **FRSI**.
2.  På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Format för att lära mappningar**.
3.  Klicka på **Kör** på snabbfliken **Versioner**.
4.  Välj **OK**.

Observera att körningen av det valda återställningsformatet lyckas. Webbläsaren kan hämta textfilen som genererades i ER-format. Eftersom det här formatet har konfigurerats för att använda definitionen **startpunkt 1** och konfiguration av modellmappning **Mappning (allmänt) - anpassa** valdes som standardkonfiguration använde det körda ER-formatet modellmappningen **Mappning (allmänt) - anpassa** för konfigurationen **Mappning (allmänt) - anpassa** som en datakälla. Därför innehåller den hämtade filen texten **generisk funktion 1 - anpassa**.

### <a name="define-the-france-specific-mapping-configuration-as-the-default-configuration"></a>Definiera den Frankrike-specifika mappningskonfigurationen som standardkonfiguration

Följ dessa steg för att definiera den anpassade konfigurationen för modellmappning **Mappning (FR)** som standardkonfiguration. Observera att eftersom den här mappningen är specifik för Frankrike kommer den att betraktas som standardmappning mellan alla konfigurationer av modellmappning som har landskoden **FR** som anges i fältet **ISO-lands-/regionkoder**.

1.  På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Mappning (FR)**.
2.  Om det behövs väljer du **redigera** för att göra den aktuella sidan klar för redigering.
3.  Ange alternativet **standard för modellmappning** till **Ja**.
4.  Välj **Spara**.

![ER-konfigurationssida, Mappingskonfiguration (FR), Standard för modellmappningsskjutreglage inställt på Ja.](./media/RCS-Context-specific-mapping-TreeFRDefault.PNG)

### <a name="run-the-configured-format"></a>Kör det konfigurerade formatet

1.  På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Format för att lära mappningar**.
2.  Klicka på **Kör** på snabbfliken **Versioner**.
3.  Välj **OK**.

Observera att körningen av det valda återställningsformatet lyckas. Webbläsaren kan hämta textfilen som genererades i ER-format. Eftersom det här formatet har konfigurerats för att använda definitionen **startpunkt 1** och konfiguration av modellmappning **Mappning (FR)** valdes som standardkonfiguration använde det körda ER-formatet modellmappningen **Mappning (FR)** för konfigurationen **Mappning (FR)** som en datakälla. Därför innehåller den hämtade filen texten **FR funktion 1**.

> [!NOTE]
> Om du ändrar det företag som du för närvarande är inloggad på och kör ER-formatet igen, beror resultatet på land/region-kontexten för det valda företaget.

## <a name="other-model-mapping-cases"></a>Andra modellmappningsfall

Som du har sett fungerar valet av modellmappning för körningen av ett ER-format på följande sätt:

- Definitionen modellmappning som används för ett ER-format anges i (**startpunkt 1** i exemplen i det här avsnittet).
- Alla mappningskonfigurationer som innehåller en mappning som har den angivna definitionen, och som uppfyller eventuella kontextbegränsningar för land/region som har konfigurerats, kan användas för att köra ER-formatet **Mappning (allmänt)**, **Mappning (allmänt) - anpassa** och **Mappning (FR)** i exemplen i det här avsnittet.
- Alla standardmodellmappningar som har begränsningar för land/region har högst prioritet för markering (**Mappning (FR)** i exemplen i det här avsnittet).
- Alla standardmodellmappningar som inte har begränsningar för land/region har nästa högsta prioritet för markering (**Mappning (allmänt) - anpassa** i exemplen i det här avsnittet).
- Alla modellmappningar som har begränsningar i land/region har högre prioritet än en modellmappning som saknar sammanhangsbegränsningar för land/region.

Följande tabell ger information om resultatet av val av modellmappning i alla möjliga fall av inställningar av modellmappning:

- Kolumn 1 anger om den första modellmappningen som saknar sammanhangsbegränsningar för land/region (t.ex. den delade mappningen **Mappning (allmänt)**) visas och om alternativet **Standard för modellmappning** anges till **Ja** för den.
- Kolumn 2 anger om den andra modellmappningen som saknar sammanhangsbegränsningar för land/region (t.ex. den delade mappningen **Mappning (allmänt) - anpassa**) visas och om alternativet **Standard för modellmappning** anges till **Ja** för den.
- Kolumn 3 anger om den första modellmappningen som har sammanhangsbegränsningar för land/region A (t.ex. den Frankrike-specifika mappningen **Mappning (FR)**) visas och om alternativet **Standard för modellmappning** anges till **Ja** för den.
- Kolumn 4 anger om den andra modellmappningen som har sammanhangsbegränsningar för land/region A och om alternativet **Standard för modellmappning** anges till **Ja** för den.
- Kolumn 5 visar resultatet av ett val av modellmappning för körning av ett ER-format under kontrollen av ett företag som har ett sammanhang för land/region A.
- Kolumn 6 visar resultatet av ett val av modellmappning för körning av ett ER-format under kontrollen av ett företag som har ett sammanhang för land/region B.

I tabellen anger ett plus tecken (+) närvaron av en konfiguration av modellmappning i den aktuella instansen av Microsoft Azure-tjänsten som används för att köra ett ER-format (antingen Finance eller RCS).

| Ärende | Modellmappning 1 utan lands-/regionskontext (MM1) | Modellmappning 2 utan lands-/regionskontext (MM2) | Modellmappning 1 med lands-/region A-kontext (MM1A) | Modellmappning 2 med lands-/region A-kontext (MM2A) | Kör under kontroll av ett företag som har ett land/region A-kontext | Kör under kontroll av ett företag som har ett land/region B-kontext |
|---------|---------|---------|---------|---------|---------------------------|----------------------------|
|         |     1   |     2   |    3    |    4    |           5               |            6               |
|     1   |         |         |         |         | Fel (mappning saknas)   | Fel (mappning saknas)    |
|     2   |     +   |         |         |         | MM1                       | MM1                        |
|     3   |     +   |     +   |         |         | Fel (flera mappningar) | Fel (flera mappningar)  |
|     4   |     +   |         |    +    |         | MM1A                      | MM1                        |
|     5   |     +   |         |    +    |    +    | Fel (flera mappningar) | MM1                        |
|     6   |     +   | standardvärde |    +    |    +    | MM2                       | MM2                        |
|     7   |     +   |         | standardvärde |         | MM1A                      | MM1                        |
|     8   |     +   |         | standardvärde |    +    | MM1A                      | MM1                        |
|     9   |     +   |         | standardvärde | standardvärde | Fel (flera mappningar) | MM1                        |
|    10   | standardvärde |         |         |         | MM1                       | MM1                        |
|    11   | standardvärde |    +    |         |         | MM1                       | MM1                        |
|    12   | standardvärde |         |    +    |         | MM1                       | MM1                        |
|    13   | standardvärde | standardvärde |         |         | Fel (flera mappningar) | Fel (flera mappningar)  |
|    14   | standardvärde |         | standardvärde |         | MM1A                      | MM1                        |
|    15   | standardvärde |         | standardvärde | standardvärde | MM1A                      | MM2A                       |
|    16   |         |         |    +    |    +    | MM1A                      | MM2A                       |
|    17   |         |         | standardvärde | standardvärde | MM1A                      | MM2A                       |

## <a name="learn-what-mapping-was-used-in-the-execution-of-an-er-format"></a>Mer information om hur mappning användes vid körning av ett ER-format

### <a name="configure-er-user-parameters"></a>Konfigurera ER-användarparametrar

1.  På sidan **Konfigurationer** i åtgärdsfönstret, på fliken **KONFIGURATIONER** markerar du **Använd parametrar**.
2.  Ställ in alternativet **Kör i felsökningsläge** till **Ja**.
4.  Välj **OK**.

### <a name="run-the-configured-format"></a>Kör det konfigurerade formatet

1.  På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Format för att lära mappningar**.
2.  Klicka på **Kör** på snabbfliken **Versioner**.
3.  Välj **OK**.

### <a name="review-the-er-debug-log"></a>Läs i ER-felsökningsloggen

1.  I navigeringsfönstret, gå till **Moduler \> Organisationsadministration \> Elektronisk rapportering \> Konfiguration av felsökningslogg**.
2.  Klicka på knappen **Läs in den här sidan**.

![Sida för ER-körningsloggar.](./media/RCS-Context-specific-mapping-DebugLog.PNG)

Observera att en ny post har lagts till i ER-felsökningsloggen för det körda ER-formatet. Eftersom fältet **nivå** för den här posten är inställt på **info**, är posten information. Eftersom fältet Formatkomponent är inställt på **Mappningskonfiguration** informerar posten om en modellmappning som användes under körningen av ER-formatet **Format för att lära mappningar** (välja fältet **Konfigurationsnamn**). Innehållet av fältet **Innehållet text** informerar om att mappningskomponenten för mappningskonfigurationen **Mappning (FR)** som komponent som finns i **Mappning (FR)** som har använts för att köra denna rapport.

## <a name="appendix-1"></a><a name="appendix1"></a> Bilaga 1

### <a name="configure-a-sample-data-model"></a>Konfigurera en exempel datamodell

Logga in på RCS-instansen.

I det här exemplet skapar du en konfiguration för exempelföretaget, Litware, Inc. För att slutföra dessa steg måste du först slutföra stegen i RCS [Skapa en konfigurationsleverantör och markera den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md).

#### <a name="create-an-er-data-model-configuration"></a>Skapa en ER datamodellskonfiguration

1.  Välj **elektronisk rapportering** på standardinstrumentpanelen.
2.  Välj panelen **rapporteringskonfigurationer**.
3.  Välj **Designer** på sidan **Skapa konfiguration**.
4.  I listrutan i fältet **namn** anger du **modell för att lära dig mappningar**.
5.  Välj **Skapa konfiguration**.
6.  Klicka på snabbfliken **konfigurationskomponenter**.

Observera att utkastversion 1 av den här ER-konfigurationen är klar för redigering. Den här versionen innehåller datamodellkomponenten.

#### <a name="design-a-sample-data-model"></a>Designa en exempel datamodell

1.  Välj **Designer** på sidan **Konfigurationer**.
2.  Välj **Ny**.
3.  Ange **Startpunkt 1** i listrutan i fältet **namn**.
4.  Markera **Lägg till**.
5.  Välj **Ny**.
6.  I listrutan i fältet **namn** anger du **funktionsbeskrivning**.
7.  Markera **Lägg till**.
8.  Välj **Ny**.
9.  I listrutan i fältgruppen **Ny nod** anger du **Modellrot**.
10. I fältet **Namn** anger du **Startpunkt 2**.
11. Välj **startpunkt 2**.
12. Markera **Lägg till**.
13. Välj **Ny**.
14. I listrutan i fältet **namn** anger du **funktionsbeskrivning**.
15. Markera **Lägg till**.

    ![Sidan ER-datamodelldesigner.](./media/RCS-Context-specific-mapping-Model.PNG)

16. Välj **Spara**.
17. Stäng sidan.

#### <a name="complete-the-modified-version-of-the-model-configuration"></a>Slutför den ändrade versionen av ER-modellkonfiguration

1.  På sidan **konfigurationer** på snabbfliken **versioner**, välj **Ändra på status**.

    > Ändra statusen för designande modellkonfiguration från **utkast** till **slutförd**, så att den kan användas för att utforma de modellmappningar och format som krävs.

2.  Välj **Slutför**.
3.  Välj **OK**.

Observera att den skapade konfigurationen sparas som slutförd version 1.

### <a name="configure-a-sample-model-mapping"></a>Konfigurera en exempel modellmappning

#### <a name="create-an-er-model-mapping-configuration"></a>Skapa en konfiguration för ER-modellmappning

1.  Välj **Designer** på sidan **Skapa konfiguration**.
2.  I listrutan i fältgruppen **Ny**, väljer du alternativet **Modellmappning baserat på datamodell för att lära sig mappningar**.
3.  I fältet **Namn** anger du **Mappning (allmänt)**.
4.  I fältet **Definition av datamodell**, välj **Startpunkt 1**.
5.  Välj **Skapa konfiguration**.

Observera att utkastversion 1 av den här ER-konfigurationen är klar för redigering. Den här versionen innehåller modellmappningskomponenten.

#### <a name="design-a-sample-model-mapping"></a>Konfigurera en exempel modellmappning

1.  Välj **Designer** på sidan **Konfigurationer**.

    Observera att modellmappning för riktningstypen **För modell** riktningstyp har automatiskt lagts till denna komponent för definitionen **startpunkt 1**.
    
2.  Välj **designer** om du vill börja redigera den tillagda modellmappningen.
3.  I **Datamodell** välj **redigera**.
4.  I fältet **Recept** ange **"generiska funktionen 1"**.
5.  Välj **Spara**.
6.  Stäng sidan **Formeldesigner**.

    ![Designersida för ER-modellmappning, definition för ingångspunkt 1.](./media/RCS-Context-specific-mapping-Mapping1.PNG)

7.  Välj **Spara**.
8.  Stäng sidan **modellmappningsdesigner**.
9.  Välj **Ny**.
10. I fältet **Definition**, välj **Startpunkt 2**.
11. I fältet **Namn** anger du **Mappning (allmänt) 2**.
12. Välj **Designer**.
13. I **Datamodell** välj **redigera**.
14. I fältet **Recept** ange **"generiska funktionen 2"**.
15. Välj **Spara**.
16. Stäng sidan **Formeldesigner**.

    ![Designersida för ER-modellmappning, definition för ingångspunkt 2.](./media/RCS-Context-specific-mapping-Mapping2.PNG)

17. Välj **Spara**.
18. Stäng sidan **modellmappningsdesigner**.

    ![Designersida för ER-modellmappning med definitioner för ingångpunkt.](./media/RCS-Context-specific-mapping-Mappings.PNG)

19. Stäng sidan **modellmappningar**.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Slutför den ändrade versionen av konfiguration av modellmappning

1.  På sidan **konfigurationer** på snabbfliken **versioner**, välj **Ändra på status**.

    > Ändra statusen för designande konfigurationen mappningskonfiguration från **utkast** till **slutförd**, så att den kan användas av ER-format.

2.  Välj **Slutför**.
3.  Välj **OK**.

Observera att den skapade konfigurationen sparas som slutförd version 1.

### <a name="configure-a-sample-format"></a>Konfigurera ett exempelformat

#### <a name="create-an-er-format-configuration"></a>Skapa ett ER-formatkonfiguration

1.  På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Modell för att lära mappningar**.
2.  Välj **Skapa konfiguration**.
3.  I listrutan i fältgruppen **Ny**, väljer du alternativet **Format baserat på datamodell för att lära sig mappningar**.
4.  I fältet **namn** anger du **format för att lära dig mappningar**.
5.  I fältet **Definition av datamodell**, välj **Startpunkt 1**.
6.  Välj **Skapa konfiguration**.

Observera att utkastversion 1 av den här ER-konfigurationen är klar för redigering. Den här versionen innehåller formatkomponenten.

#### <a name="design-a-sample-format"></a>Designa ett exempelformat

1.  Välj **Designer** på sidan **Konfigurationer**.
2.  Välj **Lägg till rot**.
3.  I fältet grupper **Text**, välj objektet **Sträng**.
4.  Välj **OK**.

#### <a name="bind-format-elements-to-a-data-source"></a>Bindningsformatelement till datakällor

1.  På sidan **formatdesigner** på fliken **mappning** expanderar du modellens datakälla.
2.  Välj fältet **funktionsbeskrivning**.
3.  Välj **bind**.

    ![ER-formatdesignersida.](./media/RCS-Context-specific-mapping-Format.PNG)

4.  Välj **Spara**.
5.  Stäng sidan.

## <a name="appendix-2"></a><a name="appendix2"></a> Bilaga 2

### <a name="configure-a-sample-model-mapping-for-general-customization"></a>Konfigurera en exempel modellmappning för allmän anpassning

Det kan vara en bra idé att anpassa en modellmappning som en konfigurationsleverantör tillhandahåller och sedan använda den anpassade versionen som en datakälla för dina ER-format. I detta fall måste du skapa en anpassad konfiguration för ER-modellmappning för att kunna utföra de ändringar som krävs i befintliga modellmappningar. I procedurerna i det här tillägget **Mapping (General)** modellmappning som ett exempel.

#### <a name="create-an-er-model-mapping-configuration"></a>Skapa en konfiguration för ER-modellmappning

1.  På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Mappning (allmänt)**.
2.  Välj **Skapa konfiguration**.
3.  I rullgardinsmenyn i fältet **Nytt**, välj **Härled från namn: Mappning (allmän), Litware, Inc.**.
4.  I fältet **Namn** anger du **Mappning (allmänt) - anpassad**.
5.  Välj **Skapa konfiguration**.

Observera att utkastversion 1 av den här ER-konfigurationen är klar för redigering.

#### <a name="design-a-sample-model-mapping"></a>Konfigurera en exempel modellmappning

1.  Välj **Designer** på sidan **Konfigurationer**.

    > Observera att modellmappningarna för baskonfigurationen har kopierats automatiskt till den här konfigurationen.

2.  Välj mappning **mappning (allmän) - kopia**.
3.  Välj **Designer**.
4.  I **Datamodell** välj **redigera**.
5.  I fältet **Recept** ange **"generiska funktionen 1 - anpassa"**.
6.  Välj **Spara**.
7.  Stäng sidan.

    ![Designersida för ER-modellmappning, anpassad formel för Generisk funktion 1.](./media/RCS-Context-specific-mapping-Mapping1Custom.PNG)

8.  Välj **Spara**.
9.  Stäng sidan.
10. Välj mappning **mappning (allmän) 2 - kopia**.
11. Välj **Designer**.
12. I **Datamodell** välj **redigera**.
13. I fältet **Recept** ange **"generiska funktionen 2 - anpassa"**.
14. Välj **Spara**.
15. Stäng sidan.

    ![Designersida för ER-modellmappning, anpassad formel för Generisk funktion 2.](./media/RCS-Context-specific-mapping-Mapping2Custom.PNG)

16. Välj **Spara**.
17. Stäng sidan.

    ![Mappningssida för ER-modell till datakälla för Mappa (allmänt) kopieringsmappning.](./media/RCS-Context-specific-mapping-MappingsCustom.PNG)

18. Stäng sidan.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Slutför den ändrade versionen av konfiguration av modellmappning

1.  På sidan **konfigurationer** på snabbfliken **versioner**, välj **Ändra på status**.

    > Ändra statusen för designande konfigurationen mappningskonfiguration från **utkast** till **slutförd**, så att den kan användas av ER-format.

2.  Välj **Slutför**.
3.  Välj **OK**.

Observera att den skapade konfigurationen sparas som slutförd version 1.

## <a name="appendix-3"></a><a name="appendix3"></a> Bilaga 3

### <a name="configure-a-sample-model-mapping-for-countryregion-specific-customization"></a>Konfigurera en exempel modellmappning för lands-/regionspecifika anpassningar

För vissa ER-format kan lands-/regionspecifika krav för förberedelse av data. I det här fallet kan du hantera en separat konfiguration av ER-modellmappning och isolera tillämpningen av dessa lands-/regionspecifika krav från den allmänna implementationen. I procedurerna i den här bilagan används ER-formatet **format för att lära mappningar** och ER-format och Frankrike-specifika krav som exempel.

#### <a name="create-an-er-model-mapping-configuration"></a>Skapa en konfiguration för ER-modellmappning

Skapa först en ny konfiguration för ER-modellmappning för att implementera lands-/regionspecifika kraven. Använd din konfiguration för ER-modellmappning som bas.

1.  På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Mappning (allmänt) - anpassa**.
2.  Välj **Skapa konfiguration**.
3.  I rullgardinsmenyn i fältet **Nytt**, välj **Härled från namn: Mappning (allmän) - anpassa, Litware, Inc.**.
4.  I fältet **Namn** anger du **Mappning (FR)**.
5.  Välj **Skapa konfiguration**.

Observera att utkastversion 1 av den här ER-konfigurationen är klar för redigering.

#### <a name="design-a-sample-model-mapping"></a>Konfigurera en exempel modellmappning

1.  Välj **Designer** på sidan **Konfigurationer**.

    > Observera att modellmappningarna för baskonfigurationen har kopierats automatiskt till den här konfigurationen.

2.  Välj mappning **mappning (allmän) - kopia**.
3.  Byt namn till **Mappning (FR)**.
4.  Välj **Designer**.
5.  I **Datamodell** välj **redigera**.
6.  I fältet **Recept** ange **"FR funktionen 1"**.
7.  Välj **Spara**.
8.  Stäng sidan.

    ![Designersida för ER-modellmappninge, formel för FR-funktion 1.](./media/RCS-Context-specific-mapping-Mapping1FR.PNG)

9.  Välj **Spara**.
10. Stäng sidan.
11. Välj mappning **mappning (allmän) 2 - kopia**.
12. Byt namn till **Mappning (FR) 2**.
13. Välj **Designer**.
14. I **Datamodell** välj **redigera**.
15. I fältet **Recept** ange **"FR funktionen 2"**.
16. Välj **Spara**.
17. Stäng sidan.

    ![Designersida för ER-modellmappninge, formel för FR-funktion 2.](./media/RCS-Context-specific-mapping-Mapping2FR.PNG)

18. Välj **Spara**.
19. Stäng sidan.

    ![Mappningssida för ER-modell till datakälla.](./media/RCS-Context-specific-mapping-MappingsFR.PNG)

20. Stäng sidan.

#### <a name="specify-countryregion-context-restrictions-for-use"></a>Ange kontextbegränsningar för land/region för användning

1.  På sidan **konfigurationer** på snabbfliken **ISO-koder för land/region**, välj **Ny**.
2.  I fältet **ISO** välj **FR**.
3.  Välj **Spara**.

Observera att du måste logga in på ett visst företag i företaget för att kunna köra ett ER-format. Detta företag kan därför betraktas som en part som kontrollerar både ER-och utkörningen av den korrekta ER-modellmappningen av ER-basdatamodellen. Genom att lägga **FR** landskoden anger du att den här modellmappningen bara kan väljas av ET-format för basdatamodellen när formatet körs under kontroll över ett företag som har franskt land/region-sammanhang.

Du kan lägga till flera lands-/regionkoder för en enskild version av en konfiguration för ER-modellmappning. På det här sättet kan modellmappningar som finns i konfigurationen modellmappningar användas för ett ER-format som körs under kontroll av företag som har en annan lands-/regionskontext.

Observera att listan med lands-/regionskoder anges för varje version av en konfiguration för ER-modellmappning och kan variera från version till version.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Slutför den ändrade versionen av konfiguration av modellmappning

1.  På sidan **konfigurationer** på snabbfliken **versioner**, välj **Ändra på status**.

    > Ändra statusen för designande konfigurationen mappningskonfiguration från **utkast** till **slutförd**, så att den kan användas av ER-format.

2.  Välj **Slutför**.
3.  Välj **OK**.

Observera att den skapade konfigurationen sparas som slutförd version 1.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)

[Hantera ER-modellmappning i separata ER-konfigurationer](./tasks/er-manage-model-mapping-configurations-july-2017.md)

[Använd sammanhang för land/region](../lcs-solutions/apply-country-context.md)

## <a name="frequently-asked-questions"></a>Vanliga frågor

#### <a name="i-configured-two-shared-er-model-mapping-configurations-in-rcs-and-marked-one-of-them-as-the-default-model-mapping-configuration-i-successfully-ran-an-er-format-that-was-created-for-the-same-base-er-data-model-configuration-to-test-model-mappings-i-then-imported-the-whole-er-solution-er-data-model-two-er-model-mapping-configurations-and-er-format-configuration-into-finance-why-do-i-receive-an-error-message-when-i-try-to-run-the-same-er-format-in-finance"></a>Jag har konfigurerat två delade konfigurations ER-modellmappningar för i RCS och markerat en av dem som standardkonfiguration för modellmappning. Jag har kört ett ER-format som skapades för samma ER-basdatamodellen för att testa modellmappningar. Jag importerar sedan hela ER-lösningen (ER-datamodellen, två ER-mappnings- och ER-formatkonfiguration) till Finance. Varför får jag ett felmeddelande när jag försöker att köra samma ER-format i Finance?
Standardinställningen för modellmappning är miljöspecifik. Den är konfigurerad i RCS men exporteras inte till Finance. För att kunna köra det här ER-formatet måste du markera en av konfigurationen för ER-modellmappning som standardkonfiguration för modellmappning i Finance.

#### <a name="i-configured-one-model-mapping-as-a-shared-model-mapping-and-completed-the-draft-version-of-it-i-then-added-a-new-model-mapping-configuration-for-same-data-model-and-configured-it-as-french-specific-why-is-the-shared-model-mapping-selected-when-i-run-an-er-format-even-though-this-er-format-uses-the-correct-root-definition-and-execution-is-done-under-the-control-of-the-company-that-has-french-countryregion-context"></a>Jag konfigurerade en modellmappning som en delad modellmappning och slutför utkastet till en version av den. Jag har sedan lagt till en ny konfiguration för modellmappning för samma datamodell och konfigurerade den som Frankrike-specifika. Varför väljs den delade modellmappningen när jag kör ett ER-format, även om detta ER-format använder rätt rotdefinition och exekvering görs under kontroll av företaget som har franska land/region-sammanhang?
Kontrollera att konfigurationen för mappning av delade modeller inte har markerats som standardkonfiguration för modellmappning. I annat fall får den högre prioritet vid val av mappning. Kontrollera också att den Frankrike-specifika konfigurationen för modellmappning när en mappning väljs under körningen av ER-format. En konfiguration för ER-modellmappning kan bara väljas om minst ett av följande villkor är uppfyllt:
- Minst en version av konfigurationen för ER-modellmappning har antingen **slutfört** eller **delad** status. I det här fallet används versionen med det högsta versions numret för ER-formatkörning.
- Alternativet **kör utkast** för konfigurationen för ER-modellmappning är aktiverat. I det här fallet används versionen **utkast** används ER-formatkörning.
> Alternativet **kör utkast** blir tillgängligt på **sidan konfigurationer** för varje konfiguration för ER-modellmappning när ER-användarparametern **Kör inställning** är aktiverad.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
