---
title: Arbeta med CSS-åsidosättningsfiler
description: Det här avsnittet beskriver varför, när och hur du använder Cascading Style Sheets (CSS) åsidosätta filer i Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-12-12
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 41fb0be51f7af25faba1b860319aea84ae7a8b56
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207809"
---
# <a name="work-with-css-override-files"></a>Arbeta med CSS-åsidosättningsfiler


[!include [banner](includes/banner.md)]

Det här avsnittet beskriver varför, när och hur du använder Cascading Style Sheets (CSS) åsidosätta filer i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Permanenta webbplatsstilar bör vanligtvis hanteras via webbplatsens tema. Teman ger grundläggande CSS och stilinställningar för modulerna på alla sidor på din webbplats. Teman skapas med hjälp av Dynamics 365 Commerce online Software Development Kit (SDK) och de distribueras till dina webbplatser via Microsoft Dynamics Lifecycle Services (LCS). Tema felsökningsfunktioner och konfigurationer av modulgränssnitt i SDK hjälp webbplatsutvecklare skapar anpassningsbara och sammanhängande designpaket för webbplatsen. När dessa designpaket distribueras till en webbplats kan webbplatsförfattarna fokusera på att skapa, redigera och publicera innehåll i stället för webbplatsutveckling.

Med tanke på den vanliga livscykeln för ett tema kan beroendet för utvecklare att göra formatändringar via SDK och LCS distributionspipeline vara oöverkomliga i vissa fall. Webbplatsprototyper eller snabbkorrigeringar kan verka omständligt om SDK inte har konfigurerats eller om du inte har tid att vänta på en LCS-distribution.

I dessa fall kan CSS åsidosätta filer hjälpa. I Commerce redigeringsverktyg kan autentiserade användare ladda upp en CSS-fil, förhandsgranska den och sedan aktivera den för att åsidosätta webbplatsens tema. Omkostnader för SDK- eller LCS-distribution krävs inte. Åsidosättningar som anges i en CSS åsidosättningfil kan vara så liten som en ändring i en enda textstil eller så vittomfattande som en fullständig varumärkesöversyn.

Innan du använder CSS åsidosättningsfiler bör du vara medveten om följande begränsningar:

- Endast en CSS åsidosättningfil kan vara aktiv på en plats i taget. Därför måste alla aktiva åsidosättningar finnas i en enda åsidosättningfil.
- Även om du kan förhandsgranska åsidosättningarna i Commerce redigeringsverktygen finns det inga särskilda felsökningsfunktioner som hjälper dig att identifiera eventuella buggar som åsidosättningarna introducerar. Med andra ord, när du använder CSS åsidosättningsfiler, har du inte samma verktygsuppsättning som SDK ger för modul och redigeringsvalidering.

CSS åsidosätta filer ger dock ett snabbt sätt att göra en prototyp av en design eller implementera en snabbkorrigering innan en fullständig temauppdatering har utvecklats och distribuerats.

## <a name="create-a-css-override-file"></a>Skapa en CSS åsidosättningfil

Om du vill skapa en CSS åsidosättningfil kan du använda valfri integrerad utvecklingsmiljö (IDE), textredigerare eller källkodsredigerare. Ett typiskt tillvägagångssätt är att använda vanliga webbfelsökare i din webbläsare för att identifiera stilväljare, egenskaper och värden på din befintliga webbplats. I de flesta webbläsare kan du ändra värden och förhandsgranska dem i felsökaren. När du har identifierat de ändringar du vill göra kan du spara dem i din egen CSS-fil.

## <a name="upload-a-css-override-file"></a>Överför en CSS åsidosättningfil

Så här överför du en CSS-fil till din webbplats i Commerce.

1. I redigeringsverktygen går du till webbplatsen.
1. I navigeringsfönstret till vänster, välj **Design**.

    > [!NOTE]
    > Beroende på vilken version av Commerce redigeringsverktyg du använder kan du behöva expandera **inställningarna** i navigeringsfönstret innan du kan välja **design**.

