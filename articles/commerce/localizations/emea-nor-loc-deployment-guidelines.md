---
title: Riktlinjer för distribution av kassaapparater för Norge (äldre)
description: Det här avsnittet fungerar som en distributionsguide som visar hur du aktiverar lokalisering av Microsoft Dynamics 365 Commerce för Norge.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2018-2-28
ms.openlocfilehash: 019bac01abdc0b2e16718c08953b44fbccef83a3
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944798"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway-legacy"></a>Riktlinjer för distribution av kassaapparater för Norge (äldre)

[!include [banner](../includes/banner.md)]

Det här avsnittet fungerar som en distributionsguide som visar hur du aktiverar lokalisering av Microsoft Dynamics 365 Commerce för Norge. Lokaliseringen består av flera utvidgningar av Commerce-komponenter. Med tilläggen kan du till exempel skriva ut anpassade fält på kvitton, registrera ytterligare verifieringshändelser, försäljningstransaktioner och betalningstransaktioner i kassa, digitalt signera försäljningstransaktioner och skriva ut X- och Z-rapporter i lokala format. Mer information om lokalisering för Norge finns i [Kassaregisterfunktionen för Norge](./emea-nor-cash-registers.md).

Detta exempel är en del av Retail Software Development Kit (SDK). Information om SDK finns i [Retail programutvecklingskit (SDK) arkitektur](../dev-itpro/retail-sdk/retail-sdk-overview.md).

Det här exemplet består av tillägg för Commerce Runtime (CRT), Retail Server och POS. Om du vill köra det här exemplet måste du ändra och bygga CRT, Retail Server och POS-projekt. Vi rekommenderar att du använder en icke-modifierad Retail SDK för att göra de ändringar som beskrivs i det här avsnittet. Vi rekommenderar också att du använder ett källkontrollsystem, till exempel Microsoft Visual Studio Online (VSO), där inga filer har ändrats ännu.

> [!NOTE]
> I Commerce 10.0.8 och ovan kallas Retail Server Commerce Scale Unit. Eftersom det här avsnittet gäller för flera tidigare versioner av programmet används *Retail Server* i hela avsnittet.
>
> Vissa steg i procedurerna i det här avsnittet varierar beroende på vilken version av Commerce du använder. Mer information finns i [Nyheter eller ändringar i Dynamics 365 Retail](../get-started/whats-new.md).

### <a name="using-certificate-profiles-in-commerce-channels"></a>Använda intygsprofiler i Commerce-kanaler

I Commerce versioner 10.0.15 och senare kan du använda funktionen [Användardefinierade certifikatprofiler för butiker](./certificate-profiles-for-retail-stores.md) som stöder redundans till offline när Key Vault eller Commerce-administration inte är tillgängliga. Den här funktionen utökar funktionen [Hantera hemligheter butikskanaler](../dev-itpro/manage-secrets.md).

För att tillämpa denna funktion i tillägget CRT, följ dessa steg.

