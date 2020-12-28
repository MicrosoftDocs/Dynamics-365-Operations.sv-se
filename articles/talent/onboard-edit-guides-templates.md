---
title: Redigera integrationsguider och mallar i Dynamics 365 Talent - Onboard
description: I det här avsnittet beskrivs hur du lägger till aktiviteter och annan information i integrationsguider och mallar i Microsoft Dynamics 365 Talent - Onboard.
author: andreabichsel
manager: ''
ms.date: 06/19/2019
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
ms.search.validFrom: 2019-06-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 291f7aefac61c26dfab81cfff28c1c6580d46de5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462607"
---
# <a name="edit-onboarding-guides-and-templates"></a>Redigera integrationsguider och mallar

[!include [banner](includes/banner.md)]

När du har skapat en integrationsguide eller mall i Microsoft Dynamics 365 Talent: Onboard måste du lägga till en introduktion, aktiviteter, kontakter och resurser. Onboard gör att du kan lägga till omfattande innehåll i dina integrationsguider, t.ex.:

- YouTube-videoklipp
- Microsoft Sway-presentationer
- Microsoft PowerApps-appar
- Microsoft Stream-videoklipp
- Microsoft Forms-formulär
- Iframes som innehåller webbinnehåll

## <a name="edit-introductions-or-activities-imported-from-a-template"></a>Redigera introduktioner eller aktiviteter som importerats från en mall

Om du skapar en integrationsguide från en mall, eller om du importerar aktiviteter från en mall till en annan, kommer du att märka en **lås**-knapp för de importerade aktiviteterna. Dessa kallas *hanterade aktiviteter*.

[![Hanterade aktiviteter](./media/onboard-edit-guide-managed-activities.png)](./media/onboard-edit-guide-managed-activities.png)

När du väljer en hanterad aktivitet kan du se källmallen överst i aktiviteten.

[![Källa för hanterad aktivitet](./media/onboard-edit-guide-managed-activity-source.png)](./media/onboard-edit-guide-managed-activity-source.png)

Om du redigerar en aktivitet i en mall, skickar Onboard ändringarna till alla mallar och ej skickade guider som baseras på mallen. Om du väljer en guide som inte har skickats och som är baserad på en mall som du har redigerat och sedan väljer fliken **aktiviteter** i guiden visas ett meddelande om att din guide har ändrats. Klicka på **OK** om du vill stänga meddelandet. 

[![Ändra meddelande](./media/onboard-edit-guide-change-notification.png)](./media/onboard-edit-guide-change-notification.png)

En svart prick visas bredvid de uppdaterade aktiviteterna.

[![Ändrad aktivitet](./media/onboard-edit-guide-changed-activity.png)](./media/onboard-edit-guide-changed-activity.png)

Du kan inte redigera hanterade aktiviteter utanför den ursprungliga mallen, förutom att lägga till en tilldelad, förfallodatum eller annan information i det högra avsnittet av aktiviteten.

Om du vill redigera en hanterad aktivitet, eller om du inte vill att en aktivitet ska ta emot uppdateringar från mallen den kommer från, väljer du **lås**-knappen för den aktiviteten. **Lås**-knappen döljs. Aktiviteten kommer inte längre att hanteras av den ursprungliga mallen och kommer inte längre att ta emot uppdateringar från den mallen. De uppdateringar du gör av en aktivitet påverkar inte den ursprungliga mallen.

Om du tar bort en aktivitet från en guide och skickar ändringarna från den guidens mall fortsätter aktiviteten att vara borttagen i guiden.

> [!NOTE]
> Kontakter och resurser hanteras inte av mallar. Utöver detta hanteras inte avsnitt, så om du lägger till eller redigerar ett avsnitt i en mall flyttas inte ändringarna till några guider eller mallar som använder den mallen.
> 
> Om du lägger till nya aktiviteter i en mall, flyttas de nya aktiviteterna till guider och mallar baserade på den mallen och de nya aktiviteterna visas högst upp.

## <a name="import-activities-from-another-template"></a>Importera aktiviteter från en annan mall

Du kan importera aktiviteter från en eller flera mallar till en guide eller en mall.

1. Välj den guide eller mall du vill redigera.

2. Välj fliken **Aktiviteter**.

3. Välj fliken **import** i avsnittet till höger.

   [![Importera aktiviteter](./media/onboard-edit-guide-import-activities.png)](./media/onboard-edit-guide-import-activities.png)

