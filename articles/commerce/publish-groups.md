---
title: Arbeta med publiceringsgrupper
description: I det här avsnittet beskrivs funktionen publicera grupper i Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 374a6c7dd33440903babbc8232f580ac2b68df82
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003175"
---
# <a name="work-with-publish-groups"></a>Arbeta med publiceringsgrupper


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs funktionen publicera grupper i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

E-handelswebbplatser uppdateras ständigt med nytt innehåll under hela året. Uppdateringar publiceras ofta i omgångar runt upptagna e-handelsevenemang som helgdagar, säsongsbetonade marknadsföringskampanjer eller kampanjlanseringar. Dessa uppdateringar kräver ofta att grupper av webbplatsinnehåll (till exempel sidor, bilder, fragment och mallar) mellanlagras, verifieras och publiceras samtidigt i en enda åtgärd.

Möjligheten att gruppera objekt i logiska uppsättningar som publicerar objekt tillsammans, där varje uppsättning har sin egen livscykel, ger många fördelar för webbplatsförfattarna. I Commerce kallas dessa logiska uppsättningar för publiceringsgrupper. De låter webbplatsförfattarna spåra uppsättningar av uppdateringar som sina egna konfigurerbara, testbara och publicerbara entiteter.

Författare kan förhandsgranska uppdateringar i en stegvis publiceringsgrupp utan att påverka den aktiva webbplatsen eller andra fristående publiceringsgrupper. Författare kan sedan schemalägga publiceringsåtgärden att samtidigt publicera alla objekt i gruppen publicera på den aktiva webbplatsen. Möjligheten att gruppera, förhandsgranska och schemalägga uppdateringar för publicering är viktigt för många företag på företagsnivå som genererar avsevärda årliga intäkter runt händelsebaserade milstolpar för webbplatsuppdateringar.

Företag kan ådra sig kostnader från långsamma eller ogiltiga innehållslanseringar som inte går smidigt. Publiceringsgrupper hjälper till att garantera att lanseringar organiseras, verifieras och publiceras i tid. Oavsett om de är stora eller små, ger publiceringsgrupper en värdefull verktygsuppsättning som hjälper författarna att organisera och förenkla pågående uppdateringsaktiviteter för webbplats.

## <a name="when-to-use-publish-groups"></a>När du ska använda publiceringsgrupper

Du kan använda publiceringsgrupper när du måste arrangera och publicera flera dokument tillsammans. Om din webbplats till exempel uppdaterar innehåll varje säsong kan du skapa publiceringsgrupper för dessa säsongsbaserade marknadsföringsrörelser. Din publiceringsgrupp "höstsäsongsuppdatering" kan innehålla nya säsongsbetonade bilder, fragment som har säsongsbetonade marknadsföringsmeddelanden, sidor som innehåller säsongsbetonade produktinsamlingar, eller andra säsongsbetonade webbplatsuppdateringar.

En fördel med publiceringsgrupper är att du kan arrangera flera uppdateringar parallellt. Till exempel, strax efter uppdateringen för Publiceringsgruppen "höstsäsongsuppdatering", kan det finnas en innehållsuppdatering för en viss helgdag. I det här fallet kan du arrangera innehåll för publiceringsgruppen "höstsäsongsuppdatering" samtidigt som du arrangerar innehåll för en efterföljande "Höstsemesteruppdatering"-publiceringsgrupp. Varje publiceringsgrupp innehåller en egen unik uppsättning sidor, bilder, fragment, mallar och så vidare. Du kan arrangera, förhandsgranska och validera dessa två publiceringsgrupper oberoende av varandra, men på en samtidig tidslinje. Varje publiceringsgrupp kan sedan schemaläggas att publicera på din webbplats vid specifika datum och tidpunkter.

## <a name="turn-on-the-publish-groups-feature"></a>Aktivera funktionen publicera grupper

Funktionen publicera grupper är valfri och måste vara aktiverad för din webbplats.

Så här aktiverar du funktionen publicera grupper för din webbplats i Commerce redigeringsverktygen.

