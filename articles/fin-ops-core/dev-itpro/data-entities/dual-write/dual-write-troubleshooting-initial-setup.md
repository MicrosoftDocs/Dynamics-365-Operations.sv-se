---
title: Felsöka problem under första installationen
description: Ämnet innehåller information som kan hjälpa dig att åtgärda problem som kan uppstå under den första installationen av integrering av dubbelriktad skrivning.
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 9a70de253eff2a3273be4a31ab32757bb014328f
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8061477"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Felsöka problem under första installationen

[!include [banner](../../includes/banner.md)]



Det här avsnittet innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan Ekonomi och Drift-appar och Dataverse. Särskilt innehåller det information som kan hjälpa dig att åtgärda problem som kan uppstå under den första installationen av integrering av dubbelriktad skrivning.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>Du kan inte koppla ett Ekonomi och Drift-app till Dataverse

**Obligatoriska autentiseringsuppgifter för att konfigurera dubbelriktad skrivning**: Systemadministratören i Ekonomi och Drift-appar och Dataverse.

Fel på sidan **Konfigurera länk till Dataverse** orsakas vanligtvis av ofullständiga installations- eller behörighetsproblem. Kontrollera att hela hälsokontrollen passerar **Konfigurera länk till Dataverse** som visas i följande illustration. Du kan inte länka dubbelriktad skrivning om inte hela hälsokontrollen passerar.

![Lyckad hälsokontroll.](media/health_check.png)

Du måste ha Azure AD autentiseringsuppgifter för klientadministratör för att länka Ekonomi och Drift och Dataverse-miljöer. När du har länkat miljöerna kan användare logga in med hjälp av sina kontouppgifter och uppdatera en befintlig tabellmappning.

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Hitta gränsen för antal juridiska tabeller eller företag som kan länkas för dubbelriktad skrivning

Följande felmeddelande kan visas när du försöker att aktivera kartor:

*Fel i dubbelriktad skrivning – registrering av plugin-program misslyckades: [(Det gick inte att hämta karta över partitioner för projekt-DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Felet överskrider högsta antal tillåtna partitioner för mappning av DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)], Ett eller flera fel uppstod.*

Den aktuella gränsen när du länkar miljöer är ungefär 40 juridiska tabeller. Det här felet uppstår om du försöker aktivera mappningar och mer än 40 juridiska tabeller är länkade mellan miljöer.

## <a name="connection-set-failed-while-linking-environment"></a>Anslutning misslyckades vid länkning av miljö

Vid kopplingen av miljön med dubbel skrivning misslyckas åtgärden med ett felmeddelande:

*Det gick inte att spara anslutningsuppsättningen! En artikel med samma nyckel har redan lagts till.*

Det finns inget stöd för flera juridiska personer/företag med samma namn. Om du till exempel har två företag med namnet "DAT" i Dataverse kommer detta felmeddelande att visas.

Du tar bort kundspärren genom att ta bort bubblettposter från kundens **cdm_company**-tabell i Dataverse. Om tabellen **cdm_company** har poster med tomt namn tar du bort eller korrigerar dessa poster.

## <a name="error-when-opening-the-dual-write-page-in-finance-and-operations-apps"></a>Fel vid öppning av sidan för dubbelriktad skrivning i Ekonomi och Drift-appar

Följande felmeddelande kan komma att visas när du försöker koppla en Dataverse-miljö för dubbel skrivning:

*Svarsstatuskoden anger inte lyckad: 404 (hittades inte).*

Detta fel uppstår när programmets medgivandesteg inte har slutförts. Du kan validera om ditt godkännande har angetts genom att logga in på `portal.azure.com` med hjälp av administratörskontot för klientorganisationen och kontrollera om tredjepartsappen med ID `33976c19-1db5-4c02-810e-c243db79efde` visas i AAD:s lista över företagsprogram. Om inte kör du godkännandesteget igen på det sätt som beskrivs i nästa avsnitt.

### <a name="providing-app-consent"></a>Tillhandahålla godkännande för app

+ Starta följande URL med dina administratörsuppgifter.

    `https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent`

+ Välj **Godkänn** för att ge ditt medgivande. Du ger ditt medgivande till att installera programmet (med `id=33976c19-1db5-4c02-810e-c243db79efde`) i din klientorganisation.
+ Detta program krävs för att Dataverse ska kunna kommunicera med Ekonomi och Drift-appar.

    ![Felsöka problem under första synkroniseringen.](media/Initial-sync-setup-troubleshooting-1.png)

> [!NOTE]
> Om detta inte fungerar startar du URL:en i privat läge i Microsoft Edge eller i osynligt läge i Chrome.

## <a name="finance-and-operations-environment-is-not-discoverable"></a>Ekonomi och Drift-miljön kan inte upptäckas

Följande felmeddelande kan komma att visas:

*Ekonomi och Drift-appmiljö \*\*\*.cloudax.dynamics.com går inte att upptäcka.*

Det finns två saker som kan orsaka att ett problem med miljön inte kan upptäckas:

+ Användaren som används för inloggning finns inte med i samma klientorganisation som Ekonomi och Drift-instansen.
+ Det finns vissa äldre Ekonomi och Drift-instanser som haft Microsoft som värd och som har haft problem med att upptäckas. Korrigera detta genom att uppdatera Ekonomi och Drift-instansen. Alla uppdateringar gör miljön möjlig att upptäcka.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