4. Om du vill förhandsgranska uppgifterna i en ny flik i webbläsaren, markerar du knappen **Öppna i ny flik** på en mall.

   [![Importera aktiviteter](./media/onboard-edit-guide-preview-activities.png)](./media/onboard-edit-guide-preview-activities.png)

5. Dra och släpp den önskade mallen till den plats i programguidens mall där du vill att aktiviteterna ska visas. Fortsätt redigera din guide eller mall.

De importerade aktiviteterna innehåller en **lås**-knapp, som anger att dessa aktiviteter hanteras av mallen som du importerade från. När du gör ändringar i den importerade mallen kommer dessa aktiviteter att uppdateras i mallen du importerade dem till. Ändringarna flyttas dock inte automatiskt till guider som skapats från mallen du importerade till.

## <a name="push-changes-from-a-template-to-other-templates-or-guides"></a>Skicka ändringar från en mall till andra mallar eller guider

Om du redigerar en mall som innehåller aktiviteter som används i andra mallar eller guider måste du utföra ändringarna om du vill att de ska visas i de andra mallarna eller guiderna.

Om du inte är säker på om din malls aktiviteter används i andra mallar eller guiderna väljer du fliken **Används i** för att visa var dessa aktiviteter förekommer.

   [![Visa guider och mallar som aktiviteter används i](./media/onboard-edit-guide-view-used-in.png)](./media/onboard-edit-guide-view-used-in.png)

Så här flyttar du dina ändringar:

1. Spara ändringarna genom att välja knappen **spara**. Om du inte gör det uppmanas du att spara ändringarna i nästa steg.

2. Välj **Skicka dessa ändringar**.

   
## <a name="add-or-edit-an-introduction"></a>Lägga till eller redigera en inledning

1. Ange en flik för **Introduktion**, ange en rubrik för guiden och ett öppningsmeddelande. Om du vill använda exempeltexten väljer du **Använd detta meddelande**.

    [![Fliken Introduktion i en Onboard-mall](./media/onboard-template-introduction.png)](./media/onboard-template-introduction.png)

2. Använd formateringsknappar om du vill skriva ut text som du behöver eller om du vill lägga till bilder eller länkar.
3. Spara arbetet genom att klicka på **Spara**.

## <a name="add-or-edit-activities"></a>Lägga till eller redigera aktiviteter

1. På fliken **aktiviteter** drar du objekt från höger till redigeringsområdet.
2. Om du vill organisera guiden i avsnitt drar du objektet **Nya avsnitt** till redigeringsområdet och anger ett namn och en valfri beskrivning av avsnittet.

    ![[Lägga till ett nytt avsnitt i en introduktionsguide eller mall](./media/onboard-edit-add-section.png)](./media/onboard-edit-add-section.png)

3. Om du vill lägga till aktiviteter för den nya anställningen drar du objektet **Ny aktivitet** till redigeringsområdet och anger ett namn och en beskrivning för aktiviteten.

    ![[Lägga till ett nytt aktivitet i en introduktionsguide eller mall](./media/onboard-edit-add-activity.png)](./media/onboard-edit-add-activity.png)

4. Lägga till omfattande innehåll i din integrationsguide:

    - Lägg till en YouTube-video genom att dra **YouTube**-objektet till redigeringsområdet, ange ett namn och en beskrivning för aktiviteten och ange URL för YouTube-videon.
    - Om du vill lägga till en Sway-presentation eller ett nyhetsbrev drar du **Sway**-objektet till redigeringsområdet, anger ett namn och en beskrivning för aktiviteten och anger den inbäddade webbadressen för Sway-presentationen eller nyhetsbrevet.
    - Om du vill lägga till en Microsoft Power Apps-app, dra **Power Apps**-objektet till redigeringsområdet, ange ett namn och en beskrivning för aktiviteten och välj antingen Power Apps-appen eller ange Power Apps app-ID.
    - Lägg till en Microsoft Stream-video genom att dra **Microsoft Stream**-objektet till redigeringsområdet, ange ett namn och en beskrivning för aktiviteten och ange URL för Microsoft Stream-videon.
    - Om du vill lägga till ett Microsoft Forms-formulär, dra **Microsoft Forms**-objektet till redigeringsområdet, ange ett namn och beskrivning för aktiviteten, ange URL-adressen för Microsoft Forms-formuläret och ange storleken på skärmområdet.
    - Om du vill lägga till en iframe som innehåller webbinnehåll, dra **Webbinnehåll (iframe)**-objektet till redigeringsområdet, ange ett namn och beskrivning för aktiviteten, ange URL-adressen för webbinnehållet och ange storleken på skärmområdet.

    ![[Lägga till omfattande innehåll till en introduktionsguide eller mall](./media/onboard-edit-add-rich-content.png)](./media/onboard-edit-add-rich-content.png)