1. I det vänstra navigeringsfönstret väljer du **Webbplatsinställningar** för att expandera den.
1. Under **Webbplatsinställningar** väljer du **funktioner**.
1. Ställ in alternativet **publicera grupper** till **på**.

## <a name="create-a-publish-group"></a>Skapa en publiceringsgrupp

För att skapa en publiceringsgrupp publicera grupper för din webbplats i Commerce redigeringsverktygen.

1. I vänstra navigeringsfönstret, välj **Publicera grupper**.
1. Överst i kommandofältet, klicka på **Ny**.
1. I dialogrutan **Skapa publiceringsgrupp** under **publicera gruppnamn**, ange ett beskrivande namn. Välj sedan **OK**.

## <a name="set-the-publish-group-authoring-context"></a>Ange redigeringskontexten för publiceringsgruppen

I Commerce är standard redigeringskontexten den aktiva webbplatsens kontext. Redigeringskontexten för den aktiva webbplatsen är standardvyn där du kan visa och göra ändringar direkt på din webbplats utan att använda en publiceringsgrupp. Den representerar de senaste direkta uppdateringarna till den publicerade versionen av din webbplats. Om kontextkontrollen under **publiceringsgrupper** i det vänstra navigeringsfönstret visar namnet **aktiva webbplatsen**, arbetar du i redigeringskontexten för den aktiva webbplatsen. **Levande webbplatsen** är standardnamnet för kontextkontrollen. I annat fall visar kontextkontrollen visar namnet på en publiceringsgrupp.

Om du vill arbeta i en publiceringsgrupp måste du växla till redigeringskontexten för publiceringsgruppen för den. Så här anger du publiceringsgruppens kontext.

- I det vänstra navigeringsfönstret markerar du kontext kontrollen direkt under **publiceringsgrupper** och markerar sedan namnet på publiceringsgruppen i listan med alternativ som visas. Kontextkontrollen byter namn och visar namnet på publiceringsgruppen.
- I det vänstra navigeringsfönstret väljer du **publiceringsgrupper**och markerar sedan namnet på **Publiceringsgruppen** under publiceringsgrupper. Kontextkontrollen byter namn och visar namnet på publiceringsgruppen.

När du har angett redigeringskontexten för publiceringsgruppen arbetar du i den publiceringsgruppens kontext när du förhandsgranskar och redigerar webbplatsinnehåll.

Om du vill återgå till standardinställningen för redigering av den aktiva webbplatsen markerar du kontextkontrollen och väljer sedan **aktiv webbplats**.

## <a name="add-pages-or-other-items-to-a-publish-group"></a>Lägga till sidor eller andra objekt i en publiceringsgrupp

När du har valt en redigeringskontext för publiceringsgrupp och kontextkontrollen i det vänstra navigeringsfönstret visar dess namn, kan du skapa innehåll precis som du gör i standardkontexten för den aktiva webbplatsen. Du kan också lägga till befintliga sidor eller andra objekt från andra publiceringsgrupper eller från aktiv webbplatskontext.

Följ dessa steg om du vill kopiera befintliga sidor till en publiceringsgrupp.

1. Välj den redigeringskontext som ska kopieras från och välj sedan **sidor** i det vänstra navigeringsfönstret.
1. Välj den sida som du vill lägga till i en publiceringsgrupp.
1. I kommandofältet väljer du **kopiera till publiceringsgrupp**.
1. I dialogrutan **Välj en publiceringsgrupp** väljer du gruppen publicera för att lägga till sidan och väljer sedan **OK**.

Du kan använda samma grundläggande steg för att skapa anpassade produktsidor, URL:er, mallar, layouter, fragment och media bibliotekstillgångar, eller lägga till befintliga objekt av dessa typer i en publiceringsgrupp.

## <a name="validate-a-publish-group"></a>Validera en publiceringsgrupp

