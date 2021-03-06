---
title: Tillägg för lagersynlighet
description: I det här avsnittet beskrivs hur du installerar och konfigurerar tillägg för lagersynlighet för Dynamics 365 Supply Chain Management.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 84f5e949f0c81f840c8a9086d05bbcfc576e42aa
ms.sourcegitcommit: b67665ed689c55df1a67d1a7840947c3977d600c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6017016"
---
# <a name="inventory-visibility-add-in"></a>Tillägg för lagersynlighet

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

Tillägget för lagersynlighet är en oberoende och mycket skalbar mikrotjänst som möjliggör spårning av lagerbehållning i realtid, vilket ger en global vy över lagersynlighet.

All information som rör lagerbehållning exporteras till tjänsten i nära real tid genom SQL-integration på låg nivå. Externa system kommer åt tjänsten via RESTful-API:er för att fråga efter information om givna dimensionsuppsättningar och på så sätt hämta en lista över tillgängliga lagerbehållningar.

Lagersynlighet är en mikrotjänst som bygger på Microsoft Dataverse, vilket innebär att du kan utöka den genom att bygga Power Apps och använda Power BI för att tillgodose dina affärsbehov. Det går också att uppgradera indexet för att göra lagerfrågeställningar.

Lagersynlighet innehåller konfigurationsalternativ som kan integreras med flera system från andra tillverkare. Det stöder standardiserad lagerdimension, anpassad utökning och standardiserade, konfigurerbara kvantiteter som kan konfigureras.

I det här avsnittet beskrivs hur du installerar och konfigurerar tillägget för lagersynlighet för Dynamics 365 Supply Chain Management och hur du använder dess API (Application Programming Interface).

## <a name="install-the-inventory-visibility-add-in"></a>Installera tillägget för lagersynlighet

Du måste installera tillägget för lagersynlighet med hjälp av Microsoft Dynamics Lifecycle Services (LCS). LCS är en samarbetsportal som tillhandahåller en miljö och en uppsättning regelbundet uppdaterade tjänster som hjälper dig att hantera programlivscykeln för dina Dynamics 365 Finance and Operations-appar.

Mer information finns i [Lifecycle Services, resurser](../../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

### <a name="inventory-visibility-add-in-prerequisites"></a>Förutsättningar för tillägg för lagersynlighet

Innan du installerar tillägget för lagersynlighet måste du göra följande:

- Skaffa ett LCS implementeringsprojekt med åtminstone en miljö distribuerad.
- Se till att kraven för att ställa in tillägg som finns i [översikt över tillägg](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md) har slutförts. Lagersynlighet kräver inte länkning av dubbelriktad skrivning.
- Kontakta lagersynlighetsteamet på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) för att få följande tre filer:
  - `Inventory Visibility Dataverse Solution.zip`
  - `Inventory Visibility Configuration Trigger.zip`
  - `Inventory Visibility Integration.zip` (om versionen av Supply Chain Management som du kör är tidigare än version 10.0.18)
- Alternativt kan du kontakta lagersynlighetsteamet på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) för att få Package Deployer-paketen. Dessa paket kan användas av ett officiellt Package Deployer-verktyg.
  - `InventoryServiceBase.PackageDeployer.zip`
  - `InventoryServiceApplication.PackageDeployer.zip`(det här paketet innehåller alla ändringar i paketet `InventoryServiceBase`, plus ytterligare programkomponenter för användargränssnittet)
