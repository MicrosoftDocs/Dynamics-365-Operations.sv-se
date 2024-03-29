---
title: Arbeta med förinställda layouter
description: I denna artikel beskrivs hur du arbetar med förinställda layouter i Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 02/03/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: b588df5702657f07e1e790ffba39d2e459901557
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286287"
---
# <a name="work-with-preset-layouts"></a>Arbeta med förinställda layouter

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du arbetar med förinställda layouter i Microsoft Dynamics 365 Commerce.

Innan du slutför procedurerna i denna artikel bör du läsa [Förinställda och anpassade layouter](templates-layouts-overview.md#preset-and-custom-layouts) En allmän översikt finns i [mallar och layouter – översikt](templates-layouts-overview.md).

## <a name="create-a-new-preset-layout"></a>Skapa en ny förinställd layout

Det finns två metoder för att skapa en förinställd layout. Du kan spara en befintlig anpassad layout som en ny förinställd layout, eller så kan du skapa en förinställd layout från början.

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a>Skapa en förinställd layout från en befintlig anpassad layout

För att skapa en förinställd layout från en befintlig anpassad layout, följ dessa steg:

1. Öppna en befintlig sida som för tillfället inte använder en förinställd layout och som har en modulstruktur som du vill återanvända för andra sidor på webbplatsen.
1. Välj **redigera** om du vill checka ut sidan.
1. Välj **Spara som ny layout**. Dialogrutan **Spara som ny layout** visas.
1. Ange ett namn och en beskrivning för din förinställda layout. De värden du anger kommer att visas för andra författare när de skapar nya sidor från layouten eller växlar till den. Ange därför värden som är användbara för sidförfattare.
1. Välj **OK**.

Den förinställda layouten blir nu tillgänglig när du skapar nya sidor eller väljer en annan layout för en sida i samma mall.

> [!TIP]
> Om du snabbt vill se om en viss sida är bunden till en förinställd layout, markerar du sidan i listvyn och kontrollerar layoutens metadata i egenskapsrutan till höger.

### <a name="create-a-new-preset-layout"></a>Skapa en ny förinställd layout

För att skapa en förinställd layout från början, följ dessa steg:

1. I navigeringsfönstret till vänster, välj **Layouter**.
1. Välj **Ny layout**. Dialogrutan **Ny layout** visas.
1. Välj den mall som ska användas för den förvalda layouten.
1. Ange ett namn och en beskrivning för din förinställda layout. De värden du anger kommer att visas för andra författare när de skapar nya sidor från layouten eller växlar till den. Ange därför värden som är användbara för sidförfattare.
1. Klicka på **OK** om du vill skapa den nya förinställda layouten och öppna layoutredigeraren.
1. I layoutvyn lägger du till och konfigurerar moduler med hjälp av dispositionsträdet till vänster och egenskapsrutan till höger. (Processen ser ut som om du lägger till och konfigurerar moduler för en mall i mallredigeraren.) Moduler och låsta standardinställningar blir den centraliserade konfigurationen av alla sidor där den här förvalda layouten används.

## <a name="modify-a-preset-layout"></a>Ändra en fördefinierad layout

För att ändra en förinställd layout, följ dessa steg:

1. I navigeringsfönstret till vänster, välj **Layouter**.
1. Välj den modul som ska ändras i dispositionsträdet till vänster i layoutvyn. Gör sedan något av följande:

    - Om du vill flytta en modul uppåt eller nedåt inuti dess överordnade, markerar du ellipsknappen (**...**) och modulen och välj sedan **flytta upp** eller **flytta ned**.
    - Om du vill ändra standardinställningarna för en modul använder du egenskapsfönstret för att ange standardvärden och för att även låsa dem för alla underordnade sidor.
    - Om du vill lägga till nya moduler eller fragment i behållarmoduler markerar du knappen och väljer **Lägg till modul** eller **Lägg till fragment**.
    - Om du vill ta bort en modul från layouten markerar du ellipsknappen och väljer sedan **Ta bort**.

## <a name="change-a-preset-layout-theme"></a>Ändra ett förinställt tema för en layout

Ett vanligt tillvägagångssätt är att ange ett standardtema för alla sidor som använder en förinställd layout.

Om du vill ange eller ändra temat för alla underordnade sidor som använder din förinställda layout följer du stegen nedan.

1. Välj den modul för sidbehållare som ska ändras i dispositionsträdet till vänster i layoutvyn. (Normalt är den här modulen den andra noden och får namnet **standardsida**.)
1. Välj ett tema i fältet **tema** i egenskapsfönstret till höger.

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a>Spara, checka in, förhandsgranska och publicera en förinställd layout

Om du vill spara och checka in din förinställda layout, följ dessa steg.

1. Välj **spara** längst upp i layoutredigeraren. Sparade ändringar påverkar inte underordnade sidor förrän de checkas in.
1. Välj **Slutför redigering**. Dina ändringar kan nu upptäckas för efterföljande arbetsflöden.

Om du vill förhandsgranska ändringarna öppnar du en befintlig sida som använder förinställd layout eller skapar en ny sida från layouten.

När du har förhandsgranskat ändringarna i din förinställda layout gör du följande för att publicera layouten på din aktiva webbplats:

1. Gå till **layouter**, markera layouten och välj sedan **publicera**.
1. Välj layoutnamn för att öppna layoutredigeraren och välj sedan **Publicera**.
1. Publicera en sida som refererar till den opublicerade layouten. Layouten kommer att publiceras automatiskt.

> [!WARNING]
> Du kan referera till förinställda layouter av flera sidor. När du publicerar en förinställd layout måste du vara medveten om att du kan påverka layouten på flera sidor.

## <a name="rename-a-preset-layout"></a>Byt namn på en fördefinierad layout

Följ dessa steg för att byta namn på fördefinierad layout i webbplatsskaparen.

1. I navigeringsfönstret till vänster välj er du **Layouter**.
1. Välj layoutnamnet på den layout som du vill byta namn på.
1. Välj **Redigera** för att börja redigera layout.
1. I rutan för layoutegenskaper väljer du pennsymbolen bredvid layoutnamnet.
1. Redigera layoutnamnet efter behov.
1. Markera kryssrutan om du vill bekräfta namnändringen.
1. Välj **Slutför redigering**.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över mallar och layouter](templates-layouts-overview.md)

[Arbeta med mallar](work-with-templates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
