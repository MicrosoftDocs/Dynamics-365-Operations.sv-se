---
title: Konfigurera ER-format för användning av parametrar som anges per juridisk person
description: I det här avsnittet beskrivs hur du kan konfigurera format för elektroniska rapporter (ER) att använda parametrar som anges per juridisk person.
author: NickSelin
manager: AnnBe
ms.date: 04/02/2021
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
ms.openlocfilehash: 3802675b2fe0615f4c2ad682462a233c67f18f1a
ms.sourcegitcommit: 74f5b04b482b2ae023c728e0df0eb78305493c6a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2021
ms.locfileid: "5853503"
---
# <a name="configure-er-formats-to-use-parameters-that-are-specified-per-legal-entity"></a>Konfigurera ER-format för användning av parametrar som anges per juridisk person

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Översikt

I många av de format för elektroniska rapportering (ER) som du vill utforma måste du filtrera data genom att använda en uppsättning värden som är specifika för varje juridisk person i din instans (t.ex. en uppsättning skattekoder som filtrerar skattetransaktioner). När filtrering av den här typen har konfigurerats i ett ER-format används värden som är beroende av den juridiska personen (t.ex. skattekoder) i uttrycken i ER-format för att ange datafiltreringsregler. Det innebär att ER-formatet blir juridiskt-specifikt och att du kan generera de nödvändiga rapporterna måste du skapa härledda kopior av det ursprungliga ER-formatet för varje juridisk person där du måste köra ER-formatet. Varje härlett ER-format måste redigeras i syfte att erhålla värden specifika för juridiska personer, vilket ombaseras så fort den ursprungliga (bas-) versionen har uppdaterats, exporterats från en testmiljö samt importerats till en produktionsmiljö när den måste distribueras för produktionsanvändning, och så vidare. Detta innebär att underhåll av den här typen av ER-lösning är komplicerad och tar lång tid, detta av flera skäl:

-   Ju fler juridiska enheter, desto fler ER-format måste konfigureras.
-   Underhåll av ER-konfigurationer kräver att företags användare har ER-kunskap.

Med hjälp av parametrarna för ER-programspecifika parametrar kan avancerade användare konfigurera datafiltrering i ett ER-format så att det baseras på en uppsättning abstrakta regler. Den här uppsättningen regler kan konfigureras till att använda datakällor som är tillgängliga i ett ER-format. Affärsanvändare kan sedan ange verkliga regler utanför ER-ramverket med hjälp av det användargränssnitt som genereras automatiskt baserat på inställningarna för motsvarande ER-format och de aktuella data för juridiska personer som kommer att användas av ER-formatets datakällor. Uppsättningen regler som anges för ett ER-format kan exporteras från den aktuella juridiska personen för instansen Dynamics 365 Finance (Finance). Den kan sedan importeras till en annan juridisk person, antingen för samma finansieringsinstans eller till en annan instans, som en uppsättning regler för samma ER-format.

## <a name="prerequisites"></a>Förutsättningar

För att slutföra exemplen i detta ämne måste du ha åtkomst till instansen av Regulatory Configuration Services (RCS) som har etablerats för samma innehavare som Finance för en av följande roller:

- Utvecklare för elektronisk rapportering
- Konsult för funktionen för elektronisk rapportering
- Systemadministratör

Vi rekommenderar att du slutför stegen i avsnittet [supportparametersamtal för ER-datakällor av typen BERÄKNADE FÄLT](er-calculated-field-type.md). Om du redan har slutfört dessa steg kan du hoppa över stegen i avsnittet **importera ER-konfigurationer till RCS** nedan.

## <a name="import-er-configurations-into-rcs"></a>Importera ER-konfigurationer till RCS

Hämta och lagra följande ER-konfigurationer lokalt.

