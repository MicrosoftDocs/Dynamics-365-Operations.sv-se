---
title: Spåra övergivna kundvagnar och skicka meddelanden till kunder
description: Detta ämne beskriver hur du anpassar exempelanslutningsprogrammet med övergivna Microsoft Dynamics 365 Commerce-kundvagnar för att hitta övergivna kundvagnar och skicka påminnelsemeddelanden till kunder via e-post.
author: bicyclingfool
ms.date: 02/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 82848f1ff068cea0adfc6ec1b33fc4bb035f78dc
ms.sourcegitcommit: 374bbdde90fc9a68c0799158a50409bfbe8ca64e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353368"
---
# <a name="detect-abandoned-carts-and-send-notifications-to-customers"></a>Spåra övergivna kundvagnar och skicka meddelanden till kunder

[!include [banner](../includes/banner.md)]

Detta ämne beskriver hur du anpassar exempelanslutningsprogrammet med övergivna Microsoft Dynamics 365 Commerce-kundvagnar för att hitta övergivna kundvagnar och skicka påminnelsemeddelanden till kunder via e-post.

Möjligheten att ta igen intäkter och behålla kunder med hjälp av övergivna kundvagnsmeddelanden är en viktig kapacitet som Dynamics 365 Commerce stöder. Genom att anpassa Commerce-exempelprogrammet för övergivna kundvagnar kan återförsäljare få åtkomst till kundvagnar i Retail Server som inte har ändrats under ett tidsfönster som butikerna anger. Dessa kundvagnar kan sedan hämtas, utökas med produkt- och kunddata och skickas vidare till en tredje parts leverantör för marknadsföring via e-post som kan generera e-postmeddelanden och skicka dem till kunderna.

Det övergivna e-postmeddelandet som kunderna får kan innehålla följande information:

- Kundens förnamn.
- Kundens efternamn.
- Kundens e-postadress.
- En URL som returnerar kunden till kundvagnen.
- Transaktionsvalutan.
- En lista med produkter i kundvagnen. För varje produkt ingår följande information:

    - Produktens visningsnamn
    - Produkt-ID (används för att skapa en URL till produktbeskrivningssidan)
    - En produktbild som kan ändras automatiskt för olika visningsstorlekar
    - Produktbildens alternativtext
    - Produktens enhetspris

## <a name="abandoned-cart-connector-sample"></a>Anslutningsprogramexempel för övergiven kundvagn

