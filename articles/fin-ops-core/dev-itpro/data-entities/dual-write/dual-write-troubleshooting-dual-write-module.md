---
title: Felsöka problem med modulen för dubbelriktad skrivning i Finance and Operations-appar
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
ms.openlocfilehash: f99f3760e75ec1bbf2ccdea497cf2eec3e28e233
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997384"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a>Felsöka problem med modulen för dubbelriktad skrivning i Finance and Operations-appar

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service. Det ger särskilt information som kan hjälpa dig att åtgärda problem med **dubbelriktad skrivning** i Finance and Operations-appar.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Du kan inte läsa in modulen för dubbelriktad skrivning i en Finance and Operations-app

Om du inte kan öppna sidan **dubbelriktad skrivning** genom att välja panelen **dubbelriktad skrivning** i arbetsytan **datahantering** är dataintegrationstjänsten förmodligen nere. Skapa en supportbiljett för att begära en omstart av dataintegrationstjänsten.

## <a name="error-when-you-try-to-create-a-new-entity-map"></a>Fel vid försök att skapa en ny entitetsmappning

**Nödvändiga autentiseringsuppgifter för att åtgärda problemet:** Samma användare som ställer in dubbelriktad skrivning.

Följande felmeddelande kan visas när du försöker konfigurera en ny entitet för dubbelriktad skrivning. Den enda användare som kan skapa en karta är den användare som ställer in anslutningen med dubbelriktad skrivning.

*Svarsstatuskoden anger inte lyckad: 401 (otillåtet)*


## <a name="error-when-you-open-the-dual-write-user-interface"></a>Fel vid öppning av användargränssnittet med dubbelriktad skrivning

Följande felmeddelande kan visas när du försöker komma åt dubbelriktad skrivning från arbetsytan **Datahantering** :

*login.microsoftonline.com vägrade att ansluta.*

Om du vill åtgärda problemet loggar du in på ett InPrivate-fönster i Microsoft Edge, ett inkognitofönster i Chromium eller ett inkognitofönster i Google Chrome. Du måste också häva blockeringen eller rensa cookies från tredje part.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a>Fel vid länkning av miljön för dubbelriktad skrivning eller lägga till en ny entitetsmappning

**Den roll som krävs för att åtgärda problemet:** Systemadministratören i båda Finance and Operations-appar och Common Data Service.

Du kan stöta på följande fel när du länkar eller skapar kartor:

*Svarsstatuskoden anger inte lyckad: 403 (tokenexchange).<br> Session s-ID: \<your session id\><br> Rotaktivitets-ID: \<your root activity id\>*

Det här felet kan uppstå om du inte har tillräcklig behörighet för att länka dubbelriktad skrivning eller skapa kartor. Det här felet kan också uppstå om Common Data Service-miljön återställdes utan att dubbelriktig skrivning avlänkas. Alla användare med rollen systemadministratör i båda Finance and Operations-apparna och Common Data Service kan länka dessa miljöer. Det är bara användaren som installerar anslutningen för dubbelriktad skrivning som kan lägga till nya entitetsmappningar. Efter installationen kan alla användare med rollen systemadministratör övervaka status och redigera mappningarna.

## <a name="error-when-you-stop-the-entity-mapping"></a>Fel när du stoppar entitetsmappningen

Följande felmeddelande kan visas när du försöker att stoppa entitetsmappningen:

*\[Förbjudet\], \[{"status":403,"source":"","message":"Fel från token exchange: Användaren har inte rätt att komma åt anslutning dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Fjärrservern returnerade ett fel: (403) Förbjudet.*

Det här felet uppstår när den länkade Common Data Service-miljön inte är tillgänglig.

Lös problemet genom att skapa en biljett till dataintegrationsteamet. Koppla nätverksspårningen så att dataintegrationsteamet kan markera kartorna som **Inte körs** i servern.

## <a name="error-while-trying-to-start-an-entity-mapping"></a>Fel vid försök att starta en entitetsmappningen

Du kan få ett felmeddelande som följande när du försöker ange status för en mappning som ska **köras** :

*Det gick inte att slutföra inledande datasynkronisering. Fel: del i dubbelriktad skrivning - registrering av plugin-program misslyckades: Det gick inte att skapa metadata för sökning för dubbelriktad skrivning.*

Korrigeringen för det här felet beror på orsaken till felet:

+ Om mappningen har beroende mappningar ska du se till att aktivera de beroende mappningarna för den här entitetsmappningen.
+ Mappningen kanske saknar käll- eller målfält. Om ett fält i Finance and Operations-appen saknas följer du stegen i avsnittet [Entitetsfält som saknas problem i kartor](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps). Om ett fält i Common Data Service saknas klickar du på knappen **Uppdatera entiteter** på mappningen så att fälten automatiskt fylls i igen i mappningen.
