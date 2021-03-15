---
title: Projektinställningar för arbetsorder
description: Det här avsnittet innehåller förklaringar av projektinställningar för arbetsorder i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderProjectSetup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 031e61549474745360ac00f9a66bef7a9dbaaf96
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021564"
---
# <a name="work-order-project-setup"></a>Projektinställningar för arbetsorder

[!include [banner](../../includes/banner.md)]

 

I modulen **Tillgångshantering** krävs en projektrelation för varje arbetsorderjobb. Projektet som är kopplat till ett arbetsorderjobb gör det möjligt att spåra kostnader för olika projekt som är relaterade till Tillgångshantering, t.ex. interna underhållsprojekt, servicehanteringsprojekt och investeringsprojekt. 

## <a name="project-setup-for-a-work-order-job"></a>Projektinställningar för ett arbetsorderjobb

När du skapar ett arbetsorderjobb på en arbetsorder, kan projektinställningarna i modulen **Projekthantering och redovisning** och inställningarna för arbetsorderprojekt i modulen **Tillgångshantering** bestämma hur projekt kan användas för kostnadskontroll på tillgången som valts för arbetsorderjobbet. I det här avsnittet beskrivs följande delar av projektinställningarna som används för en arbetsorder: det överordnade projektet (projekt-ID), projekttyp, projektaktiviteter och ekonomiska dimensioner:

- När du skapar ett arbetsorderjobb på en arbetsorder, skapas automatiskt ett unikt projekt-ID och en relaterad projektaktivitet för det. Men om flera arbetsorderjobb på en arbetsorder innehåller samma till gång används samma projekt-ID för dem. Med andra ord skapas ett projekt-ID för varje till gång på en arbetsorder.

    - Det överordnade projektet (projekt-ID) för ett arbetsorderjobb finns i inställningen för överordnat projekt. (Mer information om inställning av överordnade projekt finns i nästa avsnitt.) Om du till exempel associerar en kund eller en funktionsplats med ett specifikt överordnat projekt, används det överordnade projektet varje gång du skapar arbetsorder för den kunden eller den funktionsplatsen. Om du inte relaterar ett visst projekt-ID till t.ex. en funktionsplats, används nästa relevanta överordnade projekt i inställningarna för arbetsorderprojektet.
    - En projekttyp krävs för varje projekt-ID. Projekttypen finns under inställningen av projektgruppsinställningen. (Mer information om inställningar för projektgrupper finns i nästa avsnitt.) Om det inte finns någon matchning i projektgruppsinställningen används projektgruppsinställningen för det överordnade projektet.
    - Inställningarna för att kräva att projektaktiviteter på prognoser och journaler kopieras från det överordnade projektet till arbetsorderprojektet. Om alternativen **Timme**, **Utgift** och **Artikel** är inställda på **Ja** för projektet som används som ett överordnat projekt är en projektaktivitet obligatorisk för prognoser och journaler. (Du kommer åt dessa alternativ genom att välja **Projekthantering och redovisning** \> **Projekt** \> **Alla projekt**, och sedan välja projektet som används som överordnat projekt. Alternativen finns i avsnittet **Kräv aktivitet för journaler** på snabbfliken **Inställningar**.)

- Ekonomiska dimensioner kopieras från till gången och kopplas ihop med det överordnade projektet.

I nästa avsnitt förklaras hur du ställer in överordnade projekt och projektgrupper. Överordnat projekt och överordnade grupper används för att kontrollera arbetsorder. De används också för rapportering om arbetsorder.

## <a name="set-up-work-order-projects"></a>Ställa in arbetsorderprojekt

Innan du börjar skapa arbetsorder måste du skapa arbetsorderprojekt. Sidan **Projektinställningar för arbetsorder** (**Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Projektinställningar**) har två flikar: **Överordnat projekt** och **Projektgrupp**.

På fliken **Överordnat projekt** kan du ställa in projektrelationer som kan användas om inget projekt har ställts in för den tillgång som valts för arbetsorderjobbet. Det är inte obligatoriskt att konfigurera ett överordnat projekt om ditt företag använder tillgångsprojekt. Det är bara relevant om du vill använda arbetsorderprojekt i stället för tillgångsprojekt. I så fall måste du ställa in minst ett överordnat projekt.

På fliken **Projekt grupp** kan du ställa in projektgrupper som kan associeras med arbetsordertyper, tillgångstyper och tillgångar.

Projektgrupper kan användas för att skapa specifika kategorier (grupper) som används för kostnadskontroll. Genom att t.ex. skapa projektgrupper för specifika tillgångstyper eller arbetsordertyper kan du utföra detaljerad spårning av underhållskostnader per typ.

