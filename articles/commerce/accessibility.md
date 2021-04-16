---
title: Hjälpmedelsfunktioner
description: Det här avsnittet innehåller information om hjälpmedelsfunktioner i olika versioner av Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 13f035a080eb41b4a69cc31b7275d87a5836c686
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5796328"
---
# <a name="accessibility-features-and-capabilities"></a>Hjälpmedelsfunktioner och möjligheter

[!include [banner](includes/banner.md)]

Det här avsnittet innehåller information om hjälpmedelsfunktioner i olika versioner av Microsoft Dynamics 365 Commerce.

Hjälpmedelsfunktioner ger de funktionella medel för alla användare att komma åt och utföra åtgärder så att de kan uppnå sina mål. Detta breda spektrum av användare kan behöva hjälpmedelsverktyg för hörsel, syn, mobilitet eller neuromångfald.

Olika funktioner i Dynamics 365 Commerce låter dig bygga din webbplats så att den innehåller hjälpmedelsfunktioner. När du utformar webbplatsen bör du ta hänsyn till de tillgänglighetsfunktioner som nämns i [Microsoft Accessibility Center](https://www.microsoft.com/accessibility). 

I det här avsnittet beskrivs några ytterligare områden med hjälpmedelsfunktioner som du bör tänka på när du använder Dynamics 365 Commerce.

## <a name="image-alt-text"></a>Bild alt text

Dynamics 365 Commerce har ett inbyggt system för digital tillgångshantering för att spåra bild- och videotillgångar som används på din webbplats. Bildtexter, beskrivningar och alt text kan läggas till i fönstret Egenskaper för en bild när den markeras eller överförs.

## <a name="video-accessibility"></a>Videohjälpmedel

Dynamics 365 Commerce system för digital tillgångshantering stöder flera hjälpmedelsfunktioner för videoinnehåll. Några exempel anges i följande tabell.

| Video-funktionen               | Beskrivning |
|-----------------------------|-------------|
| Dold undertextning (CC)      | Text som kan visas för ljud- och ljudbeskrivande delar av en video, för att hjälpa användare som är döva eller hörselskadade |
| Underrubriker                   | Textningsfiler som visar texten i kontext ledtrådar eller dialogrutan på skärmen |
| Ljudutskrifter           | En textutskrift av talade ord som genereras från ljudet av en videotillgång |
| Beskrivande ljud           | En icke-primär ljudkanal som beskriver innehållet eller kontexten som förekommer på skärmen |
| Minimiålder            | Ett attribut som kan lagra den lägsta ålder som en tittare måste ha för att visa en video (endast metadata) |

### <a name="configure-video-accessibility-elements"></a>Konfigurera hjälpmedelselement för video

I Commerce, avsnittet **Mediebibliotek** för din webbplats kan du överföra videotillgångar som har separata filer för textning, vanligt ljud och beskrivande ljud. Dold textning kan också genereras automatiskt när en videotillgång laddas upp.

#### <a name="generate-or-upload-closed-caption-files-during-video-asset-upload"></a>Generera eller ladda upp filer med dold textning vid uppladdning av videotillgångar

Om du vill att en fil med dold textning ska skapas automatiskt när du laddar upp en video följer du det här steget.

- I dialogrutan **Överför tillgång**, välj **Generera automatiskt stängda bildtexter**. Om du skapar en fil med dold textning kommer filväljaren för filer med dold textning inte att vara tillgänglig i dialogrutan.

Om du vill överföra en fil med dold textning manuellt när du överför en video följer du det här steget.

- I dialogrutan **Överför tillgång**, avmarkera **Generera automatiskt stängda bildtexter**.

Om du vill överföra vanliga ljud- eller beskrivande ljudfiler för videoklippet använder du filväljaren i dialogrutan **Överför tillgång**.

> [!NOTE]
> Dold textning, regelbundet ljud och beskrivande ljudtillgångar kan också läggas till när en videotillgång har laddats upp. Gå till **Mediebibliotek**, välj videotillgången och välj **Redigera** för att checka ut den, sedan i fönstret Egenskaper överför videotillgången, ladda upp ytterligare tillgångar.

#### <a name="edit-cc-and-audio-transcript-files"></a>Redigera CC och ljudavskriftsfiler

CC och ljudavskriftsfiler kan redigeras direkt i redigeringsverktyg. Videouppspelning är tillgängligt under redigering.

Gör så här om du vill redigera CC och ljudavskriftsfiler.

1. Gå till **mediebiblioteket** och välj filnamn på videotillgången. Innehållsredigeraren för dold textning och avskrift visas.
1. Välj **Redigera**.
1. Redigera texten för dold textning eller avskrift.
1. När du är klar, välj **Spara**, och välj sedan **Slutför redigering**.
1. När du är redo att publicera väljer du **publicera**.

#### <a name="set-the-minimum-age-attribute"></a>Ange minimiåldersattribut

Ett metadataattribut för **minimiålder** kan associeras med videotillgångar.

Gör så här om du vill ange attributet för **minimiålder** för en videotillgång.

1. Gå till **Mediebibliotek** och välj videotillgången.
1. Välj **Redigera**.
1. Ange attributet **minimiålder** i fönstret Egenskaper för videotillgången.

> [!NOTE]
> Fönstret Egenskaper används bara för att ange och lagra attributvärdet metadata. Anpassade moduler måste skapas för att använda det här attributet för uppspelning.

## <a name="additional-resources"></a>Ytterligare resurser

[Hjälpmedel i formulär, produkter och kontroller](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/user-interface/enable-accessibility)

[Microsoft Accessibility Center](https://www.microsoft.com/accessibility)

[Dynamics 365 Accessibility Center](https://docs.microsoft.com/dynamics365/get-started/accessibility/index)

[Regelefterlevnad – översikt](compliance-overview.md)

[Cookie-kompatibilitet](cookie-compliance.md)

[Lägga till en sida med sekretesspolicy](add-privacy-page.md)

[Ersätt användar-ID:n som är associerade med spårade innehållsändringar](replace-IDs-tracked-changes.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