2. Valfritt: tilldela aktiviteten till en specifik person eller roll i området till höger om varje aktivitet, Lägg till ett förfallodatum och en kontaktperson och tilldela en kategorifärg. När du tilldelar en aktivitet till en person eller roll skapas en uppgift för varje enskild person. Den här uppgiften visas på menyn **aktiviteter** i Onboard.

    [![Tilldela en aktivitet i en integrationsguide eller mall](./media/onboard-assign-activity.png)](./media/onboard-assign-activity.png)

3. Spara arbetet genom att klicka på **Spara**.

Om du vill ta bort en aktivitet eller ett avsnitt väljer du knappen **Ta bort** (papperskorgsymbolen) i det övre högra hörnet av aktiviteten eller avsnittet.

Om du vill ordna om aktiviteter och avsnitt drar du dem till en ny plats.

## <a name="add-or-edit-contacts"></a>Lägga till eller redigera

Du kan lägga till kontaktpersoner som kan hjälpa din nya anställning att lyckas från dag ett. Dessa kontakter kan vara rekryterare, medarbetare, integrationskompisar, mentorer, administratörer och supportpersonal.

1. På fliken **Kontakter**, välj **Ny kontakt**.
2. I dialogrutan **Lägg till teammedlemmar**, ange kontaktpersonens namn eller e-postadress, ange en kort beskrivning som förklarar hur kontaktpersonen kan hjälpa den nya anställningen och välj sedan **Lägg till**. 

    ![[Lägga till kontakter till en introduktionsguide eller mall](./media/onboard-edit-add-contact.png)](./media/onboard-edit-add-contact.png)

    Du kan också välja en eller flera kontakter under **förslag**.

3. Spara arbetet genom att klicka på **Spara**.

Om du vill ta bort en kontakt väljer du knappen **Ta bort** (papperskorgsymbolen) till höger om kontakten.

Om du vill redigera en kontakt väljer du knappen **Redigera** (pennsymbolen) till höger om kontakten.

## <a name="add-or-edit-resources"></a>Lägga till eller redigera resurser

Du kan lägga till användbara filer, kartor och länkar till avsnittet **resurser** i din integrationsguide.

1. På fliken **Resurser**, välj **Ny resurs**.
2. Gör något av följande:

    - Om du vill lägga till en fil väljer du fliken **Fil** och drar filen till det angivna området. (Du kan också klicka någonstans i området för att bläddra efter filen på din dator eller välja **bläddra i OneDrive**.) Ange ett namn på filen och välj sedan **Lägg till**.
    - Om du vill lägga till en länk väljer väljer du fliken **Länk** och anger ett namn och en adress för länken och väljer sedan **Lägg till**.
    - Om du vill lägga till en karta väljer väljer du fliken **karta** och anger ett namn och en adress för kartan och väljer sedan **Lägg till**. Onboard kommer att innehålla en karta över den adress som du anger.

    ![[Lägga till en resurs i en introduktionsguide eller mall](./media/onboard-edit-add-resource.png)](./media/onboard-edit-add-resource.png)

3. Spara arbetet genom att klicka på **Spara**.

Om du vill ta bort en resurs väljer du knappen **Ta bort** (papperskorgsymbolen) till höger om resursen.

Om du vill redigera en kontakt väljer du knappen **Redigera** (pennsymbolen) till höger om resursen.

## <a name="next-steps"></a>Nästa steg

- [Dela innehåll med andra deltagare](./onboard-share-template.md)
- [Visa status för uppgifter och integration av medarbetare](./onboard-view-status.md)
- [Skapa anställningsteam i Onboard](./onboard-create-team.md)

### <a name="see-also"></a>Se även

- [Prova eller köp appen Onboard](https://dynamics.microsoft.com/talent/onboard/)
- [Nyheter och ändringar i Dynamics 365 Talent](./whats-new.md)
- [Utgivningsplaner](https://docs.microsoft.com/business-applications-release-notes/index)
- [Få support för Microsoft Dynamics 365 Talent](./talent-support.md)
