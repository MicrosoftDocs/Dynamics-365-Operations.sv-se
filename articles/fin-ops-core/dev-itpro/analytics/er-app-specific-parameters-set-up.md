---
title: Ställ in parametrarna för ett ER-format per juridisk person
description: I det här avsnittet beskrivs hur du kan konfigurera parametrar för ett format för elektroniska rapporter (ER) per juridisk person.
author: NickSelin
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 4003208a1f02db134bbec1ecf90c1cdd2973e67f
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751164"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a>Ställ in parametrarna för ett ER-format per juridisk person

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a>Förutsättningar

För att kunna utföra de här stegen måste du först slutföra stegen i [konfigurera ER-format för att använda parametrar som anges per juridisk person](er-app-specific-parameters-configure-format.md).

Om du vill slutföra exemplen i det här avsnittet måste du ha tillgång till Microsoft Dynamics 365 Finance (Finance) för en av följande roller:

- Utvecklare för elektronisk rapportering
- Konsult för funktionen för elektronisk rapportering
- Systemadministratör

## <a name="import-er-configurations"></a>Importera ER-konfigurationer

1.  Logga in på miljön.
2.  Välj **elektronisk rapportering** på standardinstrumentpanelen.
3.  Välj **rapporteringskonfigurationer**.
4.  Importera i den aktuella instansen av Finance de konfigurationer som du har exporterat från Regulatory Configuration Services (RCS) medan du slutförde stegen i avsnittet [konfigurera ER-format för användning av parametrar som anges per juridisk person](er-app-specific-parameters-configure-format.md). Följ de här stegen för varje konfiguration i elektronisk rapportering (ER) i följande ordning: datamodell, modellmappning och format.

    1. Välj **Kurs \> Läs in från XML-fil**.
    2. Välj **bläddra** om du vill välja en fil för den nödvändiga ER-konfigurationen i XML-format.
    3. Välj **OK**.
    
    Följande illustration visar vilka konfigurationer du måste ha när du är klar.

    ![Sidan ER-konfigurationer](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a>Ställa in parametrar för DEMF-företaget

Du kan använda ER-ramverket för att ställa in programspecifika parametrar för ett ER-format.

1.  Välj den juridiska personen **DEMF**.
2.  I konfigurationsträdet väljer du formatet **format för att lära dig hur du letar upp LE-data**.
3.  I Åtgärdsfönstret, på fliken **Konfigurationer**, i gruppen **Appspecifika parametrar**, markerar du **Konfigurera**.

    ![Sidan Importera ER-programspecifika parametrar](./media/GER-AppSpecParms-LookupForm.PNG)
    
    På sidan **Programspecifika parametrar** kan du konfigurera reglerna för datakällan **väljare** för formatet **format för att lära dig hur du söker efter LE-data**.
    
    Om bas ER-basformatet kommer att innehålla flera datakällor av typen **Slå upp** måste du välja önskad datakälla på snabbfliken **sökningar** innan du kan börja konfigurera uppsättningen regler för datakällan.
    
    För varje datakälla kan du konfigurera separata regler för varje version av det valda ER-formatet.
    
    Hela uppsättningen regler för alla datakällor för sökning som är tillgängliga i den valda versionen av ER-basformatet utgör de programspecifika parametrarna för ER-format.

4.  Välj version **1.1.1** av ER-formatet.
5.  På snabbfliken **Villkor** väljer du **Lägg till**.
6.  I fältet **Kod** för den nya posten väljer du nedrullningsbara pilen för att öppna uppslaget.

    Sökningen visar en lista över momskoder för urvalet. Den här listan returneras av datakällan **Model.Data.Tax** som har konfigurerats i ER-basformat. Eftersom datakällan innehåller fältet **namn** visas namnet på varje skattekod i sökningen.

    ![Sidan Importera ER-programspecifika parametrar](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)
    
7.  Välj momskoden **VAT19**.
8.  I fältet **Sökningsresultat** för den nya posten väljer du nedrullningsbara pilen för att öppna uppslaget. Sökningen visar en lista med värden för TaxationLevel formatuppräkning för urval.

    Observera att om tyska har valts som det prioriterade språket för den användare som du är inloggad på som, kommer etiketterna för värdena i sökningen att vara på tyska, förutsatt att de har översatts i ER-basformatet. Dessutom, om etiketten för en datakälla för sökning har översatts, kommer den etiketten att visas på användarens önskade språk på fliken **sökningar**.

    ![Sidan Importera ER-programspecifika parametrar](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9.  Välj värdet **vanlig beskattning**.

    Genom att lägga till den här posten definierar du följande regel: När datakällan för sökning **Väljare** begärs och momskoden **VAT19** skickas som ett argument, **vanlig beskattning** returneras som den begärda momsnivån.

10. Välj **Lägg till** och gör sedan följande:

    1. I fältet **Kod**, välj momskod **InVAT19**.
    2. I fältet **Sökningsresultat** välj värdet **vanlig beskattning**.
    
11. Välj **Lägg till** igen och gör sedan följande:

    1. I fältet **Kod**, välj momskod **VAT7**.
    2. I fältet **Sökningsresultat** välj värdet **Reducerad beskattning**.
    
12. Välj **Lägg till** igen och gör sedan följande:

    1. I fältet **Kod**, välj momskod **InVAT7**.
    2. I fältet **Sökningsresultat** välj värdet **Reducerad beskattning**.
    
13. Välj **Lägg till** igen och gör sedan följande:

    1. I fältet **Kod**, välj momskod **THIRD**.
    2. I fältet **Sökningsresultat** välj värdet **Ingen beskattning**.
    
14. Välj **Lägg till** igen och gör sedan följande:

    1. I fältet **Kod**, välj momskod **InVAT0**.
    2. I fältet **Sökningsresultat** välj värdet **Ingen beskattning**.
    
15. Välj **Lägg till** igen och gör sedan följande:

    1. Välj alternativet **Kod** välj alternativet **\*Ej tomt\***.
    2. I fältet **Sökningsresultat** välj värdet **Övrig**.
    
    Genom att lägga till den här posten definierar du följande regel: När datakällan för sökning skicka eftersom ett argument inte uppfyller någon av de tidigare reglerna, kommer uppslagning datakällan tillbaka **Övrig** som den begärda momsnivån.

    ![Sidan Importera ER-programspecifika parametrar](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)
    
16. I fältet **Stat**, välj **Slutförd**.

    När du kör en ER-formatversion som har statusen antingen **slutförd** eller **delad**, måste denna uppsättning regler vara **slutförd**. I annat fall avbryts körningen av ER-basformatet när formatet försöker läsa in data från den här uppsättningen regler medan datakälla för sökning **väljare** körs.
    
    När du kör en ER-formatversion som har statusen **utkast** kan ER-basformatet komma åt denna uppsättning regler, oavsett status.
    
17. Välj **Spara**.
18. Stäng sidan **Appspecifika parametrar**.

## <a name="run-the-er-format-in-the-demf-company"></a>Kör ER-formatet i DEMF-företaget

1.  I konfigurationsträdet väljer du formatet **format för att lära dig hur du letar upp LE-data**.
2.  Klicka på **Kör** i åtgärdsfönstret.
3.  I dialogrutan som visas väljer du **OK**.
4.  Hämta det utdrag som genereras och spara det lokalt.

    Observera i det genererade utdraget att sammanfattningen av momskoden **InVAT7** har placerats på nivån **reducerad** och sammanfattningar av **VAT19** och **InVA19** momskoder har placerats på nivån **normal**. Det här beteendet bestäms av konfigurationen i de regler som är beroende av den juridiska personen.
    
5.  Gå till **Moms \> Indirekt moms \> Moms \> Momskoder**.
6.  Välj momskoden **InVAT7**.
7.  I åtgärdsfönstret på fliken **Momskod** i gruppen **Förfrågningar** välj **Bokförd moms** om du vill visa information om momsvärde och tillämpad momssats per momskod.

    ![Sidan Bokförd moms](./media/GER-AppSpecParms-Statement.PNG)

8.  Stäng sidan Bokförd moms.

## <a name="set-up-parameters-for-the-usmf-company"></a>Ställa in parametrar för USMF-företaget

1.  Välj den juridiska personen **USMF**.
2.  Gå till **Organisationsadministration  \> Elektronisk rapportering \> Konfigurationer**.
3.  I konfigurationsträdet expanderar du objektet **Modell för att lära dig parameteranrop** expanderar du objektet **Format för att lära dig parameteranrop** och välj formatet **format för att lära dig hur du slår upp LE-data**.
4.  I Åtgärdsfönstret, på fliken **Konfigurationer**, i gruppen **Appspecifika parametrar**, markerar du **Konfigurera**.
5.  Välj version **1.1.1** av det valda ER-formatet.
6.  På snabbfliken **Villkor** väljer du **Lägg till**.
7.  I fältet **Kod** för den nya posten väljer du nedrullningsbara pilen för att öppna uppslaget.

    Sökningen visar nu en lista över momskoder för **USMF** företagsmoms för urvalet.

    ![Sidan Importera ER-programspecifika parametrar](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)
    
8.  Välj momskoden **EXEMPT**.
9.  I fältet **Sökningsresultat** för den nya posten, välj värdet **Ingen beskattning**.
10. Välj **Lägg till** igen.
11. I fältet **Kod** för den nya posten, välj alternativet **\*Ej tomt\***.
12. I fältet **Sökningsresultat** för den nya posten, välj värdet **Vanlig beskattning**.
13. I fältet **Stat**, välj **Slutförd**.
14. Välj **Spara**.

    ![Sidan Importera ER-programspecifika parametrar](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)
    
15. Stäng sidan **Appspecifika parametrar**.

## <a name="run-the-er-format-in-the-usmf-company"></a>Kör ER-formatet i USMF-företaget

1.  I konfigurationsträdet väljer du formatet **format för att lära dig hur du letar upp LE-data**.
2.  Klicka på **Kör** i åtgärdsfönstret.
3.  I dialogrutan som visas väljer du **OK**.
4.  Hämta det utdrag som genereras och spara det lokalt.

    Observera i det genererade uttrycket att du nu har återanvänt ER-formatet för en annan juridisk person utan att göra några justeringar av ER-format.

## <a name="reuse-legal-entitydependent-parameters"></a>Återanvänd parametrar som är beroende av den juridiska personen.

### <a name="export-parameters"></a>Exportera parametrar

1.  Gå till **Organisationsadministration \> Arbetsytor \> Elektronisk rapportering**.
2.  Välj **rapporteringskonfigurationer**.
3.  I konfigurationsträdet väljer du formatet **format för att lära dig hur du letar upp LE-data**.
4.  I Åtgärdsfönstret, på fliken **Konfigurationer**, i gruppen **Appspecifika parametrar**, markerar du **Konfigurera**.
5.  Välj version **1.1.1** av ER-formatet.
6.  Välj **Export** i åtgärdsfönstret.
7.  Hämta den fil som genereras och spara det lokalt.

    Den konfigurerade uppsättningen programspecifika parametrar har nu exporterats som en XML-fil.

### <a name="import-parameters"></a>Importera parametrar

1.  Välj version **1.1.2** av ER-formatet.
2.  Välj **Import** i åtgärdsfönstret.
3.  Välj **ja** för att bekräfta att du vill åsidosätta de befintliga programspecifika parametrarna för den här formatversionen.
4.  Välj **bläddra** om du vill söka efter filen som innehåller de exporterade programspecifika parametrarna för version **1.1.1**.
5.  Välj **OK**.

    Version **1.1.2** av ER-formatet har nu samma programspecifika parametrar som du ursprungligen konfigurerade för version **1.1.1**.
    
    Observera att de programspecifika parametrarna för ett ER-format som är beroende av den juridiska personen. Om du vill återanvända de programspecifika parametrarna som konfigurerats för en juridisk person i en annan juridisk person, måste du exportera dem när du är inloggad på den första juridiska personen och sedan importera dem när du har loggat in på den andra juridiska personen.

    Du kan också använda den här metoden om du vill överföra ER-formatrelaterade programspecifika parametrar som ursprungligen konfigurerades i en Finance-instans till en annan Finance-instans.

    Tänk på att om du konfigurerar programspecifika parametrar för en version av ett ER-format och importerar en högre version av samma format till den aktuella Finance-instansen används inte de befintliga programspecifika parametrarna för den importerade versionen.
    
    Tänk också på att när du väljer en fil för import, jämförs även programspecifika parametrar i den filen med strukturen för motsvarande datakälla av typen **uppslag** för det återställningsformat som valts för import. Importen görs när strukturen för varje programspecifik parameter matchar strukturen för motsvarande datakälla i det återställningsformat som har valts för import. Om strukturlistorna inte matchar får du ett varningsmeddelande om att importen inte kan utföras. Om du tvingar importen att utföras rensas de befintliga programspecifika parametrarna för det valda återställningsformatet och du måste ställa in dem från början.

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a>Relation mellan programspecifika parametrar och ett ER-format

Relationen mellan ett ER-format och dess programspecifika parametrar upprättas genom ER-formatets instansoberoende identifieringskod. När du tar bort ett ER-format från Finance behålls därför de programspecifika parametrar som har konfigurerats för ER-format i den aktuella instansen Finance. De kan nås varje gång som ER-basformatet återimporteras till den här instansen av Finance.

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a>Få åtkomst till programspecifika parametrar med hjälp av ER-ramverket

I föregående exempel har du tillgång till programspecifika parametrar för ett ER-format med hjälp av ER-ramverket. Med den här metoden kan du inte begränsa åtkomsten till de programspecifika parametrarna för ett visst ER-format. Gör så här om du måste tillämpa dessa begränsningar. 

1.  Återanvänd antingen ett befintligt menyalternativ **ERSolutionAppSpecificParametersDesigner** eller implementera dina egna **ERSolutionAppSpecificParametersDesigner** menyalternativ.

    ![Visual Studio-sida](./media/GER-AppSpecParms-LookupForm-Access1.PNG)
    
2.  Gör något av följande:

    1.  Skapa en ny knapp för meny objekt och länka den till motsvarande post från tabellen **ERSolutionTable** genom att ange egenskapen **Datakälla** till **ERSolutionTable**.
    
        ![Visual Studio-sida](./media/GER-AppSpecParms-LookupForm-Access2.PNG)
        
    2.  Skapa en enkel knapp och åsidosätt den **klickade** metoden som den visas i följande exempel.
    
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