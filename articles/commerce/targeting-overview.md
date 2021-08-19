---
title: Enhet, marknad och områdesbestämning
description: Det här ämnet beskriver hur du skapar, redigerar och hanterar målgrupper och mål i Microsoft Dynamics 365 Commerce webbplatsskaparen genom att använda information om enhet, marknad och geolokalisering.
author: sushma-rao
ms.date: 07/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2021-07-31
ms.dyn365.ops.version: AX 10.0.21
ms.openlocfilehash: 3ecc04c97b42b17f257aa40f665136c70de398748b9bda0da860c7000c062807
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6730861"
---
# <a name="device-market-and-geolocation-targeting"></a>Enhet, marknad och områdesbestämning

[!include [banner](includes/banner.md)]

Det här ämnet beskriver hur du skapar, redigerar och hanterar målgrupper och mål i Microsoft Dynamics 365 Commerce webbplatsskaparen genom att använda information om enhet, marknad och geolokalisering.

Dynamics 365 Commerce med hjälp av anpassade variationer av sidinnehållet (kallas *mål*) för specifika kundgrupper (känd som *målgrupper*) för att öka användarnas engagemang och tillfredsställelse. Du kan skapa antingen en målgrupp eller ett mål först. En lyckad målerfarenhet kräver dock båda dessa komponenter.

Du kan skapa och hantera kunder i Commerce Site Builder, baserat på kunddata som plats, enhetsinformation, inloggningsstatus och annan dynamiskt härledd information från kundwebbförfrågningar. Du kan också skapa och hantera mål i e-handelsmoduler ochfragment i Commerce Site Builder.

**Ansvarsfriskrivning:** Du är ansvarig för att använda den här funktionen i enlighet med alla tillämpliga lagar och regler, inklusive de som är relaterade till inriktning och profilering. 

## <a name="audiences"></a>Målgrupper

En grupp användare är framför allt en grupp och medlemskapet i gruppen bestäms av en uppsättning dynamiska regler. Dessa regler är enkla logiktester som körs mot information som är tillgänglig i kundförfrågningar eller andra tillgängliga segment. Du kan kombinera flera regler genom att använda OCH/ELLER operatorer.

Commerce har stöd för grundläggande segment som enhetsinformation, inloggningsstatus, referens och parametrar för frågesträng. Det stöder även utökningsbara segment via anslutningar till tredjepartsleverantörer.

### <a name="basic-segments"></a>Grundläggande segment

Som standard är följande segment tillgängliga och kan inkluderas i målgruppsdefinitioner:

- **Status för inloggad** – Testa om en användare autentiseras.
- **Enhetsplattform** – Testa följande enhetstyper:

    - Mobil
    - Stationär dator
    - Surfplatta
    - Övriga

- **Enhet OS** – Test av följande operativsystem:

    - Windows
    - Linux
    - iOS
    - Android, övrigt

- **Frågesträngsparametrar** – Testa om det finns ett nyckel-värde-par i en frågesträngparameter för en begäran-URL. För URL kan till exempel `www.fabrikam.com/en-us/request?promo=true` en regel skrivas för att testa att parametern **promo** har värdet **true**.
- **Cookie** – Testa ett cookie -värde som är inställt för domänen i begärans URL. En begäran Fabrikam.com till exempel omfatta en kod som har namnet **CustomLayout** och värdet **1**. Testtestet kontrollerar om det finns en sådan, men skapar inte explicit en. I det tidigare exemplet måste JavaScript tidigare ha ställt in **CustomLayout** så att den kommer från en annan modul eller någon annan affärsprocess.

    > [!NOTE]
    > Se till att din användning av cookies överensstämmer med gällande lagar.

- **Refererare** – Om en användare följer en länk för att begära sidan, är hänvisaren webbadressen till sidan som var värd för länken.

### <a name="extensible-segments"></a>Utökningsbara segment

Med Commerce kan du expandera listan över tillgängliga segment genom att ansluta till segmenteringsleverantörer som är tredjepartsföretag. En segmenteringsprovider beskriver vilka typer av segment som är tillgängliga. Mer information om hur du ansluter till en omplacering eller segmenteringsprovider finns i [Konfigurera och aktivera kontakter](e-commerce-extensibility/connectors.md).

