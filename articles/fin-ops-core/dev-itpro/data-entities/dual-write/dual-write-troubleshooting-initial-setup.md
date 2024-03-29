---
title: Felsöka problem under första installationen
description: Ämnet innehåller information som kan hjälpa dig att åtgärda problem som kan uppstå under den första installationen av integrering av dubbelriktad skrivning.
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d33fc6f4895b53f16cc6957a3a2fc6b1abe90a2f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289527"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Felsöka problem under första installationen

[!include [banner](../../includes/banner.md)]

Den här artikeln innehåller felsökningsinformation för integrering av dubbelriktad skrivning mellan appar för ekonomi och drift och Dataverse. Särskilt innehåller det information som kan hjälpa dig att åtgärda problem som kan uppstå under den första installationen av integrering av dubbelriktad skrivning.

> [!IMPORTANT]
> Vissa av de problem som det här ämnet behandlar kan kräva antingen systemadministratörsrollen eller Microsoft Azure Active Directory (Azure AD) autentiseringsuppgifter för administratör för klientorganisationen. I avsnittet för varje problem förklaras om en viss roll eller autentiseringsuppgifter krävs.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>Du kan inte koppla en app för ekonomi och drift till Dataverse

**Erforderlig roll för att konfigurera dubbelriktad skrivning**: Systemadministratören i appar för ekonomi och drift och Dataverse.

Fel på sidan **Konfigurera länk till Dataverse** orsakas vanligtvis av ofullständiga installations- eller behörighetsproblem. Kontrollera att hela hälsokontrollen passerar **Konfigurera länk till Dataverse** som visas i följande illustration. Du kan inte länka dubbelriktad skrivning om inte hela hälsokontrollen passerar.

![Lyckad hälsokontroll.](media/health_check.png)

Du måste ha administratörsbehörighet för Azure AD-klientorganisation för att länka Ekonomi och Drift till Dataverse-miljöer. När du har länkat miljöerna kan användare logga in med hjälp av sina kontouppgifter och uppdatera en befintlig tabellmappning.

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Hitta gränsen för antal juridiska tabeller eller företag som kan länkas för dubbelriktad skrivning

Följande felmeddelande kan visas när du försöker att aktivera mappningar:

*Fel i dubbelriktad skrivning – registrering av plugin-program misslyckades: [(Det gick inte att hämta mappning över partitioner för projekt-DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Felet överskrider högsta antal tillåtna partitioner för mappning av DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)], Ett eller flera fel uppstod.*

Den aktuella gränsen när du länkar miljöer är ungefär 40 juridiska tabeller. Det här felet uppstår om du försöker aktivera mappningar och mer än 40 juridiska tabeller är länkade mellan miljöer.

## <a name="connection-set-failed-while-linking-environment"></a>Anslutning misslyckades vid länkning av miljö

Vid kopplingen av miljön med dubbel skrivning misslyckas åtgärden med ett felmeddelande:

*Det gick inte att spara anslutningsuppsättningen! En artikel med samma nyckel har redan lagts till.*

Det finns inget stöd för flera juridiska personer/företag med samma namn. Om du till exempel har två företag med namnet "DAT" i Dataverse kommer detta felmeddelande att visas.

Du tar bort kundspärren genom att ta bort bubblettposter från kundens **cdm_company**-tabell i Dataverse. Om tabellen **cdm_company** har poster med tomt namn tar du bort eller korrigerar dessa poster.

## <a name="error-when-opening-the-dual-write-page-in-finance-and-operations-apps"></a>Fel vid öppning av sidan för dubbelriktad skrivning i appar för ekonomi och drift

Följande felmeddelande kan komma att visas när du försöker koppla en Dataverse-miljö för dubbel skrivning:

*Svarsstatuskoden anger inte lyckad: 404 (hittades inte).*

