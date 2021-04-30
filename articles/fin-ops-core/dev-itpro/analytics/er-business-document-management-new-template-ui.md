---
title: Användargränssnitt i Microsoft Office-stil för hantering av affärsdokument
description: Detta ämne förklarar hur du använder det nya användargränssnittet för funktionen för hantering av affärsdokument i ramverket för elektroniska rapporter (ER).
author: v-anamir
ms.date: 04/12/2021
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
ms.openlocfilehash: e6c5081f71a18dfac83b7aea950395436b42f50e
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881046"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Användargränssnitt i Microsoft Office-stil för hantering av affärsdokument

[!include [banner](../includes/banner.md)]

Hanteringen av affärsdokument gör det möjligt för affärsanvändare att redigera affärsdokumentmallar genom att använda en Microsoft 365-tjänst eller lämpligt Microsoft Office-skrivbordsprogram. Redigeringar kan omfatta designändringar eller nya distributioner, eller så kan användare lägga till platshållare för att inkludera ytterligare data utan att behöva ändra källkoden. Mer information om hur du arbetar med hantering av affärsdokument finns i [översikt över hantering av affärsdokument](er-business-document-management.md).

Det nya användargränssnittet (UI) är tydligare och bekvämare att använda. I området **affärsdokument** visas bara de mallar som är tillgängliga för den aktuella leverantören. I det föregående användargränssnittet angav fliken **Mall** alla mallar som var tillgängliga för alla leverantörer. Den visar också alla mallar som har skapats och redigerats av en användare med samma roll.

Du kan använda knappen **Nytt dokument** för att skapa och redigera en mall i en formatkonfiguration för elektronisk rapportering (ER) som tillhandahålls av en annan leverantör. I exemplet i det här avsnittet är leverantören Microsoft. Du kan också skapa en mall genom att överföra din egen mall i Excel-format.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAVQg]

