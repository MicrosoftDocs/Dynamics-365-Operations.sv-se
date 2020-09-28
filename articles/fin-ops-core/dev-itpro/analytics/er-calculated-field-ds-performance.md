---
title: Förbättra prestanda för ER-lösningar genom att lägga till parametriserade datakällor för BERÄKNADE FÄLT
description: I det här avsnittet beskrivs hur du kan förbättra prestandan hos elektronisk rapportering (ER)-lösningar genom att lägga till parametriserade datakällor för BERÄKNADE FÄLT.
author: NickSelin
manager: AnnBe
ms.date: 09/02/2020
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
ms.openlocfilehash: a87098e82284a4951f3a4de050f6ba3f587fd20a
ms.sourcegitcommit: 5472005274f2f94fba82dda90de128f39d8b8390
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760092"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a>Förbättra prestanda för ER-lösningar genom att lägga till parametriserade datakällor för BERÄKNADE FÄLT

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du kan göra [prestandaspårningar](trace-execution-er-troubleshoot-perf.md) av formatet [elektronisk rapportering (ER)](general-electronic-reporting.md) som körs och sedan använda informationen från dessa spårningar för att förbättra prestanda genom att konfigurera en parameter för datakälla **beräknat fält**.

Som en del av processen att utforma ER-konfigurationer för att generera affärsdokument definierar du metoden som används för att hämta data från applikationen och mata in den i den genererade utdata. Genom att utforma en parametriserad ER-datakälla av typen **beräknade fält** kan du minska antalet databasanrop och avsevärt minska den tid och kostnad som krävs för att samla in information om ER-formatkörning.

## <a name="prerequisites"></a>Förutsättningar

- Om du vill slutföra exemplen i det här avsnittet måste du ha tillgång till en av följande [roller](../sysadmin/tasks/assign-users-security-roles.md):

    - Utvecklare för elektronisk rapportering
    - Konsult för funktionen för elektronisk rapportering
    - Systemadministratör

