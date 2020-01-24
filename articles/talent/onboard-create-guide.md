---
title: Skapa och skicka en integrationsguide genom att använda Dynamics 365 Talent - Onboard
description: Det här avsnittet beskriver hur du använder Microsoft Dynamics 365 Talent - Onboard-appen för att skapa integrationsguide för dina nyanställda. Denna uppgift är ett viktigt första steg i en HR-strategi (HCM) för anställningsdag till pension.
author: andreabichsel
manager: ''
ms.date: 05/02/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2019-05-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 2371d86165390503312c2848842acf4745a8ed7a
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898258"
---
# <a name="create-and-send-an-onboarding-guide"></a>Skapa och skicka en integrationsguide.

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Talent: Onboard låter dig skapa integrationsguider från mallar som du själv har skapat, från mallar som är tillgängliga i ett galleri eller från grunden.

När du har skapat en integrationsguiden kan du skicka den till en ny anställning. Du kan också skicka den till flera nyanställda som du anger i en Microsoft Excel-fil som du hämtar från Onboard-appen.

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-a-single-new-hire"></a>Skapa en introduktionsguide från en mall och skicka den till en enda ny anställningsmanual

1. Välj **mallar** i menyn till vänster.
2. Under **Mina mallar**väljer du den mall som du vill konfigurera som en integrationsguide för den nyanställda.
3. Redigera mallen som du önskar. Se till att spara ditt arbete regelbundet.
4. När du är klar med redigeringen av mallen väljer du **skapa guide**.

    [![Skapa en integrationsguide från mallen.](./media/onboard-create-guide.png)](./media/onboard-create-guide.png)