Videon [Skapa ett nytt affärsdokument med hjälp av hantering av affärsdokument](https://youtu.be/gAIYl-mM_pw) (visas ovan) ingår i spellistan [Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) på YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Gör det nya dokumentgränssnittet tillgängligt i Hantering av affärsdokument

Om du vill kunna använda det nya dokumentgränssnittet i Hantering av affärsdokument måste du aktivera funktionen **Office-liknande gränssnittsupplevelser för hantering av affärsdokument** i arbetsytan **funktionshantering**.

Följ de här stegen för att aktivera funktionen för alla juridiska personer.

1. I arbetsytan **Funktionshantering** väljer du på fliken **All** funktionen **Office-liknande gränssnittsupplevelser för hantering av affärsdokument** i listan.
2. Välj **Aktivera nu** om du vill aktivera den valda funktionen.
3. Uppdatera sidan för att komma åt den nya funktionen.

## <a name="edit-templates-that-are-owned-by-other-providers"></a>Redigera mallar som ägs av andra leverantörer

1. Markera **Nytt dokument** i arbetsytan **Hantering av affärsdokument**.

    ![Arbetsyta för hantering av affärsdokument](./media/BDM_overview_new_template1.png)

2. På fliken **Välj** väljer du det dokument du vill använda som mall och sedan **Skapa dokument**.

    ![Dialogrutan affärsdokument](./media/BDM_overview_new_template2.png)

3. I den nya dialogrutan, i fältet **Rubrik** ändra rubriken efter önskemål. Rubriktexten kommer att användas som namn på den konfiguration för nytt ER-format som skapas automatiskt. Utkastet till den här konfigurationen (**Kopia av FTI-rapport för kund (GER)**) kommer att innehålla den redigerade mallen och kommer att användas för att köra detta ER-format för den aktuella användaren. Ursprungliga mallen från baskonfigurationen för ER-format för att köra det här ER-formatet för alla andra användare.
4. I fältet **Namn** ändrar du namnet på den första revisionen av den redigerbara mallen som ska skapas automatiskt.
5. I fältet **Kommentar** uppdatera kommentarerna för revisionen av den redigerbara mallen som automatiskt skapas.
6. Välj **OK** för att bekräfta starten av redigeringsprocessen.

    ![Dialogrutan skapa dokument](./media/BDM_overview_new_template3.png)

Knappen **Nytt dokument** används för att skapa och redigera en mall i formatkonfiguration för ER-format som tillhandahålls av en annan leverantör. I exemplet i det här avsnittet är leverantören Microsoft. När du klickar på **Nytt dokument** visas alla mallar som ägs av aktuella och andra leverantörer. När du har valt mallen kommer den att öppnas för redigering. Den redigerade mallen kommer sedan att lagras i en ny konfiguration för ER-format som skapas automatiskt.

## <a name="upload-a-template-that-uses-an-existing-excel-format"></a>Överföra en mall som använder ett befintligt Excel-format
Följ de här stegen om du vill ange obligatorisk information innan du överför en mall.

1. Markera **Nytt dokument** i arbetsytan **Hantering av affärsdokument**.

    ![Arbetsyta för hantering av affärsdokument](./media/BDM_overview_new_template1.png)
    
2. På sidan **Skapa en ny mall** > fliken **Ladda upp** > fliken **Mall** väljer du **Bläddra** om du vill leta efter den Excel-fil som du vill använda som mall. I avsnittet **Mall** fylls fälten **Rubrik** och **Beskrivning** i automatiskt. De anger namn och beskrivning för den nya ER-formatkonfigurationen som skapas automatiskt. Du kan redigera dessa fält efter behov.
3. I avsnittet **Dokumenttyp**, i fältet **Namn**, anger du affärsdokumenttypen. Detta värde används för att söka efter rätt datakälla (det vill säga ER-modellkonfigurationen).

    ![Mallflik](./media/BDM_overview_new_UI_import_21.jpg)

4. I fliken **Datakälla**, på snabbfliken **Filter**, väljer du **Applicera filter**. I avsnittet **Datakälla** fylls fältet **Namn** i automatiskt, eller också kan du välja ett värde manuellt. Du kan använda filtret för att söka efter rätt datakällsnamn efter namn, beskrivning, lands-/regionkod och affärsdokumenttyp.

    ![Fliken datakälla](./media/BDM_overview_new_UI_import_31.jpg)
    
    > [!NOTE]
    > Snabbfliken **Filter** används för att söka efter rätt datakälla (dvs. konfigurationen för ER-modell). Du kan redigera alla filterfält för att hitta den lämpligaste datakällan för det dokument du överför.
    > 
    > Villkoren på snabbfliken **Filter** används som **ELLER**-villkor.
    
5. På fliken **Mappning** väljer du **Automatisk identifiering**. Fältet **Rotdefinition** fylls i automatiskt, eller också kan du välja ett värde manuellt. På denna flik visas slutmappningen för elementen från mallen och modellen.

    ![Fliken Mappning](./media/BDM_overview_new_UI_import_41.jpg)
    
   > [!NOTE]
   > Mappningen i avsnittet **Mallstruktur** använder den fullständiga matchningen av etiketterna eller beskrivningarna i datakällan på användarens språk, samt i cellnamnet i mallen.

6. Välj **Skapa dokument** för att bekräfta att du vill skapa en mall och starta redigeringsprocessen.

Mer information finns i [översikt över hantering av affärsdokument](er-business-document-management.md).

Om det inte finns någon leverantör i Elektronisk rapportering kan du skapa en. Om det inte finns någon aktiv leverantör kan du välja att aktivera en.

- Om du vill skapa en leverantör ändrar du namnet på leverantören i fältet **Namn**, uppdaterar internetadressen för den nya leverantören i fältet **Internetadress** och väljer sedan **OK** för att bekräfta.

    ![Skapa ny leverantör i BDM](./media/bdm_create_provider.png)
    
- Om du vill aktivera befintlig leverantör väljer du namnet på leverantören i fältet **Konfigurationsleverantör** och väljer sedan **OK** för att ange leverantören som aktiv.

    ![Aktivera leverantör i BDM](./media/bdm_choose_provider.png)

> [!NOTE]
> Varje BDM-mall refererar till leverantören som författare av konfigurationen. Därför krävs en aktiv leverantör för mallen.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
