---
title: Arbeta med moduler
description: I det här avsnittet beskrivs hur och när du ska använda moduler i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3c4161e7a40cdbbb40292a6ce9acab58347460bd
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914804"
---
# <a name="work-with-modules"></a>Arbeta med moduler

I det här avsnittet beskrivs hur och när du ska använda moduler i Microsoft Dynamics 365 Commerce.

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

## <a name="overview"></a>Översikt

Moduler är logiska byggblock som utgör sidans struktur och har olika syfte och omfång. Vissa moduler är behållare på hög nivå, och de är bara avsedda att innehålla och organisera andra moduler (underordnade moduler). Andra moduler, t.ex. en enkel bildplaceringsmodul, har ett mycket specifikt syfte. Andra moduler, till exempel en karusellmodul, ligger någonstans mellan dessa två kategorier.

Webbplatsen Dynamics 365 Commerce innehåller som standard ett bibliotek med startpaketmoduler som gör att du kan uppnå de flesta grundläggande näthandelsscenarier. Du bör kunna skapa en slutpunkt-till-slutpunkt-plats för e-handel genom att bara använda de här modulerna. Men du kanske också vill anpassa dessa moduler eller bygga nya, anpassade moduler för specifika behov. Om du vill skapa anpassade moduler kan du använda en moduldesign-SDK (Software Development Kit) som hjälper dig att skapa ett anpassat bibliotek för modulen.

## <a name="container-modules-and-slots"></a>Moduler och platser för behållare

Som tidigare nämnts är vissa moduler avsedda att innehålla underordnade moduler. Dessa moduler kallas *behållare*, och de tillåter hierarkier för kapslade moduler. Behållarmoduler inkluderar *platser*. Platser används för att hantera layout och syfte för underordnade moduler i behållaren. Ett exempel är en grundläggande sidbehållarmodul (en modul på översta nivån för alla sidor) som definierar flera viktiga platser:

- En sidhuvudplats
- En brödtextplats
- En sidfotsplats

Modulens utvecklare definierar dessa platser och avgör vilka underordnade moduler och hur många underordnade moduler som kan placeras direkt inuti det. Sidhuvudsplatsen kan t.ex. stödja bara en av modulerna i typen **Modul för sidhuvud** medan brödtextplatsen kan stödja ett obegränsat antal moduler av vilken typ som helst (utom andra sidbehållarmoduler).

I redigeringsverktygen behöver inte sidförfattare veta i förväg vilka moduler som kan och inte kan placeras på varje plats. När sidans författare väljer en plats och sedan försöker välja en modul som ska läggas till i den, visas en filtrerad vy av modulens typer som stöds för platsen.

## <a name="content-modules"></a>Innehållsmoduler

Innehållsmoduler innehåller innehålls- och medieelement, t.ex. text (t.ex. rubriker, stycken och länkar) eller tillgångsreferenser (t.ex. bilder, video och PDF-filer). Exempel på typiska typer av innehållsmoduler är **funktion**, **innehåll** och **banderoll**. Moduler av dessa tre typer kan innehålla text eller media och de behöver inte några underordnade moduler för att göra något synligt på en sida.

De flesta vanliga, dagliga och innehållsredigeringsaktiviteterna omfattar innehållsmoduler, främst på grund av att dessa moduler definierar det faktiska innehållet som återges i sina överordnade behållarmoduler. Många innehållsmoduler är tillgängliga och dessa moduler är vanligtvis de sista delarna som du lägger till i en sidas hierarki med kapslade moduler.

I följande bild visas hur moduler kapslas inuti överordnade behållarmodulplatser.

