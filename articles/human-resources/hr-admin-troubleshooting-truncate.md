---
title: Undvika att texten trunkeras i befattningshierarkin och exportera till Visio
description: Detta ämne förklarar hur du löser ett problem där namnen på personer och befattningar trunkeras i befattningshierarkin i Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 3663f5689fc0109caad01a285185f9f4ffa6fcca
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865394"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a>Undvika att texten trunkeras i befattningshierarkin och exportera till Visio


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Utleverans**

När en kund visar befattningshierarkin i Dynamics 365 Human Resources trunkeras namnen på individer och befattningar. Därför kan det vara svårt att ta en skärmbild eller att skriva ut och distribuera hierarkin.

![Befattningshierarki.](media/position-h.png)

**Orsak**

Detta beteende är av design.

**Lösning**

Tyvärr kan användare inte enkelt ändra textens storlek. Du kan exportera befattningshierarkin från Personal och sedan importera den till Microsoft Visio. Även om följande artikel skrevs för Microsoft Dynamics AX 2012, gäller processen fortfarande för Personal: [Exportera en befattningshierarki till Microsoft Visio](/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).

Gör så här för att exportera till Visio.

1. I Personal, öppna listsidan **befattningar**.

    För att inkludera mer information i strukturdiagrammet för organisationen lägger du till fält i listan **Positioner** så att dessa blir tillgängliga när du använder **Guide för Organisationsschema** senare i den här proceduren.

2. I åtgärdsfönstret, välj knappen **Öppen i Microsoft Office** och klicka sedan på **Exportera till Excel**, välj **Befattningar**. Du kan också trycka på Ctrl+T.

    ![Exportera befattningslistsidan till Excel.](media/org-admin.png)

3. Spara Excel-filen som exporteras.

    ![Exportera till Excel-dialogruta.](media/export-excel.png)

4. I Visio, välj **Visio – skapa ny** och välj mallkategorin **Företag**.

    ![Nytt diagram.](media/new.png)

5. Välj **Guide för organisationsschema** och välj sedan **Skapa**.

    ![Dialogrutan Guide för organisationsschema.](media/orgchart-wizard.png)

6. Välj **Information som redan sparats i en fil eller databas** och välj sedan **Nästa**.

    ![Guide för Organisationsschema 1.](media/orgchart-wizard7.png)

7. Välj **En text, Org Plus (\*.txt), eller Excel-fil** och sedan **Nästa**.

    ![Guide för Organisationsschema 2.](media/orgchart-wizard3.png)

8. Bläddra till den exporterade Excel-filen som innehåller befattningshierarkin och markera sedan **Nästa**.

    ![Guide för Organisationsschema 3.](media/orgchart-wizard2.png)

9. Ange fältet **Namn** till **Befattning**, ange **Rapporterar till** till **Rapportera till befattning** och välj sedan **Nästa**.

    ![Guide för Organisationsschema 4.](media/orgchart-wizard1.png)

10. Markera de fält som ska visas på varje nod och välj **Nästa**.

    ![Guide för Organisationsschema 5.](media/orgchart-wizard5.png)

11. Lägg till kolumnen **Befattning** till listan **Formdatafält** och välj sedan **Nästa**.

    ![Guide för Organisationsschema 6.](media/orgchart-wizard6.png)

12. Bilder är inte tillgängliga för tillfället. Därför på nästa sida välj **Nästa**.
13. Välj **Jag vill att guiden ska dela upp organisationsschemat över flera sidor**.

    ![Guide för Organisationsschema 7.](media/orgchart-wizard4.png)

14. Välj **Slutför**.

    Om det finns befattningar som inte finns med i strukturen, uppmanas du att ta med dem i diagrammet.

Det diagram som skapas i Visio visar varje chef i ett separat kalkylblad.

Baserat på de fält som du valt att inkludera i diagrammet visar varje nod den lämpliga informationen när Visio-filen genereras.

![Hierarkidiagram.](media/hierarchy.png)

**Ytterligare alternativ**

I Personal kanske du också använder arbetsytan **Personer** för att visa hierarkirelaterad information.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
