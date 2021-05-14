---
title: Bädda in tredjepartsprogram
description: Det här avsnittet förklarar hur du bäddar in tredjepartsappar i syfte att utöka produktens funktionalitet.
author: jasongre
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, UserWorkspaceAdd, UserWorkspaceConfigureWebsite
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2021-04-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: d348683e0a2ed35f26830a6ce05c0bf9ca5970bd
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944858"
---
# <a name="embed-third-party-apps"></a>Bädda in tredjepartsprogram

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Många kunder använder en mängd olika program för att driva sin verksamhet. Vissa av programmen är webbprogram från tredje part som fungerar tillsammans med Finance and Operations-program. Om du vill tillhandahålla en mer sömlös användarupplevelse kan du använda funktionen **(Förhandsgranska) Helsidesappar** för att bädda in dessa tredjepartsappar direkt i dina Finance and Operations-appar (förutsatt att tredjepartapparna medger detta). På det här sättet kan användarna komma åt de webbplatser och program som de behöver utan att behöva byta flikar eller fönster.

Innan du kan bädda in tredjepartappar i produkten måste du aktivera funktionen **(Förhandsgranska) Helsidesappar** i funktionsadministreringen. Du kan sedan använda någon av följande metoder för att bädda in en app eller webbplats från tredje part. Dessa metoder överensstämmer med de metoder som används för att bädda in arbetsyteappar från Microsoft Power Apps till Finance and Operations-program.

- Bädda in appen eller webbplatsen på en befintlig sida som en ny fliksida (pivot-flik, snabbflik, blad eller arbetsyta).
- Skapa en ny helsidesupplevelse för programmet eller webbplatsen från instrumentpanelen.

## <a name="embed-a-website-on-an-existing-page"></a>Bädda in en webbplats på en befintlig sida

Använd denna procedur om du vill göra tillägg till en befintlig sida i systemet med ett inbäddat program.

1. Öppna sidan där du vill bädda in appen.
2. Öppna fönstret **Lägg till en app**:

    1. Välj **Inställningar** och sedan **Anpassa** för att öppna verktygsfältet **Anpassning**.
    2. Välj **Mer \> Lägg till en app**.

3. Välj den del av sidan där du vill lägga till appen. Denna del måste vara en *flikbehållare* för en pivot-flik, en snabbflik, ett blad eller ett avsnitt av en arbetsyta.
4. Välj **webbplats**.
5. Konfigurera inbäddade appen:

    - **Namn** – Ange den text som ska visas för fliken som innehåller den inbäddade appen. Ofta ska den här texten utgöra appens namn.
    - **URL** – Ange platsen för appen.

    > [!IMPORTANT]
    > - Av säkerhetsskäl måste URL:en använda Hypertext Transfer Protocol Secure (HTTPS).
    > - Programmet eller webbplatsen måste vara konfigurerat för att det ska vara tillåtet att bädda in det.