- Följ instruktionerna i [Snabbstart: Registrera ett program med Microsofts identitetsplattform](/azure/active-directory/develop/quickstart-register-app) om du vill registrera ett program och lägga till en klienthemlighet i AAD i samband med din Azure-prenumeration.
  - [Registrera ett program](/azure/active-directory/develop/quickstart-register-app)
  - [Lägg till en klienthemlighet](/azure/active-directory/develop/quickstart-register-app#add-a-certificate)
  - I följande steg används **ID för program (klient)**, **Klienthemlighet** samt **ID för klientorganisation**.

> [!NOTE]
> De länder och regioner som för närvarande stöds är Kanada, USA och Europeiska unionen (EU).

Om du har några frågeställningar om dessa förutsättningar kontaktar du produktteamet för lagersynlighet.

### <a name="set-up-dataverse"></a><a name="setup-microsoft-dataverse"></a>Ställ in Dataverse

Om du vill konfigurera Dataverse för användning med Lagersynlighet måste du först förbereda förutsättningarna och sedan bestämma om du vill konfigurera Dataverse med antingen Package Deployer-verktyget eller genom att importera lösningarna manuellt (du behöver inte göra båda). Installera sedan tillägget för lagersynlighet. Följande delgrupper beskriver hur du slutför varje uppgift.

#### <a name="prepare-dataverse-prerequisites"></a>Förbered Dataverse-förutsättningar

Innan du börjar konfigurera Dataverse lägger du till en tjänstprincip i din klientorganisation genom att göra följande:

1. Installera Azure AD PowerShell modul v2 enligt beskrivningen i [Installera Azure Active Directory PowerShell för Graph](/powershell/azure/active-directory/install-adv2).

1. Kör följande PowerShell-kommando:

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)
    
    New-AzureADServicePrincipal -AppId "3022308a-b9bd-4a18-b8ac-2ddedb2075e1" -DisplayName "d365-scm-inventoryservice"
    ```

#### <a name="set-up-dataverse-using-the-package-deployer-tool"></a>Konfigurera Dataverse med hjälp av Package Deployer-verktyget

När du har ställt in förutsättningarna använder du följande procedur om du föredrar att konfigurera Dataverse med hjälp av Package Deployer-verktyget. Se nästa avsnitt för information om hur du importerar lösningarna manuellt istället (gör inte båda).

1. Installera utvecklarverktyg enligt beskrivningen i [Hämta verktyg från NuGet](/dynamics365/customerengagement/on-premises/developer/download-tools-nuget).

1. Baserat på dina affärsförutsättningar väljer du `InventoryServiceBase`- eller `InventoryServiceApplication`-paketet.

1. Importera lösningarna:
    1. För `InventoryServiceBase`-paketet:
        - Packa upp `InventoryServiceBase.PackageDeployer.zip`
        - Sök efter mappen `InventoryServiceBase`, filen `[Content_Types].xml`, filen `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll`, filen `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config` och filen `Microsoft.Dynamics.InventoryServiceBase.PackageExtension.dll.config`. 
        - Kopiera var och en av dessa mappar och filer till katalogen `.\Tools\PackageDeployment`, som skapades när du installerade utvecklarverktygen.
    1. För `InventoryServiceApplication`-paketet:
        - Packa upp `InventoryServiceApplication.PackageDeployer.zip`
        - Sök efter mappen `InventoryServiceApplication`, filen `[Content_Types].xml`, filen `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll`, filen `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config` och filen `Microsoft.Dynamics.InventoryServiceApplication.PackageExtension.dll.config`.
        - Kopiera var och en av dessa mappar och filer till katalogen `.\Tools\PackageDeployment`, som skapades när du installerade utvecklarverktygen.
    1. Kör `.\Tools\PackageDeployment\PackageDeployer.exe`. Importera lösningarna genom att följa anvisningarna på skärmen.

1. Tilldela programanvändaren säkerhetsroller.
    1. Öppna URL-adressen för din Dataverse miljö.
    1. Gå till **Avancerade inställningar \> System \> Säkerhet \> Användare** och hitta användaren med namnet **# InventoryVisibility**.
    1. Välj **Tilldela roll** och välj sedan **Systemadministratör**. Om det finns en roll med namnet **Common Data Service-användare** väljer du den också.

#### <a name="set-up-dataverse-manually-by-importing-solutions"></a>Konfigurera Dataverse manuellt genom att importera lösningar

När du har ställt in förutsättningarna använder du följande procedur om du föredrar att konfigurera Dataverse manuellt genom att importera lösningar. Se föregående avsnitt för information om hur du använder Package Deployer-verktyget i stället (gör inte båda).

1. Skapa en programanvändare för lagersynlighet i Dataverse:

    1. Öppna URL-adressen för din Dataverse miljö.
    1. Gå till **Avancerade inställningar \> System \> Säkerhet \> Användare** och skapa en programanvändare. Använd visningsmenyn för att ändra sidvisningen till **appanvändare**.
    1. Välj **Ny**. Ange app-ID till *3022308a-b9bd-4a18-b8ac-2ddedb2075e1*. (Objekt-ID:t läses in automatiskt när du sparar ändringarna.) Du kan anpassa namnet. Du kan till exempel ändra den till *Lagersynlighet*. Välj **Spara** när du är klar.
    1. Välj **Tilldela roll** och välj sedan **Systemadministratör**. Om det finns en roll med namnet **Common Data Service Användare** väljer du den också.

    Mer information finns i [Skapa en appanvändare](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).

1. Om standardspråket för ditt Dataverse inte är **Engelska**:

    1. Gå till **Avancerad inställning \> Administration \> Språk**,
    1. Välj **Engelska (LanguageCode=1033)** och sedan **Verkställ**.

1. Importera `Inventory Visibility Dataverse Solution.zip` filen, inklusive Dataverse konfigurationsrelaterade enheter och Power Apps:

    1. Gå till sidan **Lösningar**.
    1. Välj **Importera**.

1. Importera flödet för flödesutlösaren för konfigurationsuppgradering:

    1. Gå till sidan Microsoft Flow.
    1. Se till att den anslutning som kallas *Dataverse (äldre)* finns. (Om den inte finns skapar du den.)
    1. Importera `Inventory Visibility Configuration Trigger.zip` filen. När den har importerats visas utlösaren under **Mina flöden**.
    1. Initialisera följande fyra variabler baserat på miljöinformation:

        - ID för Azure-innehavare
        - Klient-ID för Azure-app
        - Klienthemlighet för Azure-app
        - Slutpunkt för lagersynlighet

            Mer information om den här variabeln finns i avsnittet [Ställa in integration av lagersynlighet](#setup-inventory-visibility-integration) senare i det här avsnittet.

        ![Konfigurationsutlösare](media/configuration-trigger.png "Konfigurationsutlösare")

    1. Välj **Aktivera**.

### <a name="install-the-add-in"></a><a name="install-add-in"></a>Installera tillägget

För att installera tillägget för lagersynlighet måste du göra följande:

1. Logga in på [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index)-portalen.
1. Välj det projekt där miljön har distribuerats på startsidan.
1. Välj den miljö där du vill installera tillägget på projektsidan.
1. Rulla ned på miljösidan tills du ser avsnittet **Miljö-tillägg** i avsnittet **Power Platform integration** där du hittar Dataverse miljönamnet.
1. I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.

    ![Sidan miljö i LCS](media/inventory-visibility-environment.png "Sidan miljö i LCS")

1. Välj länken **installera ett nytt tillägg**. En lista med tillgängliga tillägg öppnas.
1. Välj **lagersynlighet** i listan.
1. Ange värden för följande fält i miljön:

    - **AAD-program-ID (klient)**
    - **AAD klientorganisationens ID**

    ![Lägg till på inställningssidan](media/inventory-visibility-setup.png "Lägg till på inställningssidan")

1. Godkänn villkoren genom att markera kryssrutan **villkor**.
1. Välj **Installera**. Tilläggets status visas som **installerar**. När det är klart uppdaterar du sidan så att status ändras till **installerad**.

### <a name="uninstall-the-add-in"></a><a name="uninstall-add-in"></a>Avinstallera tillägget

För att avinstallera tillägget, välj **avinstallera**. När du uppdaterar LCS tas tillägget för lagersynlighet bort. Avinstallationsprocessen tar bort registreringen av tillägget och startar även ett jobb för att rensa alla affärsdata som lagras i tjänsten.

## <a name="consume-on-hand-inventory-data-from-supply-chain-management"></a>Förbruka lagerbehållningsdata från Supply Chain Management

### <a name="deploy-the-inventory-visibility-integration-package"></a><a name="deploy-inventory-visibility-package"></a>Distribuera integreringspaketet för lagersynlighet

Om du kör Supply Chain Management version 10.0.17 eller tidigare, kontakta supportteamet för inventeringssyn på [inventvisibilitysupp@microsoft.com](mailto:inventvisibilitysupp@microsoft.com) för att få paketfilen. Distribuera sedan paketet i LCS.

> [!NOTE]
> Om ett versionsfel inträffar under distributionen måste du manuellt importera X++-projektet till din utvecklingsmiljö. Skapa sedan det paket som kan distribueras i din utvecklingsmiljö och distribuera det i din produktionsmiljö.
> 
> Koden ingår i med Supply Chain Management version 10.0.18. Om du kör den versionen eller senare behöver du inte distribuera den.

Kontrollera att följande funktioner är aktiverat i din Supply Chain Management-miljö. (Som standard är de aktiverade.)

| Funktionsbeskrivning | Kodversion | Växla klass |
|---|---|---|
| Aktivera eller inaktivera med hjälp av lagerdimensioner i registret InventSum | 10.0.11 | InventUseDimOfInventSumToggle |
| Aktivera eller inaktivera med hjälp av lagerdimensioner i registret InventSumDelta | 10.0.12 | InventUseDimOfInventSumDeltaToggle |

### <a name="set-up-inventory-visibility-integration"></a><a name="setup-inventory-visibility-integration"></a>Konfigurera integrering av lagersynlighet

1. I Supply Chain Management, öppna arbetsytan **[Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)** och aktivera funktionen **Integrering av lagersynlighet**.
1. Gå till **Lagerhantering \> Ställ in \> Parametrar för integrering av lagersynlighet** och ange webbadressen till den miljö där du kör lagersynlighet.

    Sök efter din LCS-miljös Azure-region och ange sedan URL-adressen. URL-adressen har följande formulär:

    `https://inventoryservice.<RegionShortName>-il301.gateway.prod.island.powerapps.com`

    Om du till exempel är i Europa har din miljö någon av följande URL-adresser:

    - `https://inventoryservice.neu-il301.gateway.prod.island.powerapps.com`
    - `https://inventoryservice.weu-il301.gateway.prod.island.powerapps.com`

    Följande regioner är för närvarande tillgängliga.

    | Azure-region | Kortnamn för region |
    |---|---|
    | Östra Australien | eau |
    | Sydöstra Australien | seau |
    | Centrala Kanada | cca |
    | Östra Kanada | eca |
    | Nordeuropa | neu |
    | Västeuropa | weu |
    | Östra USA | eus |
    | Västra USA | wus |

