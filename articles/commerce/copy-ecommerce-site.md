---
title: Kopiera en näthandelsplats
description: I detta ämne beskrivs hur du kopierar en befintlig näthandelsplats i eller mellan näthandelsmiljöer i Microsoft Dynamics 365 Commerce-webbplatsverktyget.
author: psimolin
ms.date: 03/03/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: a23f544cbd1e960cb704d2b9666b7db4c3894b5e
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462336"
---
# <a name="copy-an-e-commerce-site"></a>Kopiera en näthandelsplats

[!include [banner](../includes/banner.md)]

I detta ämne beskrivs hur du kopierar en befintlig näthandelsplats i eller mellan näthandelsmiljöer i Microsoft Dynamics 365 Commerce-webbplatsverktyget.

Dynamics 365 Commerce har stöd för kopiering av webbplatser som en självbetjäningsåtgärd i Commerce Site Builder. Webbplatser kan kopieras i en enda näthandelsmiljö eller mellan två näthandelsmiljöer. Användaren som initierar kopieringsåtgärden för webbplats måste vara klientorganisationsadministratör i både käll- och destinationsmiljöerna för näthandel.

Funktionen för webbplatskopiering kopierae allt näthandelsinnehåll från källplatsen. Detta innehåll inkluderar sidor,fragment, mallar, URL-adresser och tillgångar. Innan en ny webbplats kan användas måste den initieras genom den första körningserfarenhetsprocessen (FRE). Kanaler kan mappas och hanteras i webbplatsbyggaren på **Webbplatsinställningar \> Kanaler**.

Längden på kopieringsåtgärden för webbplats beror huvudsakligen på antalet tillgångar på källwebbplatsen. För sällsynt stora webbplatser rekommenderar vi att du istället använder åtgärden för miljökopiering. (Denna åtgärd kallas även för åtgärden för dataportabilitet).

> [!NOTE]
> - Källwebbplatsen kommer att vara skrivskyddda under hela kopieringsåtgärden för webbplats.
> - Endast publicerade versioner av dokument kopieras över. Om inga versioner har publicerats kopieras bara de senaste versionerna över.
> - Versionshistoriken för innehåll är inte tillgänglig på destinationswebbplatsen.

## <a name="copy-a-site-within-an-e-commerce-environment"></a>Kopiera en webbplats inom en näthandelsmiljö

Följ de här stegen om du vill kopiera en webbplats inom en näthandelsmiljö.

1. Logga in på webbplatsverktyget för den miljö där du vill utföra kopieringen.
1. Öppna listvyn för webbplats genom att välja **Webbplatsväxlare** i det övre högra hörnet och sedan **Hantera webbplatser**.
1. Leta upp den webbplats du vill kopiera eller klona, och välj den genom att markera kryssrutan bredvid webplatsens namn.
1. I åtgärdsfönstret väljer du **Kopiera webbplats**.
1. I dialogrutan **Kopiera webbplats**, i fältet **Nytt webbplats**, anger du ett namn för den nya webbplatsen. Det nya webbplatsnamnet måste vara unikt i näthandelsmiljön. Fälten **Källans klientorganisation** och **Källwebbplats** ställs automatiskt in på informationen för aktuell klientorganisation och vald webbplats.
1. Välj **Skapa kopia**.