En modell för anslutningsprogram som Microsoft tillhandahåller via programutvecklingsprogrammet för Retail (SDK) gör det möjligt att hämta och skicka information om övergivna kundvagnar till en tredjepartsleverantör av marknadsföring via e-post. Detta anslutningsprogram hanterar kommunikationen med Retail Server, använder Azure Key Vault för säkerhet, hanterar tidsplanering av vagnhämtning för ett angivet tidsfönster och hämtar order- och produktdata. Det tillhandahåller också en exempelimplementering för en integrering med en tredjepartsleverantör för marknadsföring via e-post. Anslutningsprogrammet har utformats för att kunna kommunicera med [Emarsys](https://emarsys.com) direkt vid leverans. Det kan dock enkelt anpassas till att integreras med andra lösningar, till exempel Constant Contact, Mailchimp och SendGrid.

I följande bild visas komponenterna i exempelanslutningsprogrammet för övergiven kundvagn.

![Komponenter i exempelanslutningsprogrammet för övergiven kundvagn](media/AbandonedCartConnector.png)

> [!IMPORTANT]
> I vissa regioner måste kunderna kunna välja att inte skicka informationen i vagnen till en leverantör av marknadsföring via e-post, eller begära att deras data ska tas bort. Microsoft tillhandahåller emellertid inte dessa alternativ för kunder. Om du tänker göra affärer i regioner som kräver dem måste du därför tillhandahålla den infrastruktur och de anpassningar som krävs för att spåra kundernas önskemål och utifrån dessa förhindra att kunddata överförs till din e-postplattform. Du måste även definiera en process för att rensa kunddata från din leverantör av marknadsföring via e-post på kundens begäran.

## <a name="obtain-the-code-sample"></a>Hämta exempelkoden

Exempelanslutningsprogrammet för övergiven kundvagn inkluderas i Retail SDK från och med version 10.0.16. Koden finns under **\\RetailSDK\\Code\\SampleExtensions\\RetailServer\\Extensions.AbandonedCartSample**. Mer information om Retail SDK och var du hittar det finns i [Programutvecklingskit för Retail (SDK)](retail-sdk/retail-sdk-overview.md).

> [!NOTE]
> Provkoden görs först tillgänglig i version 10.0.16-versioner, men den är kompatibel med version 10.0.13 och senare versioner av Retail Server.

## <a name="prerequisites-and-dependencies"></a>Förutsättningar och beroenden

Innan du kan distribuera och konfigurera exempelanslutningsprogrammets exempelkod för övergivna kundvadnar måste följande förutsättningar uppfyllas.

### <a name="access-to-commerce-resources"></a>Åtkomst till handelsresurser

Om du vill konfigurera och distribuera anslutningsprogrammet för övergivna kundvagnar måste du ha åtkomst till följande handelsresurser:

- Administratörsåtkomst till Commerce Headquarters för din miljö
- Åtkomst till Microsoft Dynamics Lifecycle Services-projektet (LCS) för din miljö

### <a name="azure-cosmos-db"></a>Azure Cosmos DB

Anslutningsprogrammet för övergivna kundvagnar använder Azure Cosmos DB för att spåra ID och tidsstämplar för kundvagnar som tidigare hämtats. Med Azure Cosmos DB kan du fortsätta lagra dessa data eller anpassa kodexempel så att detta kan integreras med andra datalagringsalternativ. Mer information om Azure Cosmos DB finns i [Välkommen till Azure Cosmos DB](/azure/cosmos-db/introduction).

Om du använder Azure Cosmos DB måste följande villkor uppfyllas innan du kan köra exemplet:

- Du måste ha ett Azure Cosmos DB-konto. Om du inte har något konto hittar du mer information i [Skapa ett databaskonto](/azure/cosmos-db/create-sql-api-dotnet#create-a-database-account).
- Du måste hämta värdena för **URI** och **PRIMÄRNYCKEL** (eller **SEKUNDÄRNYCKEL**) från fliken **Nycklar** i ditt Azure Cosmos DB-konto i Azure-portalen. Mer information om hur du hämtar slutpunkts- och nyckelinformation för ditt Azure Cosmos DB-konto finns i [Visa, kopiera och generera om åtkomstnycklar och lösenord](/azure/cosmos-db/manage-account#keys).

### <a name="azure-key-vault"></a>Azure Key Vault

Anslutningsprogrammet för övergivna kundvagnar använder Key Vault för att lagra namn och hemligheter för de olika komponenter som kräver säker åtkomst.

Följ dessa steg för att ställa in ett nyckelvalv.

1. Följ instruktionerna i [Hantera Key Vault i Azure Stack Hub med hjälp av portalen](/azure-stack/user/azure-stack-key-vault-manage-portal?view=azs-2002&preserve-view=true).
2. Skapa hemligheter för följande information:

    - Användarnamn och API-hemlighet för Emarsys-programprogrammeringsgränssnitt (API)
    - ID och henlighet för program för övergiven kundvagn

Exempelkoden för anslutningsprogram för övergiven kundvagn använder Azures standardautentiseringsuppgifter för åtkomst till Key Vault. Du måste tillhandahåll abehörigheterna **Lista** och **Läs** till den identitet med vilken du avser använda Key Vault.

Mer information om standardautentiseringsuppgifter för Azure finns i [DefaultAzureCredential Class](/dotnet/api/azure.identity.defaultazurecredential?view=azure-dotnet&preserve-view=true).

## <a name="create-an-abandoned-cart-connector-sample-app-application-id-for-the-azure-ad-tenant"></a>Skapa ett ID för exempelprogram för övergiven kundvagn för Azure AD-klientorganisationen

Du måste skapa ett exempelanslutningsprogram-ID för övergiven kundvagn för Azure Active Directory-klientorganisationen (AD). För information om hur du skapar ett program-ID, se [Så här använder du portalen för att skapa ett Azure AD-program och ett huvudkonto med åtkomst till resurser](/azure/active-directory/develop/howto-create-service-principal-portal).

## <a name="add-the-abandoned-cart-connector-sample-app-application-id-to-the-allow-list-for-the-retail-server-api"></a>Lägg ditt ID för exempelanslutningsprogram för övergiven kundvagn i listan över tillåtna program-ID:n för Retail Server-API:t

Därefter måste du lägtga till ditt ID för exempelanslutningsprogram för övergiven kundvagn i listan över tillåtna program-ID:n för Retail Server-API:t. Information om hur du lägger till ett program-ID i den tillåtna listan i Azure finns i [Support for Service to Service-autentisering i Retail Server](https://community.dynamics.com/ax/b/axforretail/posts/support-for-service-to-service-authentication-in-retail-server).

## <a name="configure-the-abandoned-cart-connector-sample-app"></a>Konfigurera exempelanslutningsprogrammet för övergiven kundvagn

Om du vill konfigurera exempelanslutningsprogrammet för övergiven kundvagn ändrar du inställningsfilen **appSettings.json** som finns i roten av katalogen **AbandonedCartDetectionSample**. I följande tabeller beskrivs egenskaperna för inställningsfilen.

### <a name="keyvaultoptions"></a>KeyVaultOptions

| Egenskap    | Beskrivning |
| ----------- | ----------- |
| KeyVaultURI | DNS-namnet på det nyckelvalv som du använder i Azure-portalen. |

### <a name="retailserverclientoptions"></a>RetailServerClientOptions

| Egenskap                                      | Beskrivning |
| --------------------------------------------- | ----------- |
| TenantId                                      | Klientorganisations-ID för Azure AD för din Azure-klientorganisation. |
| RetailServerAudienceId                        | ID:t för Retail Server-målgruppen. Du kan lämna kvar standardvärdet. |
| AppIdKeyVaultSecretName                       | Namnet på den hemlighet som du skapade för ditt exempelanslutningsprogram-ID för övergiven kundvagn. |
| AppSecretKeyVaultSecretName                   | Namnet på den hemlighet som lagrar app-hemligheten för ditt exempelanslutningsprogram-ID för övergiven kundvagn. |
| RetailServerUrl                               | URL-adressen till din Retail Server-instans. Detta värde finns i LCS. |
| OperatingUnitNumber                           | Driftenhetsnummer (OUN). Detta värde finns i administrationen för Commerce. |
| IncludeAbandonedCartsModifiedSinceLastMinutes | Början på tidsfönstret för de övergivna kundvagnarna som du vill hämta. Värdet uttrycks som ett antal minuter före den aktuella tiden. Ange exempelvis denna egenskap som **120** om du vill hämta alla kundvagnar som senast ändrades för mellan 120 minuter sedan och slutet på tidsfönstret som definieras av egenskapen **ExcludeAbandonedCartsModifiedSinceLastMinutes**. |
| ExcludeAbandonedCartsModifiedSinceLastMinutes | Slutet på tidsfönstret för de övergivna kundvagnarna som du vill hämta. Värdet uttrycks som ett antal minuter före den aktuella tiden. Om till exempel egenskapen **IncludeAbandonedCartsModifiedSinceLastMinutes** har satts till **120** anger du denna egenskap som **30** för att hämta alla vagnar som ändrades för melland 120 minuter sedan och 30 minuter sedan. I praktiken definierar den här egenskapen hur lång tid du vill vänta innan en vagn förklaras vara övergiven. |
| ReturnToCartUrl                               | Webbadressen till vagnen på webbplatsen för näthändel i det format som används i filen **app.config**. |

### <a name="azurecosmosoptions"></a>AzureCosmosOptions

Jobbstatusen för hämtning av övergiven vagn, vagns-ID samt ändrade tidsstämplar lagras i Azure Cosmos DB. Som standard pekar inställningarna i konfigurationsfilen mot den lokala emulatorinstansen av Azure Cosmos DB. När du distribuerar anslutningsprogrammet till produktion måste du uppdatera dessa inställningar så att de pekar mot Azure-instansen Cosmos DB i ditt Azure-abonnemang. Du kan avnvända [Azure Cosmos-emulatorn](/azure/cosmos-db/local-emulator) för lokal testning och testning i samndbox-miljö.

| Egenskap    | Beskrivning |
| ----------- | ----------- |
| EndPointUri | Slutpunkts-URI som tillhandahålls av Azure eller emulatorn. |
| PrimaryKey  | Den primära nyckel som tillhandahålls av Azure eller emulatorn. |
| DatabaseId  | Databasens ID. Du kan lämna standardvärdet som det är eller ange ett eget. |
| ContainerId | Behållarens ID. Du kan lämna standardvärdet som det är eller ange ett eget. |

### <a name="emarsysclientoptions"></a>EmarsysClientOptions

> [!NOTE]
> Om du integrerar med en annan leverantör av e-postmarknadsföring än Emarsys måste du utöka gränssnittet för **IEmailProvider** för att kunna kommunicera med denna leverantör.

| Egenskap                      | Beskrivning |
| ----------------------------- | ----------- |
| ApiUrl                        | `https://api.emarsys.net/api/v2/event/{0}/trigger` |
| ExternalEventId               | ID:t för den externa händelseposten som skapas i Emarsys. Värdet under **Utlösarinställningar** i kampanjen som du skapat för att skicka e-postmeddelanden om övergivna kundvagnar. |
| ApiUserNameKeyVaultSecretName | Namnet på nyckeln där användarnamnet för Emarsys API lagras. |
| ApiSecretKeyVaultSecretName   | Namnet på nyckeln där hemligheten för Emarsys API lagras. |
| EmarsysContactKeyId           | ID:t för e-postkolumnen i Emarsys-kontaktdatabasen. Standardvärdet är **3** och bör inte ändras. |

### <a name="mediaoptions"></a>MediaOptions

Om du använder näthandelsfunktionerna i Handel kan du använda Hantering av digitala tillgångar i Handel för att hämta produktbilder. Mer information om möjligheten att ändra bildstorlek i hantering av digitala tillgångar finns i [ImageSettings viewport-konfigurationen](../e-commerce-extensibility/image-component.md#imagesettings-viewport-configuration).

| Egenskap                             | Beskrivning |
| ------------------------------------ | ----------- |
| ImageServerUrl                       | Rot-URL-adressen till webbplatsens hanterare för digitala tillgångar. Värdet finns i egenskapsnyckeln för **Media Server Base-URL** på **Butik och handel \> Kanalinställningar \> Kanalprofiler** i Handelsadministrationen. |
| ImageViewPorts                       | Behållarnoden för enskilda konfigurationer för visningsområde. |
| ImageViewPorts/viewport              | Definitionen för visningsområde. Använd denna egenskap om du vill ange visningsområdets breddintervall i pixlar. Ett exempel på hur egenskapen används finns i konfigurationsfilen **appSettings.json**. |
| ImageViewPorts/imageWidth            | Visningsområdets bildbredd i pixlar. |
| imageViewPorts/imageHeight           | Visningsområdets bildhöjd i pixlar. |
| imageViewPorts/useForDefaultImageTag | Ett **sant**/**falskt** värde som anger om de bilddimensioner som definieras av visningsområdet ska användas om `<picture>` HTML-taggen inte stöds av en webbläsare eller e-postklient. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