1. Gå till **Lagerhantering \> Periodisk \> Integrering av lagerhantering** och aktivera jobbet. Alla lagerändringshändelser från Supply Chain Management bokförs nu i lagersynlighet.

## <a name="the-inventory-visibility-add-in-public-api"></a><a name="inventory-visibility-public-api"></a>Tillägg för lagersynlighet i offentlig API

Det offentliga REST-API för ett av tilläggen för lagersynlighet visar flera specifika slutpunkter för integrationen. Den stöder tre huvudinteraktionstyper:

- Bokföring av ändringar för lagerbehållning i tillägget från ett externt system
- Fråga om aktuell behållning från ett externt system
- Automatisk synkronisering med lagerbehållning av Supply Chain Management

Automatisk synkronisering av en del av den offentliga API:t. I stället hanteras den i bakgrunden för miljöer där tillägget lagersynlighet är aktiverat.

### <a name="authentication"></a><a name="inventory-visibility-authentication"></a>Äkthetsbevisning

Säkerhetstoken för plattform används för att anropa tillägget lagersynlighet. Därför måste du generera en *Azure Active Directory (Azure AD) token* med hjälp av ditt Azure AD program. Du måste sedan använda Azure AD token för att få *åtkomsttoken* från säkerhetstjänsten.

Hämta en säkerhetstjänsttoken genom att göra följande:

