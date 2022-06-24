---
title: Användargränssnitt i Microsoft Office-stil för hantering av affärsdokument (innehåller video)
description: Detta ämne förklarar hur du använder det nya användargränssnittet för funktionen för hantering av affärsdokument i ramverket för elektroniska rapporter (ER).
author: v-anamir
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bcc464a17e27393c5904c59b8439de6ca000d57a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892237"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Användargränssnitt i Microsoft Office-stil för hantering av affärsdokument

[!include [banner](../includes/banner.md)]

Hanteringen av affärsdokument gör det möjligt för affärsanvändare att redigera affärsdokumentmallar genom att använda en Microsoft Office 365-tjänst eller lämpligt Microsoft Office-skrivbordsprogram. Redigeringar kan omfatta designändringar eller nya distributioner, eller så kan användare lägga till platshållare för att inkludera ytterligare data utan att behöva ändra källkoden. Mer information om hur du arbetar med hantering av affärsdokument finns i [översikt över hantering av affärsdokument](er-business-document-management.md).

Det nya användargränssnittet (UI) är tydligare och bekvämare att använda. Området **Affärsdokument** visar endast mallar som ägs av den aktuella [aktiva](tasks/er-configuration-provider-mark-it-active-2016-11.md) [leverantören](general-electronic-reporting.md#Provider) och finns i den aktuella instansen av Dynamics 365 Finance. I det föregående användargränssnittet angav fliken **Mall** alla mallar som var tillgängliga för alla leverantörer. Den visar också alla mallar som har skapats och redigerats av en användare med samma roll.

Du kan använda knappen **Nytt dokument** arbetsytan **Hantering av affärsdokument** om du vill skapa och redigera en mall i ett format för [elektronisk rapportering (ER)](general-electronic-reporting.md) [konfiguration](general-electronic-reporting.md#Configuration) som tillhandahålls av en annan leverantör och finns i den aktuella Ekonomi-instansen, eller för att ladda upp en ny mall från en Excel-arbetsbok. Dessutom, i version 10.0.25 och senare, kan du använda **Nytt dokument** för att skapa och redigera en mall i en ER-formatkonfiguration som lagras i den [globala databasen](general-electronic-reporting.md#Repository).

I exemplen i den här artikeln är den aktiva leverantören Contoso och du använder den för att skapa en mall som baseras på en mall som tillhandahålls av Microsoft. Du kan också skapa en mall genom att överföra din egen mall i Excel-format.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWAVQg]

Videon [Skapa ett nytt affärsdokument med hjälp av hantering av affärsdokument](https://youtu.be/gAIYl-mM_pw) (visas ovan) ingår i [Ekonomi och Drift spellistan](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) på YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Gör det nya dokumentgränssnittet tillgängligt i Hantering av affärsdokument

Om du vill kunna använda det nya dokumentgränssnittet i Hantering av affärsdokument måste du aktivera funktionen **Office-liknande gränssnittsupplevelser för hantering av affärsdokument** i arbetsytan **funktionshantering**.

Följ de här stegen för att aktivera funktionen för alla juridiska personer.

1. I arbetsytan **Funktionshantering** väljer du på fliken **All** funktionen **Office-liknande gränssnittsupplevelser för hantering av affärsdokument** i listan.
2. Välj **Aktivera nu** om du vill aktivera den valda funktionen.
3. Uppdatera sidan för att komma åt den nya funktionen.

## <a name="add-or-activate-a-provider"></a>Lägg till eller aktivera en leverantör

Varje mall i ett affärsdokument lagras i en ER-formatkonfiguration som markeras som ägd av en specifik konfigurationsleverantör. När du skapar en ny mall skapas en ny ER-formatkonfiguration där den finns. Därför måste en leverantör identifieras för den konfigurationen. Den aktiva leverantören av ER-ramverket används i det här syftet. Om det inte finns någon leverantör i ER kan du skapa en. Om det inte finns någon *aktiv* leverantör kan du aktivera en av de befintliga leverantör. En dialogruta öppnas för att lägga till eller aktivera en leverantör när det behövs, medan du börjar lägga till en ny mall.

### <a name="add-a-new-provider"></a>Lägg till en ny provider

Följ dessa steg i dialogrutan **Konfigurationsleverantör** om du vill skapa en ny leverantör:

1.  På fliken **Välj konfigurationsleverantör** i fältet **Namn** anger du namnet på den nya leverantören.
2.  I fältet **Internet-adress** ange Internet-adressen (URL) för den nya leverantören. 
3.  Välj **OK**.

    ![Skapa en ny leverantör i Affärsdokumenthantering.](./media/bdm_create_provider.png)

Den tillagda leverantör aktiveras automatiskt.

### <a name="activate-a-provider"></a>Aktivera en leverantör

Följ dessa steg i dialogrutan **Konfigurationsleverantör** om du vill aktivera en leverantör:

1.  På fliken **Välj konfigurationsleverantör** i fältet **Konfigurationsleverantör** väljer du leverantören.
2.  Välj **OK**.

    ![Aktivera leverantör i Affärsdokumenthantering.](./media/bdm_choose_provider.png)

Den valda leverantör aktiveras.

> [!NOTE]
> Varje mall för hantering av affärsdokument finns i en ER-formatkonfiguration som refererar till leverantören som konfigurationsförfattare. Därför krävs en aktiv leverantör för varje mall.

## <a name="edit-a-template-that-is-owned-by-another-provider"></a>Redigera en mall som ägs av en annan leverantör

Detta exempel visat hur du använder knappen **Nytt dokument** i arbetsytan **Hantering av affärsdokument** om du vill skapa och redigera en mall i ett format för elektronisk rapportering (ER) konfiguration som tillhandahålls av en annan leverantör och finns i den aktuella Ekonomi-instansen. I det här exemplet är den aktiva leverantören Contoso, som använder den ER-formatkonfiguration som tillhandahålls av Microsoft. När du har valt **Nytt dokument**, visar fliken **Välj** på sidan **Skapa en ny mall** visar alla mallar för den aktuella Ekonomi-instansen som ägs av den nuvarande leverantören och andra leverantörer. Välj en mall för att öppna den. Du kan sedan skapa en ny redigerbar kopia av mallen. Den redigerade mallen kommer sedan att lagras i en ny konfiguration för ER-format som skapas automatiskt.

1. Markera **Nytt dokument** i arbetsytan **Hantering av affärsdokument**.

    ![Arbetsyta för hantering av affärsdokument.](./media/BDM_overview_new_template1.png)

2. På sidan **Skapa en ny mall** på fliken **Välj** väljer du dokumentet som ska användas som mall och välj sedan **Skapa dokument**.

    ![Dialogrutan Affärsdokument.](./media/BDM_overview_new_template2.png)

3. I den nya dialogrutan, i fältet **Rubrik** ändra rubriken efter önskemål. Rubriktexten kommer att användas som namn på den konfiguration för nytt ER-format som skapas automatiskt. Utkastet till den här konfigurationen (**Kopia av FTI-rapport för kund (GER)**) kommer att innehålla den redigerade mallen och kommer att användas för att köra detta ER-format för den aktuella användaren. Ursprungliga mallen från baskonfigurationen för ER-format för att köra det här ER-formatet för alla andra användare.
4. I fältet **Namn** ändrar du namnet på den första revisionen av den redigerbara mallen som ska skapas automatiskt.
5. I fältet **Kommentar** uppdatera kommentarerna för revisionen av den redigerbara mallen som automatiskt skapas.
6. Välj **OK** för att bekräfta starten av redigeringsprocessen.

    ![Dialogrutan Skapa dokument.](./media/BDM_overview_new_template3.png)

## <a name="upload-a-template-that-uses-an-existing-excel-workbook"></a>Överför en mall som använder ett befintligt Excel-arbetsbok

Detta exempel visat hur du använder knappen **Nytt dokument** i arbetsytan **Hantering av affärsdokument** för att skapa och redigera en mall i en ER-formatkonfiguration, baserat på den tillgängliga Excel-arbetsboken. I det här exemplet är den aktiva leverantören Contoso och du använder ER [datamodellen](er-overview-components.md#data-model-component) och [ER-modellmappning](er-overview-components.md#model-mapping-component) konfigurationer som tillhandahålls av Microsoft. När du har valt **Nytt dokument** väljer du fliken **Ladda upp** på sidan **Skapa en ny mall**. Där kan du ange information om en Excel-arbetsboksöverföring. När du har fört över Excel-arbetsboken transformeras den till en affärsdokumentmall som öppnas för redigering. Den redigerade mallen kommer sedan att lagras i en ny konfiguration för ER-format som skapas automatiskt.

Följ de här stegen om du vill ange obligatorisk information innan du överför en mall.

1. Markera **Nytt dokument** i arbetsytan **Hantering av affärsdokument**.
2. På sidan **Skapa en ny mall** > fliken **Ladda upp** > fliken **Mall** väljer du **Bläddra** om du vill leta efter den Excel-fil som du vill använda som mall. I avsnittet **Mall** fylls fälten **Rubrik** och **Beskrivning** i automatiskt. De anger namn och beskrivning för den nya ER-formatkonfigurationen som skapas automatiskt. Du kan redigera dessa fält efter behov.
3. I avsnittet **Dokumenttyp**, i fältet **Namn**, anger du affärsdokumenttypen. Detta värde används för att söka efter rätt datakälla (det vill säga ER-modellkonfigurationen).

    ![Fliken Mall på fliken Ladda upp på sidan Skapa en ny mall.](./media/BDM_overview_new_UI_import_21.jpg)

4. I fliken **Datakälla**, på snabbfliken **Filter**, väljer du **Applicera filter**. I avsnittet **Datakälla** fylls fältet **Namn** i automatiskt, eller också kan du välja ett värde manuellt. Du kan använda filtret för att söka efter rätt datakällsnamn efter namn, beskrivning, lands-/regionkod och affärsdokumenttyp.

    ![Fliken Datakälla på fliken Ladda upp på sidan Skapa en ny mall.](./media/BDM_overview_new_UI_import_31.jpg)

    > [!NOTE]
    > Snabbfliken **Filter** används för att söka efter rätt datakälla (dvs. konfigurationen för ER-modell). Du kan redigera alla filterfält för att hitta den lämpligaste datakällan för det dokument du överför.
    > 
    > Villkoren på snabbfliken **Filter** används som **ELLER**-villkor.

5. På fliken **Mappning** väljer du **Automatisk identifiering**. Fältet **Rotdefinition** fylls i automatiskt, eller också kan du välja ett värde manuellt. På denna flik visas slutmappningen för elementen från mallen och modellen.

    ![Fliken Mappning på fliken Ladda upp på sidan Skapa en ny mall.](./media/BDM_overview_new_UI_import_41.jpg)

    > [!NOTE]
    > Mappningen i avsnittet **Mallstruktur** använder den fullständiga matchningen av etiketterna eller beskrivningarna i datakällan på användarens språk, samt i cellnamnet i mallen.

6. Välj **Skapa dokument** för att bekräfta att du vill skapa en mall och starta redigeringsprocessen.

Mer information finns i [översikt över hantering av affärsdokument](er-business-document-management.md).

## <a name="upload-a-template-from-the-global-repository"></a>Överför en mall från den globala databasen

Detta exempel visat hur du använder knappen **Nytt dokument** i arbetsytan **Hantering av affärsdokument** om du vill skapa och redigera en mall i ett format för elektronisk rapportering (ER) konfiguration som tillhandahålls av Microsoft och finns i den globala databasen. I det här exemplet är den aktiva leverantören Contoso, som använder den ER-formatkonfiguration som tillhandahålls av Microsoft. När du har valt **Nytt dokument**, visar fliken **Importera från global databas** på sidan **Skapa en ny mall** visar alla affärsdokumentmallar som är lagrade i den globala databasen men som saknas i den aktuella Ekonomi-instansen. När du har valt en mall, importeras den från den globala databasen till den aktuella Ekonomi-instansen för att skapa en ny redigeringsbar kopia. Den redigerade mallen kommer sedan att lagras i en ny konfiguration för ER-format som skapas automatiskt.

1. Markera **Nytt dokument** i arbetsytan **Hantering av affärsdokument**.
2. På sidan **Skapa en ny mall** på fliken **Importera från global databas** väljer du dokumentet som ska användas som mall och välj sedan **Skapa dokument**.

    ![Importera från fliken Global databas på sidan Skapa en ny mall.](./media/BDM_overview_new_template22.png)

3. Välj **Ja** i meddelanderutan om du vill bekräfta att du vill importera det valda dokumentet från den globala databasen till den aktuella Ekonomi-instansen. Om du tillfrågas om auktorisering följer du instruktionerna på skärmen.
4. I den nya dialogrutan, i fältet **Rubrik** ändra rubriken efter önskemål. Rubriktexten kommer att användas som namn på den konfiguration för nytt ER-format som skapas automatiskt. Utkastet till den här konfigurationen (**Kopia av inkassobrevanteckning (Excel)**) kommer att innehålla den redigerade mallen och kommer att användas för att köra detta ER-format för den aktuella användaren. Ursprungliga mallen från baskonfigurationen för ER-format för att köra det här ER-formatet för alla andra användare.
5. I fältet **Namn** ändrar du namnet på den första revisionen av den redigerbara mallen som ska skapas automatiskt.
6. I fältet **Kommentar** uppdatera kommentarerna för revisionen av den redigerbara mallen som automatiskt skapas.
7. Välj **OK** för att bekräfta starten av redigeringsprocessen.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
