---
title: Arbeta med moduler
description: I det här avsnittet beskrivs hur och när du ska använda moduler i Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ce16aa98a37cd5dec60bcdbf86f59f74810da9755a6d3514bdd3e38a21afb748
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6728274"
---
# <a name="work-with-modules"></a>Arbeta med moduler

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur och när du ska använda moduler i Microsoft Dynamics 365 Commerce.

Moduler är logiska byggblock som utgör sidans struktur och har olika syfte och omfång. Vissa moduler är behållare på hög nivå, och de är bara avsedda att innehålla och organisera andra moduler (underordnade moduler). Andra moduler, t.ex. en enkel bildplaceringsmodul, har ett mycket specifikt syfte. Andra moduler, till exempel en karusellmodul, ligger någonstans mellan dessa två kategorier.

Webbplatsen Dynamics 365 Commerce innehåller som standard ett modulbibliotek som gör att du kan uppnå de flesta grundläggande näthandelsscenarier. Du bör kunna skapa en slutpunkt-till-slutpunkt-plats för näthandel genom att bara använda de här modulerna. Men du kanske också vill anpassa dessa moduler eller bygga nya, anpassade moduler för specifika behov. Om du vill skapa anpassade moduler kan du använda en moduldesign-SDK (Software Development Kit) som hjälper dig att skapa ett anpassat bibliotek för modulen.

## <a name="container-modules-and-slots"></a>Moduler och platser för behållare

Som tidigare nämnts är vissa moduler avsedda att innehålla underordnade moduler. Dessa moduler kallas *behållare*, och de tillåter hierarkier för kapslade moduler. Behållarmoduler inkluderar *platser*. Platser används för att hantera layout och syfte för underordnade moduler i behållaren. Ett exempel är en grundläggande sidbehållarmodul (en modul på översta nivån för alla sidor) som definierar flera viktiga platser:

- En sidhuvudplats
- En plats för underrubrik
- En huvudplats
- En sidfotsplats
- En plats för underrubrik

Modulens utvecklare definierar dessa platser och avgör vilka underordnade moduler och hur många underordnade moduler som kan placeras direkt inuti det. Sidhuvudsplatsen kan t.ex. stödja bara en av modulerna i typen **Modul för sidhuvud** medan brödtextplatsen kan stödja ett obegränsat antal moduler av vilken typ som helst (utom andra sidbehållarmoduler).

I redigeringsverktygen behöver inte sidförfattare veta i förväg vilka moduler som kan och inte kan placeras på varje plats. När sidans författare väljer en plats och sedan försöker välja en modul som ska läggas till i den, visas en filtrerad vy av modulens typer som stöds för platsen.

## <a name="content-modules"></a>Innehållsmoduler

Innehållsmoduler innehåller innehålls- och medieelement, t.ex. text (t.ex. rubriker, stycken och länkar) eller tillgångsreferenser (t.ex. bilder, video och PDF-filer). Bland de vanligaste typerna av innehållsmoduler finns innehållsblock, textblock och annonsmoduler. Moduler av dessa tre typer kan innehålla text eller media och de behöver inte några underordnade moduler för att göra något synligt på en sida.

De flesta vanliga, dagliga och innehållsredigeringsaktiviteterna omfattar innehållsmoduler, främst på grund av att dessa moduler definierar det faktiska innehållet som återges i sina överordnade behållarmoduler. Många innehållsmoduler är tillgängliga och dessa moduler är vanligtvis de sista delarna som du lägger till i en sidas hierarki med kapslade moduler.

I följande bild visas hur moduler kapslas inuti överordnade behållarmodulplatser.

