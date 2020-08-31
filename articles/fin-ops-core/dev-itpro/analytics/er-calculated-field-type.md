---
title: Stödparameteranrop till ER-datakällor för typen beräknat fält
description: Det här avsnittet innehåller information om hur du använder typen beräknat fält för ER-datakällor.
author: NickSelin
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 02d53f4326d8f31abf6ec7404575728837954bef
ms.sourcegitcommit: c9baf9a3b4552f0317b5ec87d252834f52df1b98
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2020
ms.locfileid: "3665620"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a>Stödparameteranrop till ER-datakällor för typen beräknat fält

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du kan utforma en data källa med elektronisk rapportering (ER) med hjälp av typen **beräknat fält**. Den här datakällan kan innehålla ett ER-uttryck som vid körning kan kontrolleras av värdena i parameterargumenten som är konfigurerade i en bindning som anropar den här datakällan. Genom att konfigurera parametriserade anrop av en sådan datakälla kan du återanvända en enskild datakälla i många bindningar, vilket minskar det totala antalet datakällor som måste konfigureras i ER-modellmappningar eller ER-format. Det förenklar också den konfigurerade ER-komponenten, vilket minskar underhållskostnaderna och kostnaderna för användning av andra konsumenter.

## <a name="prerequisites"></a>Förutsättningar
För att slutföra exemplet i det här avsnittet måste du ha följande åtkomst:

- Åtkomst till en av dessa roller:

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

- Åtkomst till Regulatory Configuration Services (RCS) som har etablerats för samma innehavare som Finance and Operations för en av följande roller:

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

Du måste också hämta följande filer och lagra dem lokalt.

