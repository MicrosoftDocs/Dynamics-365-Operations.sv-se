---
title: Arbeta med fragment
description: I det här avsnittet beskrivs varför, när och hur du ska använda fragment i Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1fa55ab83562983273768895db61032ec7199fa6
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793955"
---
# <a name="work-with-fragments"></a>Arbeta med fragment 

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs varför, när och hur du ska använda fragment i Microsoft Dynamics 365 Commerce.

Fragment gör det möjligt att använda en central redigeringsupplevelse för modulkonfigurationer som måste återanvändas på hela din webbplats. Sidhuvuden, sidfötter och banderoller är ofta konfigurerade som fragment, eftersom de delas på många sidor. Du kan betrakta fragment som miniatyrer av webbsidor som kan infogas på andra sidor på webbplatsen. Fragment har sin egen livscykel. Det innebär att de skapas, refereras, uppdateras och tas bort som oberoende enheter i redigeringsverktygen.

När fragment har konfigurerats kan de användas där moduler kan användas i webbplatsstrukturen. Det går att referera till fragment på sidor, i layouter, i mallar och i andra fragment.

> [!NOTE]
> Fragment kan kapslas upp till sju nivåer djup inuti andra fragment.

Om du till exempel vill marknadsföra en säsongshändelse på många sidor på webbplatsen kan du använda ett fragment. Det första steget i processen med att skapa ett nytt fragment är att välja vilken typ av modul du vill starta från. I det här exemplet kan du skapa avsnittet från en fokusmodul.

> [!NOTE]
> Fragment kan skapas med alla typer av moduler.

Du kan sedan konfigurera fokusfragment med ditt specifika säljinnehåll. Du kan också lokalisera den efter behov. Det nya fristående fokusfragmentet kan sedan förbrukas som en förkonfigurerad modul på hela din webbplats. Du kan enkelt lägga till det i mallar, specifika sidor eller till andra fragment som kan innehålla fokusmoduler.

Alla platser där fragmenten läggs till är referenser till det centrala fokusfragment som du har skapat. Om du publicerar ändringar i avsnittet visas dessa direkt på alla platser där fragmentet refereras på webbplatsen. Därför utgör fragmenten ett kraftfullt och effektivt sätt att återanvända och centralt hantera konfigurationer på en webbplats. Genom att effektivt använda dem kan du öka flexibiliteten och minska den kostnad som är kopplad till hantering av webbplatsens innehåll.

Följande bild visar hur fragment kan användas för att centralisera redigering av konfigurationer för delade moduler på en näthandelssajt.

