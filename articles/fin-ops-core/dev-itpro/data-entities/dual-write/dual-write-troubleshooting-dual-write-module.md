---
title: Felsöka problem med dubbelriktad skrivning i Finance and Operations-appar
description: Det här avsnittet innehåller felsökningsinformation som kan hjälpa dig att åtgärda problem med dubbelriktad skrivning i Finance and Operations-appar.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 3ffeb2de0acc1761bccf62a1a124852c504e2a3a
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "5131255"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a>Felsöka problem med dubbelriktad skrivning i Finance and Operations-appar

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Dataverse. Det ger särskilt information som kan hjälpa dig att åtgärda problem med **dubbelriktad skrivning** i Finance and Operations-appar.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Du kan inte läsa in modulen för dubbelriktad skrivning i en Finance and Operations-app

Om du inte kan öppna sidan **dubbelriktad skrivning** genom att välja panelen **dubbelriktad skrivning** i arbetsytan **datahantering** är dataintegrationstjänsten förmodligen nere. Skapa en supportbiljett för att begära en omstart av dataintegrationstjänsten.

## <a name="error-when-you-try-to-create-a-new-table-map"></a>Fel vid försök att skapa en ny tabellmappning

**Nödvändiga autentiseringsuppgifter för att åtgärda problemet:** Samma användare som ställer in dubbelriktad skrivning.

Följande felmeddelande kan visas när du försöker konfigurera en ny tabell för dubbelriktad skrivning. Den enda användare som kan skapa en karta är den användare som ställer in anslutningen med dubbelriktad skrivning.

*Svarsstatuskoden anger inte lyckad: 401 (otillåtet)*


## <a name="error-when-you-open-the-dual-write-user-interface"></a>Fel vid öppning av användargränssnittet med dubbelriktad skrivning

Följande felmeddelande kan visas när du försöker komma åt dubbelriktad skrivning från arbetsytan **Datahantering**:

*login.microsoftonline.com vägrade att ansluta.*

Om du vill åtgärda problemet loggar du in på ett InPrivate-fönster i Microsoft Edge, ett inkognitofönster i Chromium eller ett inkognitofönster i Google Chrome. Du måste också häva blockeringen eller rensa cookies från tredje part.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a>Fel vid länkning av miljön för dubbelriktad skrivning eller tillägg av en ny tabellmappning

**Den roll som krävs för att åtgärda problemet:** Systemadministratören i båda Finance and Operations-appar och Dataverse.

Du kan stöta på följande fel när du länkar eller skapar kartor:

*Svarsstatuskoden anger inte lyckad: 403 (tokenexchange).<br> Session s-ID: \<your session id\><br> Rotaktivitets-ID: \<your root activity id\>*

Det här felet kan uppstå om du inte har tillräcklig behörighet för att länka dubbelriktad skrivning eller skapa kartor. Det här felet kan också uppstå om Dataverse-miljön återställdes utan att dubbelriktig skrivning avlänkas. Alla användare med rollen systemadministratör i båda Finance and Operations-apparna och Dataverse kan länka dessa miljöer. Det är bara användaren som installerar anslutningen för dubbelriktad skrivning som kan lägga till nya tabellmappningar. Efter installationen kan alla användare med rollen systemadministratör övervaka status och redigera mappningarna.

## <a name="error-when-you-stop-the-table-mapping"></a>Fel när du stoppar tabellmappningen

Följande felmeddelande kan visas när du försöker att stoppa tabellmappningen:

*\[Förbjudet\], \[{"status":403,"source":"","message":"Fel från token exchange: Användaren har inte rätt att komma åt anslutning dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Fjärrservern returnerade ett fel: (403) Förbjudet.*

Det här felet uppstår när den länkade Dataverse-miljön inte är tillgänglig.

Lös problemet genom att skapa en biljett till dataintegrationsteamet. Koppla nätverksspårningen så att dataintegrationsteamet kan markera kartorna som **Inte körs** i servern.

## <a name="error-while-trying-to-start-a-table-mapping"></a>Fel vid försök att starta en tabellmappning

Du kan få ett felmeddelande som följande när du försöker ange status för en mappning som ska **köras**:

*Det gick inte att slutföra inledande datasynkronisering. Fel: del i dubbelriktad skrivning - registrering av plugin-program misslyckades: Det gick inte att skapa metadata för sökning för dubbelriktad skrivning.*

Korrigeringen för det här felet beror på orsaken till felet:

+ Om mappningen har beroende mappningar ska du se till att aktivera de beroende mappningarna för den här tabellmappningen.
+ Mappningen kanske saknar käll- eller målkolumner. Om en kolumn i Finance and Operations-appen saknas följer du stegen i avsnittet [Tabellkolumner som saknas problem i kartor](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps). Om en kolumn i Dataverse saknas klickar du på knappen **Uppdatera tabeller** på mappningen så att kolumnerna automatiskt fylls i igen i mappningen.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]