| **Innehåll**                           | **Filnamn**                                        |
|---------------------------------------|------------------------------------------------------|
| Konfiguration av exempel på ER-datamodell.    | [Modell för att lära dig parameteranrop.version.1.xml](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)     |
| Konfiguration av exempel på ER-metadata.      | [Metadata för att lära dig parameteranrop.version.1.xml](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |
| Konfiguration av exempel på ER-modellmappning | [Mappning för att lära dig parameteranrop.version.1.1.xml](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg) |
| Konfiguration av exempel på ER-format.        | [Format för att lära dig parameteranrop.version.1.1.xml](https://mbs.microsoft.com/customersource/global/AX/downloads/hot-fixes/365optelecrepeg)  |

## <a name="sign-in-to-your-rcs-instance"></a>Logga in på RCS-instansen.
I det här exemplet skapar du en konfiguration för exempelföretaget, Litware, Inc. Först, i RCS, måste du slutföra stegen i proceduren [Skapa en konfigurationsleverantör och markera den som aktiv](tasks/er-configuration-provider-mark-it-active-2016-11.md):

1. Välj **elektronisk rapportering**på standardinstrumentpanelen.
2. Välj **rapporteringskonfigurationer**.
3. Importera nedladdade konfigurationer till RCS i följande ordning: datamodell, metadata, modellmappning, format. Utför följande steg för varje ER-konfiguration:

    1. Välj **kurs**
    2. Välj **Läs in från XML-fil**.
    3. Välj **bläddra** och sedan den nödvändiga ER-konfigurationen i XML-format.
    4. Välj **OK**.

## <a name="review-the-provided-er-solution"></a>Granska den medföljande ER-lösningen

### <a name="review-model-mapping"></a>Granska modellmappning

1. I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.
2. Välj **Mappning för att lära dig parameteranrop**.
3. Välj **Designer**.
4. Välj **Designer**.  
   
    Den här ER-modellmappningen har utformats för att göra följande:

    - Hämta listan över momskoder **(moms** datakälla) som finns i **TaxTable**-registret.
    - Hämta listan över momstransaktioner **(Trans** datakälla) som finns i **TaxTrans**-registret.
    
        - Gruppera listan över hämtade transaktioner (**Gr** datakälla) efter momskod.
        - Beräkna för grupperade transaktioner efter aggregerade värden per momskod:

            - Summa av basvärde för moms.
            - Summa av momsvärden.
            - Lägsta värde för tillämpad momssats.

    Modellmappningen i den här konfigurationen implementerar basdatamodellen för alla ER-format som skapas för den här modellen och körs i Finance and Operations. Detta innebär att innehållet i datakällorna **Moms** och **Gr** visas för ER-format, t.ex. abstrakta datakällor.

    ![Sidan modellmappningsdesigner med datakällorna Moms och Gr](media/er-calculated-field-type-01.png)

5.  Stäng sidan **modellmappningsdesigner**.
6.  Stäng sidan **modellmappning**.

### <a name="review-format"></a>Granska format

1. I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.
2. Välj **Format för att lära dig parameteranrop**.
3. Välj **Designer**. Det här ER-formatet har utformats för att göra följande:

    - Generera en skattedeklaration i XML-format.
    - Lägga fram följande beskattningsnivåer i momsrapporten: vanlig, reducerad och ingen.
    - Presentera flera detaljer för varje beskattningsnivå, med olika antal detaljer på varje nivå.

    ![Formatdesignersida](media/er-calculated-field-type-02.png)

4. Välj **mappning**.
5. Expandera artiklarna **Modell**, **Data** och **Sammanfattning**. 

    Den beräknade fältet **Model.Data.Summary.Level** innehåller det uttryck som returnerar koden för beskattningsnivån (**normal**, **reducerad**, **ingen,** eller **annan**) som ett textvärde för alla momskoder som kan hämtas från datakällan **Model.Data.Summary** vid körningstillfället.

    ![Sidan Formatera designer med information om datamodellen Modell för att lära sig parameteranrop](media/er-calculated-field-type-03.png)

6. Expandera **Modell**. **Data2**-objektet.
7. Expandera **Modell**. **Data2.Summary2**-objektet.
   
    Datakällan **Modell**.**Data2.Summary2** har konfigurerats för att gruppera datakällan **Model.Data.Summary**  transaktionsdetaljer per beskattningsnivå (returneras av **Model.Data.Summary.Level** beräknat fält) och beräkna aggregeringar.

    ![Sidan Formatera designer med information om datakällan Model.Data2.Summary2 data source](media/er-calculated-field-type-04.png)

8. Granska beräknade fält **Modell**.**Data2.Level1**, **Modell**.**Data2.Level2** och **Modell**.**Data2.Level3.** De här beräknade fälten används för att filtrera **Modell**. **Data2. Summary2**-postlista och returnerar endast poster som representerar en viss beskattningsnivå.
9. Stäng sidan **Formatdesigner**.

## <a name="create-a-derived-format"></a>Skapa ett härlett format
Du kan förbättra det angivna formatet genom att lägga till ett beräknat fält för att filtrera den begärda skattenivån i stället för att använda befintliga tre fält: **Modell**.**Data2.Level1**, **Modell**.**Data2.Level2,** och **Modell**.**Data2.Level3**. Den obligatoriska skattenivån kan anges på platsen där det nya beräknade fältet ska anropas.

1. I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.
2. Välj **Format för att lära dig parameteranrop**.
3. Välj **Skapa konfiguration**.
4. Välj **Härled från namn: format om du vill lära dig parameteranrop, Microsoft**.
5. I fältet **namn** anger du **format för att lära parameteranrop (anpassad)**.
6. Välj **Skapa konfiguration**.

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a>Konfigurera ett parameter beräknat fält som returnerar en lista med poster

### <a name="start-adding-a-new-calculated-field"></a>Börja lägga till ett nytt beräknat fält

1. Välj **Designer**.
2. Välj **expandera/komprimera** om du vill expandera alla formatobjekt.
3. Välj **mappning**.
4. Expandera objektet **Modell**.
5. Välj objektet **Model.Data2**.
6. Markera **Lägg till**.
7. Välj **Funktioner\\Beräknat fält**.
8. Skriv **Utdata** i fältet **Nivåer**.
9. Välj **Redigera recept**.

### <a name="define-a-parameter-for-adding-a-calculated-field"></a>Definiera en parameter för att lägga till ett beräknat fält

1. Välj **parametrar**.
2. Välj **Ny**.
3. I fältet **Namn** anger du **beskattningsnivå**.
4. Välj **Typ** i fältet **Artikeltyp**.

    Endast primitiva datatyper kan användas för att ange typen för parameterns argument. Därför kan typerna **postlist**, **post** och **fasttext** inte användas för detta syfte.

    Det maximala antalet parametrar som kan anges för ett enskilt beräknat fält är 8.

    ![Lista över parameterdatakällor](media/er-calculated-field-type-05.png)

5. Välj **OK**.

Genom att lägga till den här parametern anger du det villkor som måste finnas på platser för att det här beräknade fältet ska kunna anropas. När du ringer detta beräknade fält måste du ange argumentet för parametern **beskattningsnivå** som ett värde med formatet **sträng**.

   Se till att du bara definierar parametrar för de beräknade fält som finns i en behållare (antingen **postlist**, **post** eller **behållare**).

   Den konfigurerade parametern finns i listan över datakällor för det här beräknade fältet. Du kan lägga till parametern i det konfigurerade uttrycket genom att välja **Lägg till datakälla**.

   ![Datakällfält](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a>Definiera ett uttryck för att lägga till ett beräknat fält

1. I fältet **Formel**, ange: 

    **WHERE(\@.Summary2, \@.Summary2.grouped.Level =**
    
2. Välj parametern **skattenivå** i listan över datakällor.
3. Välj **Lägg till datakälla**.
4. I fältet **formel** slutför uttryck:  

    **WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**

5. Välj **Spara**.

    ![Information om datakälla](media/er-calculated-field-type-07.png)

6. Stäng sidan **Formeldesigner**.

### <a name="finish-adding-a-new-calculated-field"></a>Sluta lägga till ett nytt beräknat fält

- Välj **OK**.

På sidan **formatdesigner** kräver det konfigurerade parametriserade beräknade fältet **nivåer** argumentet **sträng**.

![Utökad lista över beräknade fältnivåer](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a>Använd det konfigurerade beräknade fältet för bindningsformatelement

1. Välj **Model.Data2.Levels** för att välja det konfigurerade beräknade fältet.
2. Välj formatelementet **Statement.Taxation.Regular**.
3. Välj **bind**.
4. Välj **ja** om du vill ersätta den för tillfället använda datakällan, **level1**, med den nya datakällan, **nivåer** i alla kapslade formatelement i det valda formatelementet.

    Tillämpad bindning har byggts som ett anrop till det parametriserade beräknade fältet. Som standard används namnet på det bundna formatelementet som ett argument för parametriserade beräknat fält under följande förhållanden:

      - Det beräknade fältet konfigureras för att använda en enda parameter.
      - Datatypen för den här parametern definieras som **sträng**.

    När namnet på det bundna formatelementet är tomt används namnet på datakällan för det här elementet i tillämpad bindning.

5. Välj formatelementet **Statement.Taxation.Reduced**.
6. Välj **bind**.
7. Välj **ja** om du vill ersätta den för tillfället använda datakällan, **level2**, med den nya datakällan, **nivåer** i alla kapslade formatelement under det valda formatelementet.
8. Välj formatelementet **Statement.Taxation.None**.
9. Välj **bind**.
10. Välj **ja** om du vill ersätta den för tillfället använda datakällan, **level3**, med den nya datakällan, **nivåer** i alla kapslade formatelement under det valda formatelementet.

   Om du anger argumentet för det parametriserade beräknade fältet för XML-elementet som representerar beskattningsnivån (t.ex. **Model.Data2.Levels("Reduced")** som ett textvärde), behöver du inte göra samma sak för kapslade XML-attribut, dvs. bindningar ärver automatiskt värdet för argumentet som definieras på den överordnade nivån (**Model.Data2.Levels.aggregated.Base**, inte **Model.Data2.Levels("Reduced").aggregated.Base**).

Återkommande anrop av valfritt parametriserat beräknat fält stöds inte.

Du kan välja **Redigera formel**och ändra det argument som används som standard det parametiserade beräknade fältet i den valda bindningen. Om detta argument saknas kan det orsaka fel under körningen och användarna informeras om en sådan situation när det aktuella formatet valideras.

![Varningsmeddelande för validering](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a>Konfigurera ett parameter beräknat fält som returnera en post
När ett parametiserat beräknat fält returnerar en post måste du stödja bindningar av enskilda fält i den här posten för att kunna formatera element. I sådana fall kommer det inte att finnas någon överordnad bindning som innehåller värdet för ett argument för anrop av ett parameteriserat beräknat fält, det här värdet måste definieras i bindningen av en enskild posts fält.

### <a name="start-adding-a-new-calculated-field"></a>Börja lägga till ett nytt beräknat fält

1. Välj objektet **Model.Data2**.
2. Markera **Lägg till**.
3. Välj **Funktioner\\Beräknat fält**.
4. Skriv **Dokument** i fältet **LevelRecord**.
5. Välj **Redigera recept**.

### <a name="define-a-parameter-for-adding-a-calculated-field"></a>Definiera en parameter för att lägga till ett beräknat fält

1. Välj **parametrar**.
2. Välj **Ny**.
3. I fältet **Namn** anger du **beskattningsnivå**.
4. Välj **Typ** i fältet **Artikeltyp**.
5. Välj **OK**.

### <a name="define-an-expression-for-adding-a-calculated-field"></a>Definiera ett uttryck för att lägga till ett beräknat fält

1. I fältet **formel** anger du följande:  
    
    **FIRSTORNULL(\@.Levels(**

2. Välj parametern **skattenivå**.
3. Välj **Lägg till datakälla**.
4. I fältet **formel** lägger du till **"momsnivå"))** till det som du angav i steg 1 för att färdigställa uttrycket till:  
    
    **FIRSTORNULL(\@.Levels('Taxation Level'))**

5. Välj **Spara**.
6. Stäng sidan **Formeldesigner**.

### <a name="finish-adding-a-new-calculated-field"></a>Sluta lägga till ett nytt beräknat fält

-   Välj **OK**.

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a>Använd det konfigurerade beräknade fältet för bindningsformatelement

1. Expandera **Model.Data2.LevelRecord** för att välja det konfigurerade beräknade fältet.
2. Expandera behållaren **Model.Data2.LevelRecord.aggregated** för att välja det konfigurerade beräknade fältet.
3. Markera fältet **Model.Data2.LevelRecord.aggregated.Base**.
4. Välj formatelementet **Statement.Taxation.None**.
5. Välj **Avbind**.
6. Välj formatelementet **Statement.Taxation.None.Base**.
7. Välj **bind**.
8. Välj **Redigera recept**.
9. Ändra uttrycket till **Model.Data2.LevelRecord("None").aggregated.Base**.

![Uppdaterat uttryck](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a>Ta bort beräknade fält som inte används

1. Välj **Model.Data2.Level1**.
2. Välj **Ta bort**.
3. Välj **Model.Data2.Level2**.
4. Välj **Ta bort**.
5. Välj **Model.Data2.Level3**.
6. Välj **Ta bort**.
7. Välj **Spara**.

  > [!NOTE]
  > Du återanvänder samma beräknade fält **Model.Data2.Levels** flera gånger i formatbindningar. Det är mycket enklare att använda och underhålla ett enda beräknat fält i stället för att göra detta för flera likartade fält.

8. Stäng sidan **Formatdesigner**.

## <a name="complete-adjusted-version-of-a-derived-format"></a>Slutför justerad version av ett härlett format

1. På snabbfliken **versioner** väljer du **ändra status**.
2. Välj **Slutför**.

## <a name="export-completed-version-of-a-derived-format"></a>Exportera slutförd justerad version av ett härlett format

1. Välj formatet **format om du vill läsa parametriserade anrop (anpassat)** i konfigurationsträdet.
2. På snabbfliken **Versioner**, välj slutförd version 1.1.1.
3. Välj **kurs**
4. Välj **Exportera som XML-fil**.
5. Lagra den hämtade konfigurationen lokalt i XML-format.

## <a name="test-er-formats"></a>Testa ER-format 
Du kan köra de ursprungliga och de förbättrade ER-formaten för att säkerställa att konfigurerade parameterbaserade beräknade fält fungerar som de ska.

### <a name="import-er-configurations"></a>Importera ER-konfigurationer
Du kan importera granskade konfigurationer från RCS med hjälp av ER-databasen för **RCS**-typen. Om du redan gick igenom stegen i avsnittet [Importera konfigurationer för elektronisk rapportering (ER) från Regulatory Configuration Services (RCS)](rcs-download-configurations.md), använder du den konfigurerade återställningsdatabasen för att importera konfigurationer som beskrivs tidigare i det här avsnittet till din miljö. Annars följer du dessa steg:

1. Markera företaget **DEMF** och välj sedan **elektronisk rapportering** på standardinstrumentpanelen.
2. Välj **rapporteringskonfigurationer**.
3. Importera konfigurationer från Microsoft Download Center i följande ordning: datamodell, modellmappning, format. Utför följande steg för varje ER-konfiguration:

    1. Välj **kurs**
    2. Välj **Läs in från XML-fil**.
    3. Välj **bläddra** och sedan den nödvändiga ER-konfigurationen i XML-format.
    4. Välj **OK**.

4. Importera exporterade från RCS slutförd version 1.1.1 av formatet **Format för att lära dig parameteranrop**:

    1. Välj **kurs**
    2. Välj **Läs in från XML-fil**.
    3. Välj **bläddra** om du vill välja den lokalt lagrade filen **Format för att lära dig parameteranrop (anpassade)** i XML-format.
    4. Välj **OK**.

### <a name="run-er-formats"></a>Kör ER-format

1. I konfigurationsträdet expanderar du innehållet i objektet **modell för att lära dig parameteranrop**.
2. Välj **Format för att lära dig parameteranrop**.
3. Välj **kör** på menyfliken högst upp.
4. Spara de lokalt genererade utdata.
5. Välj objektet **format för att lära sig mer parameteranrop (anpassat**).
6. Välj **kör** på menyfliken högst upp.
7. Spara genererade utdata lokalt. 
8. Jämför innehållet i de genererade utflödena.

## <a name="additional-resources"></a>Ytterligare resurser
[Formeldesigner i elektronisk rapportering (ER)](general-electronic-reporting-formula-designer.md)
