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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 34c10e38400a72a670a93f2a72d0aa7a4aed561a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172770"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a>Felsöka problem med modulen för dubbelriktad skrivning i Finance and Operations-appar

[!include [banner](../../includes/banner.md)]



Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Finance and Operations-appar och Common Data Service. Det ger särskilt information som kan hjälpa dig att åtgärda problem med **dubbelriktad skrivning** i Finance and Operations-appar.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a>Du kan inte läsa in modulen för dubbelriktad skrivning i en Finance and Operations-app

Om du inte kan öppna sidan **dubbelriktad skrivning** genom att välja panelen **dubbelriktad skrivning** i arbetsytan **datahantering** är dataintegrationstjänsten förmodligen nere. Skapa en supportbiljett för att begära en omstart av dataintegrationstjänsten.

## <a name="error-when-you-try-to-create-a-new-entity-mapping"></a>Fel vid försök att skapa en ny entitetsmappning

**Nödvändiga autentiseringsuppgifter för att åtgärda problemet:** Azure AD klientadministratör

Följande felmeddelande kan visas när du försöker konfigurera en ny entitet för dubbelriktad skrivning:

*Svarsstatuskoden anger inte lyckad: 401 (otillåtet)*

Det här felet beror på att endast en Azure AD-klientadministratör kan lägga till en ny entitetsmappning.

För att åtgärda problemet loggar du in på Finance and Operations-appen som en Azure AD-administratörsklient. Du måste också gå till web.PowerApps.com och förnya anslutningen.

## <a name="error-when-you-open-the-dual-write-user-interface"></a>Fel vid öppning av användargränssnittet med dubbelriktad skrivning

Följande felmeddelande kan visas när du försöker komma åt dubbelriktad skrivning från arbetsytan **Datahantering**:

*login.microsoftonline.com vägrade att ansluta.*

Om du vill åtgärda problemet loggar du in på ett InPrivate-fönster i Microsoft Edge, ett inkognitofönster i Chromium eller ett inkognitofönster i Google Chrome. Du måste också häva blockeringen eller rensa cookies från tredje part.

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a>Fel vid länkning av miljön för dubbelriktad skrivning eller lägga till en ny entitetsmappning

**Nödvändiga autentiseringsuppgifter för att åtgärda problemet:** Azure AD klientadministratör

Du kan stöta på följande fel när du länkar eller skapar kartor:

*Svarsstatuskoden anger inte lyckad: 403 (tokenexchange).<br> Sessions-ID: \<din sessions-id\><br> rotaktivitets-ID: \<din rotaktivitets-id\>*

Det här felet kan uppstå om du inte har tillräcklig behörighet för att länka dubbelriktad skrivning eller skapa kartor. Du måste använda ett Azure AD-klientadministratörskonto för att länka miljöer och lägga till nya entitetsmappningar. När du har konfigurerat kan du dock använda ett icke-administratörskonto för att övervaka status och redigera mappningarna.

## <a name="error-when-you-stop-the-entity-mapping"></a>Fel när du stoppar entitetsmappningen

Följande felmeddelande kan visas när du försöker att stoppa entitetsmappningen:

*\[Förbjudet\], \[{"status":403,"source":"","message":"Fel från token exchange: Användaren har inte rätt att komma åt anslutning dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], Fjärrservern returnerade ett fel: (403) Förbjudet.*

Det här felet uppstår när den länkade Common Data Service-miljön inte är tillgänglig.

Lös problemet genom att skapa en biljett till dataintegrationsteamet. Koppla nätverksspårningen så att dataintegrationsteamet kan markera kartorna som **Inte körs** i servern.