Detta fel uppstår när programmets medgivandesteg inte har slutförts. Du kan validera om ditt godkännande har angetts genom att logga in på `portal.azure.com` med hjälp av administratörskontot för klientorganisationen och kontrollera om tredjepartsappen med ID `33976c19-1db5-4c02-810e-c243db79efde` visas i AAD:s lista över företagsprogram. Om inte kör du godkännandesteget igen på det sätt som beskrivs i nästa avsnitt.

### <a name="providing-app-consent"></a>Tillhandahålla godkännande för app

+ Starta följande URL med dina administratörsuppgifter.

    `https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent`

+ Välj **Godkänn** för att ge ditt medgivande. Du ger ditt medgivande till att installera programmet (med `id=33976c19-1db5-4c02-810e-c243db79efde`) i din klientorganisation.
+ Detta program krävs för att Dataverse ska kunna kommunicera med appar för ekonomi och drift.

    ![Felsöka problem under första synkroniseringen.](media/Initial-sync-setup-troubleshooting-1.png)

> [!NOTE]
> Om detta inte fungerar startar du URL:en i privat läge i Microsoft Edge eller i osynligt läge i Chrome.

## <a name="finance-and-operations-environment-is-not-discoverable"></a>Miljön för Ekonomi och drift kan inte hittas

Följande felmeddelande kan komma att visas:

*Ekonomi och drift-appmiljön \*\*\*.cloudax.dynamics.com går inte att hitta.*

Det finns två saker som kan orsaka att ett problem med miljön inte kan upptäckas:

+ Användaren som används för inloggning finns inte med i samma klientorganisation som Ekonomi och Drift-instansen.
+ Det finns vissa äldre Ekonomi och Drift-instanser som haft Microsoft som värd och som har haft problem med att hittas. Korrigera detta genom att uppdatera Ekonomi och Drift-instansen. Alla uppdateringar gör miljön möjlig att upptäcka.

## <a name="403-forbidden-error-while-connections-are-being-created"></a>403 (Anslutningar) fel när anslutningar skapas

Som en del av länkningsprocessen för avskrivning skapas två Power Apps anslutningar (även kallade *Apihub*-anslutningar) för användarens räkning i denlänkade Dataverse-miljön. Om kunden inte har en licens för Power Apps-miljön misslyckas genereringen av ApiHub-anslutningar och ett 403-fel (förbud) visas. Här följer ett exempel på felmeddelandet:

> MSG=\[Det gick inte att ställa in skrivmiljö. Feldetaljer: Svarsstatuskoden anger inte slutförande: 403 (förbud). - Svarsstatuskoden anger inte lyckad: 403 (förbud).\] STACKTRACE=\[   på Microsoft.Dynamics.Integrator.ProjectManagementService.DualWrite.DualWriteConnectionSetProcessor.\<CreateDualWriteConnectionSetAsync\>d\_\_29.MoveNext() in X:\\bt\\1158727\\repo\\src\\ProjectManagementService\\DualWrite\\DualWriteConnectionSetProcessor.cs:line 297 --- Slutspårning av stack från tidigare plats där undantaget kastades --- på System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw() på System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task) at Microsoft.Dynamics.Integrator.ProjectManagementService.Controllers.DualWriteEnvironmentManagementController.\<SetupDualWriteEnvironmentAsync\>d\_\_34.MoveNext() in X:\\bt\\1158727\\repo\\src\\ProjectManagementService\\Controllers\\DualWriteEnvironmentManagementController.cs:line 265\]

Det här felet uppstår på grund av att en Power Apps-licens saknas. Tilldela användaren en lämplig licens (till exempel Power Apps Utvärderingsversion 2) så att användaren har behörighet att skapa anslutningarna. Om du vill verifiera licensen kan kunden gå till webbplatsen [Mitt konto](https://portal.office.com/account/?ref=MeControl#subscriptions) och visa licenserna som för tillfället har tilldelats användaren.

Mer information om att Power Apps licens finns i följande artiklar:

- [Tilldela licenser till användare](/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide)
- [Köp Power Apps till din organisation](/power-platform/admin/signup-for-powerapps-admin)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