![EN bild visar hur fragment kan användas för att centralisera redigering av konfigurationer för delade moduler på en näthandelssajt.](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a>Skapa ett fragment

Du kan antingen skapa ett nytt fragment eller spara en befintlig modul som ett fragment.

### <a name="save-an-existing-module-configuration-as-a-fragment"></a>Spara en befintlig modulkonfiguration som ett fragment

Om du vill konvertera en tidigare konfigurerad modul till ett återanvändbart fragment i Commerce webbplatsskaparen följer du stegen nedan.

1. Öppna en sida eller mall som innehåller modulen som du vill konvertera till ett fragment.
1. Markera den tidigare konfigurerade modulen i dispositionsrutan till vänster eller direkt i visuell sidskapare.
1. Markera tre punkter (**...**) bredvid modulens namn i antingen dispositionsfönstret eller i den markerade modulens verktygsfält i visuell sidskapare. 
1. Välj **dela som fragment**. 
1. I dialogrutan **Spara som fragment** anger du namnet för fragmentet.
1. Välj **OK** om du vill spara modulens konfiguration som ett fragment som kan läggas till på andra sidor.
<!-- The following image shows how to save a module configuration as a fragment.-->
<!--![A screen capture of how to save a module configuration as a fragment](./media/save-as-fragment.png)-->

### <a name="create-a-new-fragment"></a>Skapa ett nytt fragment

För att skapa ett nytt fragment i Commerce webbplatsskaparen.

1. I navigeringsfönstret till vänster, välj **fragment**.
1. Välj **Ny**. En dialogruta visas **Nya fragment** med alla tillgängliga modultyper. Som tidigare nämnts kan fragment skapas från alla typer av moduler.
1. Välj en modultyp för fragmentet.

<!-- The following image shows where to create a new fragment.-->
<!-- ![A screen capture of where to create a new fragment](./media/fragment-nav-menu.png)-->
> [!TIP]
> Genom att välja en generisk behållarmodultyp får du den mest flexibla när du måste uppdatera och konfigurera fragmentet senare.

## <a name="add-remove-or-edit-fragments-on-a-page"></a>Lägga till, ta bort eller redigera fragment på en sida

I följande procedurer beskrivs hur du lägger till, tar bort och redigerar fragment.

### <a name="add-a-fragment"></a>Lägg till ett fragment

För att lägga till ett fragment till en sida i Commerce webbplatsskaparen.

1. I dispositionsfönstret till vänster eller direkt i visuell sidskapare, välj en behållare eller fack som underordnade moduler kan läggas till.
1. Välj tre punkter (**...**) bredvid namnet på behållaren eller platsen.  Om du vill kan du även välja plustecknet (**+**) om du använder visuell sidskapare.  
1. Välj **Lägg till fragment**.
    <!-- ![A screen capture of how to add an existing fragment to a slot or container](./media/add-fragment.png)-->
 
    > [!NOTE]
    > Om en behållare eller en plats inte stöder nya underordnade moduler är alternativet **Lägg till fragment** inte tillgängligt.
    
1. Sök efter och markera ett fragment som ska läggas till i dialogrutan **Välj fragment**. Om det inte finns några tillgängliga fragment kanske du först måste skapa ett fragment från en modultyp som den valda behållaren eller platsen stöder.
1. Välj önskat fragment om du vill lägga till behållaren eller platsen på sidan.
<!--    ![A screen capture of the fragment picker modal window](./media/fragment-picker.png)-->

> [!NOTE]
> Modulerna som är tillåtna i en behållare eller plats definieras av sidans mall eller modulernas egna definitioner.

### <a name="remove-a-fragment"></a>Ta bort ett fragment

Om du vill ta bort ett fragment från ett fack eller en behållare på en sida i Commerce webbplatsskapare följer du stegen nedan.

1. I dispositionsrutan till vänster, välj ellipsknappen (**...**) bredvid namnet på det fragment som du vill ta bort och markera sedan knappen papperskorgen.  Du kan också markera avsnittet i visuell sidskapare och välja papperskorgssymbolen i fragmentets verktygsfält.
1. När du uppmanas att bekräfta att du vill ta bort fragmentet väljer du **OK**.

> [!NOTE]
> När du tar bort ett fragment från en sida tar du bara bort referensen till det från den sidan. Du tar **inte** bort fragmentet från webbplatsen. Om du vill ta bort fragment från platsen måste du använda användargränssnittet för fragmentkontrollen. Du kan bara ta bort fragment från en plats om de inte är refererade till några sidor, mallar eller andra fragment.

### <a name="edit-a-fragment"></a>Redigera ett fragment

Om du vill redigera fragment måste du använda gränssnittet för fragmentredigeraren. Denna begränsning är av design. Den garanterar att författare inte förvirrar processen att redigera modulerna för en viss sida med processen för att redigera fragment som kan delas på många sidor.

För att redigera ett fragment i Commerce webbplatsskaparen.

1. I navigeringsfönstret till vänster, välj **fragment**.
1. Under **Fragment**, välj det fragment du redigera.
1. Redigera fragmentets modulegenskaper och struktur efter behov. Processen ser ut som om du redigerar modulerna i vyn sidredigerare.

Du kan också redigera ett fragment genom att markera det på en sida, i en mall eller i ett överordnat fragment, och sedan välja **redigera fragment** i egenskapsrutan till höger.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över mallar och layouter](templates-layouts-overview.md)

[Arbeta med mallar](work-with-templates.md)

[Arbeta med förinställda layouter](work-with-layouts.md)

[Arbeta med publiceringsgrupper](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