5. I fönstret **Skapa en guide** under **Vem introducerar du** anger du den nyanställdas namn eller e-postadressen. Om den nyanställda inte finns i systemet ännu väljer du **Lägg till nu** och anger medarbetarens information.

    ![[Ange information för introduktionsguiden](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

6. Under **När börjar de** väljer du ett startdatum.
7. Om integrationsguiden ska skickas automatiskt till den nyanställa på ett visst datum, se till att alternativet **Schemalägg ett automatiskt utskicksdatum** är aktiverat och välj sedan automatiskt utskicksdatum. Om du vill skicka guiden omedelbart stänger du av alternativet **Schemalägg ett automatiskt utskicksdatum**.
8. Välj **Klar**.
9. När du är klar med redigeringen av integrationsguiden väljer du **Skicka** i det övre högra hörnet. Gör sedan något av följande:

    - Om du vill skicka den nyanställda en länk till integrationsguiden väljer du **Kopiera en länk** och väljer sedan **kopiera**.
    - Om du vill anpassa e-postmeddelandet för integrationsguiden innan du skickar det väljer du **Anpassa e-postmeddelandet innan du skickar det**, välj sedan **Nästa**, anpassa e-postmeddelandet som du önskar och välj **skicka**.
    - Om du vill skicka e-postmeddelandet utan att anpassa det väljer du **Nästa** och sedan **skicka**.

## <a name="create-an-onboarding-guide-from-a-template-and-send-it-to-multiple-new-hires"></a>Skapa en introduktionsguide från en mall och skicka den till flera nya anställda

Onboard låter dig skicka en integrationsguiden till flera nyanställda samtidigt.

1. Välj **mallar** i menyn till vänster.
2. Under **Mina mallar**väljer du den mall som du vill konfigurera som en integrationsguide för den nyanställda.
3. Redigera mallen som du önskar. Se till att spara ditt arbete regelbundet.
4. När du är klar med redigeringen av mallen väljer du **skapa guide**.
5. I fönstret **skapa en guide** väljer du **Behöver du introducera flera personer på samma gång**.

    [![Skapa en integrationsguide för flera nya anställda](./media/onboard-send-guide-multiple-people.png)](./media/onboard-send-guide-multiple-people.png)

6. Välj **mall för nyanställda**.
7. När .xlsx-filen har hämtats väljer du **öppna**, anger medarbetarens information i Excel-arbetsboken och sparar arbetsboken.

    [![Hämtar Excel-mallen för att skicka integrationsguiden till flera nya anställda](./media/onboard-send-guide-download-spreadsheet.png)](./media/onboard-send-guide-download-spreadsheet.png)

    > [!NOTE]
    > Innan du kan redigera arbetsboken måste du välja **Aktivera redigering** i Excel.
    > 
    > [![Aktivera redigering](./media/onboard-send-guide-enable-editing.png)](./media/onboard-send-guide-enable-editing.png)

8. Dra Excel-arbetsboken till det angivna området i fönstret **skapa flera guider**, eller klicka var som helst i området om du vill bläddra efter filen på din dator.

    [![Dra den redigerade arbetsboken](./media/onboard-send-guide-drag-spreadsheet.png)](./media/onboard-send-guide-drag-spreadsheet.png)

9. När du är klar med redigeringen av integrationsguiden väljer du **Skicka** i det övre högra hörnet. Gör sedan något av följande:

    - Om du vill skicka den nyanställda en länk till integrationsguiden väljer du **Kopiera en länk** och väljer sedan **kopiera**.
    - Om du vill anpassa e-postmeddelandet för integrationsguiden innan du skickar det väljer du **Anpassa e-postmeddelandet innan du skickar det**, välj sedan **Nästa**, anpassa e-postmeddelandet som du önskar och välj **skicka**.
    - Om du vill skicka e-postmeddelandet utan att anpassa det väljer du **Nästa** och sedan **skicka**.

## <a name="create-a-guide-without-using-a-template"></a>Skapa en guide utan att använda en mall

Du behöver inte alltid skapa en guide från en mall. Om du vill kan du skapa en guide från början i stället.

1. På den vänstra menyn väljer du **guider** och klickar sedan på knappen **Lägg till** (plus tecknet \[**+**\]).
2. I fönstret **Skapa en guide** under **Vem introducerar du** anger du den nyanställdas namn eller e-postadressen. Om den nyanställda inte finns i systemet ännu väljer du **Lägg till nu** och anger medarbetarens information.

    ![[Ange information för introduktionsguiden](./media/onboard-create-a-guide-window.png)](./media/onboard-create-a-guide-window.png)

3. Under **När börjar de** väljer du ett startdatum.
4. Om integrationsguiden ska skickas automatiskt till den nyanställa på ett visst datum, se till att alternativet **Schemalägg ett automatiskt utskicksdatum** är aktiverat och välj sedan automatiskt utskicksdatum. Om du vill skicka guiden omedelbart stänger du av alternativet **Schemalägg ett automatiskt utskicksdatum**.
5. Välj **Klar**.

## <a name="save-a-guide-as-a-template"></a>Spara en guide som en mall.

Du kan spara en integrationsguiden som en mall. På det här sättet kan du spara tid när du senare måste skapa fler integrationsguider.

1. Välj **guider** i menyn till vänster.
2. Välj knappen **Mer** (ellipsen \[**...**\]) för den guide som du vill skapa en mall från och välj **Spara som mall**.

    ![[Spara en integrationsguiden som en mall](./media/onboard-save-guide-as-template.png)](./media/onboard-save-guide-as-template.png)

3. I fönstret **Spara som en ny mall** anger du ett namn för din nya mall och väljer sedan **Spara**.

## <a name="next-steps"></a>Nästa steg

- [Redigera integrationsguider och mallar](./onboard-edit-guides-templates.md)
- [Dela innehåll med andra deltagare](./onboard-share-template.md)
- [Visa status för uppgifter och integration av medarbetare](./onboard-view-status.md)
- [Skapa anställningsteam i Onboard](./onboard-create-team.md)

### <a name="see-also"></a>Se även

- [Prova eller köp appen Onboard](https://dynamics.microsoft.com/talent/onboard/)
- [Nyheter och ändringar i Dynamics 365 Talent](./whats-new.md)
- [Utgivningsplaner](https://docs.microsoft.com/business-applications-release-notes/index)
- [Få support för Microsoft Dynamics 365 Talent](./talent-support.md)
