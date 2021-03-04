---
title: Lägga till nya fält i en affärsdokumentmall i Microsoft Excel
description: Det här avsnittet innehåller information om hur du lägger till nya fält i en affärsdokumentmall i Microsoft Excel genom att använda funktionen för hantering av affärsdokument.
author: NickSelin
manager: AnnBe
ms.date: 11/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: fcfbcb021b192cef75d59b0db1796e994f3dc27d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681386"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a>Lägga till nya fält i en affärsdokumentmall i Microsoft Excel

[!include[banner](../includes/banner.md)]

Du kan lägga till nya fält i en mall som används för att generera affärsdokument i Microsoft Excel-formatet. Dessa fält kan läggas till som platshållare som används för att fylla genererade dokument med nödvändig information från programmet. För varje fält som du lägger till kan du också ange en bindning till datakällorna, där du anger vilka programdata som ska anges i fältet när mallen används för att generera affärsdokument.

Om du vill veta mer om den här funktionen fyller du i exemplet i det här avsnittet. I det här exemplet visas hur du uppdaterar en mall så att fälten fyller i fritextfakturaformulär som skapas.

## <a name="configure-business-document-management-to-edit-templates"></a>Konfigurera affärsdokumenthantering för att redigera mallar

Eftersom Hantering av affärsdokument (BDM) bygger ovanpå ramverket [Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md) måste du konfigurera de nödvändiga återställnings- och BDM-parametrarna innan du kan börja arbeta med BDM.

1.  Logga in på instansen av Microsoft Dynamics 365 Finance som systemadministratör.
2.  Slutför följande steg i exemplet i avsnittet [Hantering av affärsdokument – översikt:](er-business-document-management.md):

    1.  Konfigurera ER-parametrar.
    2.  Starta BDM.

Nu kan du börja använda BDM för att redigera mallar för affärsdokument.

## <a name="import-er-solutions-that-contain-a-template"></a>Importera ER-lösningar som innehåller en mall

Exemplet i den här proceduren använder den officiellt publicerade ER-lösningen. Du måste importera ER-konfigurationer för lösningen till din aktuella Finance-instans.

Konfigurationen för ER-format **Fritextfaktura (Excel)** för den här lösningen innehåller affärsdokumentmallen i Excel-format som kan redigeras med BDM. Importera den senaste versionen av den här konfigurationen för ER-format från Microsoft Dynamics Lifecycle Service (LCS). De motsvarande konfigurationerna för ER-datamodell och ER-modellmappning kommer att importeras automatiskt.

Mer information om att importera ER-konfigurationer finns i [Hantera livscykeln för konfiguration av elektronisk rapportering](general-electronic-reporting-manage-configuration-lifecycle.md).

