---
title: Kategoribegäranden från leverantörer
description: Detta ämnet beskriver hur leverantörer kan begära anskaffningskategorier för sina konton. Det beskriver också godkännandeprocessen som har slutförts av anskaffningsmedarbetare.
author: kamaybac
ms.date: 04/19/2021
ms.topic: article
ms.search.form: VendRequestNewCategory
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1951f85f84c3b8b2d42f49d5f464d90d410ebfa2
ms.sourcegitcommit: 51cad1ce3ed44ebf7eb9bdf553ee2df4c1f03135
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/10/2021
ms.locfileid: "6015961"
---
# <a name="category-requests-from-vendors"></a>Kategoribegäranden från leverantörer

[!include [banner](../includes/banner.md)]

Med denna process för kategoribegäran kan våra leverantörer begära att nya anskaffningskategorier ska associeras med kontot. Dessa anskaffningskategorier kan sedan användas vid relaterade anskaffnings- och inköpsprocesser. (Mer information finns i [Översikt över anskaffningskataloger](procurement-catalogs.md).)

Kategoribegäranden initieras av leverantörer i arbetsytan **Leverantörsinformation**. De skickas sedan till din myndighet för granskning och godkännande. Godkända kategorier läggs till i listan över anskaffningskategorier för leverantörens konto.

## <a name="turn-on-the-feature-in-your-system"></a>Aktivera funktionen i systemet

