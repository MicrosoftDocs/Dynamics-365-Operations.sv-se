---
title: Konfigurera Regulatory Configuration Service (RCS)
description: Detta ämne förklarar hur du ställer in Regulatory Configuration Service (RCS).
author: gionoder
ms.date: 10/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.custom: 97423,  ""intro-internal
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: 32ced98925ee66e02f0b073b4acbd586666ac20c
ms.sourcegitcommit: 1ecfc1d8afb2201ab895ae6f93304ba2b120f14b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2022
ms.locfileid: "9710792"
---
# <a name="set-up-regulatory-configuration-service-rcs"></a>Konfigurera Regulatory Configuration Service (RCS)

[!include [banner](../includes/banner.md)]

Detta ämne förklarar hur du ställer in Regulatory Configuration Service (RCS).

## <a name="turn-on-globalization-features"></a>Aktivera globaliseringsfunktionerna

1. Logga in på RCS-kontot.
2. Välj panelen **funktionshantering**.
3. I arbetsytan **Funktionshantering** välj **Globaliseringfunktioner** i listan och sedan **Aktivera nu**.

En panel för arbetsytan för **globaliseringsfunktioner** ska nu visas på huvudinstrumentpanelen för RCS.

## <a name="set-up-the-parameters-for-rcs-integration-with-electronic-invoicing"></a>Ställ in parametrarna för RCS-integrationen med e-fakturering

1. I arbetsytan **Globaliseringsfunktioner** i avsnittet **Relaterade inställningar** väljer du länken **Parametrar för elektronisk rapportering**.
2. Första gången du ställer in parametrarna uppmanas du att ansluta till Lifecycle Services (LCS). Välj **Klicka här för att ansluta till Lifecycle Services** och välj **OK** när anslutningen är upprättad.

    > [!IMPORTANT]
    > I länder eller regioner där datauppehållet tillämpas, och om din RCS har tillhandahållits i en annan region där LCS tillhandahålls, kan du få följande anslutningsfelmeddelande i RCS: "Ingen HTTP-resurs hittades som matchar begäran-URI". Välj **OK**. Du kan få ett annat felmeddelande i RCS: Det gick inte att generera användartoken för Dynamics Lifecycle Services på uppdrag av användaren (). Kontakta systemadministratören."
    >  
    > Detta inträffar eftersom LCS är en global tjänst och finns i en amerikansk region. På grund av policyn för data uppehållstillstånd kan omformarna från din aktuella region inte ansluta till LCS. Under dessa omständigheter finns det två möjliga lösningar:
    > - Ta bort RCS från den aktuella regionen och återskapa den i den amerikanska regionen.
    > - Ignorera felen och fortsätt med inställningarna för elektronisk fakturering. Dessa fel påverkar inte funktionen för elektronisk fakturering.

3. På fliken **E-fakturering**, i fältet **URI för tjänsteslutpunkt**, anger du ungefärlig tjänsteslutpunkt för ditt Microsoft Azure-område enligt följande tabell.

    | Azure-område för datacenter | URI för tjänstslutpunkt |
    |----------------------------|----------------------|
    | USA              | <p>`https://gw.us-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.us-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Europa                     | <p>`https://gw.eu-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il103.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il104.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il105.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il106.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il107.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il108.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il109.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.eu-il110.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Storbritannien             | <p>`https://gw.uk-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.uk-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Asien                       | <p>`https://gw.as-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p><p>`https://gw.as-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Japan                      | <p>`https://gw.jp-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Schweiz                | <p>`https://gw.ch-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Brasilien                     | <p>`https://gw.br-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.br-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Förenade Arabemiraten       | <p>`https://gw.ae-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Australien                  | <p>`https://gw.au-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.au-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Kanada                     | <p>`https://gw.ca-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> <p>`https://gw.ca-il102.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Frankrike                     | <p>`https://gw.fr-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Indien                      | <p>`https://gw.in-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Norge                     | <p>`https://gw.no-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |
    | Sydafrika               | <p>`https://gw.za-il101.gateway.prod.island.powerapps.com/electronicinvoicing/`</p> |