Om du vill kontrollera att alla beroenden i publiceringsgruppens innehåll är uppfyllda och att alla valideringar skickas, kan du köra validering för att identifiera eventuella problem som måste åtgärdas innan du schemalägger en publiceringsåtgärd.

Gör så här om du vill validera din publiceringsgrupp innan du schemalägger den.

1. I vänstra navigeringsfönstret, välj **Publicera grupper**.
1. Välj publiceringsgruppen som ska valideras.
1. Överst i kommandofältet, klicka på **Valideras**.

Valideringen körs på allt innehåll i publiceringsgruppen. Eventuella problem som förhindrar att en lyckad publiceringsåtgärd visas i en meddelanderuta som visas uppe till höger.

> [!NOTE]
> Valideringen körs alltid automatiskt när en publiceringsgrupp schemaläggs. Knappen **validera** i kommandofältet är dock användbar eftersom den hjälper dig att identifiera problem som du måste åtgärda innan du försöker schemalägga en publiceringsgrupp att publicera.

## <a name="schedule-a-publish-group-to-go-live"></a>Schemalägga en publiceringsgrupp att publicera

Om du vill schemalägga en publiceringsgrupp så att den publiceras på webbplatsen följer du dessa steg.

1. I vänstra navigeringsfönstret, välj **Publicera grupper**.
1. Under **publiceringsgrupper** väljer du den publiceringsgrupp som ska schemaläggas.
1. Överst i kommandofältet, klicka på **Redigera schema**. Dialogrutan **Redigera schema** visas.
1. Välj datum och tid när publiceringsgruppen ska publiceras och välj sedan **OK**.

Om du vill avschemalägga en publiceringsgrupp följer du samma steg, men väljer **Ej schemalagd publiceringsgrupp** i dialogrutan **Redigera scheman**.

> [!NOTE]
> Mycket stora publiceringsgrupper kan ta upp till en minut eller två som ska publiceras när deras schemalagda tid anländer. Tänk på att en publiceringsåtgärd inte är ögonblicklig och att mindre publiceringsgrupper kommer att publiceras snabbare.

## <a name="publish-groups-faq"></a>Vanliga frågor om publiceringsgrupper

**Hur många objekt kan finnas i en publiceringsgrupp?**

För närvarande finns det en gräns på 2 000 objekt per publiceringsgrupp. Var medveten om att mycket stora publiceringsgrupper kan ta flera minuter att publiceras när deras schemalagda tid anländer.

**Är publiceringsgrupper som kod "grenar" i terminologi för programvaruutveckling?**

Ja och nej. Publiceringsgrupper kan betraktas som kluven versioner av din webbplats. På så sätt agerar de som grenar. Det finns dock inget begrepp om en sammanslagning på nivån för enskilda objekt. Den artikel som publiceras sist skriver bara över vad som tidigare fanns och den senaste publiceringsåtgärden ersätter alltid tidigare publiceringsåtgärder.

**Kan jag schemalägga två publiceringsgrupper att publicera samtidigt?**

Nr. Av prestanda- och konfliktskäl tvingar systemet dig att sprida schemalagda publiceringsgrupper minst fem minuters mellanrum.

**Kan jag använda publiceringsgrupper för att schemalägga backoffice-objekt för flerkanal, till exempel rabatter och produktuppdateringar?**

För närvarande stöder funktionen publiceringsgrupper endast webbplatsinnehåll. Microsoft är dock medveten om att integrering med marknadsföringsscenarier med backoffice kan vara värdefullt för koordineringen och automatiseringen av kampanjlanseringar i flerkanal.

## <a name="additional-resources"></a>Ytterligare resurser

[Sätt att lägga till innehåll](add-manage-content.md)

[Ordlista för sidmodell](page-elements-overview.md)

[Dokumentera tillstånd och livscykel](document-states-overview.md)

[Arbeta med moduler](work-with-modules.md)

[Arbeta med fragment](work-with-fragments.md)

[Översikt över mallar och layouter](templates-layouts-overview.md)

[Anpassa webbplatsnavigeringen](customize-site-navigation.md)