1. Logga in på Azure-portalen och använd den för att hitta `clientId` och `clientSecret` för din Supply Chain Management-app.
1. Hämta ett Azure Active Directory-token (`aadToken`) genom att skicka en HTTP-begäran med följande egenskaper:
    - **URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`
    - **Metod** - `GET`
    - **Brödtext (formulärdata)**:

        | nyckel | värde |
        | --- | --- |
        | klient-ID | ${aadAppId} |
        | client_secret | ${aadAppSecret} |
        | grant_type | client_credentials |
        | resurs | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
1. Du bör få `aadToken` i svar, som liknar följande exempel.

    ```json
    {
        "token_type": "Bearer",
        "expires_in": "3599",
        "ext_expires_in": "3599",
        "expires_on": "1610466645",
        "not_before": "1610462745",
        "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
        "access_token": "eyJ0eX...8WQ"
    }
    ```

1. Formulera en JSON-begäran som liknar följande:

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    Där:
    - Värdet `client_assertion` måste vara det `aadToken` du tog emot i föregående steg.
    - Värdet `context` måste vara det miljö-ID där du vill distribuera tillägget.
    - Ställ in alla andra värden enligt exemplet.

1. Skicka en HTTP-begäran med följande egenskaper:
    - **URL** - `https://securityservice.operations365.dynamics.com/token`
    - **Metod** - `POST`
    - **HTTP-rubrik** - Inkludera API-versionen (nyckeln är `Api-Version` och värdet är `1.0`)
    - **Brödtext** - Inkludera den JSON-begäran som du skapade i det föregående steget.