> [!NOTE]
> - Om en extern leverantör är aktiverad kan den ansluta till en tjänst med oförutsägbara prestanda. Om en användare begär en sida med mål, och den sidan hänvisar till en målgrupp som kontrollerar en leverantör av tredje part, visas sidans standardversion för att ge en bättre användarupplevelse.
> - Användaren måste gå med på att tillåta cookies. Användarens webbläsare begär sedan alla segment från relevant leverantör, och resultatet placeras i en cookie som returneras till användaren. Efterföljande förfrågningar på sidan använder denna information för att tjäna som målinnehåll till användaren. Mer information om överensstämmelse med cookies finns i [Cookie-regelefterlevnad](cookie-compliance.md).

**Ansvarsfriskrivning:** Om du aktiverar den här funktionen delas dina data med tredjepartssystem som du väljer. Du styr vilka data, om det finns, som du tillhandahåller till tredje part. Du förstår att tredje parts datahanterings- och efterföljandestandarder kan skilja sig från standarder för Microsoft Dynamics 365 Commerce. Din integritet är viktig för Microsoft. Mer information finns i vår [sekretess- och cookiepolicy](https://privacy.microsoft.com/privacystatement).

### <a name="create-an-audience-in-site-builder"></a>Skapa en målgrupp i webbplatsskaparen

För att skapa en målgrupp i Commerce webbplatsskaparen.

1. I navigeringsfönstret till vänster välj er du **Målgrupper**.
1. Välj **Ny**.
1. Ange ett namn för målgrupp. Du kan även lägga till taggar och en beskrivning om du vill.
1. Välj **Skapa** och **Lägg sedan till nytt regelblock**. Ett regelblock är en samling regler som sammanfogas av OCH-villkor. Du kan också skapa flera regelblock som har ELLER villkor mellan dem.
1. Välj en datakälla för dina segment och ange sedan segmentnamn, operator och värden. Du kan skapa och ta bort fler regler i ett regelblock eller så kan du skapa och ta bort hela regelblock. Du kan även flytta regelblock upp eller ned efter behov.

    > [!NOTE]
    > Du kan ha upp till 100 värden i en lista och varje listartikel får innehålla upp till 50 tecken.

1. När du är nöjd med konfigureringen för målgrupp väljer du **Slutför redigering**. Du kan sedan välja **Publicera** för att göra målgruppen tillgänglig för användning i ett live-mål. Alternativt kan du publicera målgruppen tillsammans med målet. 

Om du vill redigera en målgrupp väljer du hyperlänken för den på fliken **Målgrupp** och väljer **Redigera** i den redigering av målgrupp som visas. Om du vill visa listan med mål och sidor som refererar till en målgrupp väljer du målgruppen i listvyn och väljer sedan **Visa tilldelningar**. Om du vill ta bort en målgrupp i visningen av en målgrupp eller i visningen av målgruppen tar du bort den om den redan har publiceras och väljer **Radera** i kommandotolken.

> [!NOTE]
> Målgrupp är ett koncept på site-nivå i Commerce webbplatsskaparen. Du kan använda samma målgrupp för flera mål.

## <a name="targets"></a>Mål

Ett mål är användarupplevelsen som visas för medlemmar i en eller flera valda målgrupper. Det kan innehålla variationer av en eller flera moduler på en sida eller i ett fragment. 

Du kan definiera ett schema för dina mål om du vill ange hur länge de ska vara aktiva. Observera att den här åtgärden är skild från åtgärden att schemalägga en publiceringsgrupp som bestämmer när en samling innehåll ska publiceras. Du kan också förhandsgranska dina mål om du vill se hur de ser ut för de valda målgrupperna. Du kan dessutom prioritera dina mål och ange vilka mål som ska visas i händelse av en konflikt.

### <a name="create-a-target"></a>Skapa ett mål

För att skapa ett målskal för sidmoduler i Commerce-webbplatsbyggaren genom att följa dessa steg.

1. I navigeringsfönstret till vänster, välj **sidor**. Välj sedan hyperlänk för sidan som har de moduler som du vill sikta mot.
1. Välj **redigera** för att kolla sidan för redigering.
1. På menyn **Mål**, välj **Nytt mål** för att skapa ett nytt målskal. Du kan skapa flera mål på en sida efter behov.
1. Ange ett namn på och en beskrivning för ditt mål och välj sedan **Nästa**.
1. Välj **Lägg till** om du vill inkludera målgrupperna som ska se det avsedda innehållet eller utesluta en målgrupp. Välj sedan **Nästa**.

    > [!NOTE]
    > Målgruppstilldelning är ett valfritt steg när ett mål skapas. Innan du publicerar målet måste du dock inkludera minst en målgrupp för att se till att de avsedda användargrupperna ser det avsedda innehållet.

1. Definiera tidsfönstret för visningen av ditt mål genom att välja tidszon samt start- och slutdatum. Du kan ställa in målet så att det visas alltid under fönstret, eller så kan du välja specifika dagar och tider. Välj **Nästa** när du är klar.

    > [!NOTE]
    > De tider och tidszoner som du anger är globala. Om du vill sikta mot olika platser vid olika tider eller i olika tidszoner, måste du skapa olika mål och definiera önskat schema för varje plats.

1. Gå igenom detaljerna och när allt ser korrekt ut väljer du **Skapa målupplevelse** och sedan **Gå till mål**. Målskalet har skapats. Nu kan du lägga till moduler i den.
1. Välj modulen som du vill sikta mot, välj ellipsen (**...**) och välj **Lägg till nuvarande mål**. När du siktar på en överordnad modul blir alla underordnade moduler den del av målet. De målmoduler som är markerade i grönt.
1. Gör de uppdateringar av innehållet som behövs i målmodulen och lägg till fler moduler till målet efter behov. Spara ändringarna genom att klicka på **Spara**.
1. Innan du publicerar målet måste du välja **Förhandsgranska** i kommandofältet för att granska det. Du kan välja något av följande alternativ:

    - **Förhandsgranskning** – Välj det här alternativet om du bara vill förhandsgranska den valda varianten (standardsida eller mål), utan tillhörande målgrupper.
    - **Avancerad förhandsgranskning** – Välj det här alternativet om du har flera mål på en sida och vill förhandsgranska dem som en användare som tillhör en vald uppsättning målgrupper eller på ett visst datum/tid. Välj **Nästa** om du vill välja från en lista över relevanta målgrupper. Du kan också ta bort filtret för att välja bland alla målgrupper.

1. När du är nöjd med målkonfigurationen måste du publicera sidan för att målet ska gå direkt. Välj **Publicera** om du vill att målet ska börja live på en gång. Du kan också använda en publiceringsgrupp för att schemalägga när sidan ska visas. Mer information om publiceringsgrupper finns i [arbeta med publiceringsgrupper](publish-groups.md).

Du kan också målfragment. Proceduren liknar. Men i steg 1 väljer du **Fragment** i stället för **Sidor** i navigeringsfönstret.

> [!NOTE]
> För att undvika att dina värden påverkas negativt kan du ha antingen ett eller flera mål på en sida eller i ett fragment. Du kan inte ha både ett experiment och mål.

### <a name="manage-targets"></a>Hantera mål

Om du vill redigera, duplicera eller ta bort mål går du till standardsidan eller fragmentet och följer stegen nedan.

1. Välj i rullgardinsmenyn **Mål** och välj **Hantera mål**.
1. Välj ett mål som du vill redigera, duplicera eller ta bort.
1. Om du har flera mål i samma modul eller om flera mål har motstridiga scheman väljer du **Prioritera mål** för att ange ordningen som de ska visas i. Om du lägger till mer än ett mål på en sida eller i ett fragment, kommer **Prioritera mål** knappen visas också i meddelandefältet för att påminna dig om att prioritera målen. Om ingen prioritet har angetts väljs det senaste målet som standard.

### <a name="localize-targets"></a>Lokalisera mål

Mål på sidor och i fragment inkluderas automatiskt när XLIFF-filer exporteras och importeras för localization-syfte. Om det inte krävs några nationella språk kan du dock ta bort målen för dem efter att de lokaliserade XLIFF-filerna har importerats.

> [!NOTE]
> Målen hanteras per kanal och språk. Ändringar som du gör i mål i en kanal eller ett språk förs inte automatiskt vidare till andra kanaler eller språk.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