6. Välj **Spara** för att bädda in appen på sidan. Appen läggs till som sista flik eller avsnitt i gruppen.
7. Bekräfta att programmet visas som förväntat. Om programmet inte återges hittar du mer information i avsnittet [Felsökning](#troubleshooting) senare i det här ämnet.
8. Öppna visningsväljaren och välj antingen **Spara** (om programmet ska associeras med den aktuella vyn) eller **Spara som** (för att spara appen i en annan vy).

    Om sidan inte har någon visningsväljare (om sidan till exempel är en dialogruta eller en arbetsyta) kan du hoppa över det här steget.

## <a name="embed-a-website-as-a-full-page-experience-from-the-dashboard"></a>Bädda in en webbplats som en fullständig användarupplevelse från instrumentpanelen

Använd den här proceduren om programmet som du vill bädda in inte är relaterat till en befintlig sida eller om du bara vill ha en helsidesupplevelse för appen inuti Finance and Operations-programmet.

1. Öppna instrumentpanelen.
2. Markera och håll ned (eller högerklicka) på sidan, välj **Anpassa** och välj sedan **Lägg till en sida**.
3. I fönstret **Lägg till en sida** väljer du **Webbplats**.
4. Konfigurera inbäddade appen:

    - **Namn** – Ange texten som ska visas på panelen som har lagts till för det inbäddade programmet på instrumentpanelen. Ofta ska den här texten utgöra appens namn.
    - **URL** – Ange platsen för appen.

    > [!IMPORTANT]
    > - Av säkerhetsskäl måste URL:en använda HTTPS.
    > - Programmet eller webbplatsen måste vara konfigurerat för att det ska vara tillåtet att bädda in det.

5. Välj **Spara** om du vill lägga till programmet i instrumentpanelen som en ny panel.
6. Markera den nya panelen på instrumentpanelen och bekräfta att programmet visas som förväntat. Om programmet inte återges hittar du mer information i avsnittet [Felsökning](#troubleshooting) senare i det här ämnet.

## <a name="sharing-embedded-apps"></a>Dela inbäddade appar

När du har bäddat in ett program med en av metoderna som beskrivs i de föregående avsnitten, kanske du vill dela vyn med andra användare i systemet. Om du vill dela ett inbäddat program använder du någon av följande metoder:

- **Publicera vyn (rekommenderas):** Om det inbäddade programmet har sparats i en vy bör du publicera den för användare med rätt säkerhetsroller. På så sätt kommer alla användare som innehar de säkerhetsroller som den publicerade vyn riktar in sig på att se appen i Finance and Operations-appar. Mer information om hur du publicerar en vy finns i [Publicera vyer](saved-views.md#publishing-views).

    Du kan också publicera ett program som har bäddats in som en helsiderfarenhet från instrumentpanelen. Markera och håll (eller högerklicka) den panel som är kopplad till programmet på instrumentpanelen, välj **Anpassa** och sedan **Publicera sida**. Du kan för tillfället endast publicera i säkerhetsroller. Möjligheten att publicera till juridiska personer läggs emellertid till innan funktionen blir allmänt tillgänglig.

- **Kopiera anpassningen:** För sidor som inte har stöd för vyer (till exempel dialogrutor eller arbetsytor) eller för en helsides-apperfarenhet kan du kopiera anpassningen till lämpliga användare. Mer information finns i [Dela anpassningar](personalize-user-experience.md#sharing-personalizations).

## <a name="viewing-embedded-apps"></a>Visa inbäddade appar

Om du vill visa en inbäddad app på en sida i Finance and Operations-appar öppnar du sidan där den inbäddad appen finns. Kom ihåg att inbäddade appar kan nås på vissa sidor med hjälp av knappen **Power Apps** i det vanliga åtgärdsfönstret. Alternativt kan de komma att visas direkt på sidan som en ny flik, snabbflik, blad eller ett nytt avsnitt på en arbetsyta.

## <a name="editing-or-removing-embedded-apps"></a>Redigera eller ta bort inbäddade program

När en app har bäddats in på en sida kanske du måste redigera dess konfiguration (till exempel genom att ändra avsnittsetiketten eller URL-adressen). Du kanske också måste ta bort den från sidan. Använd någon av följande procedurer när du vill redigera konfigurationen för ett inbäddat program eller ta bort det helt.

### <a name="apps-that-are-embedded-on-existing-pages"></a>Program som bäddas in på befintliga sidor

1. Öppna sidan där appen bäddats in.
2. Välj **Inställningar** och sedan **Anpassa** för att öppna verktygsfältet **Anpassning**.
3. Välj verktyget **Välj** och sedan det inbäddade programmet.
4. Om du vill redigera programmet gör du nödvändiga ändringar i konfigurationen och väljer sedan **Spara**.

    Du kan även ta bort programmet genom att välja **Ta bort**.

5. Spara eller publicera vyn på nytt. Observera att om du lämnar sidan utan att explicit spara vyn, så bibehålls inte någon av de åtgärder som du utför i fönstret **Redigera webbplats**.

### <a name="apps-that-are-embedded-from-the-dashboard"></a>Program som bäddas in från instrumentpanelen

1. Öppna instrumentpanelen.
2. Markera och håll (eller högerklicka) den panel som är kopplad till det inbäddade programmet, och välj sedan **Anpassa**.
3. Om du vill redigera programmet väljer du **Redigeringssidan**. I fönstret **Redigera webbplats** utför du nödvändiga ändringar i programkonfigurationen och väljer sedan **Spara**.

    Du kan även ta bort programmet genom att välja **Ta bort sida**.

## <a name="appendix"></a>Bilaga

### <a name="troubleshooting"></a>Felsökning

Om en webbplats inte återges på rätt sätt efter det att den bäddats in i en Finance and Operation-app, eller om du får ett felmeddelande om att URL:en har nekats en anslutning, är webbplatsen troligen konfigurerad för att förhindra att den bäddas in i en iFrame. Följ anvisningarna nedan för att ta reda på om webbplatsen kan bäddas in.

1. Öppna utvecklingsverktygen för den webbläsare du använder.
2. I fliken **Nätverk** söker du upp och väljer svaret från den inbäddade webbplatsen.
3. På fliken **Rubriker**, under **Svarsrubriker**, letar du upp **Alternativ för x-frame**. Om **Alternativ för x-frame** finns i svarsrubrikerna och har värdet **DENY** eller **SAMEORIGIN** kan webbplatsen inte bäddas in på korrekt sätt. Du måste samarbeta med programmets ägare för att den ska gå att bädda in säkert.

### <a name="developer-modeling-a-website-on-a-form"></a>[Utvecklare] Basera en webbplats på ett formulär

Även om det här avsnittet är fokuserat på inbäddade tredjepartsprogram eller webbplatser via anpassning kan utvecklare också bädda in dem i ett formulär genom att använda utvecklarupplevelsen Visual Studio. Lägg bara till en **WebsiteHostControl**-kontroll i formuläret. Metadataegenskaperna som finns i kontrollen ger samma funktioner som anpassningsupplevelsen.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