3. Granska och ange det fasta värdet i fältet **Program-ID** **0cdb527f-a8d1-4bf8-9436-b352c68682b2**. Se till att endast en global unik identifierare (GUID) anges och att värdet inte innehåller några andra symboler, till exempel blanksteg, kommatecken, punkter eller citationstecken.
4. I fältet **ID för LCS-miljö** anger du ID för din Microsoft Dynamics Lifecycle Services (LCS)-miljö. Detta värde är referensen till den Ekonomi- eller Supply Chain Management-miljö som du kommer att använda med e-faktureringstjänsten. Du hämtar ditt ID genom att logga in i  [LCS](https://lcs.dynamics.com/), öppna ditt projekt och sedan på fliken **Hantera miljöer**, i avsnittet **Miljödetaljer**, söka i fältet **Miljö-ID**.

    > [!IMPORTANT]
    > Om tillägget för e-fakturering är installerat i flera miljöer för Ekonomi eller Supply Chain Management i LCS måste du alltid använda miljö-ID:t för den senast installerade miljön. Om du bestämmer dig för att installera tillägget i en ny miljö När du har ställt in och arbetar med funktionen för e-fakturering, sak du uppdatera fältet **ID för LCs-miljö** i RCS till det senaste värdet.

5. Markera **Spara** och stäng sedan sidan.

## <a name="configuration-providers"></a>Konfigurationsleverantörer

Du kan använda konfigurationsleverantörer för att skilja ut ägaren av de ER-konfigurationer (Elektronisk rapportering) som används i e-faktureringsprocesser och ägarens globaliseringsfunktioner. För alla globaliseringsfunktioner som Microsoft tillhandahåller och publiceras i den globala databasen ställs konfigurationsprovidern in på **Microsoft** (`http://microsoft.com`).

Du kan endast justera ER-konfigurationer och globaliseringsfunktioner som tillhör den aktiva konfigurationsprovidern. Du kan använda dessa konfigurationer och funktioner som mallar när du vill skapa konfigurationer och funktioner som tillhör den aktiva konfigurationsprovidern, så att du kan justera dem.

Skapa först konfigurationsprovidern. Ställ sedan in en av dem som aktiv. Du kan inte ställa in konfigurationsprovidern **Microsoft** som aktiv.

### <a name="create-a-configuration-provider"></a>Skapa en konfigurationsleverantör

1. I arbetsytan **elektronisk rapportering** i avsnittet **Relaterade länkar** väljer du **Konfigurationsleverantörer**.
2. Välj **Ny**.
3. I fältet **Namn** anger du ett unikt namn för konfigurationsprovidern.
4. I fältet **Internetadress** anger du den unika webbadressen (URL) för den nya konfigurationsprovidern.
5. Markera **Spara** och stäng sedan sidan.

### <a name="select-a-configuration-provider-as-active"></a>Välj en konfigurationsprovider som aktiv

1. I listan över konfigurationsproviders väljer du den konfigurationsprovider som du vill ställa in som aktiv.
2. Ställ in **Ange aktiva**.

## <a name="import-er-configurations-from-the-global-repository"></a>Importera ER-konfigurationer från den globala databasen

1. I arbetsytan **elektronisk rapportering** i avsnittet **Relaterade länkar** väljer du **Konfigurationsleverantörer**.
2. I listan över konfigurationsproviders väljer du **Microsoft** och sedan **Databaser**.
3. Välj **Global** och sedan, i åtgärdsfönstret, **Öppna**.
4. Importera följande ER-modeller:

    - **Kontextmodell för kundfaktura**
    - **Fakturamodell**
    - **Skattadokument** (för brasilianska scenarier, vid behov)
    - **Modell för svarsmeddelande**

5. Om **Fakturamodellmappning** inte importerades automatiskt importerar du den.
6. Stäng sidan.