![Kapslade moduler.](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a>Lägg till eller ta bort moduler

I följande procedurer beskrivs hur du lägger till och tar bort moduler.

### <a name="add-a-module"></a>Lägg till modul

För att lägga till en modul till en plats eller behållare på en sida, följ dessa steg.

1. I dispositionsfönstret till vänster eller direkt i huvudarbetsytan, välj en behållare eller fack som underordnade moduler kan läggas till.

    > [!NOTE]
    > Moduldesignern definierar listan med moduler som kan läggas till i en specifik modulplats. Mallförfattare kan sedan förfina de tillåtna modulernas alternativ så att du kan garantera en konsekvent sökmotoroptimering (SEO) och redigera effektiviteten för alla sidor som skapas från en viss mall. Bär du lägger till en modul till en plats filtreras dialogrutan **Lägg till modul** automatiskt så att den bara visar moduler som stöds i den valda behållaren eller platsen. Listan med tillåtna moduler bestäms av sidans mall eller definition för behållarmodul.

1. Om du använder konturfönstret väljer du tre punkter (**...**) bredvid modulnamnet och väljer **Lägg till modul**. Om du använder kontrollerna direkt på arbetsytan markerar du plustecknet (**+**) i en tom plats eller invid den valda modulen och väljer sedan **Lägg till modul**.

    > [!NOTE]
    > Om en behållare eller en plats inte stöder nya underordnade moduler är alternativet **Lägg till modul** inte tillgängligt.

1. I dialogrutan **Lägg till modul** välj en modul för att lägga till din sida.

    > [!TIP]
    > **Innehållsblock** är en god modultyp som den nybörjare kan arbeta med.

1. Klicka på **OK** om du vill lägga till den valda modulen i den valda behållaren eller platsen på sidan.

### <a name="remove-a-module"></a>Ta bort en modul

För att ta bort en modul från en plats eller behållare på en sida, följ dessa steg.

1. I dispositionsrutan till vänster, välj ellipsknappen (**...**) bredvid namnet på det modul som du vill ta bort och markera sedan knappen papperskorgen. Alternativt kan du, på huvudarbetsytan, välja papperskorgssymbol i verktygsfältet för en markerad modul.
1. När du uppmanas att bekräfta att du vill ta bort modulen väljer du **OK**.

## <a name="move-a-module-to-a-new-position"></a>Flytta en fokusmodul på en ny position

Om du vill flytta en modul till en ny plats på sidan använder du någon av följande metoder.

### <a name="move-a-module-using-the-outline-pane"></a>Flytta en modul med hjälp av dispositionsfönstret

Flytta en modul med hjälp av dispositionsfönstret enligt följande instruktioner.

1. Markera och håll modulen du vill flytta i dispositionsfönstret och dra sedan modulen till en ny position i dispositionen. Den blå linjen i dispositionen och på arbetsytan anger var modulen kan placeras.
1. Släpp modulen om du vill släppa den på den nya platsen.

### <a name="move-a-module-directly-within-the-canvas"></a>Flytta en modul direkt på arbetsytan

Flytta en modul direkt i arbetsytan enligt följande instruktioner.

1. Välj den modul du vill flytta på arbetsytan. 
1. Markera antingen en pil som pekar uppåt eller nedåt i modulens verktygsfält och dra sedan pilen till en ny plats på sidan. Den blå linjen i arbetsytan och dispositionen anger var modulen kan placeras. Om en modul inte kan flyttas uppåt eller nedåt, kommer den att vara nedtonad. 
1. Släpp modulen om du vill släppa den på den nya platsen.

### <a name="move-a-module-using-the-ellipsis-menu"></a>Flytta en modul med hjälp av ellips-menyn

Flytta en modul med hjälp av ellips-menyn enligt följande instruktioner.

1. Välj en modul antingen i dispositionen eller på arbetsytan.
1. Markera tre punkter (**...**) bredvid modulens namn i antingen dispositionsfönstret eller i den markerade modulens verktygsfält på arbetsytan.
1. Om modulen kan flyttas upp eller ned i behållaren eller platsen visas alternativ för **Flytta upp** eller **Flytta ned**. Markera alternativet flytta om du vill flytta modulen uppåt eller nedåt i förhållande till objekt på samma nivå.

## <a name="configure-modules"></a>Konfigurera moduler

I följande procedurer beskrivs hur du konfigurerar innehåll och behållarmoduler.

### <a name="configure-a-content-module"></a>Konfigurera en innehållsmodul

Om du vill konfigurera en innehållsmodul på en sida följer du stegen nedan.

1. I dispositionsfönstret till vänster expanderar du trädet och väljer en innehållsmodul (t.ex. **innehållsblock**). Alternativt kan du välja modulen i huvudarbetsytan.
1. I fönstret för modulegenskaper till höger anger du egenskaper för alla önskade modulkontroller.
1. På kommandofältet, välj **Spara**. Då uppdateras även arbetsytan med förhandsgranskning.

### <a name="edit-module-text-properties"></a>Redigera egenskaper för textmodul

Modulens textegenskaper som inte är skrivskyddade kan redigeras direkt på arbetsytan.

Om du vill redigera textegenskaperna för modulen följer du stegen nedan.

1. Markera textkontrollen på arbetsytan och placera markören där du vill redigera texten.
1. Ange ditt textinnehåll.
1. Välj var som helst utanför textinnehållet om du vill fortsätta redigera annat innehåll.

### <a name="inline-image-selection"></a>Markering av infogad bild

Modulbilder som inte är skrivskyddade kan ändras direkt från arbetsytan.

Om du vill välja en ny bild för innehållsmodul följer du stegen nedan.

1. Dubbelklicka på bilden i arbetsytan. Detta gör att fönstret för medieväljaren visas.
1. Sök reda på och välj en ny bild som du vill använda och välj sedan **OK**. Den nya bilden återges nu på arbetsytan.

### <a name="configure-a-container-module"></a>Konfigurera en behållarmodul

Om du vill konfigurera en behållarmodul på en sida följer du stegen nedan.

1. Välj en behållarmodul på sidan (t.ex. en karusell eller en flytande behållarmodul).
1. I egenskapsrutan till höger expanderar du de kapslade kontrollerna genom att markera rubrikerna och ange önskade kontrollvärden.
1. I dispositionsfönstret till vänster väljer du ellipsknappen bredvid namnet på antingen behållaren eller valfri plats i behållaren och välj sedan **Lägg till modul**. Lägg sedan till underordnade moduler i den valda behållaren. Mer information finns i avsnitt [Arbeta med moduler modul](#add-a-module) tidigare i det här avsnittet.
1. Om det finns flera underordnade moduler på samma nivå i en överordnad behållare kan du ändra deras visningsordning i den överordnade behållaren. Välj ellipsknappen för en modul och använd sedan knapparna uppåtpil och nedåtpil.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över mallar och layouter](templates-layouts-overview.md)

[Arbeta med mallar](work-with-templates.md)

[Arbeta med förinställda layouter](work-with-layouts.md)

[Arbeta med fragment](work-with-fragments.md)

[Lägg till en behållarmodul på en sida](add-container-module.md)

[Arbeta med publiceringsgrupper](publish-groups.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