Projektgrupper är inte obligatoriska. Om du inte ställer in projektgrupper används det överordnade projektet för att bestämma projektgruppen och ett underordnat projekt skapas från det överordnade projektets projektgrupp.

Inställningen möjliggör fullständig integration med modulen **Projekthantering och redovisning**. Därför kan du spåra kostnaderna som är relaterade till arbetsorder i de relaterade projekten. I följande procedur beskrivs inställningarna för arbetsorderprojekt.

1. Välj **Tillgångshantering** \> **Inställningar** \> **Arbetsorder** \> **Projektinställningar**.
2. På fliken **Överordnat projekt** väljer du **Lägg till**.
3. I fälten **Arbetsordertyp**, **Funktionsplats**, **Tillgångstyp** och **Tillgång** väljer du värden. För varje rad som du lägger till kan du bara ange ett fält eller flera fält. Antalet fält som du anger bestämmer vilken kombination som används när ett projekt-ID väljs i Tillgångshantering. 

    Om du väljer en funktionsplats inkluderas automatiskt underordnade platser. Om du väljer en till gång kan du skapa fler inställningsrader för arbetsorderprojekt för samma till gång, men du kan välja olika projekt för den tillgången.

4. I fältet **Projekt-ID**, välj det projekt som ska vara relaterat till inställningen som du skapade i steg 3.
5. Om projektinställningarna bara ska gälla under en begränsad period väljer du ett slutdatum i fältet **Slutdatum**. Annars väljer du **Inget**.

    Som standard är startdatumet det datum då du lägger till arbetsorderprojektet på sidan. Det styrs av fältet **Giltig från**, som är dolt som standard. Om du vill visa fältet **Giltig från** väljer du **Visa** \> **Allt**. Du kan sedan använda fältet **Giltig från** tillsammans med fältet **Slutdatum** för att ange en begränsad giltighetsperiod för arbetsorderprojektet.

    ![Sidan Projektinställningar för arbetsorder](media/17-setup-for-work-orders.png)

6. På fliken **Projektgrupp** väljer du **Lägg till**.
7. I fältet **arbetsordertyp** väljer du en arbetsorder.
8. Om du vill att projektgruppsassociationen ska vara mer specifik väljer du en tillgångstyp i fältet **Tillgångstyp** eller en tillgång i fältet **Tillgång**.
9. I fältet **Projektgrupp** väljer du den projektgrupp som ska vara relaterad till arbetsordertypen. En arbetsordertyp med namnet **Förebyggande underhåll** kan till exempel associeras med en projektgrupp som har namnet **Förebyggande underh** eller **Internt**. Alternativt kan en arbetsordertyp **Investering** som används för arbetsorder som är relaterade till investeringar och anläggningstillgångar associeras med en projektgrupp med namnet **Investera** eller **Investering**.
10. Välj **Spara**.

![Sidan Projektinställningar för arbetsorder, Lägg till arbetsorder](media/18-setup-for-work-orders.png)

> [!NOTE]
> Varje gång en arbetsorderrad skapas söker Tillgångshantering efter en projektgrupp som ska relateras till jobbprojektet för arbetsordern. Sökningen baseras på inställningarna som beskrivs i det här avsnittet. Varje projektgrupp har en relaterad projekttyp. Projekt grupper som har projekttypen **Tid och material** eller **Fastpris** är endast giltiga för tillgångar som är relaterade till ett kundkonto.
>
> När det tillgängliga arbetsorderprojektet eller projektgruppen väljs i systemet för överordnade projekt och projekt grupper, baseras valet på de poster som du skapade med hjälp av föregående procedur. Tillgångshantering går igenom poster som är relaterade till arbetsorderprojektet för att söka efter en eventuell matchning. Den kontrollerar alltid den mest specifika kombinationen först. Med andra ord, för arbetsorderns överordnade projekt söker Tillgångshantering först efter en möjlig matchning för fältet **Tillgång**. Om ingen matchning hittas söker den efter en matchning för fältet **Tillgångstyp**. Om ingen matchning hittas söker den efter en matchning för fältet **Funktionsplats** och så vidare. Som du kan se i layouten på sidan **Projektinställningar för arbetsorder** innebär detta att, för att hitta den mest specifika kombinationen, kontrollerar Tillgångshantering varje post från höger till vänster för en matchning. Om det inte finns någon matchning används den standardpost där endast ett projekt-ID har valts. Du hittar den relaterade projektgruppen på samma sätt. Tillgångshantering kontrollerar först en möjlig matchning för fältet **Tillgång**, sedan fältet **Tillgångstyp** och sedan fältet **Arbetsordertyp**. Om det inte finns någon matchning används den standardpost där endast en projektgrupp har valts.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]