---
title: Introduktion till funktionsplatser
description: Det här avsnittet innehåller en översikt över funktionsplatser i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5d7d98ec5434d9cdc93276952035b559625be2bd
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783603"
---
# <a name="introduction-to-functional-locations"></a>Introduktion till funktionsplatser

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Det här avsnittet innehåller en översikt över funktionsplatser i tillgångshantering. Funktionsplatser är element av en teknisk struktur, till exempel funktionella enheter i ett system. Funktionsplatser skapas hierarkiskt och du installerar tillgångar på dem. Installationen av funktionsplatser i ditt företag beror på företagets krav.

Här är några exempel på hur du kan använda funktionsplatser:

- **Funktionell** – funktionsplatser kan vara användarorienterade och används för att hantera tillgångar som har liknande beteende.
- **Processrelaterade** – funktionsplatserna kan vara arbetsflödesorienterade.
- **Rumslig** – funktionsplatser kan representera geografiska platser eller platser.

Varje funktionsplats hanteras oberoende av tillgångshantering. Här är några av de mest användbara funktionerna i funktionsplatser:

- Ställ in specifikationer för funktionsplats.
- Ställ in tillgångsspecifikationskrav.
- Ställ in underhållsekvenser för förebyggande och reaktivt underhåll.
- Hantera installerade tillgångar.
- Spåra aktiva begäranden och arbetsorder som är relaterade till installerade tillgångar.
- Spåra fel som är registrerade på tillgångar.
- Spåra underhållskostnader på de tillgångar som är relaterade till en funktionsplats vid en given tidpunkt.

Funktionsplatser ger spårbarhet av tillgångar i relation till begäranden, arbetsorder, felregistreringar, tillståndsbedömningar, registreringar av produktionsstopp och registreringar tillgångsräknare.

> [!NOTE]
> Även om en tillgång installeras på olika funktionsplatser under dess livstid, kan kostnaderna relateras till varje plats. Därför är tillgångskostnader alltid relaterade till den funktionsplats som tillgången installerades på vid en viss tidpunkt.

Funktionsplatser är **inte** flexibla. När du har konfigurerat en funktionsplatshierarki kan du därför inte flytta runt platser i den. 

När du har skapat en funktionsplatshierarki är nästa steg att installera tillgångar på den. För mer information, se [installera tillgångar på funktionsplatser](../functional-locations/install-objects-on-functional-locations.md).

## <a name="all-functional-locations"></a>Alla funktionsplatser

Välj **tillgångshantering** \> **allmänt** \> **funktionsplatser** \> **alla funktionsplatser** för att öppna listsidan **alla funktionsplatser**. Den här sidan visar alla funktionsplatser och en del av den information som är relaterad till varje. Om du bara vill visa aktiva funktionsplatser väljer du **aktiva funktionsplatser**. Om du endast vill visa de funktionsplatser som du är relaterad till som arbetare, välj **, Mina aktiva funktionsplatser**. (Den här relationen har ställts in på sidan **arbetare**. Mer information finns i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md).)

På listsidan **Alla funktionsplatser** väljer du en länk i kolumnen **funktionsplats** för att visa information om den valda posten. Om du vill redigera funktionsplatsen väljer du knappen **redigera**. Detaljvyn visar detaljerad information som är relaterad till platsen. Den innehåller också fönstret **relaterat information** till höger. I det här fönstret visas funktionsplatshierarkin. Du kan expandera och komprimera fönstret **relaterad information**.

Knapparna i åtgärdsfönstret är ordnade på flikar. I följande tabell beskrivs kortfattat knappar som är relaterade till tillgångshantering.

| Namn på knapp                         | Beskrivning                                                                                                                                  |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Redigera                                | Växla mellan redigeringsläge och visningsläge för sidan.                                                                                         |
| Nytt                                 | Skapa en ny funktionsplats.                                                                                                            |
| Radera                              | Radera den valda funktionsplatsen.                                                                                                     |
| Ändra namn på                              | Ändra namn på den valda funktionsplatsen.                                                                                                     |
| Kopiera struktur för funktionsplats  | Kopiera funktionsplatshierarkin.                                                                                                      |
| Installera tillgång                       | Installera en tillgång, inklusive underordnade tillgångar, på funktionsplatsen.                                                                        |
| Ersätt tillgång                       | Ersätt tillgångshierarkin med en annan tillgångshierarki på funktionsplatsen.                                                         |
| Kostnadskontroll                        | Öppna sidan **kostnadskontroll för funktionsplats** där du kan göra en kostnadsberäkning för den valda funktionsplatsen.                |
| Timkontroll                        | Öppna sidan **timkontroll för funktionsplats** där du kan göra en kostnadsberäkning för den valda funktionsplatsen.                |
| Tillgångar                              | Öppna sidan **alla tillgångar** där du kan visa en lista över tillgångar som är relaterade till den valda funktionsplatsen.                      |
| Förfrågningar                            | Öppna sidan **aktiva förfrågningar** där du kan visa en lista över förfrågningar som är relaterade till den valda funktionsplatsen.               |
| Arbetsorder                         | Öppna sidan **aktiva arbetsorder** där du kan visa en lista över arbetsorder som är relaterade till den valda funktionsplatsen.         |
| Fel                              | Öppna sidan **tillgångsfel** där du kan visa en lista över registreringar av tillgångsfel som är relaterade till den valda funktionsplatsen. |
| Uppdatera funktionsplatsens tillstånd    | Uppdatera fasen för den valda funktionsplatsen                                                                                        |
| Logg för livscykeltillstånd                 | Visa en logg som visar faser för den valda funktionsplatsen.                                                                        |