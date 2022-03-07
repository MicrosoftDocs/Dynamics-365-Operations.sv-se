---
title: Uppdatera strukturen för en affärsdokumentmall
description: I det här ämnet beskrivs hur du uppdaterar strukturen för en affärsdokumentmall med hjälp av funktionen för hantering av affärsdokument.
author: NickSelin
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 2f57e3f3a84a6e767755c69074bc194e90793e6edd79d0e07ae7449d45ec7539
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6775296"
---
# <a name="update-the-structure-of-a-business-document-template"></a>Uppdatera strukturen för en affärsdokumentmall 

[!include[banner](../includes/banner.md)]

I fönstret **Mallstruktur** i mallredigeraren för [Hantering av affärsdokument](er-business-document-management.md) kan du ändra en affärsdokumentmall genom att [lägga till nya fält](er-bdm-add-field-to-excel-template.md) i en mall i Microsoft Excel. Mallens struktur uppdateras sedan automatiskt i Dynamics 365 Finance för att återspegla ändringarna som du gjorde i fönstret **Mallstruktur**.

Du kan också ändra en mall genom att använda online funktionerna i Office 365. Du kan till exempel lägga till ett nytt namngivet objekt, som en bild eller form, i det redigerbara kalkylbladet. I det här fallet uppdateras inte mallens struktur automatiskt i Finance och den post du har lagt till visas inte i fönstret **Mallstruktur**. Uppdatera mallstrukturen manuellt i Finance genom att markera **Uppdatera struktur** på sidan för att redigera mallar.

För mer information om den här funktionen slutför du följande exempel.

## <a name="example-update-the-structure-of-a-business-document-template"></a>Exempel: Uppdatera strukturen för en affärsdokumentmall

Det här exemplet visar hur en systemadministratör kan uppdatera strukturen för en affärsdokumentmall i Finans när mallen har ändrats i Office Online. I följande avsnitt beskrivs de steg som ingår.

### <a name="prepare-a-business-document-template-for-editing"></a>Förbereda en affärsdokumentmall för redigering

Slutför följande procedurer i [Översikt över hantering av affärsdokument](er-business-document-management.md).

1. [Konfigurera ER-parametrar](er-business-document-management.md#configure-er-parameters)
2. [Importera ER-lösningar](er-business-document-management.md#import-er-solutions)
3. [Aktivera hantering av affärsdokument](er-business-document-management.md#enable-business-document-management)
4. [Konfigurera parametrar](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a>Redigera en affärsdokumentmall

1. Markera **Nytt dokument** i arbetsytan **Hantering av affärsdokument**.
2. På sidan **Skapa en ny mall** väljer du mallen **Fritextfaktura (ER-exempel)(Excel)**.
3. Välj **Skapa dokument**.
4. I fältet **Titel** anger du **FTI-exempel Litware**.
5. Skapa en ny mall genom att välja **OK**.

    > [!NOTE]
    > Om du inte redan har loggat in på Office Online [dirigeras du om till Office 365-inloggningssidan](er-business-document-management.md#frequently-asked-questions). Om du vill återgå till Finance-miljön väljer du knappen **Tillbaka** i webbläsaren.

    Den nya mallen öppnas för redigering i den inbäddade kontrollen i Excel Online på sidan för att redigera mall.

[![Börja redigera en affärsdokumentmall med arbetsytan för hantering av affärsdokument.](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)

### <a name="review-the-current-structure-of-the-editable-template"></a>Granska den redigerbara mallens aktuella struktur

1. I Excel Online, i menyfliken, på fliken **Visa** i gruppen **Visa** väljer du **Rutnät**.
2. Markera rektangeln ovanför mallrubriken i den redigerbara mallen. Den här rektangeln är en bild som heter **rptHeaderCompLogo**.
3. Om fönstret **Mallstruktur** är dolt väljer du **Visa struktur**.
4. I fönstret **Mallstruktur** expanderar du **Rapport \> Faktura \> rptHeader \> rptHeaderPart1**.
5. Observera att posten **rptHeaderCompLogo** i mallstrukturen i Finance, presenteras underordnad post till **Rapport \> Faktura \> rptHeader \> rptHeaderPart1**.

[![Granska den aktuella strukturen för en redigerbar mall med arbetsytan för hantering av affärsdokument.](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a>Uppdatera strukturen för en affärsdokumentmall genom att radera en bild

1. Markera bilden **rptHeaderCompLogo** i den redigerbara mallen i Excel Online .
2. Gör något av följande för att radera den markerade bilden från den redigerbara mallen:

    - Välj tangenten **Delete** på tangentbordet.
    - Markera och håll (eller högerklicka på) bilden och välj sedan **Klipp ut**.

    > [!NOTE]
    > **RptHeaderCompLogo**-posten finns fortfarande i mallstrukturen i Finance, även om bilden inte längre ingår i Excel-mallen.

3. Välj **Uppdatera struktur** för att synkronisera strukturen för den redigerbara mallen i Excel och Finance.
4. I fönstret **Mallstruktur** expanderar du **Rapport \> Faktura \> rptHeader \> rptHeaderPart1**.
5. Observera att posten **rptHeaderCompLogo** inte längre ingår i mallstrukturen i Finance.

[![Radera en bild från en affärsdokumentmall med arbetsytan för hantering av affärsdokument.](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a>Uppdatera strukturen för en affärsdokumentmall genom att lägga till en bild

1. I Excel Online, i menyfliken, på fliken **Infoga** i gruppen **Illustrationer** väljer du **Bild**.
2. Välj **Välj fil**, bläddra till den bild som du vill lägga till, markera den och välj sedan **OK**.
3. Välj **Infoga**.
4. Flytta den nya bilden till rätt plats. Som standard namnger Excel bilden. Exempelvis kan bilden få namnet **Bild 2**.
5. Välj **Uppdatera struktur** för att synkronisera strukturen för den redigerbara mallen i Excel och Finance.
6. I fönstret **Mallstruktur** expanderar du **Rapport \> Faktura \> rptHeader \> rptHeaderPart1**.
7. Observera att den nya bilden nu ingår som en post i mallstrukturen i Finance.

[![Lägg till en bild i en affärsdokumentmall med arbetsytan för hantering av affärsdokument.](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)

## <a name="related-links"></a>Relaterade länkar

[Översikt över elektronisk rapportering (ER)](general-electronic-reporting.md)

[Hantering av affärsdokument – översikt](er-business-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]