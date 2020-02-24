---
title: Autentisering
description: ''
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: 025feca31eed8649bc319a1e1a1b6d1af3ddb128
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010648"
---
# <a name="authentication"></a><span data-ttu-id="3af37-102">Autentisering</span><span class="sxs-lookup"><span data-stu-id="3af37-102">Authentication</span></span>

<span data-ttu-id="3af37-103">Den här artikeln innehåller översiktlig information om hur du autentiserar med Microsoft Dynamics 365 Human Resources API.</span><span class="sxs-lookup"><span data-stu-id="3af37-103">This article provides overview information about how to authenticate with the Microsoft Dynamics 365 Human Resources data application programming interface (API).</span></span>

## <a name="overview"></a><span data-ttu-id="3af37-104">Översikt</span><span class="sxs-lookup"><span data-stu-id="3af37-104">Overview</span></span>

<span data-ttu-id="3af37-105">Data-API för personal är en OData-implementering.</span><span class="sxs-lookup"><span data-stu-id="3af37-105">The data API for Human Resources is an OData implementation.</span></span> <span data-ttu-id="3af37-106">Mer information finns i [Öppna dataprotokoll (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span><span class="sxs-lookup"><span data-stu-id="3af37-106">For more information, see [Open Data Protocol (OData)](../fin-ops-core/dev-itpro/data-entities/odata.md).</span></span>

<span data-ttu-id="3af37-107">Ditt program måste autentiseras som en auktoriserad anropare innan API kan betjäna begäran från ditt program.</span><span class="sxs-lookup"><span data-stu-id="3af37-107">Your application must authenticate as an authorized caller before the API will service requests from your application.</span></span>

## <a name="fundamentals"></a><span data-ttu-id="3af37-108">Grunder</span><span class="sxs-lookup"><span data-stu-id="3af37-108">Fundamentals</span></span>

<span data-ttu-id="3af37-109">För att anropa data-API måste ditt program skaffa ett åtkomsttoken från Microsoft identitetsplattform.</span><span class="sxs-lookup"><span data-stu-id="3af37-109">To call the data API, your application must acquire an access token from the Microsoft identity platform.</span></span> <span data-ttu-id="3af37-110">Åtkomsttoken innehåller information om programmet och den behörighet som det måste ha för att kunna anropa resurser i personal.</span><span class="sxs-lookup"><span data-stu-id="3af37-110">The access token contains information about your application and the permission that it has to call resources in Human Resources.</span></span>

### <a name="access-token"></a><span data-ttu-id="3af37-111">Åtkomsttoken</span><span class="sxs-lookup"><span data-stu-id="3af37-111">Access token</span></span>

<span data-ttu-id="3af37-112">Åtkomsttoken som utfärdas av Microsoft identitetsplattform är base64 – kodad JavaScript Object Notation (JSON) webbtoken (JWTs).</span><span class="sxs-lookup"><span data-stu-id="3af37-112">Access tokens issued by the Microsoft identity platform are base64–encoded JavaScript Object Notation (JSON) Web Tokens (JWTs).</span></span> <span data-ttu-id="3af37-113">De innehåller information (anspråk) som används av data-API (och andra webb-API:er som skyddas av Microsoft identitetsplattform) för att validera anroparen och kontrollera att anroparen har rätt behörigheter för att utföra den åtgärd de begär.</span><span class="sxs-lookup"><span data-stu-id="3af37-113">They contain information (claims) that the data API (and other web APIs that are secured by the Microsoft identity platform) use to validate the caller and make sure that the caller has the correct permissions to perform the operation they're requesting.</span></span> <span data-ttu-id="3af37-114">Under anrop kan du behandla åtkomsttoken som täckande.</span><span class="sxs-lookup"><span data-stu-id="3af37-114">During calls, you can treat access tokens as opaque.</span></span> <span data-ttu-id="3af37-115">Du bör alltid skicka åtkomsttoken över en säker kanal, t.ex. TLS (Transport Layer Security) och Hypertext Transfer Protocol Secure (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="3af37-115">You should always transmit access tokens over a secure channel, such as Transport Layer Security (TLS) and Hypertext Transfer Protocol Secure (HTTPS).</span></span>

<span data-ttu-id="3af37-116">Här följer ett exempel på ett åtkomsttoken som utfärdas av Microsoft identitetsplattform.</span><span class="sxs-lookup"><span data-stu-id="3af37-116">Here is an example of an access token that is issued by the Microsoft identity platform.</span></span>

```jwt
EwAoA8l6BAAU7p9QDpi/D7xJLwsTgCg3TskyTaQAAXu71AU9f4aS4rOK5xoO/SU5HZKSXtCsDe0Pj7uSc5Ug008qTI+a9M1tBeKoTs7tHzhJNSKgk7pm5e8d3oGWXX5shyOG3cKSqgfwuNDnmmPDNDivwmi9kmKqWIC9OQRf8InpYXH7NdUYNwN+jljffvNTewdZz42VPrvqoMH7hSxiG7A1h8leOv4F3Ek/oeJX6U8nnL9nJ5pHLVuPWD0aNnTPTJD8Y4oQTp5zLhDIIfaJCaGcQperULVF7K6yX8MhHxIBwek418rKIp11om0SWBXOYSGOM0rNNN59qNiKwLNK+MPUf7ObcRBN5I5vg8jB7IMoz66jrNmT2uiWCyI8MmYDZgAACPoaZ9REyqke+AE1/x1ZX0w7OamUexKF8YGZiw+cDpT/BP1GsONnwI4a8M7HsBtDgZPRd6/Hfqlq3HE2xLuhYX8bAc1MUr0gP9KuH6HDQNlIV4KaRZWxyRo1wmKHOF5G5wTHrtxg8tnXylMc1PKOtaXIU4JJZ1l4x/7FwhPmg9M86PBPWr5zwUj2CVXC7wWlL/6M89Mlh8yXESMO3AIuAmEMKjqauPrgi9hAdI2oqnLZWCRL9gcHBida1y0DTXQhcwMv1ORrk65VFHtVgYAegrxu3NDoJiDyVaPZxDwTYRGjPII3va8GALAMVy5xou2ikzRvJjW7Gm3XoaqJCTCExN4m5i/Dqc81Gr4uT7OaeypYTUjnwCh7aMhsOTDJehefzjXhlkn//2eik+NivKx/BTJBEdT6MR97Wh/ns/VcK7QTmbjwbU2cwLngT7Ylq+uzhx54R9JMaSLhnw+/nIrcVkG77Hi3neShKeZmnl5DC9PuwIbtNvVge3Q+V0ws2zsL3z7ndz4tTMYFdvR/XbrnbEErTDLWrV6Lc3JHQMs0bYUyTBg5dThwCiuZ1evaT6BlMMLuSCVxdBGzXTBcvGwihFzZbyNoX+52DS5x+RbIEvd6KWOpQ6Ni+1GAawHDdNUiQTQFXRxLSHfc9fh7hE4qcD7PqHGsykYj7A0XqHCjbKKgWSkcAg==
```

<span data-ttu-id="3af37-117">Om du vill anropa data-API kopplar du åtkomsttoken som ett token till auktoriseringsrubriken i din HTTP-begäran.</span><span class="sxs-lookup"><span data-stu-id="3af37-117">To call the data API, you attach the access token as a bearer token to the authorization header in your HTTP request.</span></span> <span data-ttu-id="3af37-118">Här är ett exempel:</span><span class="sxs-lookup"><span data-stu-id="3af37-118">Here is an example.</span></span>

```HTTP
HTTP/1.1
Authorization: Bearer EwAoA8l6BAAU ... 7PqHGsykYj7A0XqHCjbKKgWSkcAg==
Host: https://{cluster}.hr.talent.dynamics.com
GET https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/JobTypes
```

## <a name="register-a-new-application-by-using-the-azure-portal"></a><span data-ttu-id="3af37-119">Registrera ett program med Azure-portalen</span><span class="sxs-lookup"><span data-stu-id="3af37-119">Register a new application by using the Azure portal</span></span>

1. <span data-ttu-id="3af37-120">Logga in på [Microsoft Azure-portalen](https://portal.azure.com) med ett arbets- eller skolkonto, eller ett personligt Microsoft-konto.</span><span class="sxs-lookup"><span data-stu-id="3af37-120">Sign in to the [Microsoft Azure portal](https://portal.azure.com) with a work or school account, or a personal Microsoft account.</span></span>

2. <span data-ttu-id="3af37-121">Om ditt konto ger dig åtkomst till fler än en innehavare väljer du ditt konto i det övre högra hörnet och ställer in portalsessionen till önskad Azure Active Directory (Azure AD) klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="3af37-121">If your account gives you access to more than one tenant, select your account in the upper-right corner, and set your portal session to the Azure Active Directory (Azure AD) tenant that you want.</span></span>

3. <span data-ttu-id="3af37-122">I vänstra fönstret, markera tjänsten **Azure Active Directory** och välj **Appregistreringar \> Ny registrering**.</span><span class="sxs-lookup"><span data-stu-id="3af37-122">In the left pane, select the **Azure Active Directory** service, and then select **App registrations \> New registration**.</span></span>

4. <span data-ttu-id="3af37-123">När sidan **registrera ett program** visas anger du programmets registreringsinformation:</span><span class="sxs-lookup"><span data-stu-id="3af37-123">When the **Register an application** page appears, enter your application's registration information:</span></span>

    - <span data-ttu-id="3af37-124">**Namn**: Ange ett meningsfullt programnamn som ska visas för användarna av appen.</span><span class="sxs-lookup"><span data-stu-id="3af37-124">**Name**: Enter a meaningful application name that will be shown to users of the app.</span></span>
    - <span data-ttu-id="3af37-125">**Konto typer som stöds**: Välj de typer av konton som din app ska ha stöd för.</span><span class="sxs-lookup"><span data-stu-id="3af37-125">**Supported account types**: Select the types of accounts that your app should support.</span></span>

        | <span data-ttu-id="3af37-126">Kontotyper som stöds</span><span class="sxs-lookup"><span data-stu-id="3af37-126">Supported account types</span></span> | <span data-ttu-id="3af37-127">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3af37-127">Description</span></span> |
        |-------------------------|-------------|
        | <span data-ttu-id="3af37-128">Endast konton i den här organisationsenhetskatalogen</span><span class="sxs-lookup"><span data-stu-id="3af37-128">Accounts in this organizational directory only</span></span> | <span data-ttu-id="3af37-129">Välj det här alternativet om du bygger en app med affärsmässiga företag.</span><span class="sxs-lookup"><span data-stu-id="3af37-129">Select this option if you're building a line-of-business app.</span></span> <span data-ttu-id="3af37-130">Det här alternativet är inte tillgängligt om du inte registrerar programmet i en katalog.</span><span class="sxs-lookup"><span data-stu-id="3af37-130">This option isn't available unless you're registering the app in a directory.</span></span><p><span data-ttu-id="3af37-131">Det här alternativet är endast mappat till en **Azure AD-innehavare**.</span><span class="sxs-lookup"><span data-stu-id="3af37-131">This option is mapped to **Azure AD only single-tenant**.</span></span></p><p><span data-ttu-id="3af37-132">Det här alternativet är standardalternativet om du inte registrerar appen utanför en katalog.</span><span class="sxs-lookup"><span data-stu-id="3af37-132">This option is the default option unless you're registering the app outside a directory.</span></span> <span data-ttu-id="3af37-133">I det fallet är standardalternativet **Azure AD flera innehavare och personliga Microsoft-konton**.</span><span class="sxs-lookup"><span data-stu-id="3af37-133">In that case, the default option is **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p> |
        | <span data-ttu-id="3af37-134">Endast konton en organisationsenhetskatalog</span><span class="sxs-lookup"><span data-stu-id="3af37-134">Accounts in any organizational directory</span></span> | <span data-ttu-id="3af37-135">Välj det här alternativet om du vill rikta alla affärs- och utbildningskunder.</span><span class="sxs-lookup"><span data-stu-id="3af37-135">Select this option to target all business and educational customers.</span></span><p><span data-ttu-id="3af37-136">Det här alternativet är endast mappat till en **Azure AD flera innehavare**.</span><span class="sxs-lookup"><span data-stu-id="3af37-136">This option is mapped to **Azure AD only multi-tenant**.</span></span></p><p><span data-ttu-id="3af37-137">Om du har registrerat appen som endast en **Azure AD innehavare**, kan du använda bladet **verifiering** för att uppdatera det till endast flera **Azure AD innehavare** och sedan tillbaka till endast en **Azure AD innehavare**.</span><span class="sxs-lookup"><span data-stu-id="3af37-137">If you registered the app as **Azure AD only single-tenant**, you can use the **Authentication** blade to update it to **Azure AD only multi-tenant** and then back to **Azure AD only single-tenant**.</span></span></p> |
        | <span data-ttu-id="3af37-138">Konton i alla organisationskataloger och privata Microsoft-konton</span><span class="sxs-lookup"><span data-stu-id="3af37-138">Accounts in any organizational directory and personal Microsoft accounts</span></span> | <span data-ttu-id="3af37-139">Välj det här alternativet om du vill rikta de bredaste kunduppsättningarna.</span><span class="sxs-lookup"><span data-stu-id="3af37-139">Select this option to target the widest set of customers.</span></span><p><span data-ttu-id="3af37-140">Det här alternativet mappas till **Azure AD flera innehavare och personliga Microsoft-konton**.</span><span class="sxs-lookup"><span data-stu-id="3af37-140">This option is mapped to **Azure AD multi-tenant and personal Microsoft accounts**.</span></span></p><p><span data-ttu-id="3af37-141">Om du har registrerat appen som **Azure AD flera innehavare och personliga Microsoft-konton**kan du inte ändra den här inställningen i användargränssnittet.</span><span class="sxs-lookup"><span data-stu-id="3af37-141">If you registered the app as **Azure AD multi-tenant and personal Microsoft accounts**, you can't change this setting in the user interface (UI).</span></span> <span data-ttu-id="3af37-142">I stället måste du använda programmets manifestredigeraren för att ändra de kontotyper som stöds.</span><span class="sxs-lookup"><span data-stu-id="3af37-142">Instead, you must use the application manifest editor to change the supported account types.</span></span></p> |

    - <span data-ttu-id="3af37-143">**Omdirigera URI (valfritt)** – Välj den typ av app som du skapar: **webb** eller **offentlig klient (mobil och skrivbord)**.</span><span class="sxs-lookup"><span data-stu-id="3af37-143">**Redirect URI (optional)** – Select the type of app that you're building: **Web** or **Public client (mobile & desktop)**.</span></span> <span data-ttu-id="3af37-144">Ange sedan omdirigerings-URI (eller svars-URL) för appen.</span><span class="sxs-lookup"><span data-stu-id="3af37-144">Then enter the redirect URI (or reply URL) for the app.</span></span>

        - <span data-ttu-id="3af37-145">Ange bas-URL:en för webbprogram.</span><span class="sxs-lookup"><span data-stu-id="3af37-145">For web apps, provide the base URL of the app.</span></span> <span data-ttu-id="3af37-146">Till exempel `http://localhost:31544` kan vara URL:en för ett webbprogram som körs på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="3af37-146">For example, `http://localhost:31544` might be the URL for a web app that runs on your local machine.</span></span> <span data-ttu-id="3af37-147">Användarna använder sedan denna URL för att logga in i en webbklientapp.</span><span class="sxs-lookup"><span data-stu-id="3af37-147">Users then use this URL to sign in to a web client app.</span></span>
        - <span data-ttu-id="3af37-148">För offentliga klientprogram anger du den URI som Azure AD använder för att returnera tokenbegäran.</span><span class="sxs-lookup"><span data-stu-id="3af37-148">For public client apps, provide the URI that Azure AD uses to return token responses.</span></span> <span data-ttu-id="3af37-149">Ange ett värde som är specifikt för din app, till exempel `myapp://auth`.</span><span class="sxs-lookup"><span data-stu-id="3af37-149">Enter a value that is specific to your app, such as `myapp://auth`.</span></span>

        <span data-ttu-id="3af37-150">Specifika exempel på webbprogram och egna program finns i snabbstartsprogrammen i [Microsoft identitetsplattform (tidigare Azure Active Directory för utvecklare)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).</span><span class="sxs-lookup"><span data-stu-id="3af37-150">To see specific examples for web apps or native apps, see the quickstarts in [Microsoft identity platform (formerly Azure Active Directory for developers)](https://docs.microsoft.com/azure/active-directory/develop/#quickstarts).</span></span>

5. <span data-ttu-id="3af37-151">Under **API-behörighet**, välj **Lägg till behörighet**.</span><span class="sxs-lookup"><span data-stu-id="3af37-151">Under **API permissions**, select **Add a permission**.</span></span> <span data-ttu-id="3af37-152">Sedan på fliken **API:er som min organisation använder** söker du efter **Dynamics 365 Human Resources** och lägger till behörigheten **användare\_personifiering** till din app.</span><span class="sxs-lookup"><span data-stu-id="3af37-152">Then, on the **APIs my organization uses** tab, search for **Dynamics 365 Human Resources**, and add the **user\_impersonation** permission to your app.</span></span> <span data-ttu-id="3af37-153">Program-ID för personal är f9be0c49-aa22-4ec6-911a-c5da515226ff.</span><span class="sxs-lookup"><span data-stu-id="3af37-153">The Application ID for Human Resources is f9be0c49-aa22-4ec6-911a-c5da515226ff.</span></span> <span data-ttu-id="3af37-154">Använd detta ID för att kontrollera att du har valt rätt program.</span><span class="sxs-lookup"><span data-stu-id="3af37-154">Use this ID to ensure you have chosen the correct application.</span></span>

6. <span data-ttu-id="3af37-155">Välj **Registrera**.</span><span class="sxs-lookup"><span data-stu-id="3af37-155">Select **Register**.</span></span>

   <span data-ttu-id="3af37-156">[![Registrera en ny app i Azure-portalen](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3af37-156">[![Registering a new app in the Azure portal](media/api-new-app-registration-expanded.png)](media/api-new-app-registration-expanded.png#lightbox)</span></span>

<span data-ttu-id="3af37-157">Azure AD tilldelar ditt program ett unikt program-ID och går till sidan **översikt** för din app.</span><span class="sxs-lookup"><span data-stu-id="3af37-157">Azure AD assigns a unique application ID (client ID) to your app, and takes you to the **Overview** page for your app.</span></span> <span data-ttu-id="3af37-158">Om du vill lägga till fler funktioner i din app kan du välja andra konfigurationsalternativ, till exempel alternativ för anpassning och för certifikat och hemligheter.</span><span class="sxs-lookup"><span data-stu-id="3af37-158">To add more capabilities to your app, you can select other configuration options, such as options for branding and for certificates and secrets.</span></span>

## <a name="retrieving-an-access-token"></a><span data-ttu-id="3af37-159">Hämta en åtkomsttoken</span><span class="sxs-lookup"><span data-stu-id="3af37-159">Retrieving an access token</span></span>

<span data-ttu-id="3af37-160">Information om hur du hämtar en åtkomsttoken för anrop till API för Personal beror på vilken teknik du använder för att utveckla klient programmet.</span><span class="sxs-lookup"><span data-stu-id="3af37-160">The specifics of how you retrieve an access token for calling the Human Resources data API will depend on what technologies you're using to develop your client application.</span></span> <span data-ttu-id="3af37-161">Du kan till exempel [testa med ett tredje parts verktyg](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (t.ex. med brevbärare), utveckla ett C#-konsolprogram eller en webbtjänst eller skapa en JavaScript/typescript-klient.</span><span class="sxs-lookup"><span data-stu-id="3af37-161">For example, you might be [testing with a third party utility](../fin-ops-core/dev-itpro/data-entities/third-party-service-test.md) (such as Postman), developing a C# console application or web service, or building a javascript/TypeScript client.</span></span>

<span data-ttu-id="3af37-162">Exempel C# klientprogram:</span><span class="sxs-lookup"><span data-stu-id="3af37-162">Example C# client application:</span></span>
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

<span data-ttu-id="3af37-163">När du har hämtat en åtkomsttoken överför du token i auktoriseringsrubriken som ett ansvarigt token till varje begäran som du skickar till data-API enligt beskrivningen ovan.</span><span class="sxs-lookup"><span data-stu-id="3af37-163">Once you've retrieved an access token, you'll pass the token in the Authorization header as a bearer token with each request you send to the data API, as described above.</span></span>