När informationen har validerats visas ett meddelande om att ett nytt kopieringsjobb har skapats för webbplatsen. Du kan övervaka jobbets förlopp i det [högra fönstret på sidan **Jobb för klientorganisation**](#monitor-the-site-copy-operation). När kopieringen har slutförts visas den nya webbplatsen i listan över webbplatser.

I bilden nedan visas ett exempel på dialogrutan **Kopiera webbplats** i webbplatsbyggaren.

![Kopiera dialogrutan för webbplats i webbplatsverktyget.](media/site-copy_1.png)

## <a name="copy-a-site-between-two-e-commerce-environments"></a>Kopiera en webbplats mellan två näthandelsmiljöer

Följ de här stegen om du vill kopiera en webbplats mellan två näthandelsmiljöer.

1. Logga in i webbplatsverktyget för målnäthandelsmiljön.
1. I åtgärdsfönstret väljer du **Kopiera webbplats**.
1. I dialogrutan **Kopiera webbplats**, i fältet **Nytt webbplats**, anger du ett namn för den nya webbplatsen. Det nya webbplatsnamnet måste vara unikt i näthandelsmiljön.
1. I fältet **Källklient** väljer du namnet på källklientorganisationen.
1. I fältet **Källwebbplats** anger du kälwebbplatsen.
1. Välj **Skapa kopia**.

> [!NOTE]
> Administratörsbehörigheter för innehavare krävs för både näthandelsmiljöer för källa och destination.

När informationen har validerats visas ett meddelande om att ett nytt kopieringsjobb har skapats för webbplatsen. Du kan övervaka jobbets förlopp i det [högra fönstret på sidan **Jobb för klientorganisation**](#monitor-the-site-copy-operation). När kopieringen har slutförts visas den nya webbplatsen i listan över webbplatser.

## <a name="monitor-the-site-copy-operation"></a>Övervaka kopieringsåtgärden för webbplatsen

Följ de här stegen om du vill övervaka förloppet för kopieringsåtgärden för webbplats.

1. Logga in i webbplatsverktyget för målnäthandelsmiljön.
1. I navigeringsfönstret till vänster väljer du **Klientorganisationsjobb**.
1. På sidan **Klientorganisationsjobb** söker du upp och väljer kopieringsjobbet för webbplats i listan. Ett fönster visas till höger och anger status och information för det valda jobbet.

Du kan avbryta ett jobb som har statusen **Pågår**. Markera jobbet i listan och välj sedan **Avbryt** i åtgärdsfönstret.

Du kan försöka göra om ett jobb som har statusvärdet **Misslyckades** eller **Slutfördes med fel**. Markera jobbet i listan och välj sedan **Försök igen** i åtgärdsfönstret.

> [!NOTE]
> Bearbetningen av videotillgångar kan komma att fortsätta även efter det att ett kopieringsjobb för webbplatsen har slutförts.

I följande bild visas ett exempel på högerfönstret på sidan **Klientorganisationsjobb** i webbplatsverktyget.

![Jobbinformation i det högra fönstret på sidan Klientorganisationsjobb i webbplatsverktyget.](media/site-copy_2.png)

## <a name="initialize-a-new-site-by-using-the-fre-process"></a>Initialisera en ny webbplats med hjälp av processen FRE

Innan en ny webbplats kan användas måste den initieras genom processen FRE.

Om du vill initiera en ny webbplats med hjälp av processen FRE följer du dessa steg.

1. Logga in på webbplatsverktyget för den nya webbplatsen.
1. Öppna listvyn för webbplats genom att välja **Webbplatsväxlare** i det övre högra hörnet och sedan **Hantera webbplatser**.
1. Sök reda på och välj den nya webbplats som du vill initialisera.
1. I dialogrutan **Konfigurera din webbplats**, i fältet **Välj en domän**, väljer du en domän. Du kan välja alla domäner som har associerats med näthandelsmiljön under initialiseringen.
1. I fältet **Välj en standardkanal** väljer du associerad kanal för nätbutik. Den valda kanalen kommer att tillhandahålla sortiment och annan information som är lagrad i Commerce-administrationen.
1. I fältet **Välj ett standardspråk** väljer du standardspråket för redigering. Alla språk som har konfigurerats för den valdanätbutikskanalen går att välja.
1. I fältet **Sökväg** består värdet av basdomänen och en valfri URL-sökväg som du kan ange. URL-sökvägen kan lämnas tom om kanalen tas från domänroten, eller om du vill ange den här informationen senare i kanalkonfigurationsvyn i webbplatsverktyget. Webbpltsens sökväg måste vara unik i näthandelsmiljön.
1. Välj **OK**. Webbplatsen initialiseras med den information du angett och du vidarebefordras till vyn för webbplatshantering.

I bilden nedan visas ett exempel på dialogrutan **Konfigurera din webbplats** i webbplatsverktyget.

![Dialogrutan Konfigurera din webbplats i webbplatsverktyget.](media/site-copy_3.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera ditt domännamn](configure-your-domain-name.md)

[Distribuera en ny klientorganisation för näthandel](deploy-ecommerce-site.md)

[Associera en Dynamics 365 Commerce-webbplats med en onlinekanal](associate-site-online-store.md)

[Hantera robots.txt-filer](manage-robots-txt-files.md)

[Överför URL-omdirigeringar i bulk](upload-bulk-redirects.md)

[Ställa in en B2C-innehavare i Commerce](set-up-b2c-tenant.md)

[Ställa in anpassade sidor för användarinloggningar](custom-pages-user-logins.md)

[Konfigurera flera B2C-innehavare i en Commerce-miljö](configure-multi-b2c-tenants.md)

[Lägga till stöd för ett innehållsleveransnätverk (CDN)](add-cdn-support.md)

[Aktivera platsbaserad butiksdetektering](enable-store-detection.md)