1. Skapa ett nytt CRT anknytningsprojekt (projekttypen C# - klassbibliotek). Använd exempelmallarna från Sdk (Retail Software Development Kit) (RetailSDK\SampleExtensions\CommerceRuntime).

2. Lägg till anpassad hanterare för CertificateSignatureServiceRequest i projektet SequentialSignatureRegister.

3. Om du vill läsa ett samtal, `GetUserDefinedSecretCertificateServiceRequest` använder du en konstruktor med profileId-parameter. Då startas funktionen så att funktionen fungerar med inställningar från intygsprofiler. Baserat på inställningarna hämtas certifikatet antingen från Azure Key Vault eller lokal maskinlagring.

    ```csharp
    GetUserDefinedSecretCertificateServiceRequest getUserDefinedSecretCertificateServiceRequest = new GetUserDefinedSecretCertificateServiceRequest(profileId: "ProfileId", secretName: null, thumbprint: null, expirationInterval: null);
    GetUserDefinedSecretCertificateServiceResponse getUserDefinedSecretCertificateServiceResponse = request.RequestContext.Execute<GetUserDefinedSecretCertificateServiceResponse>(getUserDefinedSecretCertificateServiceRequest);

    X509Certificate2 Certificate = getUserDefinedSecretCertificateServiceResponse.Certificate;
    ```

4. När certifikatet hämtas fortsätter du med datasigneringen.

5. Skapa CRT tilläggsprojektet.

6. Kopiera utdataklassens bibliotek och klistra in det i ...\RetailServer\webroot\bin\Ext för manuell testning.

7. Uppdatera sammansättningen av filnamnstillägget med den anpassade biblioteksinformationen i filen CommerceRuntime.Ext.config.

## <a name="development-environment"></a>Utvecklingsmiljö

Slutför dessa procedurer för att ställa in en utvecklingsmiljö så att du kan testa och utöka exemplet.

### <a name="the-crt-extension-components"></a>Tilläggskomponenter för CRT

CRT tilläggskomponenter inkluderas i CRT-exemplen. För att slutföra följande procedurer, öppna CRT-lösningen, **CommerceRuntimeSamples.sln**, under **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="receiptsnorway-component"></a>ReceiptsNorway-komponent

1. Leta upp projektet **Runtime.Extensions.ReceiptsNorway** och skapa det.
2. I mappen **Extensions.ReceiptsNorway\\bin\\Debug** mappen, hitta **Contoso.Commerce.Runtime.ReceiptsNorway.dll** sammansättningsfilen.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under Microsoft Internet Information Services (IIS) Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="salespaymenttransext-component"></a>SalesPaymentTransExt-komponent

1. Leta upp projektet **Runtime.Extensions.SalesPaymentTransExt** och skapa det.
2. I mappen **Extensions.SalesPaymentTransExt\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.SalesPaymentTransExt.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="xzreportsnorway-component"></a>XZReportsNorway-komponent

1. Leta upp projektet **Runtime.Extensions.XZReportsNorway** och skapa det.
2. I mappen **Extensions.XZReportsNorway\\bin\\Debug** mappen, hitta **Contoso.Commerce.Runtime.XZReportsNorway.dll** sammansättningsfilen.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

# <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

#### <a name="registerauditevent-sample-component"></a>RegisterAuditEvent komponent

1. Leta upp projektet **Runtime.Extensions.RegisterAuditEventSample** och skapa det.
2. I mappen **Extensions.RegisterAuditEventSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="salestransactionsignature-sample-component"></a>SalesTransactionSignature exempelkomponent

1. Hitta projektet **Runtime.Extensions.SalesTransactionSignatureSample**.
2. Ändra filen **App.config** genom att ange tumavtryck, butiksplats och butiksnamn för certifikatet som ska användas för att signera försäljningstransaktioner.
3. Skapa projektet.
4. I mappen **Extensions.SalesTransactionSignatureSample\\bin\\Debug** hitta följande filer:

    - Sammansättningsfilen **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - Konfigurationsfilen **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Kopiera filer till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

6. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

7. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

# <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

#### <a name="registerauditevent-sample-component"></a>RegisterAuditEvent komponent

1. Leta upp projektet **Runtime.Extensions.RegisterAuditEventSample** och skapa det.
2. I mappen **Extensions.RegisterAuditEventSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="salestransactionsignature-sample-component"></a>SalesTransactionSignature exempelkomponent

1. Hitta projektet **Runtime.Extensions.SalesTransactionSignatureSample**.
2. Ändra filen **App.config** genom att ange tumavtryck, butiksplats och butiksnamn för certifikatet som ska användas för att signera försäljningstransaktioner.
3. Skapa projektet.
4. I mappen **Extensions.SalesTransactionSignatureSample\\bin\\Debug** hitta följande filer:

    - Sammansättningsfilen **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - Konfigurationsfilen **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Kopiera filer till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

6. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

7. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="salestransactionsignaturesamplemessages-component"></a>SalesTransactionSignatureSample.Messages komponent

1. Hitta projektet **Runtime.Extensions.SalesTransactionSignatureSample.Messages**.
2. I mappen **Extensions.SalesTransactionSignatureSample.Messages\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

# <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

#### <a name="registerauditevent-sample-component"></a>RegisterAuditEvent komponent

1. Leta upp projektet **Runtime.Extensions.RegisterAuditEventSample** och skapa det.
2. I mappen **Extensions.RegisterAuditEventSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="salestransactionsignature-sample-component"></a>SalesTransactionSignature exempelkomponent

1. Hitta projektet **Runtime.Extensions.SalesTransactionSignatureSample**.
2. Ändra filen **App.config** genom att ange tumavtryck, butiksplats och butiksnamn för certifikatet som ska användas för att signera försäljningstransaktioner.
3. Skapa projektet.
4. I mappen **Extensions.SalesTransactionSignatureSample\\bin\\Debug** hitta följande filer:

    - Sammansättningsfilen **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
    - Konfigurationsfilen **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

5. Kopiera filer till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

6. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

7. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="sequentialsignatureregistercontracts-component"></a>SequentialSignatureRegister.Contracts komponent

1. Leta upp projektet **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. I mappen **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

# <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

#### <a name="registerauditevent-sample-component"></a>RegisterAuditEvent komponent

1. Leta upp projektet **Runtime.Extensions.RegisterAuditEventSample** och skapa det.
2. I mappen **Extensions.RegisterAuditEventSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.RegisterAuditEventSample.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="sequentialsignatureregister-component"></a>SequentialSignatureRegister komponent

1. Hitta projektet **Runtime.Extensions.SequentialSignatureRegister**.
2. Ändra filen **App.config** genom att ange tumavtryck, butiksplats och butiksnamn för certifikatet som ska användas för att signera försäljningstransaktioner.
3. Skapa projektet.
4. I mappen **Extensions.SequentialSignatureRegister\\bin\\Debug** hitta följande filer:

    - Sammansättningsfilen **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - Konfigurationsfilen **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Kopiera filer till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

6. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

7. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="salestransactionsignaturenorway-component"></a>SalesTransactionSignatureNorway-komponent

1. Hitta projektet **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. I mappen **Extensions.SalesTransactionSignatureNorway\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="sequentialsignatureregistercontracts-component"></a>SequentialSignatureRegister.Contracts komponent

1. Leta upp projektet **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. I mappen **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

#### <a name="salespaymenttransextnorway-component"></a>SalesPaymentTransExtNorway komponent

1. Leta upp projektet **Runtime.Extensions.SalesPaymentTransExtNorway** och skapa det.
2. I mappen **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**  hitta sammansättningsfilen **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

# <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

#### <a name="registerauditeventnorway-component"></a>RegisterAuditEventNorway komponent

1. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

2. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="sequentialsignatureregister-component"></a>SequentialSignatureRegister komponent

1. Hitta projektet **Runtime.Extensions.SequentialSignatureRegister**.
2. Ändra filen **App.config** genom att ange tumavtryck, butiksplats och butiksnamn för certifikatet som ska användas för att signera försäljningstransaktioner.
3. Skapa projektet.
4. I mappen **Extensions.SequentialSignatureRegister\\bin\\Debug** hitta följande filer:

    - Sammansättningsfilen **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - Konfigurationsfilen **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Kopiera filer till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

6. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

7. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="salestransactionsignaturenorway-component"></a>SalesTransactionSignatureNorway-komponent

1. Hitta projektet **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. I mappen **Extensions.SalesTransactionSignatureNorway\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="sequentialsignatureregistercontracts-component"></a>SequentialSignatureRegister.Contracts komponent

1. Leta upp projektet **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. I mappen **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

#### <a name="salespaymenttransextnorway-component"></a>SalesPaymentTransExtNorway komponent

1. Leta upp projektet **Runtime.Extensions.SalesPaymentTransExtNorway** och skapa det.
2. I mappen **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**  hitta sammansättningsfilen **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

# <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

#### <a name="registerauditeventnorway-component"></a>RegisterAuditEventNorway komponent

1. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

2. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="sequentialsignatureregister-component"></a>SequentialSignatureRegister komponent

1. Hitta projektet **Runtime.Extensions.SequentialSignatureRegister**.
2. Ändra filen **App.config** genom att ange tumavtryck, butiksplats och butiksnamn för certifikatet som ska användas för att signera försäljningstransaktioner.
3. Skapa projektet.
4. I mappen **Extensions.SequentialSignatureRegister\\bin\\Debug** hitta följande filer:

    - Sammansättningsfilen **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll**
    - Konfigurationsfilen **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config**

5. Kopiera filer till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

6. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

7. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="salestransactionsignaturenorway-component"></a>SalesTransactionSignatureNorway-komponent

1. Hitta projektet **Runtime.Extensions.SalesTransactionSignatureNorway**.
2. I mappen **Extensions.SalesTransactionSignatureNorway\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

#### <a name="sequentialsignatureregistercontracts-component"></a>SequentialSignatureRegister.Contracts komponent

1. Leta upp projektet **Runtime.Extensions.SequentialSignatureRegister.Contracts**.
2. I mappen **Extensions.SequentialSignatureRegister.Contracts\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

#### <a name="salespaymenttransextnorway-component"></a>SalesPaymentTransExtNorway komponent

1. Leta upp projektet **Runtime.Extensions.SalesPaymentTransExtNorway** och skapa det.
2. I mappen **Extensions.SalesPaymentTransExtNorway\\bin\\Debug**  hitta sammansättningsfilen **Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll**.
3. Kopiera sammansättningsfilen till CRT-tilläggsmappen:

    - **Retail Server:** kopiera sammansättningen till mappen **\\bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** kopiera sammansättningen till mappen **\\ext** under den lokala platsen för CRT Client Broker.

4. Hitta konfigurationsfilen för tillägget för CRT:

    - **Retail Server:** Filen kallas **commerceruntime.ext.config** och finns i mappen **bin\\ext** under IIS Retail Server webbplatsen.
    - **Lokal CRT på Modern POS:** filen heter **CommerceRuntime.MPOSOffline.Ext.config** och det är under den lokala platsen för CRT-klienten Broker.

5. Registrera CRT-ändringen i konfigurationsfilen för tillägget.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
    ```

    > [!WARNING]
    > Redigera **inte** filerna commerceruntime.config och CommerceRuntime.MPOSOffline.config files. Dessa filer är inte avsedda för några anpassningar.

---

### <a name="the-retail-server-extension-components"></a>Komponenter för butiksservertillägg

#### <a name="salestransactionsignature-retail-server-sample-component"></a>Exempelkomponenten SalesTransactionSignature Retail Server

1. I mappen **RetailSDK\\SampleExtensions\\RetailServer\\RetailServer.Extensions.SalesTransactionSignatureSample** hitta **RetailServer.Extensions.SalesTransactionSignatureSample** och skapa det.
2. I mappen **RetailServer\\Extensions.SalesTransactionSignatureSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.RetailServer.SalesTransactionSignatureSample.dll**.
3. Kopiera sammansättningsfilen till Retail Server-tilläggsmappen.

    # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

    Mappen är en **\\bin** mapp under IIS Retail Server webbplatsen.

    # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

    Mappen är en **\\bin** mapp under IIS Retail Server webbplatsen.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    Mappen är en bin mapp under **\\bin\\ext** under IIS Retail Server webbplatsen.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

    Mappen är en bin mapp under **\\bin\\ext** under IIS Retail Server webbplatsen.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

    Mappen är en bin mapp under **\\bin\\ext** under IIS Retail Server webbplatsen.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

    Mappen är en bin mapp under **\\bin\\ext** under IIS Retail Server webbplatsen.

    ---

4. Hitta konfigurationsfilen för Retail Server. Filen kallas **web.config** och det finns i rotmappen under IIS Retail Server webbplatsen.
5. Registrera tilläggen för Retail Server i avsnittet **extensionComposition** i konfigurationsfilen.

    ``` xml
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />
    ```

6. Registrera beroendena för tilläggen för Retail Server.

    # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4/)

    1. I mappen **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug** hitta följande filer:

        - Sammansättningsfilen **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll**
        - Konfigurationsfilen **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config**

    2. Kopiera filerna till **\\bin** mapp under IIS Retail Server webbplatsen.
    3. Registrera CRT ändringen i konfigurationsfilen för CRT. Denna fil kallas **commerceruntime.ext.config** och finns i mappen **bin** under IIS Retail Server-webbplatsen.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        ```

    # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later/)

    1. I mappen **CommerceRuntime\\Extensions.SalesTransactionSignatureSample.Messages\\bin\\Debug** hitta **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll** sammansättningsfilen.
    2. Kopiera filen till **\\bin** mapp under IIS Retail Server webbplatsen.
    3. Registrera CRT ändringen i konfigurationsfilen för CRT. Denna fil kallas **commerceruntime.ext.config** och finns i mappen **bin** under IIS Retail Server-webbplatsen.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
        ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Inga åtgärder krävs.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

    > [!NOTE]
    > Inga åtgärder krävs.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

    > [!NOTE]
    > Inga åtgärder krävs.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

    > [!NOTE]
    > Inga åtgärder krävs.

    ---

### <a name="the-modern-pos-extension-components"></a>Tilläggskomponenter för Modern POS

#### <a name="implement-the-proxy-code-for-offline-mode"></a>Implementera proxykoden för offlineläge

Den här delen motsvarar Retail Server-kontrollant, men utökar den lokala som CRT används när klienten inte är ansluten.

1. I filen **customization.settings**, ändra avsnittet **@(RetailServerLibraryPathForProxyGeneration)** så att den använder den nya Retail Server-sammansättningen för proxygenerering. 
2. Implementera följande gränssnittsmetoder i **StoreOperationsManager** klassen. Lägg till följande kod vid den första iterationen:

    # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady()
    {
        throw new NotImplementedException();
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        throw new NotImplementedException();
    }
    ```

    # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady(string correlationId)
    {
        throw new NotImplementedException();
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        throw new NotImplementedException();
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Det här steget gäller inte för den här versionen.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

    > [!NOTE]
    > Det här steget gäller inte för den här versionen.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

    > [!NOTE]
    > Det här steget gäller inte för den här versionen.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

    > [!NOTE]
    > Det här steget gäller inte för den här versionen.

    ---

3. För att återskapa proxykoden, bygg mappen **Proxyn** från kommandoraden med kommandot **msbuild /t:Rebuild**.
4. Lösa projektberoenden inom **Proxies.RetailProxy**: 

    # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

    Öppna **RetailSDK\\Proxies\\RetailProxy\\Proxies.RetailProxy.csproj**, lägg till **RetailSDK\\SampleExtensions\\CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\CommerceRuntime.Extensions.SalesTransactionSignatureSample** projekt till lösningen och lägg till en projektreferens till **RetailProxy** till referens **SalesTransactionSignatureSample**.

    # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

    Öppna **RetailSDK\\Proxies\\RetailProxy\\Proxies.RetailProxy.csproj**, lägg till **RetailSDK\\SampleExtensions\\CommerceRuntime\\Extensions.SalesTransactionSignatureSample.Messages\\CommerceRuntime.Extensions.SalesTransactionSignatureSample.Messages** projekt till lösningen och lägg till en projektreferens till **RetailProxy** till referens **SalesTransactionSignatureSample.Messages**.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Det här steget gäller inte för den här versionen.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

    > [!NOTE]
    > Det här steget gäller inte för den här versionen.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

    > [!NOTE]
    > Det här steget gäller inte för den här versionen.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

    > [!NOTE]
    > Det här steget gäller inte för den här versionen.

    ---

5. Justera gränssnittsmetoder i **StoreOperationsManager** klassen:

    # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady()
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<SalesTransactionSignatureServiceIsReadyResponse>(new SalesTransactionSignatureServiceIsReadyRequest(), null).IsReady);
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<GetLastFiscalTransactionResponse>(new GetLastFiscalTransactionRequest(), null).FiscalTransaction);
    }
    ```

    # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

    ``` csharp
    public Task<bool> SalesTransactionSignatureServiceIsReady(string correlationId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<SalesTransactionSignatureServiceIsReadyResponse>(new SalesTransactionSignatureServiceIsReadyRequest(), null).IsReady);
    }
    public Task<FiscalTransaction> GetLastFiscalTransaction(string storeNumber, string terminalId)
    {
        return Task.Run(() => CommerceRuntimeManager.Runtime.Execute<GetLastFiscalTransactionResponse>(new GetLastFiscalTransactionRequest(), null).FiscalTransaction);
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    > [!NOTE]
    > Det här steget gäller inte för den här versionen.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

    > [!NOTE]
    > Det här steget gäller inte för den här versionen.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

    > [!NOTE]
    > Det här steget gäller inte för den här versionen.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

    > [!NOTE]
    > Det här steget gäller inte för den här versionen.

    ---

6. Uppdatera filen **dllhost.exe.config** så att Client Broker läser in den nya RetailProxy-monteringen.

    ``` xml
    <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy" />
    <add key="AdaptorCallerFullTypeName" value="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller" />
    ```

#### <a name="retail-proxy-extension-component-retail-731-and-later"></a>Tilläggskomponenten Retail proxy (Retail 7.3.1 och senare)

Slutför endast följande procedur om du använder Retail 7.3.1 och senare.

1. I mappen **RetailSDK\\SampleExtensions\\RetailProxy\\RetailProxy.Extensions.SalesTransactionSignatureSample** hitta **RetailServer.Extensions.SalesTransactionSignatureSample** och skapa det.
2. I mappen **RetailProxy\\RetailProxy.Extensions.SalesTransactionSignatureSample\\bin\\Debug** hitta sammansättningsfilen **Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample**.
3. Kopiera monteringsfilerna till mappen **\\ext** under lokalen CRT Client Broker-plats.
4. Registrera Retail proxy-ändringen i konfigurationsfilen för tillägget. Filen heter **RetailProxy.MPOSOffline.ext.config** och är under den lokala CRT Client Broker platsen.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
    ```

#### <a name="modern-pos-extension-components"></a>Tilläggskomponenter för Modern POS

1. Öppna lösningen på **RetailSdk\\POS\\ModernPOS.sln** och se till att den kan kompileras utan fel. Kontrollera dessutom att du kan köra Modern POS från Microsoft Visual Studio med hjälp av kommandot **kör**.

    > [!NOTE]
    > Modern POS får inte anpassas. Du måste aktivera User Account Control (UAC) och du måste avinstallera tidigare installerade instanser av Modern POS efter behov.

2. Inkludera följande befintliga källkodsmappar i projektet **Pos.Extensions**.

    # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

3. Aktivera att tilläggen kompileras i **tsconfig.json** genom att ta bort följande mappar från undantagslistan.

    # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

4. Aktivera tilläggen som måste läsas in genom att lägga till följande rader i filen **extensions.json**.

    # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    ---

    > [!NOTE]
    > Mer information och exempel som visar hur du inkluderar källkodsmappar och aktiverar tillägg som ska läsas in finns i instruktionerna i readme.md filen i projektet **Pos.Extensions**.

5. Återskapa lösningen.
6. Kör Modern POS i felsökaren och testa funktionen.

### <a name="cloud-pos-extension-components"></a>Tilläggskomponenter för Cloud POS

1. Öppna lösningen på **RetailSdk\\POS\\CloudPOS.sln** och se till att den kan kompileras utan fel.
2. Inkludera följande befintliga källkodsmappar i projektet **Pos.Extensions**.

    # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

3. Aktivera att tilläggen kompileras i **tsconfig.json** genom att ta bort följande mappar från undantagslistan.

    # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

    - AuditEventExtensionSample
    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

    - SalesTransactionSignatureSample
    - SalesTransactionSignatureNorway
    - SequentialSignature

    ---

4. Aktivera tilläggen som måste läsas in genom att lägga till följande rader i filen **extensions.json**.

    # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    }
    ```

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

    ``` json
    {
        "baseUrl": "AuditEventExtensionSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

    ``` json
    {
        "baseUrl": "Microsoft/AuditEvent.NO"
    },
    {
        "baseUrl": "SalesTransactionSignatureSample"
    },
    {
        "baseUrl": "SalesTransactionSignatureNorway"
    },
    {
        "baseUrl": "SequentialSignature"
    }
    ```

    ---

    > [!NOTE]
    > Mer information och exempel som visar hur du inkluderar källkodsmappar och aktiverar tillägg som ska läsas in finns i instruktionerna i readme.md filen i projektet **Pos.Extensions**.

5. Återskapa lösningen.
6. Kör lösningen med hjälp av kommandot **kör** och följa stegen i handboken Retail SDK.
7. Funktionaliteten:

### <a name="set-up-required-parameters-in-headquarters"></a>Ställ in obligatoriska parametrar i Administration

Mer information finns i [Kassafunktion för Norge](./emea-nor-cash-registers.md).

## <a name="production-environment"></a>Produktionsmiljö

Följ dessa steg för att skapa distribuerbara paket som innehåller Commerce-komponenter och för att tillämpa dessa paket i en produktionsmiljö.

1. Slutför stegen i avsnittet [Cloud POS tilläggskomponenter](#cloud-pos-extension-components) eller [Modern POS tilläggskomponenter](#modern-pos-extension-components) tidigare i detta ämne.
2. Gör följande ändringar i paketkonfigurationsfilerna under mappen **RetailSdk\\Assets**:

    1. I konfigurationsfilerna **commerceruntime.ext.config** och **CommerceRuntime.MPOSOffline.Ext.config** lägger du till följande rader i avsnittet **komposition**:

        # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.RegisterAuditEventSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.RegisterAuditEventNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.ReceiptsNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExt" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesPaymentTransExtNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SequentialSignatureRegister" />
        <add source="assembly" value="Contoso.Commerce.Runtime.SalesTransactionSignatureNorway" />
        <add source="assembly" value="Contoso.Commerce.Runtime.XZReportsNorway" />
        ```

        ---

    2. Aktivera anpassning av Commerce Proxy:

        # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

        I konfigurationsfilen **dllhost.exe.config** lägger du till följande rader i **appSettings** underavsnittet för avsnittet **konfiguration**.

        ``` xml
        <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy"/>
        <add key="AdaptorCallerFullTypeName" value ="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller"/>
        ```

        # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

        I konfigurationsfilen **dllhost.exe.config** lägger du till följande rader i **appSettings** underavsnittet för avsnittet **konfiguration**.

        ``` xml
        <add key="RetailProxyAssemblyName" value="Contoso.Commerce.RetailProxy"/>
        <add key="AdaptorCallerFullTypeName" value ="Contoso.Commerce.RetailProxy.Adapters.AdaptorCaller"/>
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        I konfigurationsfilen **RetailProxy.MPOSOffline.ext.config** lägg till följande rader i avsnittet **komposition**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

        I konfigurationsfilen **RetailProxy.MPOSOffline.ext.config** lägg till följande rader i avsnittet **komposition**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

        I konfigurationsfilen **RetailProxy.MPOSOffline.ext.config** lägg till följande rader i avsnittet **komposition**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

        I konfigurationsfilen **RetailProxy.MPOSOffline.ext.config** lägg till följande rader i avsnittet **komposition**:

        ``` xml
        <add source="assembly" value="Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample" />
        ```

        ---

3. Gör följande ändringar i konfigurationsfilerna för paketanpassning **Customization.settings**:

    1. Aktivera anpassning av Retail Proxy.

        # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

        Lägg till följande rader i **&lt;ItemGroup Condition="'@(RetailServerLibraryPathForProxyGeneration)' == ''"&gt;** avsnittet.

        ``` xml
        <RetailServerLibraryPathForProxyGeneration Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll"/>
        ```

        # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

        Lägg till följande rader i **&lt;ItemGroup Condition="'@(RetailServerLibraryPathForProxyGeneration)' == ''"&gt;** avsnittet.

        ``` xml
        <RetailServerLibraryPathForProxyGeneration Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll"/>
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        Lägg till följande rader till avsnittet **ItemGroup** för att inkludera Retail proxy-tillägget i de distribuerbara paketen.

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

        Lägg till följande rader till avsnittet **ItemGroup** för att inkludera Retail proxy-tillägget i de distribuerbara paketen.

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

        Lägg till följande rader till avsnittet **ItemGroup** för att inkludera Retail proxy-tillägget i de distribuerbara paketen.

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

        Lägg till följande rader till avsnittet **ItemGroup** för att inkludera Retail proxy-tillägget i de distribuerbara paketen.

        ``` xml
        <ISV_RetailProxy_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.RetailProxy.SalesTransactionSignatureSample.dll" />
        ```

        ---

    2. Lägg till följande rader till avsnittet **ItemGroup** för att inkludera CRT-tillägget i de distribuerbara paketen.

        # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.RegisterAuditEventSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.ReceiptsNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExt.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesPaymentTransExtNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureNorway.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SequentialSignatureRegister.Contracts.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.XZReportsNorway.dll" />
        ```

        ---

    3. Lägg till följande rader till avsnittet **ItemGroup** för att inkludera Retail Server-tillägget i de distribuerbara paketen.

        # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config" />
        ```

        # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.SalesTransactionSignatureSample.Messages.dll" />
        ```

        # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

        ``` xml
        <ISV_RetailServer_CustomizableFile Include="$(SdkReferencesPath)\Contoso.RetailServer.SalesTransactionSignatureSample.dll" />
        ```

        ---

4. Ändra följande filer när du vill inkludera resursfilerna för Norge i distributionsbara paket:
    - Paket\_SharedPackagingProjectComponents\Sdk.ModernPos.Shared.csproj
    - Paket\RetailServer\Sdk.RetailServerSetup.proj
  
  - För filen **Sdk.ModernPos.Shared.csproj** 
    - Lägga till rad i avsnittet **ItemGroup**
    
        ``` xml
        <<File_name> Include="$(SdkReferencesPath)\nb-NO\*" />
        ```
    > [!Note]
    > I stället <File_name> ange ett namn på resursfilen. Samma sak gäller för de övriga nedan angivna exemplen.
 
    - Lägg till rad i avsnittet **Målnamn="CopyPackageFiles"** 
       ``` xml
        <Copy SourceFiles="@(<File_name>)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\nb-NO" SkipUnchangedFiles="true" />
        ```
  
  - För filen **Sdk.RetailServerSetup.proj** 
    - Lägga till rad i avsnittet **ItemGroup**
        ``` xml
        <<File_name> Include="$(SdkReferencesPath)\nb-NO\*" />
        ```    
    - Lägg till rad i avsnittet **Målnamn="CopyPackageFiles"** 
         ``` xml
        <Copy SourceFiles="@(<File_name>)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\nb-NO" SkipUnchangedFiles="true" />
        ```    

5. Ändra filen certifikatets konfigurationsfil genom att ange tumavtryck, butiksplats och butiksnamn för certifikatet som ska användas för att signera försäljningstransaktioner. Kopiera sedan konfigurationsfilen till **referensmappen**.

    # <a name="application-update-4"></a>[Programuppdatering 4](#tab/app-update-4)

    Filen med namnet **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config** och under **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="application-update-5-and-later"></a>[App-plattformsuppdatering 5 och senare](#tab/app-update-5-and-later)

    Filen med namnet **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config** och under **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="retail-731"></a>[Retail 7.3.1](#tab/retail-7-3-1)

    Filen med namnet **Contoso.Commerce.Runtime.SalesTransactionSignatureSample.dll.config** och under **CommerceRuntime\\Extensions.SalesTransactionSignatureSample\\bin\\Debug**.

    # <a name="retail-732-and-later"></a>[Retail 7.3.2 och senare](#tab/retail-7-3-2)

    Filen med namnet **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config** och under **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    # <a name="retail-735-and-later"></a>[Retail 7.3.5 och senare](#tab/retail-7-3-5)

    Filen med namnet **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config** och under **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    # <a name="retail-811-and-later"></a>[Retail 8.1.1 och senare](#tab/retail-8-1-1)

    Filen med namnet **Contoso.Commerce.Runtime.SequentialSignatureRegister.dll.config** och under **Extensions.SequentialSignatureRegister\\bin\\Debug**.

    ---

6. Uppdatera konfigurationsfilen för Retail Server. I konfigurationsfilen **RetailSDK\\Packages\\RetailServer\\Code\\web.config**, lägg till följande rader till avsnittet **extensionComposition**.

    ``` xml
    <add source="assembly" value="Contoso.RetailServer.SalesTransactionSignatureSample" />
    ```

7. Kör **msbuild** för hela Retail SDK för att skapa distribuerbara paket.
8. Tillämpa paketen via Microsoft Dynamics Lifecycle Services (LCS) eller manuellt. Mer information finns i [skapa distribuerbara paket](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>Aktivera den digitala signaturen i offlineläge för Modern POS

Om du vill aktivera den digitala signaturen i offlineläget för Modern POS måste du följa dessa steg efter att du aktiverat Modern POS på en ny enhet.

1. Logga in på POS.
2. Kontrollera att sidan **Status för databasanslutning**, se till att offlinedatabasen är helt synkroniserad. När värdet i fältet **Pågående hämtningar** är **0** (noll) synkroniseras databasen helt.
3. Logga ut från POS.
4. Vänta en stund innan offline-databasen är helt synkroniserad.
5. Logga in på POS.
6. Kontrollera att sidan **Status för databasanslutning**, se till att offlinedatabasen är helt synkroniserad. När värdet i fältet **Väntande transaktioner i offlinedatabas** är **0** (noll) synkroniseras databasen helt.
7. Starta om Modern POS.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
