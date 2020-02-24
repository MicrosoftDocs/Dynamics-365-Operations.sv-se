---
title: Lägga till en sida med sekretesspolicy
description: I det här avsnittet beskrivs hur du lägger till en sida med sekretesspolicy till din webbplats i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ee9a68f46c91299065732e5f65479906f9e06079
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001333"
---
# <a name="add-a-privacy-policy-page"></a>Lägga till en sida med sekretesspolicy


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till en sida med sekretesspolicy till din webbplats i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Sekretessefterlevnad omfattar organisatoriska åtgärder som informerar webbplatsanvändarna om hur deras data samlas in och hanteras. Användarna kan sedan bestämma hur de vill att deras personuppgifter ska hanteras och kan vidta lämpliga åtgärder.

## <a name="review-the-microsoft-privacy-statement-in-dynamics-365-commerce"></a>Granska Microsofts sekretesspolicy i Dynamics 365 Commerce

Om du vill granska Microsofts sekretesspolicy när du är inloggad på Dynamics 365 Commerce redigeringsverktygen väljer du knappen **hjälp** (**?**) i det övre högra hörnet och väljer sedan **sekretess och cookies**. En ny flik öppnas som har en länk till [Microsofts sekretesspolicy](https://privacy.microsoft.com/privacystatement).

## <a name="build-a-privacy-policy-page-for-your-site"></a>Skapa en sekretesspolicysida för din webbplats

I Dynamics 365 Commerce finns det flera sätt att ge användare av din webbplats tillgång till din sekretesspolicy. Det här avsnittet visar hur du skapar en sekretesspolicysida och sedan referera till sidan med hjälp av ett sidfotavsnitt.

Vägledningen som följer är ett exempel som visar hur du skapar en generisk sekretesspolicysida för en Commerce-webbplats. Du är ansvarig för att utforma och implementera en lösning för sekretesspolicysida som bäst uppfyller ditt företags juridiska krav.

Starta i redigeringsverktyg, gå till den webbplats som du vill skapa en sekretesspolicysida för.

### <a name="create-a-template"></a>Skapa en mall

> [!NOTE]
> Om en mall som kan användas för sekretesspolicysidan redan har skapats, gå vidare till avsnittet [skapa en sekretesspolicysida](#build-a-privacy-policy-page).

Gör så här om du vill skapa en arbetsmall.

1. Gå till **Mallar \> Ny mall**.
1. Ange mallnamn och klicka sedan på **OK**.
1. I mallen lägger du till nödvändiga moduler till de obligatoriska sidfacken. För vägledning håller du muspekaren över de röda utropstecknen.

    Till exempe facket **HTML-rubrik** kräver en **extern standardskript**-modul.

1. I facket **Brödtext**, lägg till en **standardsid**-modul.
1. I **standardsid**-modulen, i facket **Huvud**, lägg till en **Innehållsrikt block**-modul.
1. I **Innehållsrikt block**-modulen lägger du till en **innehållsrika blockobjekt**-modul.
1. Checka in mallen och publicera den.

### <a name="build-a-privacy-policy-page"></a>Skapa en sida med sekretesspolicy

Gör så här om du vill skapa en sekretesspolicysida.

1. Gå till **Sidor \> Ny sida**.
1. Välj mallen för sidan sekretesspolicy.
1. Ange ett sidnamn och en URL och klicka sedan på **OK**. 
1. Lägg till platsen **Huvud** på ny sida, lägg till en **innehållsrik block**-modul.
1. I **Innehållsrikt block**-modulen lägger du till en **innehållsrika blockobjekt**-modul.
1. I egenskapsfönstret för **innehållsrik block**-modulen, välj **Lägg till data källa** och välj sedan **RTF-innehåll**.
1. I RTF-redigeraren anger du innehållet för sidan sekretesspolicy. Expandera RTF-redigeraren till helskärmsläge som du behöver.
1. När du är klar med att ange innehåll väljer du **förhandsgranska** för att förhandsgranska sidan i webbläsaren.
1. Slutför eventuella återstående tillägg till sid- och modulegenskaperna.
1. Checka in sidan sekretesspolicy och publicera den.

För att publicera URL för sidan sekretesspolicy, följ dessa steg.

1. Gå till **URL:er** och välj webbadressen till sidan sekretesspolicy.
1. Publicera markerade URL.

### <a name="create-a-link-to-the-privacy-policy-page-in-a-footer"></a>Skapa en länk till sidan sekretesspolicy i en sidfot

Du kan lägga till en länk till sidan sekretesspolicy till ett fragment. På så sätt kan du dela länken och uppdatera den över flera webbplatssidor genom att referera till fragmentet. I det här exemplet visas hur du lägger till en länk till sidan sekretesspolicy i ett sidfotavsnitt.

Om du vill lägga till en länk till ett sidfotavsnitt gör du följande.

1. Gå till **Sidfragment \> Nytt sidfragment**.
1. Markera **sidfot**-modulen och ange sedan ett namn i fältet **sidfragmentets namn**.
1. I facket **Sidfotskategori**, lägg till en **sidfotsartikel**-modul.
1. I egenskapsrutan till höger, välj egenskapen **Länktext**.
1. I dialogrutan **länktext** anger du länktexten och länkmålet för sidan sekretesspolicy och klickar sedan på **OK**.

    Om du vill hämta webbadressen till sidan sekretesspolicy går du till **sidor** går till sidan sekretesspolicy och kopierar webbadressen från fönstret Egenskaper.

1. Spara fragmentet, checka in det och publicera det.
1. Förhandsgranska fragmentet och testa länken till sidan sekretesspolicy.

Fragmentet kan nu refereras i mallen för andra webbplatssidor. När det här fragmentet refereras i **sidfoten** i en modul för en mall visas länkreferensen på alla sidor som har skapats med den mallen.

## <a name="additional-resources"></a>Ytterligare resurser

[Regelefterlevnad – översikt](compliance-overview.md)

[Hjälpmedelsfunktioner](accessibility.md)

[Cookie-kompatibilitet](cookie-compliance.md)