![Sidan LCS delat tillgångsbibliotek](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a>Redigera ER-lösningsmallen

1.  Logga in som en användare med åtkomst till sidan **arbetsyta för hantering av affärsdokument**.
2.  Öppna arbetsytan för **hantering av affärsdokument**.

    ![Arbetsyta för hantering av affärsdokument](./media/BDM-AddFldExcel-Workspace.png)

3.  I rutnätet väljer du mallen **fritextfaktura (Excel)**.
4.  Välj **ny mall** i det högra fönstret om du vill skapa en ny mall som baseras på den valda mallen.
5.  I fältet **rubrik** anger du **fritextfaktura (Excel) Contoso** som rubrik för den nya mallen.
6.  Välj **OK** för att bekräfta starten av redigeringsprocessen.

Sidan BDM-mallredigerare visas. Du kan använda Microsoft 365 för att redigera den valda mallen online i den inbäddade kontrollen.

![Sidan BDM-mallredigerare](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a>Lägga till etiketten för ett nytt fält i mallen

1.  På sidan BDM-mallredigerare, på Excel-menyfliken på fliken **Visa**, välj kryssrutan **Rubriker och stödlinjer** för den redigerbara Excel-mallen.

    ![Kryssrutorna rubriker och stödlinjer är markerade](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  Markera cellerna **E8:F8**.
3.  I Excel-menyfliksområdet på fliken **Start** välj **Sammanfoga och centrera** om du vill sammanfoga de markerade cellerna till en ny sammanfogad **E8:F8**-cell.
4.  I den sammanfogade cellen **E8:F8**, ange **URL**.
5.  Markera sammanfogad cell **E7:F7**, välj **Hämta format** och markera sedan sammanfogad cell **E8:F8** om du vill formatera den på samma sätt som den sammanfogade cellen **E7:F7**.

    ![Nytt fält har lagts till i mallen](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a>Formatera mallen till att reservera utrymme för ett nytt fält

1.  Välj sammanfogad cell **G8:H8** på sidan BDM mallredigerare.
2.  I Excel-menyfliksområdet på fliken **Start** välj **Sammanfoga och centrera** om du vill sammanfoga de markerade cellerna till en ny sammanfogad **G8:H8**-cell.
3.  Markera sammanfogad cell **G7:H7**, välj **Hämta format** och markera sedan sammanfogad cell **G8:H8** om du vill formatera den på samma sätt som den sammanfogade cellen **G7:H7**.

    ![Utrymme reserverat för det nya fältet](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  I fältet **Namn** välj **CompanyInfo**.

    Intervallet **CompanyInfo** för den aktuella Excel-mallen innehåller alla fält som används för att fylla rubriken för en genererad rapport med information om det aktuella företaget som säljare.

    ![CompanyInfo-intervall har valts](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a>Lägg till ett nytt fält till mallen

1.  På sidan **BDM-mallredigerare** i åtgärdsfönstret, välj **Visa format**.
2.  I fönstret **Mallstruktur** välj **Lägg till**.

    > [!NOTE]
    > Du måste justera avsnittet i den mall som du vill använda som ett nytt fält. Du har redan gjort denna justering genom att formatera sammanfogad cell **G8:H8**.

    ![Lägg till ett nytt fält till mallen](./media/BDM-AddFldExcel-AddCell.png)

3.  Välj **Excel\Cell** om du vill lägga till ett nytt fält som en cell i mallen.

    Du kan välja **Excel\intervall** om du vill lägga till ett nytt intervall i mallen. Det angivna intervallet kan innehålla flera celler. Du kan lägga till dessa celler senare.
    
    Observera att **CompanyInfo** väljs automatiskt i fönstret **mallstruktur**, eftersom det är den mest lämpliga överordnade komponenten i den aktuella mallstrukturlistan för det fält som du lägger till.
    
4.  I fältet **Excel-intervall** anger du **CompanyURL_Value**.
5.  Välj **OK**.

    ![CompanyURL_Value fält som lagts till i mallstrukturlistan](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  I fönstret **mallstruktur** väljer du ellipsknappen (...) och väljer **Visa bindningar**.

    ![Visa valda bindningar](./media/BDM-AddFldExcel-ShowBindings.png)

    I fönstret **mallstruktur** visas nu de datakällor som är tillgängliga i det underliggande ER-formatet.

7.  Välj **CompanyInfo_Value** som fältet som du vill binda till en datakälla för det underliggande ER-formatet.
8.  I avsnittet **Datakällor** i fönstret **Mallstruktur** expanderar du **Modell \> InvoiceBase \> CompanyInfo**.
9.  Under **CompanyInfo** väljer du artikeln **WebsiteURI**.

    ![Artikeln WebsiteURI har markerats](./media/BDM-AddFldExcel-BindURL.png)

10. Välj **bind**.
11. I fönstret **mallstruktur** väljer du **spara** och stänger sedan sidan BDM mallredigerare.

På arbetsytan **Hantering av affärsdokument** visar fliken **Mall** i det högra fönstret den uppdaterade mallen. I rutnätet observerar du att fältet **Status** för den redigerade mallen har ändrats till **Utkast** och fältet **Ändring** inte längre är tomt. Dessa ändringar anger att processen för redigering av den här mallen har startats.

![Redigerad mall på arbetsytan för hantering av affärsdokument](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a>Granska företagsinställningar

1.  Gå till **Organisationsadministration \> Organisationer \> Juridiska personer**.
2.  På snabbfliken **kontaktinformation** kontrollerar du att företags-URL:en har angetts.

![Företags-URL som angetts på sidan juridiska personer](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a>Generera affärsdokument för att testa den uppdaterade mallen

1.  I programmet, ändra företaget till **USMF** och gå till **Kundreskontra \> Fakturor \> Alla fritextfakturor**.
2.  Välj faktura **FTI-00000002** och välj sedan **Utskriftshantering**.
3.  I det vänstra fönstret expanderar du **Modul - kundreskontra \> Dokument \> Fritextfaktura**.
4.  Under **Fritextfaktura**, välj nivån **Originaldokument** för att ange omfånget med fakturor för bearbetning.
5.  I det högra fönstret, i fältet **rapportformat**, väljer du **fritextfaktura (Excel) Contoso**-mallen för angiven dokumentnivå.

    ![Mallen fritextfaktura (Excel) Contoso har valts](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  Tryck på **Esc** för att stänga den aktuella sidan.
7.  Välj **Skriv ut \> Markerade**.
8.  Hämta det genererade dokumentet och öppna det i Excel.

    ![Fritextfaktura i Excel](./media/BDM-AddFldExcel-PreviewReport.png)

Den modifierade mallen används för att generera fritextfakturarapporten för den valda artikeln. Om du vill analysera hur den här rapporten påverkas av de ändringar som du har gjort i mallen kan du köra den här rapporten i en programsession direkt efter att du har ändrat mallen i en annan programsession.

## <a name="related-links"></a>Relaterade länkar

[Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)

[Hantering av affärsdokument – översikt](er-business-document-management.md)

[Utforma en konfiguration för rapportgenerering i OPENXML-format](tasks/er-design-reports-openxml-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]