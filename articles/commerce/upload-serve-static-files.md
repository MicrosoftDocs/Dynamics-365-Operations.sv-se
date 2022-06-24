---
title: Ladda upp och hantera statiska filer
description: I denna artikel beskrivs hur du överför en statisk fil till webbplatsskaparen för Microsoft Dynamics 365 Commerce, samt hur du skapar en anpassad URL och ett filnamn som kan användas för att begära den filen.
author: StuHarg
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: a1b14feba1466c3a5efc3b0ea66f20e9e818a8a5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8885332"
---
# <a name="upload-and-serve-static-files"></a>Ladda upp och hantera statiska filer

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du överför en statisk fil till webbplatsskaparen för Microsoft Dynamics 365 Commerce, samt hur du skapar en anpassad URL och ett filnamn som kan användas för att begära den filen.

Vissa anslutningar från tredje part kräver att en fil hanteras och servas från näthandelssajten. Dessa anslutningsprogram förväntar sig att filen ska returneras av begäranden till en viss URL-sökväg och ett visst filnamn för motringning. Därför förklarar denna artikel hur du överför och betjänar en statisk fil som har en användardefinierbar URL och ett filnamn på en Dynamics 365 Commerce-näthandelssajt.

## <a name="create-a-site-url-that-returns-a-static-file"></a>Skapa en webbplats-URL som returnerar en statisk fil

Om du vill skapa en webbplats-URL som returnerar en statisk fil i Commerce-webbplatsbyggaren följer du stegen nedan.

1. Gå till mediebiblioteket för din webbplats och överför filen som ska betjänas av begäranden till den URL som du ska definiera. Om du redan har överfört filen kan du hoppa över det här steget.
1. Gå till **URL:er** för webbplatsen.
1. Välj **Nytt \> Ny URL**.
1. I dialogrutan **Ny URL** väljer du **Mediebibliotekstillgång**.
1. I fältet **URL-sökväg** anger du URL:en på nytt. Inkludera filnamnet i sökvägen.
1. Välj **Nästa**. Mediebiblioteket öppnas och visar alla medietillgångar tillhörande den **dokument** typ som har överförts.
1. Markera den fil som ska betjänas för begäranden till den URL som du definierade i steg 5.
1. Välj **Spara**.

I det här läget har den URL som du skapade statusen "utkast". Filen som URL:en pekar mot kommer inte att returneras förrän URL:en publiceras. Innan du publicerar URL:en kan du validera att den returnerar rätt data.

## <a name="validate-and-publish-a-url"></a>Validera och publicera en URL

Följ dessa steg om du vill validera en URL innan du publicerar den.

1. Gå till **URL:er** för webbplatsen och välj den URL som ska förhandsgranskas.
2. I egenskapsfönstret till höger, under knappen **Redigera**, väljer du korrekt URL-länk. Ett nytt webbläsarfönster öppnas och felmeddelandet 404 visas.
3. Lägg till frågesträngen **?preview=inprogress** i URL:en (t. ex. `https://yoursite.com/callback.html?preview=inprogress`) och läs in sidan igen. Filen som du överförde till mediebiblioteket ska returneras i svaret.

När du har validerat URL:en kan du publicera den.

1. Gå till **URL:er** för webbplatsen och välj URL:en.
2. Välj **publicera** i kommandofältet.

## <a name="update-the-file-that-a-url-points-to"></a>Uppdatera filen som en URL pekar mot

När en URL publiceras kan du uppdatera den så att den pekar mot en annan fil. Du kan också uppdatera URL:en så att den pekar mot en annan typ av resurs, enligt beskrivningen i nästa avsnitt. Du kan till exempel rikta URL:en mot en intern sida eller en omdirigering.

Om du vill uppdatera filen som en URL pekar mot följer du dessa steg.

1. Gå till **URL:er** för din webbplats och välj den URL som ska uppdateras.
1. I egenskapsrutan till höger, välj egenskapen **Redigera**.
1. Under **URL-tilldelning** markerar du rutan **Steg 2** och väljer sedan ett nytt dokument i mediebiblioteket.
1. Välj **Tillämpa**.

## <a name="update-the-asset-type-that-a-url-points-to"></a>Uppdatera den tillgångstyp som en URL pekar mot

Du kan också uppdatera en URL så att den pekar mot en annan typ av tillgång (resurs), t. ex. en intern sida eller en omdirigering.

Om du vill uppdatera tillgångstypen som en URL pekar mot följer du dessa steg.

1. Gå till **URL:er** för din webbplats och välj den URL som ska uppdateras.
1. I egenskapsrutan till höger, välj egenskapen **Redigera**.
1. Under **URL-tilldelning** väljer du ett annat tillgångsnamn under **Steg 1**.
1. Markera rutan **Steg 2** och välj sedan den nya tillgången.
1. Välj **Tillämpa**.

## <a name="change-the-url-path"></a>Ändra URL-sökvägen

När en URL har skapats kan dess sökväg inte ändras. Om du måste ändra URL-sökvägen som används för en fil eller någon annan typ av resurs måste du skapa en ny URL, mappa den till den befintliga filen eller en annan resurs och sedan ta bort publiceringen samt den gamla URL:en.

För att ändra URL-sökväg, följ stegen nedan.

1. Om du vill skapa en ny URL och mappa den till den befintliga filen eller en annan resurs följer du instruktionerna i avsnittet [Skapa en webbplats-URL som returnerar en statisk fil](#create-a-site-url-that-returns-a-static-file) tidigare i denna artikel.
1. Markera den nya URL:en och välj **Publicera** i kommandofältet. Den nya URL:en publiceras.
1. Om du vill ta bort den gamla URL:en markerar du den och väljer sedan **Ta bort** i kommandofältet. Du kan nu ta bort den gamla URL:en om du vill.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av digital Tillgångshantering](dam-overview.md)

[Överför bilder](dam-upload-images.md)

[Överför videor](dam-upload-video.md)

[Överför andra filer än bilder och videor](dam-upload-files.md)

[Beskär bilder](dam-crop-images.md)

[Anpassa bildens fokuspunkter](dam-custom-focal-point.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]