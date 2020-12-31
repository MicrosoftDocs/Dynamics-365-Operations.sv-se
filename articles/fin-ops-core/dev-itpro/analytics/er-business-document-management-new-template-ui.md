---
title: Nytt användargränssnitt för dokument i hantering av affärsdokument
description: I det här avsnittet finns information om hur du använder det nya användargränssnittet för funktionen för hantering av affärsdokument i ramverket elektroniska rapporter (ER).
author: v-anamir
manager: AnnBe
ms.date: 05/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 2cb6e0da4af07b9b8486bf1e5bda29523cbd08e9
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681362"
---
# <a name="new-document-user-interface-in-business-document-management"></a>Nytt användargränssnitt för dokument i hantering av affärsdokument

[!include [banner](../includes/banner.md)]

Hanteringen av affärsdokument gör det möjligt för affärsanvändare att redigera affärsdokumentmallar genom att använda en Microsoft 365-tjänst eller lämpligt Microsoft Office-skrivbordsprogram. Redigeringar kan omfatta designändringar eller nya distributioner, eller så kan användare lägga till platshållare för att inkludera ytterligare data utan att behöva ändra källkoden. Mer information om hur du arbetar med hantering av affärsdokument finns i [översikt över hantering av affärsdokument](er-business-document-management.md).

Användargränssnittet för det nya dokumentet är tydligare och bekvämare att använda. I området **affärsdokument** visas bara de mallar som är tillgängliga för den aktuella leverantören.

Med knappen **Nytt dokument** kan användare skapa och redigera en mall i formatkonfiguration för elektronisk rapportering (ER) som tillhandahålls av en annan leverantör. I exemplet i det här avsnittet är leverantören Microsoft.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Gör det nya dokumentgränssnittet tillgängligt i Hantering av affärsdokument

Om du vill kunna använda det nya dokumentgränssnittet i Hantering av affärsdokument måste du aktivera funktionen **Office-liknande gränssnittsupplevelser för hantering av affärsdokument** i arbetsytan **funktionshantering**.

Följ de här stegen för att aktivera funktionen för alla juridiska personer.

1. I arbetsytan **funktionshantering** på fliken **Ny** väljer du **Office-liknande gränssnittsupplevelser för hantering av affärsdokument** i listan.
2. Välj **Aktivera nu** om du vill aktivera den valda funktionen.
3. Uppdatera sidan för att komma åt den nya funktionen.

### <a name="edit-templates-that-are-owned-by-other-providers"></a>Redigera mallar som ägs av andra leverantörer

1. Markera **Nytt dokument** i arbetsytan **Hantering av affärsdokument**.

    ![Arbetsyta för hantering av affärsdokument](./media/BDM_overview_new_template1.png)

2. I dialogrutan väljer du det dokument som ska användas som mall och väljer sedan **Skapa dokument**.

    ![Dialogrutan affärsdokument](./media/BDM_overview_new_template2.png)

3. I den nya dialogrutan, i fältet **Rubrik** ändra rubriken efter önskemål. Rubriktexten kommer att användas som namn på den konfiguration för nytt ER-format som skapas automatiskt. Utkastet till den här konfigurationen (**Kopia av FTI-rapport för kund (GER)**) kommer att innehålla den redigerade mallen och kommer att användas för att köra detta ER-format för den aktuella användaren. Ursprungliga mallen från baskonfigurationen för ER-format för att köra det här ER-formatet för alla andra användare.
4. I fältet **Namn** ändrar du namnet på den första revisionen av den redigerbara mallen som ska skapas automatiskt.
5. I fältet **Kommentar** uppdatera kommentarerna för revisionen av den redigerbara mallen som automatiskt skapas.
6. Välj **OK** för att bekräfta starten av redigeringsprocessen.

    ![Dialogrutan skapa dokument](./media/BDM_overview_new_template3.png)

Knappen **Nytt dokument** används för att skapa och redigera en mall i formatkonfiguration för ER-format som tillhandahålls av en annan leverantör. I exemplet i det här avsnittet är leverantören Microsoft. När du klickar på **Nytt dokument** visas alla mallar som ägs av aktuella och andra leverantörer. När du har valt mallen kommer den att öppnas för redigering. Den redigerade mallen kommer sedan att lagras i en ny konfiguration för ER-format som skapas automatiskt.

Mer information finns i [översikt över hantering av affärsdokument](er-business-document-management.md).
