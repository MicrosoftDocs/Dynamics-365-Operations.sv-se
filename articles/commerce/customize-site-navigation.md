---
title: Anpassa webbplatsnavigeringen
description: I denna artikel beskrivs hur du skapar en anpassad onlinemapp för navigering i syfte att ordna dina produkter för bläddring på din Microsoft Dynamics 365 Commerce-webbplats.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 319bc4af5da19a7a8604f1d30088dbb4aefa6b63
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275661"
---
# <a name="customize-site-navigation"></a>Anpassa webbplatsnavigeringen

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du skapar en anpassad onlinemapp för navigering i syfte att ordna dina produkter för bläddring på din Microsoft Dynamics 365 Commerce-webbplats.

Nätbutiker gör vanligtvis att kunderna hittar och bläddrar igenom produkter genom att navigera genom produktkategorier. Den här funktionen tillhandahålls vanligtvis med flikar högst upp på sidan eller genom ett navigeringsfält till vänster. I Dynamics 365 Commerce kan du skapa och hantera den hierarkiska strukturen för kategorinavigeringen och de produkter som ingår i de olika kategorierna.

## <a name="create-a-channel-navigation-hierarchy"></a>Skapa en navigeringshierarki för kanal

Följ stegen nedan om du vill skapa en navigeringshierarki för kanaler.

1. Gå till **Butik och handel \> Produkter och kategorier \> Kategori- och produkthantering**.
1. Markera **kategorihierarkier** och välj sedan **Ny**.
1. Namn på hierarkin.

    > [!NOTE]
    > Den översta kategorin som du skapar är rotkategorinoden. Den visas inte på din webbplats. Om du vill skapa en kategorihierarki där en enskild nod på den översta nivån visas på din webbplats, skapar du och namnger kategorin som underordnad till rotkategorin.

1. Välj **ny kategorinod** och ge kategorin ett namn.
1. Fortsätt att skapa kategorier på samma nivå och underordnade kategorier som du behöver.

Nu kan du tilldela produkter till varje kategori som du har skapat under kategorin på den högsta nivån.

## <a name="customize-the-order-of-categories"></a>Anpassa ordningen på kategorier

De kategorier som du definierar visas som standard i alfabetisk ordning på webbplatsen. Du kan dock även anpassa visningsordningen för kategorier.

## <a name="assign-a-category-hierarchy-type"></a>Tilldela en kategorihierarkityp

1. Gå till **Butik och handel \> Produkter och kategorier \> Kategori- och produkthantering**.
1. Välj **kategorihierarkier**.
1. I åtgärdsfönstret, på fliken **kategorihierarki** i gruppen **Inställning** markerar du **Associera hierarki**.
1. Välj **Ny**.
1. I fältet **Kategorihierarkityp**, välj **Navigeringshierarki för kanal**.
1. I fältet **kategorihierarki** väljer du den hierarki för kanalnavigering som du skapade tidigare.

## <a name="publish-new-or-updated-navigation-hierarchies"></a>Publicera nya eller uppdaterade navigeringsnoder

Gör så här om du vill att din navigeringsnoden ska vara tillgänglig för din nätbutik:

1. Gå till **Butik och handel \> Kanalinställningar \> Kanalkategorier och produktattribut**.
1. I trädet till vänster väljer du onlinebutiken.
1. Välj **Publicera kanaluppdateringar**.
1. Gå till **Butik och handel \> Butik och handel-IT \> Distributionsschema**.
1. I listan söker du och väljer **Jobb 1040**.
1. Välj **kör nu**.
1. Upprepa steg 5 och 6 för jobben 1070 och 1150.

## <a name="show-categories-on-your-site"></a>Visa kategorier på din webbplats

Om du vill visa kategorihierarkin i din nätbutik måste du lägga till modulen för navigeringsmenyn på lämplig plats i en mall eller i ett fragment. Modulen navigeringsmeny visar sedan webbhierarkin, förutsatt att du har publicerat din hierarki på den kanal som webbplatsen är bunden till.

> [!NOTE]
> Med modulen navigeringsmeny som ingår i modulbibliotek kan användarna bara navigera till kategorier som inte har underkategorier. Om dina kunder ska kunna navigera till kategorier som har underkategorier måste du anpassa modulen för navigeringsmenyn.

## <a name="add-custom-navigation-options"></a>Lägga till anpassade navigeringsalternativ

På navigeringsmenyn kan du lägga till navigeringsalternativ som inte ingår i din produktkategorihierarki. I slutet av listan med produktkategorier kan du till exempel lägga till artikeln **kontakta oss** som pekar mot en kontaktsida som du har skapat för webbplatsen.

Om du vill lägga till anpassade navigeringsalternativ på navigeringsmenyn följer du stegen nedan.

1. I mallen eller fragmentet som du vill anpassa väljer du modulen navigeringsmeny.
1. I fönstret egenskaper, på fliken **Data** väljer du **Lägg till objekt** för att skapa ett nytt navigeringsobjekt i innehållshanteringssystem (CMS).
1. Ange länktext och en URL.
1. Upprepa steg 2 och 3 om du vill lägga till fler anpassade navigeringsalternativ.
1. När du är klar väljer du **Spara** för att spara mallen eller fragmentet och väljer sedan **Slutför redigering** för att checka in den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över mallar och layouter](templates-layouts-overview.md)

[Arbeta med mallar](work-with-templates.md)

[Arbeta med förinställda layouter](work-with-layouts.md)

[Arbeta med fragment](work-with-fragments.md)

[Arbeta med moduler](work-with-modules.md)

[Skapa URL för webbsida](create-page-url.md)

[Arbeta med publiceringsgrupper](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