| **Beskrivning av innehåll**                        | **Filnamn**                                        |
|------------------------------------------------|------------------------------------------------------|
| Konfigurationsfil av exempel på **ER-datamodell**.    | [Modell för att lära dig parameteranrop.version.1.xml](https://download.microsoft.com/download/2/d/b/2db913a0-3622-494e-91a2-97fc494af9b9/Modeltolearnparameterizedcalls.version.1.xml)     |
| Konfigurationsfil av exempel på **ER-metadata**.      | [Metadata för att lära dig parameteranrop.version.1.xml](https://download.microsoft.com/download/1/b/3/1b343968-5a47-4000-b5a8-6487698ef4c0/Metadatatolearnparameterizedcalls.version.1.xml)  |
| Konfigurationsfil av exempel på **ER-modellmappning** | [Mappning för att lära dig parameteranrop.version.1.1.xml](https://download.microsoft.com/download/8/6/6/866e0ab6-2e05-4d98-9d52-d2da2038f6e4/Mappingtolearnparameterizedcalls.version.1.1.xml) |
| Konfiguration av exempel på **ER-format**.             | [Format för att lära dig parameteranrop.version.1.1.xml](https://download.microsoft.com/download/e/3/9/e392eadc-b9b4-4834-95c3-b8066dd00b9c/Formattolearnparameterizedcalls.version.1.1.xml)  |

Logga sedan in på RCS-instansen.

I det här exemplet ska du skapa en konfiguration för exempelföretaget, Litware. Innan du kan slutföra stegen i den här proceduren måste du först slutföra stegen i avsnittet [Skapa en konfigurationsleverantör och markera den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md) i RCS.

1.  Välj **elektronisk rapportering** på standardinstrumentpanelen.
2.  Välj **rapporteringskonfigurationer**.
3.  Importera de ER-konfigurationer du laddade ned innan till RCS i följande ordning: datamodell, metadata, modellmappning och format. Följ dessa steg för varje ER-konfiguration:

    1.  Välj **kurs**
    2.  Välj **Läs in från XML-fil**.
    3.  Välj **bläddra** om du vill välja en fil för den nödvändiga ER-konfigurationen i XML-format.
    4.  Välj **OK**.

## <a name="review-the-er-solution-that-is-provided"></a>Granska den medföljande ER-lösningen

1.  I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.
2.  Välj objektet **format för att lära sig mer parameteranrop**.
3.  Välj **Designer**.
4.  Växla mellan **expandering/komprimering**.

    ER-formatet **Formatet för att lära sig parameteranrop** är utformat för att generera en skatterapport i XML-format som visar flera skattenivåer (vanlig, reducerad och ingen). Varje nivå har ett annat antal detaljer.

    ![Flera nivåer av ER-format, format för att lära sig parameteriserade anrop](./media/RCS-AppSpecParms-ReviewFormat.PNG)

5.  På fliken **mappning** expanderar du objekten **modell**, **data** och **sammanfattnings**.

    Datakällan **Model.Data.Summar** returnerar listan över skattetransaktioner. Transaktionernas sammanfattas per skattekod. För den här datakällan har det beräknade fältet **Model.Data.Summary.Level** konfigurerats att returnera koden för skattenivån för respektive summerad post. För alla skattekoder som kan hämtas från datakällan **Model.Data.Summary** vid körning returnerar det beräknade fältet beskattningsnivåskod (**normal**, **reducerad**, **ingen** eller **annan**) som textvärde. Det beräknade fältet **Model.Data.Summary.Level** används för att filtrera poster av datakällan **Model.Data.Summary** och ange de filtrerade data i varje XML-element representerar en beskattningsnivå genom att använda fältet **Model.Data2.Level1**, **Model.Data2.Level2** och **Model.Data2.Level3**.

    ![Datakällan Model.Data.Summar listan över skattetransaktioner](./media/RCS-AppSpecParms-ReviewFormat-Data2Fld.PNG)

    Det beräknade fältet **Model.Data.Summary.Level** har konfigurerats så att det innehåller ett ER-uttryck. Skattekoder (**VAT19**, **InVAT19**, **VAT7**, **InVAT7**, **THIRD** och **InVAT0**) är hårdkodade i denna konfiguration. Därför beror detta ER-format på den juridiska person där dessa skattekoder har konfigurerats.

    ![Beräknat fält Model.Data.Summary.Level med hårdkodade skattekoder](./media/RCS-AppSpecParms-ReviewFormat-LevelFld.PNG)

    Om du vill stödja en annan uppsättning skattekoder för varje juridisk person måste du göra följande:

    - Skapa en härledd version av ER-formatet för varje juridisk person.
    - Uppdatera skattekoderna i det beräknade fältet **Model.Data.Summary.Level** baserat på inställningen för juridisk person.

6.  Stäng sidan **Formatdesigner**.

## <a name="create-a-derived-format"></a>Skapa ett härlett format

Därefter ska du använda funktionen ER-programspecifika parametrar för att stödja en annan uppsättning skattekoder för respektive juridisk person i ett enda ER-format.

1.  I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.
2.  Välj objektet **format för att lära sig mer parameteranrop**.
3.  Välj **Skapa konfiguration**.
4.  Välj alternativet **Härled från namn: format om du vill lära dig parameteranrop, Microsoft**.
5.  I fältet **namn** anger du **format för att lära dig hur du slår upp IE-data**.
6.  Välj **Skapa konfiguration**.

## <a name="configure-a-derived-format"></a>Konfigurera ett härlett format

### <a name="add-a-format-enumeration"></a>Lägg till formatuppräkning

Nu ska du lägga till en ny uppräkning för ER-format. Värdena i detta formatuppräkningsformulär visas för företagsanvändare, som anger juridiska personer – beroende uppsättningar med skattekoder för de olika skattenivåerna som används i ER-format.

1.  Välj **Designer**.
2.  Välj **formatuppräkningar**.
3.  Markera **Lägg till**.
4.  I fältet **Namn** anger du **Lista över beskattningsnivåer**.
5.  Välj **Spara**.
6.  På fliken **Format uppräkningsvärden** välj **Lägg till**.
7.  I fältet **Namn** anger du **Regelbunden beskattning**.
8.  Välj **Lägg till** igen.
9.  I fältet **Namn** anger du **Reducerad beskattning**.
10. Välj **Lägg till** igen.
11. I fältet **Namn** anger du **Ingen beskattning**.
12. Välj **Lägg till** igen.
13. Skriv **Utdata** i fältet **Andra**.

    ![Ny post på sidan formatuppräkningar](./media/RCS-AppSpecParms-ConfigureFormat-Enum.PNG)

    Eftersom olika språk används i affärsanvändarna för att ange uppsättningar av skattekoder som är beroende av den juridiska personen rekommenderar vi att du översätter värdena för denna uppräkning till de språk som är konfigurerade som prioriterade språk för dessa användare i Finance.

14. Välj posten **ingen avgift**.
15. Klicka i fältet **etikett**.
16. Välj **översätt**.
17. I fönstret **Textöversättning**, i fältet **Etikett-ID**, anger du **LBL_LEVELENUM_NO**.
18. I fältet **text på standardspråk** anger du **ingen beskattning**.
19. I fältet **Språk** välj **DE**.
20. I fältet **Översatt text** anger du **keine Besteuerung**.
21. Välj **översätt**.

    ![Textöversättningsbild ut](./media/RCS-AppSpecParms-ConfigureFormat-EnumTranslate.PNG)

22. Välj **Spara**.
23. Stäng sidan **formatuppräkningar**.

### <a name="add-a-new-lookup-data-source"></a>Lägg till en ny datakälla för sökning

Därefter ska du lägga till en ny datakälla som anger hur affärsanvändare ska ange regler som är beroende av den juridiska personen för att känna igen den korrekta skattenivån för varje summerad transaktionspost.

1.  Välj **ta bort** på fliken **Lägg till**.
2.  Välj **formatuppräkning\uppslag**.

    Du har just identifierat att varje regel som affärsanvändare anger för att beräkna skattenivå returnerar ett värde i ett ER-format uppräkningsresultat. Observera att datakällatypen **uppslag** kan nås under **datamodellen** och **Dynamics 365 for Operations**-blocken förutom blocket **formatuppräkning**. Därför kan ER-uppräkningar av datamodeller och program användas för att ange vilken typ av värden som returneras för datakällor av den typen. Mer information om datakällorna för **Sökning** finns i [Konfigurera datakällor för sökning att använda funktionen för ER-programspecifika parametrar](er-lookup-data-sources.md).
    
3.  Skriv **väljare** i fältet **Namn**.
4.  I fältet **Formatuppräkning** anger du **Lista över beskattningsnivåer**.

    Du har angett att en företagsanvändare måste välja ett av värdena som anges i formatuppräkningen **Lista över beskattningsnivåer** som ett returnerat värde för varje enskild regel som anges i denna datakälla.
    
5.  Välj **redigera uppslag**.
6.  Välj **kolumner**.
7.  Expandera objektet **Modell**.
8.  Expandera objektet **Data**.
9.  Expandera objektet **Skatt**.
10. Välj objektet **Model.Data.Tax.Code**.
11. Välj knappen **Lägg till** (högerpilen).

    ![Kolumner bild ut](./media/RCS-AppSpecParms-ConfigureFormat-Lookup1.PNG)

    Du har precis angett att för varje regel som anges i denna datakälla för erkännande av beskattningsnivå måste en företagsanvändare välja en av skattekoderna som villkor. Listan över skattekoder som affärsanvändaren kan välja returneras av datakällan **Model.Data.Tax**. Eftersom datakällan innehåller fältet **namn** visas namnet på skattekoden för varje momskodvärde i sökningen som visas för affärsanvändaren.
    
12. Välj **OK**.

    ![Sökdesignersida](./media/RCS-AppSpecParms-ConfigureFormat-Lookup2.PNG)

    Affärsanvändare kan lägga till flera regler som poster i den här datakällan. Varje post kommer att numreras med en radkod. Regler kommer att utvärderas i stigande ordning på radnumret.

    Eftersom du har valt fältet **Skattekod** som ett villkor för regler i denna uppslagningsdatakälla och därför anges **Skattekod** anges som fält för datatypen **Sträng** utvärderas varje regel vid körning genom att jämföra skattekoden som skickas till datakällan med skattekoden som har definierats i den här posten i datakällan.

    När en regel som uppfyller det konfigurerade villkoret hittas returnerar denna datakälla uppslagsvärden för regeln som definieras i fältet **uppslagsresultat**. Om ingen regel hittas genereras ett undantag för att meddela användaren att den aktuella datakällan inte kan returnera ett korrekt värde.

13. Välj **Spara**.
14. Stäng sidan **Sökningsdesigner**.
15. Välj **OK**.

    Lägg märke till att du har lagt till en ny datakälla som returnerar skattenivån som värdet i **listan över beskattningsnivåer** formatberäkning för eventuella skattekoder som skickas till datakällan som argument till parametern **Kod** för datatypen **sträng**.
    
    ![Formatdesignersida med ny datakälla](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld.PNG)

    Utvärderingen av konfigurerade regler beror på datatypen för de fält som har valts att definiera villkoren för dessa regler. När du väljer ett fält som är konfigurerat som ett fält av datatypen **numerisk** eller **datum**, skiljer sig villkoren från kriterierna som beskrevs tidigare för datatypen **sträng**. För fälten **numerisk** och **datum** måste regeln anges som ett värdeintervall. Regelns villkor kommer då att betraktas som uppfyllt när ett värde som skickas till datakällan finns i det konfigurerade intervallet.
    
    Följande illustration visar ett exempel på den här typen av inställning. Förutom fältet **Model.Data.Tax.Code** för datatypen **Sträng** används fältet **Model.Tax.Summary.Base** för datatypen **Real** används för att ange villkor för en datakälla för sökning.
    
    ![Sökdesignersida med ytterligare kolumner](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld2.PNG)

    Eftersom fälten **Model.Data.Tax.Code** och **Model.Tax.Summary.Base** markeras för den här datakälla för sökning konfigureras varje regel för den här datakällan på följande sätt:
    
    -   I listan som visas måste värdet i formatet **Lista över beskattningsnivåer** väljs som ett returnerat värde.
    -   Skattekoden måste anges som villkor för regeln. Endast skattekoder som tillhandahålls av datakällan **Model.Data.Tax** är tillämpliga.
    -   Lägsta och högsta värde för basbeloppet måste anges som villkor för regeln.

    Så här kommer varje regel för den här datakällan att utvärderas under körning:
    -   Är koden för datatypen **sträng** skickades till den här datakällan lika med skattekoden för en regel?
    -   Faller värdet på datatypen **verklig** som skickades till den här datakällan mellan specifika lägsta och högsta värde?

    En regel kommer att betraktas som tillämplig när båda villkoren uppfylls.

### <a name="translate-the-label-of-the-lookup-data-source-that-was-added"></a>Översätt etiketten för datakälla för sökning som lades till

Eftersom olika språk används i affärsanvändarna för att ange uppsättningar av skattekoder som är beroende av den juridiska personen rekommenderar vi att du översätter etiketten för alla datakällor för sökning som du lägger till, så att den presenteras på varje användares önskade språk på motsvarande sida.

1.  Markera datakällan **Model.Data.Selector**.
2.  Välj **Redigera**.
3.  Klicka i fältet **etikett**.
4.  Välj **översätt**.
5.  I fönstret **Textöversättning**, i fältet **Etikett-ID**, ange **LBL_SELECTOR_DS**.
6.  I fältet **text i standardfältet** anger du **Välj skattenivå per skattekod**.
7.  I fältet **Språk** välj **DE**.
8.  I fältet **Översätt text**, ange **Steuerebene für Steuerkennzeichen auswählen**.
9.  Välj **översätt**.
10. Välj **OK**.

    ![Datakällsegenskaper bild ut](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFldTranslate.PNG)

### <a name="add-a-new-field-to-consume-the-configured-lookup"></a>Lägg till ett nytt fält för att förbruka det konfigurerade uppslaget

1.  Expandera objektet **Model.Data**.
2.  Välj objektet **Model.Data.Summary**.
3.  Markera **Lägg till**.
4.  Välj **Fältet funktioner/beräknat fält**.
5.  I fältet **Namn** anger du **LevelByLookup**.
6.  Välj **Redigera recept**.
7.  I **fältet formel**, ange **Model.Selector(Model.Data.Summary.Code)**.
8.  Välj **Spara**.

    ![Lägga till Model.Selector(Model.Data.Summary.Code) till sidan Formeldesigner](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld.PNG)

9.  Stäng sidan **receptredigering**.
10. Välj **OK**.

    ![Formatdesignersida med ny formel tillagd](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld2.PNG)

    Observera att det beräknade fältet **LevelByLookup** som du har lagt till kommer att återge beskattningsnivån som värdet på formatuppräkningen **Lista över beskattningsnivåer** för varje sammanfattad skattetransaktionspost. Skattekoden för posten skickas till datakälla för sökning **Model.Selector** och uppsättningen med regler för den här datakällan används för att välja korrekt beskattningsnivå.

### <a name="add-a-new-format-enumeration-based-data-source&quot;></a>Lägg till ett nytt format med beräkningsbaserad datakälla.

Därefter ska du lägga till en ny datakälla som refererar till uppräkningen av format som du lade till tidigare. Värden för denna datakälla kommer att användas i ett formatuttryck för ER-formatering senare.

1.  Välj **Lägg till rot**.
2.  Välj **formatuppräkningar\uppräkningar**.
3.  I fältet **Namn** anger du **TaxationLevel**.
4.  I fältet **Formatuppräkning** anger du **Lista över beskattningsnivåer**.
5.  Välj **Spara**.

### <a name=&quot;modify-an-existing-field-to-start-to-use-the-lookup&quot;></a>Ändra ett befintligt fält till start om du vill använda sökningen

Därefter ska du ändra det befintliga beräknade fältet så att det använder den konfigurerade datakälla för sökning för att returnera rätt skattenivåvärde, beroende på skattekoden.

1.  Välj objektet **Model.Data.Summary.Level**.
2.  Välj **Redigera**.
3.  Välj **Redigera recept**.

    Observera att det aktuella uttrycket för fältet **Model.Data.Summary.Level** innehåller följande hårdkodade skattekoder:
    
    CASE (@.Code, &quot;VAT19&quot;, &quot;Regular&quot;, &quot;InVAT19&quot;, &quot;Regular&quot;, &quot;VAT7&quot;, &quot;Reduced&quot;, &quot;InVAT7&quot;, &quot;Reduced&quot;, &quot;THIRD&quot;, &quot;None&quot;, &quot;InVAT0&quot;, &quot;None&quot;, &quot;Other")

4.  I fältet **Formula** ange **CASE(@.LevelByLookup, TaxationLevel.'Regular taxation', "Regular", TaxationLevel.'Reduced taxation', "Reduced", TaxationLevel.'No taxation', "None", "Other")**.

    ![ER-åtgärdsdesignersida](./media/RCS-AppSpecParms-ConfigureFormat-ChangeLookupFld.PNG)
    
    Notera att uttrycket tillhörande fältet **Model.Data.Summary.Level** returnerar skattenivån, baserat på den aktuella postens skattekod och den uppsättning regler som en företagsanvändare konfigurerar i sökningsdatakällan **Model.Data.Selector**.
    
5.  Välj **Spara**.
6.  Stäng sidan **Formeldesigner**.
7.  Välj **OK**.
8.  Välj **Spara**.
9.  Stäng sidan **Formatdesigner**.

## <a name="complete-the-draft-version-of-a-derived-format"></a>Slutför utkastversion av ett härlett format

1.  På snabbfliken **versioner** väljer du **ändra status**.
2.  Välj **Slutför**.
3.  Välj **OK**.

## <a name="export-completed-version-of-modified-format"></a>Exportera slutförd justerad version av ett modifierat format

1.  I konfigurationsträdet väljer du objektet **Format för att lära sig hitta LE-data**.
2.  På snabbfliken **Versioner** väljer du den post som har statusen **Slutförd**.
3.  Välj **kurs**
4.  Välj **Exportera som XML-fil**.
5.  Välj **OK**.
6.  Webbläsaren hämtar filen **Format för att lära sig hitta LE data.xml**. Spara den här filen lokalt.

Upprepa stegen i detta avsnitt för överordnade objekt i formatet **Format för att lära sig hitta LE-data**, och lagra följande filer lokalt:

-   Format för att lära dig parameteranrop.xml
-   Mappning för att lära dig parameteranrop.xml
-   Modell för att lära dig parameteranrop.xml

Om du vill lära dig använda konfigurerat ER-format **Format för att lära sig hitta LE-data** i syfte att konfigurera skattekoduppsättningar oberoende av juridisk peson i syfte att filtrera skattetransaktioner beroende på skattenivå, slutför då stegen i ämnet [Konfigurera parametrar för ett ER-format per juridisk person](er-app-specific-parameters-set-up.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Formeldesigner i elektronisk rapportering](general-electronic-reporting-formula-designer.md)

[Ställa in parametrarna för ett ER-format per juridisk person](er-app-specific-parameters-set-up.md)

[Konfigurera sökningsdatakällor att använda funktionen för ER-programspecifika parametrar](er-lookup-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
