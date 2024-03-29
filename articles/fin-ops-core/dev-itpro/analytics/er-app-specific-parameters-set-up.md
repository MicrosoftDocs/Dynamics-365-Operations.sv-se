---
title: Ställa in parametrarna för ett ER-format per juridisk person
description: I den här artikeln beskrivs hur du kan konfigurera parametrar för ett format för elektroniska rapporter (ER) per juridisk person.
author: kfend
ms.date: 03/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.custom: ''
ms.assetid: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
ms.openlocfilehash: 4b2e91e43938b71b78a4b7bc57b5b16ca174b1b7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291405"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a>Ställ in parametrarna för ett ER-format per juridisk person

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a>Förutsättningar

För att kunna utföra de här stegen måste du först slutföra stegen i [konfigurera ER-format för att använda parametrar som anges per juridisk person](er-app-specific-parameters-configure-format.md).

Om du vill slutföra exemplen i den här artikeln måste du ha tillgång till Microsoft Microsoft Dynamics 365 Finance för en av följande roller:

- Utvecklare för elektronisk rapportering
- Konsult för funktionen för elektronisk rapportering
- Systemadministratör

## <a name="import-er-configurations"></a>Importera ER-konfigurationer
För att importera ER-konfigurationer, följ dessa steg: 

1. Logga in på miljön.
2. Välj **elektronisk rapportering** på standardinstrumentpanelen.
3. Välj **rapporteringskonfigurationer**.
4. I den aktuella instansen av Finance, importera de konfigurationer du har exporterat från Regulatory Configuration Services (RCS) medan du slutförde stegen i avsnittet [konfigurera ER-format för användning av parametrar som anges per juridisk person](er-app-specific-parameters-configure-format.md). Följ de här stegen för varje konfiguration [elektronisk rapportering (ER)](general-electronic-reporting.md) i följande ordning: datamodell, modellmappning och format.

    1. Välj **Kurs \> Läs in från XML-fil**.
    2. Välj **bläddra** om du vill välja en fil för den nödvändiga ER-konfigurationen i XML-format.
    3. Välj **OK**.

    Följande illustration visar vilka konfigurationer du måste ha när du är klar.

    ![Sidan ER-konfigurationer.](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a>Ställa in parametrar för DEMF-företaget

Du kan använda ER-ramverket för att ställa in programspecifika parametrar för ett ER-format.

1. Välj den juridiska personen **DEMF**.
2. I konfigurationsträdet väljer du formatet **format för att lära dig hur du letar upp LE-data**.
3. I Åtgärdsfönstret, på fliken **Konfigurationer**, i gruppen **Appspecifika parametrar**, markerar du **Konfigurera**.

    ![ER-appspecifika parametersida för att ställa in parametrar.](./media/GER-AppSpecParms-LookupForm.PNG)

    På sidan **Programspecifika parametrar** kan du konfigurera reglerna för datakällan **väljare** för formatet **format för att lära dig hur du söker efter LE-data**.

    Om bas ER-basformatet kommer att innehålla flera datakällor av typen **Slå upp** måste du välja önskad datakälla på snabbfliken **sökningar** innan du kan börja konfigurera uppsättningen regler för datakällan.

    För varje datakälla kan du konfigurera separata regler för varje version av det valda ER-formatet.

    Hela uppsättningen regler för alla datakällor för sökning som är tillgängliga i den valda versionen av ER-basformatet utgör de programspecifika parametrarna för ER-format.

4. Välj version **1.1.1** av ER-formatet.
5. På snabbfliken **Villkor** väljer du **Lägg till**.
6. I fältet **Kod** för den nya posten väljer du nedrullningsbara pilen för att öppna uppslaget.

    Sökningen visar en lista över momskoder för urvalet. Den här listan returneras av datakällan **Model.Data.Tax** som har konfigurerats i ER-basformat. Eftersom datakällan innehåller fältet **namn** visas namnet på varje skattekod i sökningen.

    ![Sidan Importera ER-programspecifika parametrar, kodfältsökning.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)

7. Välj momskoden **VAT19**.
8. I fältet **Sökningsresultat** för den nya posten väljer du nedrullningsbara pilen för att öppna uppslaget. Sökningen visar en lista med värden för TaxationLevel formatuppräkning för urval.

    Observera att om tyska har valts som det prioriterade språket för den användare som du är inloggad på som, kommer etiketterna för värdena i sökningen att vara på tyska, förutsatt att de har översatts i ER-basformatet. Dessutom, om etiketten för en datakälla för sökning har översatts, kommer den etiketten att visas på användarens önskade språk på fliken **sökningar**.

    ![Uppslagsfältet som översätts till tyska på ER-programspecifika parametersidan.](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9. Välj värdet **vanlig beskattning**.

    Genom att lägga till den här posten definierar du följande regel: När datakällan för sökning **Väljare** begärs och momskoden **VAT19** skickas som ett argument, **vanlig beskattning** returneras som den begärda momsnivån.

10. Välj **Lägg till** och gör sedan följande:

    1. I fältet **Kod**, välj momskod **InVAT19**.
    2. I fältet **Sökningsresultat** välj värdet **vanlig beskattning**.

11. Välj **Lägg till** och gör sedan följande:

    1. I fältet **Kod**, välj momskod **VAT7**.
    2. I fältet **Sökningsresultat** välj värdet **Reducerad beskattning**.

12. Välj **Lägg till** och gör sedan följande:

    1. I fältet **Kod**, välj momskod **InVAT7**.
    2. I fältet **Sökningsresultat** välj värdet **Reducerad beskattning**.

13. Välj **Lägg till** och gör sedan följande:

    1. I fältet **Kod**, välj momskod **THIRD**.
    2. I fältet **Sökningsresultat** välj värdet **Ingen beskattning**.

14. Välj **Lägg till** och gör sedan följande:

    1. I fältet **Kod**, välj momskod **InVAT0**.
    2. I fältet **Sökningsresultat** välj värdet **Ingen beskattning**.

15. Välj **Lägg till** och gör sedan följande:

    1. Välj alternativet **Kod** välj alternativet **\*Ej tomt\***.
    2. I fältet **Sökningsresultat** välj värdet **Övrig**.

    Genom att lägga till den här posten definierar du följande regel: När datakällan för sökning skicka eftersom ett argument inte uppfyller någon av de tidigare reglerna, kommer uppslagning datakällan tillbaka **Övrig** som den begärda momsnivån.

    ![Senaste rekordet tillagt ER-programspecifika parametrar, kodfältsökning.](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)

16. I fältet **Stat**, välj **Slutförd**.

    När du kör en ER-formatversion som har statusen antingen **slutförd** eller **delad**, måste denna uppsättning regler vara **slutförd**. I annat fall avbryts körningen av ER-basformatet när formatet försöker läsa in data från den här uppsättningen regler medan datakälla för sökning **väljare** körs.

    När du kör en ER-formatversion som har statusen **utkast** kan ER-basformatet komma åt denna uppsättning regler, oavsett status.

17. Välj **Spara**.
18. Stäng sidan **Appspecifika parametrar**.

## <a name="run-the-er-format-in-the-demf-company"></a>Kör ER-formatet i DEMF-företaget
Följ dessa steg för att köra ER-formatet i DEMF-företaget: 

1. I konfigurationsträdet väljer du formatet **format för att lära dig hur du letar upp LE-data**.
2. Klicka på **Kör** i åtgärdsfönstret.
3. I dialogrutan som visas väljer du **OK**.
4. Hämta det utdrag som genereras och spara det lokalt.

    Observera i det genererade utdraget att sammanfattningen av momskoden **InVAT7** har placerats på nivån **reducerad** och sammanfattningar av **VAT19** och **InVA19** momskoder har placerats på nivån **normal**. Det här beteendet bestäms av konfigurationen i de regler som är beroende av den juridiska personen.

5. Gå till **Moms \> Indirekt moms \> Moms \> Momskoder**.
6. Välj momskoden **InVAT7**.
7. I åtgärdsfönstret på fliken **Momskod** i gruppen **Förfrågningar** välj **Bokförd moms** om du vill visa information om momsvärde och tillämpad momssats per momskod.

    ![Sidan Bokförd moms.](./media/GER-AppSpecParms-Statement.PNG)

8. Stäng sidan **Bokförd moms**.

## <a name="set-up-parameters-for-the-usmf-company"></a>Ställa in parametrar för USMF-företaget
Ställ in parametrar för USMF-företaget genom att utföra följande steg: 

1. Välj den juridiska personen **USMF**.
2. Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
3. I konfigurationsträdet expanderar du objektet **Modell för att lära dig parameteranrop** expanderar du objektet **Format för att lära dig parameteranrop** och välj formatet **format för att lära dig hur du slår upp LE-data**.
4. I Åtgärdsfönstret, på fliken **Konfigurationer**, i gruppen **Appspecifika parametrar**, markerar du **Konfigurera**.
5. Välj version **1.1.1** av det valda ER-formatet.
6. På snabbfliken **Villkor** väljer du **Lägg till**.
7. I fältet **Kod** för den nya posten väljer du nedrullningsbara pilen för att öppna uppslaget.

    Sökningen visar nu en lista över momskoder för **USMF** företagsmoms för urvalet.

    ![Momskoder för USMF-företagsskatten.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)

8. Välj momskoden **EXEMPT**.
9. I fältet **Sökningsresultat** för den nya posten, välj värdet **Ingen beskattning**.
10. Markera **Lägg till**.
11. I fältet **Kod** för den nya posten, välj alternativet **\*Ej tomt\***.
12. I fältet **Sökningsresultat** för den nya posten, välj värdet **Vanlig beskattning**.
13. I fältet **Stat**, välj **Slutförd**.
14. Välj **Spara**.

    ![Sidan Importera ER-programspecifika parametrar.](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)

15. Stäng sidan **Appspecifika parametrar**.

## <a name="run-the-er-format-in-the-usmf-company"></a>Kör ER-formatet i USMF-företaget
Följ dessa steg för att köra ER-formatet i USMF-företaget:

1. I konfigurationsträdet väljer du formatet **format för att lära dig hur du letar upp LE-data**.
2. Klicka på **Kör** i åtgärdsfönstret.
3. I dialogrutan som visas väljer du **OK**.
4. Hämta det utdrag som genereras och spara det lokalt.

    Observera i det genererade uttrycket att du nu har återanvänt ER-formatet för en annan juridisk person utan att göra några justeringar av ER-format.

## <a name="reuse-legal-entitydependent-parameters"></a>Återanvänd parametrar som är beroende av den juridiska personen.

### <a name="duplicate-existing-parameters"></a>Duplicera befintliga parametrar

#### <a name="export-parameters"></a>Exportera parametrar
Utför följande steg för att exportera parametrar:

1. Gå till **Organisationsadministration \> Arbetsytor \> Elektronisk rapportering**.
2. Välj **rapporteringskonfigurationer**.
3. I konfigurationsträdet väljer du formatet **format för att lära dig hur du letar upp LE-data**.
4. I Åtgärdsfönstret, på fliken **Konfigurationer**, i gruppen **Appspecifika parametrar**, markerar du **Konfigurera**.
5. Välj version **1.1.1** av ER-formatet.
6. Välj **Export** i åtgärdsfönstret.
7. Hämta den fil som genereras och spara det lokalt.

    Den konfigurerade uppsättningen programspecifika parametrar har nu exporterats som en XML-fil.

#### <a name="import-parameters"></a>Importera parametrar
Utför följande steg för att importera parametrar:

1. Välj version **1.1.2** av ER-formatet.
2. Välj **Import** i åtgärdsfönstret.
3. Välj **ja** för att bekräfta att du vill åsidosätta de befintliga programspecifika parametrarna för den här formatversionen.
4. Välj **bläddra** om du vill söka efter filen som innehåller de exporterade programspecifika parametrarna för version **1.1.1**.
5. Välj **OK**.

    Version **1.1.2** av ER-formatet har nu samma programspecifika parametrar som du ursprungligen konfigurerade för version **1.1.1**.

##### <a name="applicability-considerations"></a>Tillämplighet, beaktande

De programspecifika parametrarna för ett ER-format som är beroende av den juridiska personen. Om du vill återanvända de programspecifika parametrarna som konfigurerats för en juridisk person i en annan juridisk person, måste du exportera dem när du är inloggad på den första juridiska personen. Importera dem sedan när du har loggat in till den andra juridiska personen.

Du kan också använda den här export-import-metoden om du vill överföra ER-formatrelaterade programspecifika parametrar som ursprungligen konfigurerades i en Finance-instans till en annan Finance-instans.

Om du konfigurerar programspecifika parametrar för en version av ett ER-format och sedan importerar en senare version av samma format till den aktuella ekonomiinstansen, tillämpas inte de befintliga programspecifika parametrarna på den importerade versionen såvida du inte använder den använd programspecifika parametrarna från tidigare versioner av funktionen **ER-format**. Mer information finns i avsnittet [Återanvänd befintliga parametrar](#reuse-existing-parameters) senare i den här artikeln.

När du väljer en fil för import, jämförs även programspecifika parametrar i den filen med strukturen för motsvarande datakälla av typen **uppslag** för det återställningsformat som valts för import. Som standard är importen är slutförd endast om strukturen för varje programspecifik parameter matchar strukturen för motsvarande datakälla i det återställningsformat som har valts för import. Om strukturlistorna inte matchar får du ett varningsmeddelande om att importen inte kan slutföras. Om du tvingar importen rensas de befintliga programspecifika parametrarna för det valda återställningsformatet och du måste ställa in dem från början.


Från och med Finance version 10.0.24, du kan ändra standardbeteendet och undvika att få ett varningsmeddelande genom att aktivera funktionen **Justera ER-appspecifika parametrar under import** i arbetsytan **Funktionshantering**. När den här funktionen är aktiverad, om strukturen för programspecifika parametrar som du importerar skiljer sig från strukturen för motsvarande datakällor i mål-ER-formatet som har valts för import, kommer importen att lyckas i följande fall:

- Strukturen för mål-ER-formatet har ändrats genom att nya villkorskolumner läggs till i alla befintliga datakällor för **söktypen**. När importen är klar uppdateras de programspecifika parametrarna. I alla importerade poster med applikationsspecifika parametrar initieras värdena i varje tillagd villkorskolumn med standardvärdet för [datatyp](er-formula-supported-data-types-primitive.md) i den kolumnen.
- Strukturen för mål-ER-formatet har ändrats genom att ta bort vissa villkorskolumner från alla befintliga datakällor för **söktypen**. När importen är klar uppdateras de programspecifika parametrarna. I alla importerade poster för programspecifika parametrar raderas värdena i alla borttagna villkorskolumner.
- Strukturen för mål-ER-formatet har ändrats genom att lägga till nya datakällor för **söktypen**. När importen är klar läggs de tillagda uppslagningarna till de programspecifika parametrarna.
- Strukturen för mål-ER-formatet har ändrats genom att ta bort vissa av befintliga datakällor för **söktypen**. När importen är klar tas alla artefakter som är relaterade till datakällorna för **söktypen** som tagits bort från mål-ER-formatet från de importerade programspecifika parametrarna.

När importen är klar, utöver de ändringar som just beskrevs, ändras tillståndet för de importerade programspecifika parametrarna till **Pågår**. Ett varningsmeddelande informerar om att de automatiskt justerade programspecifika parametrarna måste redigeras manuellt.

#### <a name="replicate-parameters"></a>Replikera parametrar

Från och med Finance version 10.0.27 kan du kopiera de parametrar som du konfigurerat i ett företag till andra företag samtidigt.

Utför följande steg för att kopiera parametrar.

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. Välj **rapporteringskonfigurationer**.
3. I konfigurationsträdet väljer du formatet **format för att lära dig hur du letar upp LE-data**.
4. I Åtgärdsfönstret, på fliken **Konfigurationer**, i gruppen **Appspecifika parametrar**, markerar du **Konfigurera**.
5. Välj version **1.1.1** av ER-formatet.
6. I åtgärdsfönstret, välj **Replikera**.
7. I dialogrutan **Replikera** på fliken **Företag**, välj de företag som du vill kopiera parametrar till.

    > [!NOTE]
    > Välj de företag som du vill kopiera parametrar till [roll](../sysadmin/role-based-security.md#security-roles) som är konfigurerad för att ge åtkomst till alla organisationer.

8. Välj **OK**.

    > [!NOTE]
    > Bekräftelsedialogrutan informerar dig om vissa målföretag innehåller tidigare konfigurerade parametrar för den valda versionen av ett ER-format. Välj **Ja** om du vill åsidosätta parametrarna genom att kopiera dem från det aktuella företaget.

    Den konfigurerade uppsättningen med programspecifika parametrar kopieras nu till de valda företagen.

### <a name="reuse-existing-parameters"></a>Använd befintliga parametrar igen

Från och med Finance version 10.0.23, du kan återanvända programspecifika parametrar som har konfigurerats för en version av ett ER-format när du kör en högre version av samma format. För att återanvända befintliga parametrar aktivera du funktionen genom att **Använd appspecifika parametrar från tidigare versioner av ER-format** i arbetsytan **Funktionshantering**. När den här funktionen är aktiverad och du kör en version av ett ER-format som försöker läsa programspecifika parametrar försöker ER att hitta programspecifika parametrar som har konfigurerats för den körande versionen av det här formatet. Om de inte är tillgängliga kommer ER att försöka hitta dem för närmaste lägre version av formatet.

> [!NOTE]
> Du kan bara återanvända programspecifika parametrar i den aktuella juridiska personens område.
>
> Ett fel visas vid körning när du kör en högre version av ett ER-format som försöker återanvända programspecifika parametrar som har konfigurerats för en lägre version av samma format och strukturen för minst en datakälla av typen **Sökning** i det högre formatet har versionen ändrats.

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a>Relation mellan programspecifika parametrar och ett ER-format

Relationen mellan ett ER-format och dess programspecifika parametrar upprättas genom ER-formatets instansoberoende identifieringskod. När du tar bort ett ER-format från Finance behålls därför de programspecifika parametrar som har konfigurerats för ER-format i den aktuella instansen Finance. De kan nås varje gång som ER-basformatet återimporteras till den här instansen av Finance.

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a>Få åtkomst till programspecifika parametrar med hjälp av ER-ramverket

I föregående exempel har du tillgång till programspecifika parametrar för ett ER-format med hjälp av ER-ramverket. Med den här metoden kan du inte begränsa åtkomsten till de programspecifika parametrarna för ett visst ER-format. Gör så här om du måste tillämpa dessa begränsningar. 

1. Återanvänd antingen ett befintligt menyalternativ **ERSolutionAppSpecificParametersDesigner** eller implementera dina egna **ERSolutionAppSpecificParametersDesigner** menyalternativ.

    ![Menyobjektvisning av ERSolutionAppSpecificParametersDesigner.](./media/GER-AppSpecParms-LookupForm-Access1.PNG)

2. Gör något av följande:

    1. Skapa en ny knapp för meny objekt och länka den till motsvarande post från tabellen **ERSolutionTable** genom att ange egenskapen **Datakälla** till **ERSolutionTable**.

        ![Visning av nya inställningar för menyalternativ.](./media/GER-AppSpecParms-LookupForm-Access2.PNG)

    2. Skapa en enkel knapp och åsidosätt den **klickade** metoden som den visas i följande exempel.

        Genom att använda den här metoden kan du ange ett unikt lösnings-ID (definierat via värdet **GUID**) som tillåter åtkomst till programspecifika parametrar för endast ett visst ER-format och underordnade kopior som har härletts från den.
        
        ```xpp
        public void clicked()
            {
                super();

                ERSolutionTable solutionTableRecord = ERSolutionTable::findByGUID(str2Guid('ADACCB2F-EFD1-4C90-877D-7E1E5D1AEE92'));

                Args args = new Args();
                args.record(solutionTableRecord);
                args.caller(this);

                new MenuFunction(menuItemDisplayStr(ERSolutionAppSpecificParametersDesigner), MenuItemType::Display)
                    .run(args);
            }
        ```

## <a name="additional-resources"></a>Ytterligare resurser

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Konfigurera ER-format för användning av parametrar som anges per juridisk person](er-app-specific-parameters-configure-format.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