- Företaget måste vara inställt på **DEMF**.
- Följ instruktionerna i [Bilaga 1](#appendix1) i det här avsnittet för att hämta komponenterna för exemplet Microsoft ER-lösning som krävs för att slutföra exemplen i detta ämne.
- Följ stegen i [tillägg 2](#appendix2) i det här avsnittet om du vill konfigurera den minsta uppsättningen ER-parametrar som krävs för att använda ER-ramverket för att förbättra prestanda i exempel Microsoft ER-lösningen.

## <a name="import-the-sample-er-solution"></a>Importera ER-exempellösning

Tänk dig att du måste designa en ER-lösning för att skapa en ny rapport som visar leverantörstransaktioner. För närvarande kan du hitta transaktionerna för en vald leverantör på sidan **leverantörstransaktioner** (gå till **leverantörsreskontra** \> **leverantörer** \> **alla leverantörer**, välj en leverantörer och sedan i åtgärdspanelen på fliken **leverantörer** i gruppen **transaktioner** väljer du **transaktioner**). Du vill dock ha alla leverantörstransaktioner samtidigt i ett elektroniskt dokument i XML-format. Den här lösningen består av flera ER-konfigurationer som innehåller den nödvändiga datamodellen, modellmappning och formatkomponenter.

Det första steget är att importera exempel ER-lösningen för att generera en leverantörstransaktionsrapport.

1. Logga in på den instans av Microsoft Dynamics 365 Finance som har etablerats för ditt företag.
2. I det här avsnittet ska du skapa och ändra konfigurationer för exempelföretaget **Litware, Inc**. Kontrollera att denna konfigurationsleverantör har lagts till i din Finance-instans och valts som aktiv. Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. På arbetsytan **Elektronisk rapportering** väljer du panelen **Rapporteringskonfiguration**.
4. På sidan **konfigurationer** importerar du de ER-konfigurationer som du hämtade som en förutsättning i Finance i följande ordning: datamodell, modellmappning, format. Följ dessa steg för varje konfiguration:

    1. På Åtgärdsfönster väljer du **växla** \> **läs in från XML-fil**.
    2. Välj **bläddra** om du vill välja en fil för ER-konfigurationen i XML-format.
    3. Välj **OK**.

![Importerade konfigurationer på sidan Konfigurationer](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a>Granska ER-exempellösning

### <a name="review-the-model-mapping"></a>Granska modellmappningen

1. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **modell för prestandaförbättring** och väljer sedan **mappning av prestandaförbättring**.
2. Klicka på **Designer** i åtgärdsfönstret.
3. På sidan **Modell till mappning av datakälla** i åtgärdsfönstret, välj **Designer**.

    Den här ER-modellmappningen har utformats för att göra följande åtgärder:

    - Hämta listan med leverantörstransaktioner som är lagrade i registret VendTrans (**Trans** datakälla).
    - För varje transaktion hämtas från tabellen VendTable, posten för en leverantör som transaktionen har bokförts för (**\#Vend** datakälla).

    > [!NOTE]
    > Datakälla **\#Vend** är konfigurerad för att hämta motsvarande leverantörspost genom att använda den befintliga många till en-relationen **\@.'\>Relations'.VendTable\_AccountNum**.

    Modellmappningen i den här konfigurationen implementerar basdatamodellen för alla ER-format som skapas för den här modellen och körs i Finance. Detta innebär att innehållet i datakällan**Trans** visas för ER-format, t.ex. abstrakta datakällor **modell**.

    ![Trans datakälla på sidan för modellmappningsdesigner](media/er-calculated-field-ds-performance-mapping-1.png)

4. Stäng sidan **modellmappningsdesigner**.
5. Stäng sidan **modell till mappning av datakälla**.

### <a name="review-format"></a>Granska format

1. På sidan **konfigurationer** i konfigurationsträdet i vänster fönster expanderar du **modell för prestandaförbättring** och väljer sedan **format för prestandaförbättring**.
2. Klicka på **Designer** i åtgärdsfönstret.
3. På sidan **Formatdesigner** på fliken **Mappning** välj **Utöka/Komprimera**.
4. Expandera artiklarna **Modell**, **Data** och **Transaktion**.

    Det här ER-formatet är utformat för att skapa en leverantörstransaktionsrapport i XML-format.

    ![Formatera datakällor och konfigurerade bindningar för formatelement på sidan formatdesigner](media/er-calculated-field-ds-performance-format.png)

5. Stäng sidan **Formatdesigner**.

## <a name="run-the-sample-er-solution-to-trace-execution"></a>Kör exempel ER-lösning för att spåra körning

Anta att du har skapat den första versionen av ER-lösningen. Du vill nu testa lösningen i Finance-instansen och analysera körningsprestanda.

### <a name="turn-on-the-er-performance-trace"></a>Aktivera ER-prestandaspårning

1. Välj företaget **DEMF**.
2. Följ stegen i [Aktivera ER-prestationsspårning](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) för att generera en prestandaspårning medan ett ER-format körs.

    ![Dialogruta Användarparametrar](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a>Kör ER-format

1. Gå till **Organisationsadministration** \> **Elektronisk rapportering** \> **Konfigurationer**.
2. På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Prestandaförbättringsformat**.
3. Klicka på **Kör** i åtgärdsfönstret.

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a>Använd prestandaspårning för att analysera modell mappningsresultat

1. På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Prestandaförbättringsmappning**.
2. Klicka på **Designer** i åtgärdsfönstret.
3. På sidan **Modellmappning** i åtgärdsfönstret, välj **Designer**.
4. På snabbfliken **Modellmappningsdesigner** på åtgärdsfönstret väljer du **Prestandaspårningsformat**.
5. Markera den senaste spårningen som genererades och välj sedan **OK**.

Ny information är nu tillgänglig för vissa datakällobjekt i den aktuella modellmappningen:

- Den faktiska tid som användes för att hämta data genom att använda datakällan
- Samma tid uttryckt i procent av den totala tid som användes för att köra hela modellmappningen

![Körningstid på sidan modellmappningsdesigner](./media/er-calculated-field-ds-performance-mapping-2.png)

Rutnätet **Prestandastatistik** visar att datakällan **Trans** anropar VendTrans-registret en gång. Värdet **\[265\]\[Q:265\]** för datakällan **Trans** anger att 265 leverantörstransaktioner har hämtats från appregistret och återgått till datamodellen.

I rutnätet **Prestandastatistik** visas också att den aktuella modellmappningen duplicerar databas begäran när datakällan **\#Vend** körs. Denna dubblering sker på grund av följande:

- Leverantörsregistret kallas två gånger för var och en av de 265 upprepade leverantörstransaktionerna, för totalt 530 samtal:

    - Ett samtal görs för att ange leverantörskontonumret.
    - Ett samtal görs för att ange leverantörsnamnet.

- Leverantörsregistret anropas för varje förbrukad leverantörstransaktion även om de hämtade transaktionerna bara har bokförts för fem leverantörer. Av 530 samtal, 525 är dubbletter. Följande illustration visar meddelandet som du får om att ringa upp (databas begäran).

![Meddelande om dubbla databasbegäranden på sidan modellmappningsdesigner](./media/er-calculated-field-ds-performance-mapping-2a.png)

För den totala modellmappningens körningstid (ungefär åtta sekunder), lägg märke till att mer än 80 procent (cirka sex sekunder) har hämtats till värden från apptabellen för VendTable. Procentandelen är för stor för två attribut för fem leverantörer, jämfört med mängden information från apptabellen VendTrans.

Om du vill minska antalet samtal som görs för att hämta leverantörsinformation för varje transaktion och förbättra modellmappningens prestanda, kan du använda cachelagring för datakällan **\#Vend**.

> [!NOTE]
> Datakällan **Trans\\\#Vend** cachelagras i omfånget för den aktuella transaktionen i datakällan **Trans** vid körning.

Genom att cachelagra datakällan **\#Vend** minskar du antalet duplicerade samtal från 525 till 260, men du eliminerar inte dubbletterna helt. Om du vill ta bort duplicering helt kan du konfigurera en ny parametriserad datakälla för typen **beräknade fält**.

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>Förbättra modellmappningen utifrån information från körningsspårningen

### <a name="change-the-logic-of-the-model-mapping"></a>Ändra logiken för modellmappningen

Gör så här om du vill använda cachelagring och en datakälla för typen **beräknat fält** för att förhindra att samtal till databasen dubbleras.

1. På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Prestandaförbättringsmappning**.
2. Klicka på **Designer** i åtgärdsfönstret.
3. På sidan **Modellmappning** i åtgärdsfönstret, välj **Designer**.
4. På sidan **modellmappningsdesigner** följer du dessa steg för att lägga till en datakälla för typen **Tabellregister** för åtkomst till poster i VendTable-appregistret:

    1. I fönstret **Datakälltyper** expandera **Dynamics 365 for Operations** och välj **registerposter**.
    2. Välj **Lägg till rot**.
    3. I dialogrutan i fältet **Namn**, ange **Vend**.
    4. I fältet **Tabell** ange **VendTable**.
    5. Välj **OK**.

5. Du kan endast parameteranrop till datakällor av typen **beräknat fält** om dessa datakällor finns i en behållare. Följ därför dessa steg för att lägga till en datakälla för typen **tomma behållare** för att lagra en ny parametriserad datakälla för typen **beräknat fält**:

    1. I fönstret **Datakälltyper** expandera **Allmän** och välj **Töm behållare**.
    2. Välj **Lägg till rot**.
    3. I dialogrutan i fältet **Namn**, ange **Ruta**.
    3. Välj **OK**.

    ![Ruta datakälla på sidan för modellmappningsdesigner](./media/er-calculated-field-ds-performance-mapping-3.png)

6. Följ dessa steg för att lägga till en parameteriserad datakälla för typen **beräknat fält**:

    1. I fönstret **datakällor** välj **ruta**.
    2. I fönstret **datakälltyper** expanderar du **funktioner** och markerar **beräknade fält**.
    3. Markera **Lägg till**.
    4. I dialogrutan i fältet **Namn**, ange **Vend**.
    5. Välj **Redigera recept**.
    6. På sidan **Formeldesigner** välj **Parametrar** för att ange vilka parametrar som måste anges när denna datakälla anropas.
    7. I dialogrutan **Parametrar** välj **Ny**.
    8. I fältet **Namn** anger du **parmVendAccNumber**.
    9. Välj **Typ** i fältet **Artikeltyp**.
    10. Välj **OK**.
    11. I fältet **Formel** anger du **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.
    12. Stäng sidan **Spara** och **Formeldesigner**.
    13. Klicka på **OK** om du vill lägga till den nya datakällan.

7. Markera den tillagda datakällan som cachelagrad under körningen genom att följa stegen nedan:

    1. I **Datakällor** välj **Box\\Vend**.
    2. Välj **cache**.

    > [!NOTE]
    > Datakällan **Box\\Vend** cachelagras i omfånget för alla leverantörstransaktionen i datakällan **Trans** vid körning.

8. Följ dessa steg för att uppdatera den kapslade datakällan **Trans\\\#Vend** så att den använder fältet datakälla **Box\\Vend**:

    1. Välj **Stödprocess** i fönstret expandera **Trans**.
    2. Markera den datakällan **Trans\\\#Vend** och välj **Redigera** \> **Redigera recept**.
    3. På sidan **Formeldesigner** i fältet **Formel** ange **Box.Vend(\@.AccountNum)**.
    4. Välj **Spara** och stäng sedan sidan **Formeldesigner**.
    5. Klicka på **OK** om du vill slutföra ändringarna i den valda datakällan.

9. Välj **Spara**.

    ![Vend datakälla på sidan för modellmappningsdesigner](./media/er-calculated-field-ds-performance-mapping-4.png)

10. Stäng sidan **modellmappningsdesigner**.
11. Stäng sidan **modellmappningar**.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>Slutför den ändrade versionen av ER-modellmappningen

1. På sidan **Konfigurationer** på snabbfliken **Versioner** FastTab, välj version **1.2** av konfigurationen **prestandaförbättringsmappning**.
2. Välj **Ändra status** \> **Slutför** och välj sedan **OK**.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>Kör modifierad ER-lösning för att spåra körning

Upprepa stegen i avsnittet [kör ER-format](#run-format) tidigare i det här avsnittet om du vill generera en ny prestandaspårning.

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a>Använd prestandaspårning för att analysera justeringar till modellmappning 

1. På sidan **konfigurationer** i konfigurationsträdet väljer du artikeln **Prestandaförbättringsmappning**.
2. Klicka på **Designer** i åtgärdsfönstret.
3. På sidan **Modellmappning** i åtgärdsfönstret, välj **Designer**.
4. På snabbfliken **Modellmappningsdesigner** på åtgärdsfönstret väljer du **Prestandaspårningsformat**.
5. Markera den senaste spårningen som genererades och välj sedan **OK**.

Observera att justeringarna som du har gjort av modellmappningen har eliminerat dubbla frågor till databasen. Antalet anrop till databasregister och datakällor för den här modellmappningen har också minskats.

![Spåra information på sidan för modellmappningsdesigner 1](./media/er-calculated-field-ds-performance-mapping-5.png)

Den totala körningstiden har reducerats omkring 20 gånger (från cirka 8 sekunder till cirka 400 millisekunder). Därför har hela ER-lösningens prestanda förbättrats.

![Spåra information på sidan för modellmappningsdesigner 2](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a>Tillägg 1: Hämta komponenterna i exemplet Microsoft ER-lösning

Du måste ladda ner följande filer och lagra dem lokalt.

| Fil                                        | Innehåll |
|---------------------------------------------|---------|
| Prestandaförbättringsmodell.version.1     | [Konfiguration av exempel på ER-datamodell.](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Prestandaförbättringsmappning.version.1.1 | [Konfiguration av exempel på ER-modellmappning](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Prestandaförbättringsformat.version.1.1  | [Konfiguration av exempel på ER-format.](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a>Bilaga 2: Konfigurera ER-ramverket

Innan du kan börja använda ER-ramverket för att förbättra prestanda i exempel Microsoft ER-lösningen måste du konfigurera den minsta uppsättningen ER-parametrar.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Konfigurera ER-parametrar

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **parametrar för elektronisk rapportering**.
3. På sidan **parametrar för elektronisk rapportering** på fliken **allmänna** anger du alternativet till **aktivera designläge** till **Ja**.
4. Ange följande parametrar på fliken **Bilagor**:

    - I fältet **Konfigurationer** välj typen **Fil** för **DEMF**-företaget.
    - I fältet **Jobbarkiv**, **Tillfälliga**, **Baslinje** och **Andra** och välj typen **Fil**.

Mer information om ER-parametrar finns i [Konfigurera om ER-ramverket](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Aktivera en ER-konfigurationsleverantör

Varje ER-konfiguration som läggs till markeras som ägd av en ER-konfigurationsleverantör. Den ER-konfigurationsleverantör för ER som aktiveras i arbetsytan **Elektronisk rapportering** används för det här syftet. Därför måste du aktivera en ER-konfigurationsleverantör i arbetsytan **Elektronisk rapportering** innan du börjar lägga till eller redigera ER-konfigurationer.

> [!NOTE]
> Endast ägaren till en ER-konfiguration kan redigera konfigurationen. Därför måste en lämplig ER-konfigurationsleverantör aktiveras innan en ER-konfiguration kan redigeras arbetsytan **Elektronisk rapportering**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Granska listan med ER-konfigurationsleverantörer

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **Konfigurationsleverantörer**.
3. På sidan **Tabellen konfigurationsleverantörer** har varje leverantörspost ett unikt namn och en URL. Granska innehållet på den här sidan. Om det redan finns en post för **Litware, Inc.** hoppar du över nästa procedur [Lägg till en ny ER-konfigurationsleverantör](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>Lägg till en ny ER-konfigurationsleverantör

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **Relaterade länkar** väljer du **Konfigurationsleverantörer**.
3. Välj **Konfigurationsleverantörer** på sidan **Leveranssätt**.
4. I fältet **Namn** anger du **Litware, Inc.**.
5. I fältet **Internetadress** anger du `https://www.litware.com`.
6. Välj **Spara**.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Aktivera en ER-konfigurationsleverantörer

1. Gå till **Organisationsadministration** \> **Arbetsytor** \> **Elektronisk rapportering**.
2. På sidan **lokaliseringskonfiguration** i avsnittet **konfigurationsleverantörer** välj panelen **Litware, Inc.** och välj sedan **Ange aktiv**.

Mer information om ER-konfigurationsleverantörer finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="additional-resources"></a>Ytterligare resurser

- [Översikt över elektronisk rapportering](general-electronic-reporting.md)
- [Spåra körningen av ER-format för att felsöka prestandaproblem](trace-execution-er-troubleshoot-perf.md)
- [Stödparameteranrop till ER-datakällor för typen beräknat fält](er-calculated-field-type.md)