![Kapslade moduler](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a>Lägg till eller ta bort moduler

I följande procedurer beskrivs hur du lägger till och tar bort moduler.

### <a name="add-a-module"></a>Lägg till modul

För att lägga till en modul till en plats eller behållare på en sida, följ dessa steg.

1. I dispositionsrutan till vänster väljer du en behållare eller en plats som en underordnad modul kan läggas till i.

    > [!NOTE]
    > Moduldesignern definierar listan med moduler som kan läggas till i en specifik modulplats. Mallförfattare kan sedan förfina de tillåtna modulernas alternativ så att du kan garantera en konsekvent sökmotorsoptimering (SEO) och redigera effektiviteten för alla sidor som skapas från en viss mall.

1. Markera knappen med punkter för modulen (**...**) och välj sedan **Lägg till modul**. Dialogrutan **Lägg till modul** visas. Denna dialogruta filtreras automatiskt så att den bara visar moduler som stöds i den valda behållaren eller platsen. Listan med moduler bestäms av sidans mall eller definition för behållarmodul.

    > [!NOTE]
    > Om en behållare eller en plats inte stöder nya underordnade moduler är alternativet **Lägg till modul** inte tillgängligt.

1. Sök efter och markera en modul som ska läggas till på sidan i dialogrutan.

    > [!TIP]
    > **Funktion** och **fokus** är bra modultyper som nybörjare kan arbeta med.

1. Klicka på **OK** om du vill lägga till den valda modulen i den valda behållaren eller platsen på sidan.

### <a name="remove-a-module"></a>Ta bort en modul

För att ta bort en modul från en plats eller behållare på en sida, följ dessa steg.

1. Markera ellipsknappen bredvid namnet på den modul som du vill ta bort i dispositionsrutan till vänster och markera sedan knappen papperskorgen.
1. När du uppmanas att bekräfta att du vill ta bort modulen väljer du **OK**.

## <a name="configure-modules"></a>Konfigurera moduler

I följande procedurer beskrivs hur du konfigurerar innehåll och behållarmoduler.

### <a name="configure-a-content-module"></a>Konfigurera en innehållsmodul

Om du vill konfigurera en innehållsmodul på en sida följer du stegen nedan.

1. I dispositionsfönstret till vänster väljer du en innehållsmodultyp (t.ex. **innehåll**, **fokus** eller **banderoll**).
1. I egenskapsrutan till höger expanderar du de kapslade kontrollerna genom att markera rubrikerna och ange önskade kontrollvärden.
1. Om egenskapsfönstret har ett avsnitt för **datakonfiguration**, markerar du det för att expandera det. Gå annars till steg 5.
1. Om det finns en knapp för att **Lägga till datakälla** markerar du den och markerar sedan de innehållsobjekt som ska läggas till.
1. Ange inställningar för alla nödvändiga eller önskade modulkontroller.
1. Välj **Spara**.

### <a name="configure-a-container-module"></a>Konfigurera en behållarmodul

Om du vill konfigurera en behållarmodul på en sida följer du stegen nedan.

1. Välj en behållarmodul på sidan (t.ex. en karusell eller en flytande behållarmodul).
1. I egenskapsrutan till höger expanderar du de kapslade kontrollerna genom att markera rubrikerna och ange önskade kontrollvärden.
1. I dispositionsfönstret till vänster väljer du ellipsknappen bredvid namnet på antingen behållaren eller valfri plats i behållaren och välj sedan **Lägg till modul**. Lägg sedan till underordnade moduler i den valda behållaren. Mer information finns i proceduren [Lägg till en modul](#add-a-module) tidigare i det här avsnittet.
1. Om det finns flera underordnade moduler på samma nivå i en överordnad behållare kan du ändra deras visningsordning i den överordnade behållaren. Välj ellipsknappen för en modul och använd sedan knapparna uppåtpil och nedåtpil.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över mallar och layouter](templates-layouts-overview.md)

[Arbeta med mallar](work-with-templates.md)

[Arbeta med förinställda layouter](work-with-layouts.md)

[Arbeta med fragment](work-with-fragments.md)

[Lägg till en behållarmodul på en sida](add-container-module.md)

[Lägg till modul för innehållsplacering till en sida](add-content-placement-modules.md)

[Arbeta med publiceringsgrupper](publish-groups.md)

