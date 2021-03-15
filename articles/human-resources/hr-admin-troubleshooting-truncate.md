---
title: Undvika att texten trunkeras i befattningshierarkin och exportera till Visio
description: Det här avsnittet beskriver hur du löser ett problem där namnen på personer och befattningar trunkeras när kunder visar befattningshierarkin i Microsoft Dynamics 365 Human Resources. Texttrunkering kan göra det svårt att ta en skärmbild eller skriva ut hierarkin.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0dc91d3165f14c165f75756dc63a3dc8f63149aa
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114286"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a>Undvika att texten trunkeras i befattningshierarkin och exportera till Visio

**Utleverans**

När en kund visar befattningshierarkin i Dynamics 365 Human Resources trunkeras namnen på individer och befattningar. Därför kan det vara svårt att ta en skärmbild eller att skriva ut och distribuera hierarkin.

![Befattningshierarki](media/position-h.png)

**Orsak**

Detta beteende är av design.

**Upplösning**

Tyvärr kan användare inte enkelt ändra textens storlek. Du kan exportera befattningshierarkin från Personal och sedan importera den till Microsoft Visio. Även om följande artikel skrevs för Microsoft Dynamics AX 2012, gäller processen fortfarande för Personal: [Exportera en befattningshierarki till Microsoft Visio](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).

Gör så här för att exportera till Visio.

1. I Personal, öppna listsidan **befattningar**.

    För att inkludera mer information i organisationsstrukturdiagrammet, lägg till fält i listan **Positioner** så att de blir tillgängliga när du använder guiden senare i den här proceduren.

2. I åtgärdsfönstret, välj knappen **Öppen i Microsoft Office** och klicka sedan på **Exportera till Excel**, välj **Befattningar**. Du kan också trycka på Ctrl+T.

    ![Exportera positionslistsidan till Excel](media/org-admin.png)

3. Spara Excel-filen som exporteras.

    ![Exportera till Excel-dialogruta](media/export-excel.png)

4. I Visio, välj **Visio – skapa ny** och välj mallkategorin **Företag**.

    ![Nytt diagram](media/new.png)

5. Välj **Guide för organisationsschema** och välj sedan **Skapa**.

    ![Dialogrutan Guide för organisationsschema](media/orgchart-wizard.png)

6. Välj **Information som redan sparats i en fil eller databas** och välj sedan **Nästa**.

    ![Organisationsschema 1](media/orgchart-wizard7.png)

7. Välj **En text, Org Plus (\*.txt), eller Excel-fil** och sedan **Nästa**.

    ![Organisationsschema 2](media/orgchart-wizard3.png)

8. Bläddra till den exporterade Excel-filen som innehåller befattningshierarkin och markera sedan **Nästa**.

    ![Organisationsschema 3](media/orgchart-wizard2.png)

9. Ange fältet **Namn** till **Befattning**, ange **Rapporterar till** till **Rapportera till befattning** och välj sedan **Nästa**.

    ![Organisationsschema 4](media/orgchart-wizard1.png)

10. Markera de fält som ska visas på varje nod och välj **Nästa**.

    ![Organisationsschema 5](media/orgchart-wizard5.png)

11. Lägg till kolumnen **Befattning** till listan **Formdatafält** och välj sedan **Nästa**.

    ![Organisationsschema 6](media/orgchart-wizard6.png)

12. Bilder är inte tillgängliga för tillfället. Därför på nästa sida välj **Nästa**.
13. Välj **Jag vill att guiden ska dela upp organisationsschemat över flera sidor**.

    ![Organisationsschema 7](media/orgchart-wizard4.png)

14. Välj **Slutför**.

    Om det finns befattningar som inte finns med i strukturen, uppmanas du att ta med dem i diagrammet.

Det diagram som skapas i Visio visar varje chef i ett separat kalkylblad.

Baserat på de fält som du valt att inkludera i diagrammet visar varje nod den lämpliga informationen när Visio-filen genereras.

![Hierarkidiagram](media/hierarchy.png)

**Ytterligare alternativ**

I Personal kanske du också använder arbetsytan **Personer** för att visa hierarkirelaterad information.


[!INCLUDE[footer-include](../includes/footer-banner.md)]