Om systemet inte redan omfattar den funktion som beskrivs i detta ämne går du till [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktiverar funktionen *Tillåt att leverantörer kan ansöka om anskaffningskategorier genom leverantörssamarbete*.

När funktionen har aktiverats kan du fortfarande lägga till anskaffningskategorier på leverantörskonton manuellt. Mer information finns i [Godkänn leverantörer för specifika anskaffningskategorier](tasks/approve-vendors-specific-procurement-categories.md).

## <a name="vendor-collaboration-requirements"></a>Krav för leverantörssamarbete

Innan en leverantör kan interagera med kategoribegäranden måste denna ha ställts in för samarbete mellan leverantörer.

Leverantören måste ha minst en samarbetsanvändare för leverantörer. Endast leverantörsanvändare med säkerhetsrollen *Leverantörsadministratör (extern)* kan skapa och skicka kategoribegäranden.

Mer information finns i [Ställa in och underhålla leverantörssamarbete](set-up-maintain-vendor-collaboration.md).

## <a name="set-up-the-vendor-category-request-workflow"></a>Konfigurera arbetsflöde för leverantörskategoribegäran

Arbetsflödet *Leverantörskategoribegäran* måste ha ställts in i anskaffnings- och inköpsarbetsflödena. Leverantörer skickar nya kategoribegäranden som du kan granska och godkänna. Begärda anskaffningskategorier läggs till på ett leverantörskonto efter det att en kategoriförfrågan har godkänts.

Följande exempel visar hur du ställer in ett enkelt arbetsflöde för *leverantörskategoribegäranden* med en enda godkännare. Du måste granska dina interna processer för att kunna avgöra vilka arbetsflödesinställningar som behövs för din myndighet.

1. Gå till **Anskaffning och källa \> Inställningar \> Arbetsflöden för anskaffning och källa**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Välj **Arbetsflöde för leverantörskategoribegäran** för att öppna redigeraren för arbetsflöde.
1. Logga in i arbetsflödesredigeraren.
1. Välj **Egenskaper** i åtgärdsfönstret.
1. På sidan **Egenskaper** för arbetsflödet anger du instruktionstext i fältet **Instruktioner för överföring**. Instruktionerna visas för leverantörerna när dessa skickar in en kategoribegäran.
1. Stäng sidan **Egenskaper**.
1. Dra arbetsflödeselementet **Godkänn ny kategoribegäran** till arbetsytan.
1. Dra en länk från arbetsflödeselementet **Starta** till arbetsflödeselementet **Godkänn ny kategoribegäran**.
1. Dra en länk från arbetsflödeselementet **Godkänn ny kategoribegäran** till arbetsflödeselementet **Slut**.
1. Tryck två gånger eller dubbelklicka på arbetsflödeselementet **Godkänn ny kategoribegäran**.
1. Markera och håll (eller högerklicka) på arbetsflödeselementet **Steg 1** och välj sedan **Egenskaper**.
1. På sidan **Egenskaper** för arbetsflödeselementet anger du ämnestexten i fältet **Ämne för arbetsartikel**. Denna text visas som värdet i fältet **Ämne** på sidan **Arbetsobjekt som har tilldelats mig**.
1. I fältet **Arbetsuppgiftsinstruktioner** anger du instruktionstexten. Instruktionerna visas för godkännare när dessa väljer **Arbetsflöde** i åtgärdsfönstret i en kategoribegäran.
1. Välj **Tilldelning** i det vänstra fönstret.
1. På fliken **Tilldelningstyp** anger du **Tilldela användare till detta arbetsflödeselement** som *Användare*.
1. På fliken **Användare** och i listan **Tillgängliga användare** väljer du en godkännare. Välj till exempel en användare på anskaffningsavdelningen.
1. Välj höger pilknapp (**\>**) för att flytta godkännaren till listan **Valda användare**.
1. Stäng sidan **Egenskaper**.
1. Välj **Spara och stäng**.
1. Skriv anteckningar om arbetsflödet i fältet **Versionsanteckningar**.
1. Välj **OK** för att spara arbetsflödet.
1. Om du vill börja testa arbetsflödet väljer du **Aktivera den nya versionen**. Annars ska du välja **Aktivera inte den nya versionen**.
1. Välj **OK** för att slutföra konfigurationen av arbetsflödet.

> [!TIP]
> Om din myndighet inte kräver godkännande av kategoribegäranden bör du konfigurera arbetsflödet för automatiskt godkännande.

För mer information om hur du konfigurerar arbetsflöden, se [Översikt över arbetsflödessystem](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).

## <a name="create-and-submit-a-category-request"></a>Skapa och skicka en kategoriförfrågan

I det här avsnittet beskrivs hur leverantörer kan använda arbetsytan **Leverantörsinformation** för att skapa, redigera, visa och skicka kategoribegäranden.

### <a name="start-a-new-request"></a>Starta en ny begäran

Starta en ny kategoribegäran genom att följa dessa steg.

1. I arbetsytan **Leveransinformation** väljer du panelen **Kategoribegäranden**.
1. På sidan **Kategoribegäranden** väljer du **Ny kategoriförfrågan** i åtgärdsfönstret.
1. I dialogrutan **Ny kategoribegäran** letar du upp den kategori som du vill tillämpa genom att bläddra dig fram i trädet och/eller använda filtret högst upp i listan. Markera kryssrutan för respektive relevant kategori.

    Observera följande:

    - Kategorier som för närvarande är aktiva på ditt leverantörskonto visas som valda och går inte att ta bort.
    - Du kan begära flera anskaffningskategorier i en enskild kategoriförfrågan.

1. Skapa begäran om utkast genom att välja **OK**.

    Den nya utkastbegäran visas nu på sidan **Kategoribegäranden**.

1. Öppna den nya utkastförfrågan om du vill granska och redigera den efter behov.

    - Välj snabbfliken **Begärda kategorier** för att visa listan över de kategorier som för tillfället ingår i begäran.
    - Du visar aktiva kategorier genom att öppna faktaboxen **Aktiva kategorier** till höger på sidan.
    - Om du vill lägga till en kategori i begäran väljer du **Lägg till** i verktygsfältet på snabbfliken **Begärda kategorier**.
    - Om du vill ta bort en kategori från begäran väljer du kategorin på snabbfliken **Begärda kategorier** och sedan **Ta bort** i verktygsfältet.
    - Om du vill bifoga ett dokument till begäran väljer du **Bilagor** i åtgärdsfönstret. Bifogade dokument blir tillgängliga för godkännare när de granskar kategoriförfrågan.
    - Om du vill ta bort ett bifogat dokument från begäran väljer du **Bilagor** i åtgärdsfönstret. Välj det dokument du vill ta bort och sedan **Ta bort** i åtgärdsfönstret.

1. Om du är redo att skicka denna begäran väljer du **Skicka** i åtgärdsfönstret. I annat fall stänger du bara sidan och hoppar över återstående steg i den här proceduren. Du kan sedan återgå till denna begäran vid en senare tidpunkt.
1. Läs alla sändningsinstruktioner som visas och välj sedan **Skicka**.
1. I rutan **Kommentar** anger du eventuell ytterligare information som krävs. Välj sedan **Skicka** för att slutföra begäran.

### <a name="edit-a-draft-or-recalled-request"></a>Redigera ett utkast eller en återkallad begäran

Om du vill redigera en utkast- eller en återkallad kategoribegäran gör du på följande sätt:

1. I arbetsytan **Leveransinformation** väljer du panelen **Kategoribegäranden**.
1. Välj utkast eller återkallad begäran för att öppna det/den.
1. Redigera begäran efter behov och stäng den antingen sedan eller skicka den enligt beskrivningen i föregående procedur.

### <a name="submit-a-draft-or-recalled-request"></a>Skicka ett utkast eller en återkallad begäran

Om du vill skicka ett utkast eller en återkallad kategoribegäran gör du på följande sätt:

1. I arbetsytan **Leveransinformation** väljer du panelen **Kategoribegäranden**.
1. Välj det utkast eller den återkallade begäran som du vill skicka.
1. I åtgärdsfönstret väljer du **Skicka**.
1. Läs alla sändningsinstruktioner som visas och välj sedan **Skicka**.
1. I rutan **Kommentar** anger du eventuell ytterligare information som krävs. Välj sedan **Skicka** för att slutföra begäran.

    Statusvärdet för kategoriförfrågan ändras till något av följande värden:

    - _Väntar på granskning_ – Begäran finns i arbetsflödet.
    - _Väntar på godkännande_ – Godkännande krävs.

### <a name="recall-a-submitted-request-that-hasnt-yet-been-approved"></a>Återkalla en skickad begäran som ännu inte har godkänts

Om du vill återkalla en kategoribegäran som har skickats men ännu inte godkänts, följer du dessa steg.

1. I arbetsytan **Leveransinformation** väljer du panelen **Kategoribegäranden**.
1. Välj den pågående begäran som du vill återkalla.
1. Välj **Återkalla** i åtgärdsfönstret.
1. I rutan **Ange en kommentar** anger du eventuell ytterligare information som krävs. Välj sedan **Skicka** för att slutföra begäran.

    Statusen för kategoribegäran ändras till _Avbröts_. Begäran kvarstår i denna status tills du tar bort eller skickar den på nytt.

### <a name="delete-a-draft-or-recalled-request"></a>Ta bort ett utkast eller en återkallad begäran

Om du vill ta bort ett utkast eller en återkallad kategoribegäran gör du på följande sätt:

1. I arbetsytan **Leveransinformation** väljer du panelen **Kategoribegäranden**.
1. Välj det utkast eller den återkallade begäran som du vill ta bort.
1. Välj sedan **Ta bort** i åtgärdsfönstret.
1. Välj **Ja** för att bekräfta raderingen.

### <a name="view-completed-requests"></a>Visa slutförda begäranden

Om du vill visa slutförda begäranden öppnar du arbetsytan **Leverantörsinformation** och väljer panelen **Kategoribegäranden**. Kategoribegäranden som har slutförts får någon av följande statusar:

- _Godkänd_ – Begäran godkändes. Om du vill visa nya kategorier som har lagts till går du tillbaka till arbetsytan **Leverantörsinformation**, öppnar listrutan **Mer information** i vänstra fönstret, och väljer sedan **Kategorier**.
- _Avvisat_ – Begäran har avvisats. Du kan skapa en ny kategoribegäran efter behov.

## <a name="review-category-requests"></a>Granska kategoribegäranden

I det här avsnittet beskrivs hur du godkänner, avslår och delegerar kategoribegäranden som leverantörer har skickat, och hur du visar slutförda begäranden. Dessa arbetsflödesåtgärder gäller för hela kategoriförfrågan.

### <a name="view-category-requests"></a>Visa kategoribegäranden

Visa en ny kategoribegäranden genom att följa dessa steg:

1. Gå till **Anskaffning och inköp \> Leverantörer \> Begäranden om samarbete mellan leverantörer \> Kategoribegäranden**.

    Sidan **Kategoribegäranden** visas. På standardsidan visas kategoribegäranden som har statusvärdet *Inväntar åtgärd*.

1. Om du vill visa alla begäranden väljer du *Alla* i fältet **Visa förfrågningar**.
1. Öppna en begäran om du vill granska och redigera den efter behov.

    - Välj snabbfliken **Begärda kategorier** för att visa listan över de kategorier som för tillfället ingår i begäran.
    - Du visar aktiva kategorier genom att öppna faktaboxen **Aktiva kategorier** till höger på sidan.
    - Om dokument har skickats visar knappen **Bilagor** (gem) i åtgärdsfönstret antalet kopplade dokument. Om du vill visa bifogade dokument väljer du knappen **Bilagor**. Markera sedan dokumentet som du vill visa och välj **Öppna** om du vill visa det.
    - Om du vill bifoga ett dokument till begäran väljer du **Bilagor** i åtgärdsfönstret. Bifogade dokument blir tillgängliga för godkännare när de granskar kategoriförfrågan.
    - Om du vill ta bort ett bifogat dokument från begäran väljer du **Bilagor** i åtgärdsfönstret. Välj det dokument du vill ta bort och sedan **Ta bort** i åtgärdsfönstret.
    - Välj **Arbetsflöde** i åtgärdsfönstret för att visa arbetsflödeshistoriken. Välj **Mer** och sedan **Arbetsflödeshistorik** bland alternativen för arbetsflödeshistorik. Sidan **Arbetsflödeshistorik** visas.

### <a name="approve-a-pending-category-request"></a>Godkänn en väntande kategoriförfrågan

Om du vill godkänna en pågående kategoribegäran följer du dessa steg.

1. Gå till **Anskaffning och inköp \> Leverantörer \> Begäranden om samarbete mellan leverantörer \> Kategoribegäranden**.
1. Välj den pågående begäran som ska godkännas.
1. Granska kategoribegäranden.
1. Valfritt: Välj en orsakskod på snabbfliken **Allmänt** > fältet **Orsakskod**. I fältet **Orsakskommentar** anger du sedan en kommentar angående orsakskoden.
1. Klicka på **Arbetsflöde** i åtgärdsfönstret.
1. Välj **Godkänn** bland arbetsflödesalternativen.
1. I fältet **Kommentar** anger du eventuell ytterligare information som krävs. Välj sedan **Godkänn** för att slutföra begäran.

    Statusvärdet för kategoriförfrågan ändras till _Godkänd_ och anskaffningskategorierna läggs till på leverantörskontot.

### <a name="reject-a-pending-category-request"></a>Avvisa en väntande kategoriförfrågan

Om du vill avvisa en pågående kategoribegäran följer du dessa steg.

1. Gå till **Anskaffning och inköp \> Leverantörer \> Begäranden om samarbete mellan leverantörer \> Kategoribegäranden**.
1. Välj den pågående begäran som ska avvisas.
1. Granska kategoribegäranden.
1. I åtgärdsfönstret väljer du **Redigera**.
1. I snabbfliken **Allmänt** väljer du en orsakskod i fältet **Orsakskod**. I fältet **Orsakskommentar** anger du sedan en kommentar angående orsakskoden.
1. Klicka på **Spara** i åtgärdsfönstret.
1. Klicka på **Arbetsflöde** i åtgärdsfönstret.
1. Välj **Mer** och sedan **Avvisa** bland alternativen för arbetsflöde.
1. I fältet **Kommentar** anger du eventuell ytterligare information som krävs. Välj sedan **Avvisa** för att slutföra begäran.

    Statusen för kategoribegäran ändras till _Avvisades_. Vid den här tidpunkten kan leverantören skapa en ny kategoribegäran efter behov.

### <a name="delegate-a-pending-category-request"></a>Delegera en väntande kategoriförfrågan

Om du vill delegera en pågående kategoribegäran till en annan användare gör du så här:

1. Gå till **Anskaffning och inköp \> Leverantörer \> Begäranden om samarbete mellan leverantörer \> Kategoribegäranden**.
1. Välj den pågående begäran som du vill godkänna.
1. Klicka på **Arbetsflöde** i åtgärdsfönstret.
1. Välj **Mer** och sedan **Delegera** i alternativen för arbetsflöde.
1. I fältet **Användare** väljer du den användare som du vill tilldela kategoribegäran till för granskning.
1. I fältet **Kommentar** anger du eventuell ytterligare information som krävs.
1. Välj **Delegera** för att slutföra delegeringen. Den valda användaren kan nu granska kategoriförfrågan.

### <a name="view-procurement-categories-for-a-vendor"></a>Visa anskaffningskategorier för en leverantör

Följ dessa steg om du vill visa anskaffningskategorier för en leverantör efter det att en kategoribegäran har godkänts.

1. Gå till **Anskaffning och källa \> Leverantörer \> Alla leverantörer**.
1. På sidan **Alla leverantörer** väljer du den leverantör som du vill visa anskaffningskategorier för.
1. I åtgärdsfönstret öppnar du fliken **Allmänt**, och i gruppen **Inställningar** väljer du **Kategorier**.

    Sidan **Kategorier** visas. På snabbfliken **Anskaffning** visas anskaffningskategorier som har lagts till via kategoriförfrågan.

1. På snabbfliken **Anskaffning** kan du göra ändringar om det behövs. Du kan till exempel ställa in fältet **Status för leverantörskategori** som _Prioriterat_.