1. Överst i huvuddesignfönstret väljer du fliken **CSS åsidosätt** om den inte redan är markerad.
1. Under **tillgängliga CSS åsidosättningar** väljer du **överför CSS-fil**. Ett filwebbläsarfönster visas.
1. I Utforskaren bläddrar du till och väljer en CSS-fil och väljer sedan **öppna** Den överförda CSS-filen visas nu under **tillgängliga CSS åsidosättningar**.

## <a name="preview-a-css-override-file"></a>Förhandsgranska en CSS åsidosättningfil

För att förhandsgranska en CSS åsidosättningfil innan du gör den aktiv på din aktiva webbplats.

1. I navigeringsfönstret till vänster väljer du **design** och sedan på fliken **CSS åsidosätt** under **tillgängliga CSS åsidosättningar**, leta upp CSS-filen som du vill förhandsgranska.
1. Bredvid CSS filnamnet, välj **förhandsgranska webbplats**.
1. I dialogrutan **Välj en URL** väljer du URL-adressen till den webbplats som du vill visa åsidosättningen för och väljer sedan **OK**.
1. Om det finns flera varianter för den valda webbadressen väljer du önskad variant i dialogrutan **Förhandsgranska variationer** som visas.

En ny webbläsarflik eller ett nytt fönster öppnas, där du kan validera dina stilåsidosättningar mot din webbplats. Du kan sedan dela URL:en med andra autentiserade Commerce-användare för granskning och feedback.

## <a name="activate-a-css-override-file-on-your-live-site"></a>Aktivera en CSS åsidosättningfil på din aktiva webbplats

När du har förhandsgranskat och godkänt CSS åsidosättningfilen kan du aktivera den på din aktiva webbplats.

> [!NOTE]
> Endast en CSS åsidosättningfil kan vara aktiv på en plats i taget. Om du aktiverar en ny åsidosättningfil inaktiveras den tidigare åsidosättningsfilen. Kontrollera därför att alla obligatoriska åsidosättningar finns i en enda CSS åsidosättningfil.

Gör så här om du vill aktivera en CSS åsidosättningfil.

1. I navigeringsfönstret till vänster väljer du **design** och sedan på fliken **CSS åsidosätt** under **tillgängliga CSS åsidosättningar**, leta upp CSS-filen som du vill aktivera.
1. Under CSS filnamnet väljer du **aktivera**. Åsidosättningfilen blir omedelbart aktiv på din aktiva webbplats.

## <a name="deactivate-a-css-override-file-on-your-live-site"></a>Inaktivera en CSS åsidosättningfil på din aktiva webbplats

Så här inaktiverar du en CSS åsidosättningfil på din webbplats.

1. I navigeringsfönstret till vänster väljer du **design** och sedan på fliken **CSS åsidosätt** under **tillgängliga CSS åsidosättningar**, leta upp CSS-filen som du vill inaktivera.
1. Under CSS filnamnet väljer du **inaktivera**. Åsidosättningfilen blir omedelbart inaktiv på din aktiva webbplats.

> [!TIP]
> Om du vill komma åt ytterligare alternativ för CSS åsidosättningsfiler väljer du ellipsen (**...**) bredvid CSS-filnamnet. Alternativen **Hämta**, **Byt namn** och **Ersätt** är användbara för snabba ändringar i en befintlig CSS åsidosättningfil.

## <a name="additional-resources"></a>Ytterligare resurser

[Lägga till en logotyp](add-logo.md)

[Välja ett tema för webbplatsen](select-site-theme.md)

[Arbeta med förinställda stilar](style-presets.md)

[Lägga till en favoritikon](add-favicon.md)

[Lägga till ett välkomstmeddelande](add-welcome-message.md)

[Lägga till ett copyrightmeddelande](add-copyright-notice.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]