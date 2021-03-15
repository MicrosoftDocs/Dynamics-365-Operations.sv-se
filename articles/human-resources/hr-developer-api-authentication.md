---
title: Äkthetsbevisning
description: Den här artikeln innehåller översiktlig information om hur du autentiserar med Microsoft Dynamics 365 Human Resources API.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 963bec2b817c59e3b5860c5ff5885e165ec8656a
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115570"
---
# <a name="authentication"></a>Äkthetsbevisning

Den här artikeln innehåller översiktlig information om hur du autentiserar med Microsoft Dynamics 365 Human Resources API.

## <a name="overview"></a>Översikt

Data-API för personal är en OData-implementering. Mer information finns i [Öppna dataprotokoll (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).

Ditt program måste autentiseras som en auktoriserad anropare innan API kan betjäna begäran från ditt program.

## <a name="fundamentals"></a>Grunder

För att anropa data-API måste ditt program skaffa ett åtkomsttoken från Microsoft identitetsplattform. Åtkomsttoken innehåller information om programmet och den behörighet som det måste ha för att kunna anropa resurser i personal.

### <a name="access-token"></a>Åtkomsttoken

Åtkomsttoken som utfärdas av Microsoft identitetsplattform är base64 – kodad JavaScript Object Notation (JSON) webbtoken (JWTs). De innehåller information (anspråk) som används av data-API (och andra webb-API:er som skyddas av Microsoft identitetsplattform) för att validera anroparen och kontrollera att anroparen har rätt behörigheter för att utföra den åtgärd de begär. Under anrop kan du behandla åtkomsttoken som täckande. Du bör alltid skicka åtkomsttoken över en säker kanal, t.ex. TLS (Transport Layer Security) och Hypertext Transfer Protocol Secure (HTTPS).

Här följer ett exempel på ett åtkomsttoken som utfärdas av Microsoft identitetsplattform.

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

Om du vill anropa data-API kopplar du åtkomsttoken som ett token till auktoriseringsrubriken i din HTTP-begäran. Här är ett exempel:

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a>Registrera ett program med Azure-portalen

1. Logga in på [Microsoft Azure-portalen](https://portal.azure.com) med ett arbets- eller skolkonto, eller ett personligt Microsoft-konto.

2. Om ditt konto ger dig åtkomst till fler än en innehavare väljer du ditt konto i det övre högra hörnet och ställer in portalsessionen till önskad Azure Active Directory (Azure AD) klientorganisation.

3. I vänstra fönstret, markera tjänsten **Azure Active Directory** och välj **Appregistreringar \> Ny registrering**.

4. När sidan **registrera ett program** visas anger du programmets registreringsinformation:

    - **Namn**: Ange ett meningsfullt programnamn som ska visas för användarna av appen.
    - **Konto typer som stöds**: Välj de typer av konton som din app ska ha stöd för.

        | Kontotyper som stöds | Beskrivning |
        |-------------------------|-------------|
        | Endast konton i den här organisationsenhetskatalogen | Välj det här alternativet om du bygger en app med affärsmässiga företag. Det här alternativet är inte tillgängligt om du inte registrerar programmet i en katalog.<p>Det här alternativet är endast mappat till en **Azure AD-innehavare**.</p><p>Det här alternativet är standardalternativet om du inte registrerar appen utanför en katalog. I det fallet är standardalternativet **Azure AD flera innehavare och personliga Microsoft-konton**.</p> |
        | Endast konton en organisationsenhetskatalog | Välj det här alternativet om du vill rikta alla affärs- och utbildningskunder.<p>Det här alternativet är endast mappat till en **Azure AD flera innehavare**.</p><p>Om du har registrerat appen som endast en **Azure AD innehavare**, kan du använda bladet **verifiering** för att uppdatera det till endast flera **Azure AD innehavare** och sedan tillbaka till endast en **Azure AD innehavare**.</p> |
        | Konton i alla organisationskataloger och privata Microsoft-konton | Välj det här alternativet om du vill rikta de bredaste kunduppsättningarna.<p>Det här alternativet mappas till **Azure AD flera innehavare och personliga Microsoft-konton**.</p><p>Om du har registrerat appen som **Azure AD flera innehavare och personliga Microsoft-konton** kan du inte ändra den här inställningen i användargränssnittet. I stället måste du använda programmets manifestredigeraren för att ändra de kontotyper som stöds.</p> |

    - **Omdirigera URI (valfritt)** – Välj den typ av app som du skapar: **webb** eller **offentlig klient (mobil och skrivbord)**. Ange sedan omdirigerings-URI (eller svars-URL) för appen.

        - Ange bas-URL:en för webbprogram. Till exempel `http://localhost:31544` kan vara URL:en för ett webbprogram som körs på den lokala datorn. Användarna använder sedan denna URL för att logga in i en webbklientapp.
        - För offentliga klientprogram anger du den URI som Azure AD använder för att returnera tokenbegäran. Ange ett värde som är specifikt för din app, till exempel `myapp://auth`.

        Specifika exempel på webbprogram och egna program finns i snabbstartsprogrammen i [Microsoft identitetsplattform (tidigare Azure Active Directory för utvecklare)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).

5. Under **API-behörighet**, välj **Lägg till behörighet**. Sedan på fliken **API:er som min organisation använder** söker du efter **Dynamics 365 Human Resources** och lägger till behörigheten **användare\_personifiering** till din app. Program-ID för personal är f9be0c49-aa22-4ec6-911a-c5da515226ff. Använd detta ID för att kontrollera att du har valt rätt program.

6. Välj **Registrera**.

   [![Registrera en ny app i Azure-portalen](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)

Azure AD tilldelar ditt program ett unikt program-ID och går till sidan **översikt** för din app. Om du vill lägga till fler funktioner i din app kan du välja andra konfigurationsalternativ, till exempel alternativ för anpassning och för certifikat och hemligheter.

## <a name="retrieving-an-access-token"></a>Hämta en åtkomsttoken

Information om hur du hämtar en åtkomsttoken för anrop till API för Personal beror på vilken teknik du använder för att utveckla klient programmet. Du kan till exempel [testa med ett tredje parts verktyg](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (t.ex. med brevbärare), utveckla ett C#-konsolprogram eller en webbtjänst eller skapa en JavaScript/typescript-klient.

Exempel C# klientprogram:
```C#
using System;
using System.Net.Http;
using System.Threading.Tasks;

// requires appropriate NuGet package references in the project
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace TalentODataPoC
{
    class Program
    {
        // prereq: This client app must be registered in Azure Active Directory. The app must be
        // registered as requiring permission to the Dynamics 365 for Talent API (with the Dynamics
        // HCM Workload delegated permission).
        static string clientId = "4fc703ef-672c-4e2c-813f-2f9d29d726db"; // This value should be obtained from AAD and must match your registered app
        static string talentNamespaceUri = "";

        public static async Task CallTalentODataService()
        {
            // authority URI
            UriBuilder uri = new UriBuilder("https://login.microsoftonline.com/common");
            AuthenticationContext authenticationContext = new AuthenticationContext(uri.ToString());

            // request token for the resource we want to access (Human Resources). This will authenticate
            // the user and return an access token containing claims for the authenticated user.
            var authResult = await authenticationContext.AcquireTokenAsync(
                "http://hr.talent.dynamics.com", /*Talent app id or resource URI*/
                clientId, /*registered client app id*/
                new Uri("https://localhost"), /*redirect URI, as registered in your AAD app*/
                new PlatformParameters(PromptBehavior.SelectAccount));

            // create the authorization header, which needs to be passed in the Header of the HTTP Requests to Talent
            string authHeader = authResult.CreateAuthorizationHeader();

            // HINT: paste the JWT into https://jwt.ms to decode and view it
            Console.Write("authHeader: ");
            Console.WriteLine(authHeader);
            Console.WriteLine();

            HttpClient client = new HttpClient();
            client.DefaultRequestHeaders.Add("Authorization", authHeader);

            string s;

            Console.Write("Talent Namespace URI: ");
            Console.WriteLine(talentNamespaceUri);
            Console.WriteLine();

            // call the OData service to get JobType data from Talent
            var resultOdata = await client.GetAsync(talentNamespaceUri + "data/JobTypes");
            s = await resultOdata.Content.ReadAsStringAsync();
            Console.WriteLine(s);
            Console.WriteLine();
        }

        static void Main(string[] args)
        {
            Console.WriteLine();

            // if the user passes in a single parameter, assume it is the namespaceUri for Talent
            if (args.Length == 1)
            {
                talentNamespaceUri = args[0];
            } else if (args.Length == 0)
            {
                Console.WriteLine("Enter Talent URL including namespace.");
                Console.WriteLine("Example: https://aos-rts-sf-21454f9d830-prod-westus2.hr.talent.dynamics.com/namespaces/2328af1a-2d45-4c6a-99e3-12a4c3867dcf/");
                Console.Write("> ");
                talentNamespaceUri = Console.ReadLine();
                if (!talentNamespaceUri.EndsWith("/"))
                {
                    talentNamespaceUri = talentNamespaceUri + "/";
                }
            } else
            {
                Console.WriteLine("Unexpected Arguments");
                System.Environment.Exit(1);
            }

            Task t = Program.CallTalentODataService();
            t.Wait();
        }
    }
}
```

När du har hämtat en åtkomsttoken överför du token i auktoriseringsrubriken som ett ansvarigt token till varje begäran som du skickar till data-API enligt beskrivningen ovan.


[!INCLUDE[footer-include](../includes/footer-banner.md)]