1. Du får ett `access_token` i svar. Detta är vad du behöver som ägartoken för att anropa API för lagersynlighet. Här är ett exempel:

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="sample-request"></a><a name="inventory-visibility-sample-request"></a>Exempelbegäran

För din referens följer här ett exempel på en http-begäran- du kan använda valfritt verktyg eller kodspråk för att skicka denna, begäran, exempelvis ``Postman``.

```json
# Url
# replace {RegionShortName} and {EnvironmentId} with your value
https://inventoryservice.{RegionShortName}-il301.gateway.prod.island.powerapps.com/api/environment/{EnvironmentId}/onhand

# Method
Post

# Header
# replace {access_token} with the one get from security service
Api-version: "1.0"
Content-Type: "application/json"
Authorization: "Bearer {access_token}"

# Body
{
    "id": "id-bike-0001",
    "organizationId": "usmf",
    "productId": "Bike",
    "quantities": {
        "pos": {
            "inbound": 5
        }  
    },
    "dimensions": {
        "SizeId": "Small",
        "ColorId": "Red",
        "SiteId": "1",
        "LocationId": "11"
    }
}
```

### <a name="configure-the-inventory-visibility-api"></a><a name="inventory-visibility-configuration"></a>Konfigurera API för lagersynlighet

Innan du använder tjänsten måste du slutföra de konfigurationer som beskrivs i följande underavsnitt. Konfigurationen kan variera beroende på vad som gäller för din miljö. Den omfattar huvudsakligen fyra delar:

- [Partitionering](#partitioning)
- [Dimensionskonfigurationer](#dimension-configurations)
- [Indexering](#indexing)
- [Anpassat mått](#custom-measurement)

#### <a name="partitioning"></a>Partitionering

Partitionering kan i stor grad påverka prestandan för API för lagersynlighet. Det är en god idé att definiera ett schema som gör det möjligt att göra små grupperade data samtidigt som det går att ändå göra meningsfulla datafrågeställningar.

`organizationId` (`dataAreaId` i Supply Chain Management) är alltid en del av partitionering och som standard är lagersynlighet inställt på partition per dimension som *Webbplats + plats*. Detta innebär att tjänsten alltid måste tillfrågas med dessa dimensioner definierade i filtren.

> [!NOTE]
> *Webbplats* och *Plats* är två allmänna standarddimensioner för lagersynlighet. I Supply Chain Management kallas dessa dimensioner *Webbplats* (`InventSiteId`) och *Lagerställe* (`InventLocationId`)

### <a name="dimension-configurations"></a>Dimensionskonfigurationer

Lagersynlighet innehåller en lista över allmänna standarddimensioner som gör att integreringen med flera källsystem kan användas.

I följande register visas de lagerdimensioner som kommer att vara standarddimensionsnamn i lagersynlighet.

| Dimensionstyp | Dimensionsnamn |
|---|---|
| Produkt | `ColorId` |
| Produkt | `SizeId` |
| Produkt | `StyleId` |
| Produkt | `ConfigId` |
| Spårning | `BatchId` |
| Spårning | `SerialId` |
| Plats | `LocationId` |
| Plats | `SiteId` |
| Lagerstatus | `StatusId` |
| Lagerställespecifik | `WMSLocationId` |
| Lagerställespecifik | `WMSPalletId` |
| Lagerställespecifik | `LicensePlateId` |

> [!NOTE]
> Dimensionstypen som visas i föregående tabell är endast referens. Du behöver inte ange dimensionstypen i lagersynlighet.

Om det finns en anpassad dimension som måste flödas till ett standardvärde när den förbrukas efter lagersynlighet, kan du konfigurera namnet **anpassade dimensionen** i lagersynlighet.

Externa system får åtkomst till lagersynlighet genom RESTful-API som aktiverar behållningsinformation för angivna dimensionsuppsättningar. Vid integreringen kan du med hjälp av lagersynlighet konfigurera *datakällan för den externa kanalen* och källdimensionen till *måldimensionerna* i lagersynlighet.

Måldimensionerna måste vara en av följande:

- Standarddimensioner vid lagersynlighet
- Anpassade dimensioner

Syftet med dimensionskonfigurationen är att standardisera integrationen av flera system för frågeställningen på dimensioner och bokföringshändelsen med dimensioner.

#### <a name="indexing"></a>Indexering

För det mesta blir lagerbehållningsfrågan inte bara på den högsta total nivån, men du kanske vill visa resultat som baseras på lagerdimensionerna.

Lagersynlighet ger flexibilitet genom att du kan ställa in indexen, som baseras på dimensionen eller kombinationen av dimensionerna.

> [!NOTE]
> För närvarande kan du bara konfigurera index till maximalt fem. Du måste noga överväga vilken dimension eller dimensionskombination du kommer att använda innan du implementerar den för att säkerställa att den uppfyller dina affärsbehov. Om du till exempel vill söka efter produkter enligt följande:

- Fråga den aggregerade produktens behållning i dimensionerna *färg* och *storlek*.
- I vissa fall vill du bara fråga den totala produkten.

Två index är definierade som följande:

- `["ColorId", "SizeId"]`
- `[]`

Den tomma hakparentesen aggregerar baserat på produkt-ID i partitionen.

Indexeringen definierar hur du kan gruppera resultaten utifrån `groupBy` frågeinställning. I det här fallet om du inte definierar några `groupBy` värden får du total summor efter `productid`. Om du i annat fall definierar `groupBy` som `groupBy=ColorId&groupBy=SizeId` kan flera rader returneras, baserat på de olika kombinationerna av färger och storlekar i systemet.

Du kan ange frågevillkor i den begärandetext.

Här är en exempel fråga på produkten med kombinationen färg och storlek.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct1", "MyProduct2"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

För fältet `filters` stöder för närvarande bara `ProductId` flera värden. Om matrisen `ProductId` är tom kommer alla produkter att efterfrågas.

#### <a name="custom-measurement"></a>Anpassat mått

Standardmåttkvantiteterna är kopplade till Supply Chain Management. Det kan dock vara en bra kvantitet som består av en kombination av standardmåtten. För att kunna göra detta kan du konfigurera anpassade kvantiteter som läggs till i utmatningen av behållningsfrågeställningarna.

Med hjälp av funktionen kan du definiera en uppsättning mått som ska läggas till, och/eller en uppsättning mått som subtraheras, för att från det anpassade måttet.

Med följande frågevillkor konfigurerar du till exempel den anpassade måttkvantiteten som ska `MyCustomAvailableforReservation` konsumeras av förbrukningssystemet.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| Förbrukningssystem | Beräknade mått | Datakälla | Modifierare | Beräkningstyp för modifierare |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | Tillägg |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | Tillägg |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | Subtraktion |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | Tillägg |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | Subtraktion |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | Tillägg |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | Tillägg |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | Subtraktion |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | Subtraktion |

Med detta kommer frågeställningen för den anpassade måttkvantiteten att returnera följande resultat.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

`MyCustomAvailableforReservation`-resultatet baseras på beräkningsinställningen i de anpassade måtten som:  
 *100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*

### <a name="posting-on-hand-changes"></a>Bokföra lagerbehållningsändringar

Den exakta URL som händelsen ska skickas till beror på din geografiska region. Formuläret kommer att ha följande format:

`https://{serviceURL}/api/environment/{environmentId}/onhand`

När den autentiseras kan den här URL:en användas tillsammans med HTTP `POST`-metoden för att skicka ändringshändelser för behållning till tjänsten.

En särskild rubrik används för kommunikation med Dynamics 365-tjänster via HTTP-begäranden, vilket anger miljö-ID för den instans av Supply Chain Management som data är kopplade till. Exempel:

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a>Skicka behållningsändringar fråga exempel 1

I det här exemplet visas ett scenario där dimensionskonfigurationen ska ställas in i Power Apps.

Använd följande fråga för att konfigurera dimensionsmappningen i Power Apps:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Nu kan du ange `dimensionDataSource` och använda anpassade dimensioner i dina frågeställningar. Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a>Skicka behållningsändringar fråga exempel 2

I det här exemplet visas ett scenario där inga mappningar har ställts in för dimensionskonfigurationen i Power Apps, så bokföringen ska också använda basdimensionerna. Alla dimensioner måste vara basdimensioner när fältet `dimensionDataSource` är null, tomt eller tomt utrymme.

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a>JSON dokumentfältegenskaper

De fält från exempel för JSON-frågeställningar som tidigare har angetts har de egenskaper som anges i följande tabell.

| Fält-ID | beskrivning |
|---|---|
| `id` | Ett unikt ID för den specifika ändringshändelsen. Detta ID används för att säkerställa att om en kommunikation med tjänsten misslyckas under bokföringen, innebär det att om händelsen skickas till en händelse som räknas två gånger i systemet. |
| `organizationId` | Identifierare för den organisation som är kopplad till händelsen. Detta mappar till Supply Chain Management organisations eller dataområdes-ID. |
| `productId` | Den unika identifieraren av produkten i fråga. |
| `quantity` | Kvantiteten som behållningen måste ändras med. Om till exempel 10 nya bagels har lagts till i en hylla är detta värde 10. Om 3 bagels sedan togs bort från hyllan eller sålde skulle detta värde vara -3. |
| `dimensionDataSource` | Datakällan för de dimensioner som används vid ändring av bokföringshändelse och fråga. Om du anger datakällan kan du använda de anpassade dimensionerna från den angivna datakällan. Med dimensions konfigurationen kan lagersynlighet mappa de anpassade dimensionerna till de allmänna standarddimensionerna. Om `dimensionDataSource` inte anges kan du bara använda de allmänna standarddimensionerna i frågeställningarna.   |
| `dimensions` | En dynamisk uppsättning nyckel/värde-par. Dessa mappar till några av dimensionerna i Supply Chain Management, men du kan också lägga till anpassade dimensioner (t.ex. *källa*) som kan ange om händelsen kommer från Supply Chain Management eller ett externt system. |

### <a name="querying-current-on-hand"></a>Fråga aktuell behållning

Slutpunkten för att hämta den aktuella behållningen har en liknande URL:

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

Den kommer att frågas med HTTP `POST`-metoden.

#### <a name="current-on-hand-query-example-1"></a>Aktuellt behållningsexempel 1

I det här exemplet visas ett scenario där du redan har slutfört dimensionskonfigurationen i Power Apps.

Använd följande fråga för att konfigurera dimensionsmappningen i Power Apps:

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

Nu kan du ange `dimensionDataSource` och använda anpassade dimensioner i dina frågeställningar. Systemet konverterar automatiskt anpassade dimensioner till basdimensioner. Du kan ange `DimensionDataSource` i `filters` och ange anpassade dimensioner i både `filters` och `groupByValues`. Systemet konverterar automatiskt anpassade dimensioner till basdimensioner.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a>Aktuellt behållningsexempel 2

I det här exemplet visas ett scenario där inga mappningar har ställts in för dimensionskonfigurationen i Power Apps, så bokföringen ska också använda basdimensionerna. Alla dimensioner måste vara basdimensioner när fältet `dimensionDataSource` under `filters` är null, tomt eller tomt utrymme.

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a>Exempel på returresultat

Frågeställningarna som visas i föregående exempel kan returnera resultatet.

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

Observera att kvantitetsfälten är strukturerade som en ordlista med mått och tillhörande värden.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
