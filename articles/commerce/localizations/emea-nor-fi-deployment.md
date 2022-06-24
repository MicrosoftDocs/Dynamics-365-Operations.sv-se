---
title: Riktlinjer för distribution av kassaapparater för Norge
description: Denna artikel innehåller information om hur du aktiverar kassaapparatfunktionen för Microsoft Dynamics 365 Commerce-lokalisering för Norge.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: 1f2226432237662e28b9e26017020ab81bb6026b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899077"
---
# <a name="deployment-guidelines-for-cash-registers-for-norway"></a>Riktlinjer för distribution av kassaapparater för Norge

[!include[banner](../includes/banner.md)]

Denna artikel innehåller information om hur du aktiverar kassaapparatfunktionen för Microsoft Dynamics 365 Commerce-lokalisering för Norge. Lokaliseringen består av flera utvidgningar av komponenter. Dessa tillägg låter dig utföra åtgärder som att skriva ut anpassade fält på kvitton, registrera ytterligare revisionshändelser, försäljningstransaktioner och betalningstransaktioner i försäljningsställe (POS), digital signering av försäljningstransaktioner och skriva ut rapporter i lokala format. Mer information om lokalisering för Norge finns i [Kassaregisterfunktionen för Norge](./emea-nor-cash-registers.md). Mer information om hur du konfigurerar Commerce för Norge finns i [Konfigurera Commerce för Norge](./emea-nor-cash-registers.md#setting-up-commerce-for-norway).

> [!WARNING]
> På grund av begränsningar i den [nya oberoende förpacknings- och anknytningsmodellen](../dev-itpro/build-pipeline.md), det kan för närvarande inte användas för denna lokaliseringsfunktion. Du måste använda versionen av exemplet på digital signering för Norge i den tidigare versionen av Retail Software Development Kit (SDK) på en virtuell dator för utvecklare i Microsoft Dynamics Lifecycle Services (LCS). Mer information finns i [Riktlinjer för distribution för kassaregister för Norge (äldre)](./emea-nor-loc-deployment-guidelines.md).
>
> Stöd för den nya oberoende förpacknings- och anknytningsmodellen för skatteintegreringsexempel planeras för senare versioner.

## <a name="set-up-fiscal-registration-for-norway"></a>Ställa in räkenskapsregistrering för Norge

Exemplet på räkenskapsregistreringstjänsten för Norge baseras på [räkenskapsintegreringsfunktionen](fiscal-integration-for-retail-channel.md) och ingår i Retail SDK. Exemplet finns i mappen **src\\FiscalIntegration\\SequentialSignatureNorway** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (till exempel [i version/9.34](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.34/src/FiscalIntegration/SequentialSignatureNorway)). Exemplet [består](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) av en leverantör av skattedokument och en räkenskapskoppling, som är förlängningar av Commerce Runtime (CRT). Mer information om hur du använder Retail SDK finns i [Retail SDK-arkitekturen](../dev-itpro/retail-sdk/retail-sdk-overview.md) och [konfigurera ett försäljningsförlopp för oberoende förpacknings-SDK](../dev-itpro/build-pipeline.md).

Slutför konfigurationsstegen för räkenskapsregistrering som beskrivs i [konfigurera räkenskapsintegrering för Commerce-kanaler](./setting-up-fiscal-integration-for-retail-channel.md):

1. [Ställa in process för räkenskapsregistrering](./setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Var noga med att notera inställningarna för den process för räkenskapsregistrering som är [specifika för Norge](#configure-the-fiscal-registration-process).
1. [Ange inställningar för felhantering](./setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Aktivera manuell körning av uppskjutna räkenskapsregistreringar](./setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Konfigurera kanalkomponenter](#configure-channel-components).

### <a name="configure-the-fiscal-registration-process"></a>Konfigurera räkenskapsregistreringsprocessen

Följ dessa steg för att aktivera den skattemässiga registreringsprocessen för Norge i Commerce headquarters.

1. Ladda ner konfigurationsfiler för leverantören av skattedokument och skatteanslutningen från Commerce SDK:

    1. Öppna [Dynamics 365 Commerce Solutions](https://github.com/microsoft/Dynamics365Commerce.Solutions/) databasen.
    1. Öppna den senast tillgängliga frisläppningsgrenen (till exempel **[version/9.34](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.34)**).
    1. Öppna **src \> FiscalIntegration \> SequentialSignatureNorway \> CommerceRuntime**.
    1. Hämta konfigurationsfilen för räkenskapsdokumentprovidern på **DocumentProvider.SequentialSignNorway \> Konfiguration \> DocumentProviderSequentialSignatureNorwaySample.xml** (till exempel [fil för version/9.34](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.34/src/FiscalIntegration/SequentialSignatureNorway/CommerceRuntime/DocumentProvider.SequentialSignNorway/Configuration/DocumentProviderSequentialSignatureNorwaySample.xml)).
    1. Ladda ner konfigurationsfilen för räkenskapskoppling på **Connector.SequentialSignNorway \> Konfiguration \> ConnectorSequentialSignatureNorwaySample.xml** (till exempel [filen för version/9.34](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.34/src/FiscalIntegration/SequentialSignatureNorway/CommerceRuntime/Connector.SequentialSignNorway/Configuration/ConnectorSequentialSignatureNorwaySample.xml)).

1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> Delade parametrar**. På fliken **allmänt** anger du alternativet **Aktivera räkenskapsintegrering** till **Ja**.
1. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegrering \> Räkenskapskopplingar** och läs in konfigurationsfilen för räkenskapskoppling för skattedokumentleverantören som du laddade ner tidigare.
1. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapsintegrering \> Leverantörer av skattedokument** och läs in konfigurationsfilen för skattedokumentleverantören som du laddade ner tidigare.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegrering \> Funktionsprofiler för koppling**. Skapa en ny funktionsprofil för koppling och välj dokumentleverantören och kopplingen som du laddade tidigare.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegrering \> Tekniska profiler för koppling**. Skapa en ny teknisk profil för koppling och välj kopplingen som du laddade tidigare. Ange att kopplingstypen är **intern**.
1. Gå till **Retail och Commerce \> Kanalinställningar \> Räkenskapskoppling \> Räkenskapskopplingsgrupper** och skapa en ny finansiell kopplingsgrupp för kopplingsfunktionsprofilen som du skapade tidigare.
1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegrering \> Processer för räkenskapsregistrering**. Skapa en ny räkenskapsregistrering och räkenskapsregistrering och välj den grupp för räkenskapskoppling som du skapade tidigare.
1. Gå till **Butik och handel \> Kanalinställningar \> Kassainställningar \> Kassaprofiler \> Funktionsprofiler**. Välj en funktionsprofil som är kopplad till butiken där registreringsprocessen ska aktiveras. På snabbfliken **Process för räkenskapsregistrering**, välj räkenskapsregistreringsprocessen som du skapade tidigare. På snabbfliken **Skattetjänster**, välj teknisk profil för koppling som du skapade tidigare. 
1. Gå till **Retail and Commerce \> Retail and Commerce-IT \> Distributionsschema**. Öppna distributionsschema och välj jobb **1070** och **1090** för att överföra data till kanaldatabasen.

### <a name="configure-the-digital-signature-parameters"></a>Konfigurera parametrarna för digital signatur

Du måste konfigurera certifikat som ska användas för digital signering av försäljningstransaktioner i en butik. Ett digitalt certifikat som lagras i Azure Key Vault används vid signeringen. För offlineläget i Modern POS kan signeringen även göras med ett digitalt certifikat som lagras i den lokala lagringen av den maskin som Modern POS är installerat på.

Innan du kan använda ett digitalt certifikat som lagras i Key Vault-lagring måste följande steg utföras.

1. Key Vault-lagring måste skapas. Vi rekommenderar att du distribuerar lagring i samma geografiska region som Commerce Scale Unit.
1. Certifikatet måste överföras till Key Vault-lagring som en base64-sträng.
1. Programobjektserverns (AOS) program måste ha behörighet att läsa läses av från Key Vault-lagringen.

Mer information om hur du arbetar med Key Vault finns i [Komma igång med Azure Key Vault](/azure/key-vault/key-vault-get-started).

På sidan **Key Vault-parametrar** måste du ange parametrarna för åtkomst till Key Vault-lagringen:

- **Namn** och **beskrivning** – Namnet på och beskrivningen av Key Vault-lagringen.
- **Key Vault-URL** – URL för Key Vault-lagringen.
- **Key Vault-klient** – Ett interaktivt klient-ID för Azure Active Directory (Azure AD) appen som är kopplad till Key Vault-lagring för autentisering. Den här klienten ska ha åtkomst att läsa från lagringsmediet.
- **Key Vault hemlig nyckel** – En hemlig nyckel som är associerad med programmet Azure AD som används för autentisering i Key Vault-lagring.
- **Namn**, **Beskrivning** och **Hemlig referens** – Namnet, beskrivningen och referensen till intyget.

Sedan måste du konfigurera en connector för dina certifikat som är lagrade i Key Vault eller lokal certifikatlagring. Denna kontakt används för signering på kanalsidan.

1. Gå till **Retail och Commerce \> Kanalinställning \> Räkenskapsintegrering \> Tekniska profiler för koppling**.
1. På snabbfliken **Inställningar**, ange följande parametrar för digitala signaturer:

    - **Hemligt namn** – Välj det hemliga namnet som du konfigurerade tidigare på **Key Vault-parametrar**.
    - **Lokalt certifikats tumavtryck** – Ange ett tumavtryck för ett certifikat som lagras lokalt.
    - **Hash-algoritm** – Ange en av de kryptografiska hash-algoritmerna som stöds av Microsoft .NET till exempel **SHA1**.
    - **Certifikatbutikens namn** – Detta fält är valfritt. Använd den för att ange ett standardnamn för butiken som ska användas för att söka efter lokala certifikat.
    - **Certifikatbutikens plats** – Detta fält är valfritt. Använd den för att ange ett standardplats för butiken som ska användas för att söka efter lokala certifikat.
    - **Försök först lokalt certifikat** – Välj det här alternativet för att använda certifikatet från den lokala butiken som standard för signering av data, istället för certifikatet från Key Vault.
    - **Aktivera hälsokontroll** – För mer information om hälsokontrollfunktionen, se [hälsokontroll av räkenskapsregistrering](./fiscal-integration-for-retail-channel.md#fiscal-registration-health-check).

> [!NOTE]
> - Bara **SHA1**-kryptografisk hash-algoritm är för närvarande godtagbar för Norge.
> - Standardnamnet på butiken och lagringsplatsen läggs till för att förenkla processen att söka i lokala certifikat i CRT. X509StoreProvider har en lista med mappar där certifikat lagras. Om standardnamnet på butiken och standardplatsen för arkivet inte anges försöker X509StoreProvider hitta ett certifikat i de andra mapparna i listan.

### <a name="configure-channel-components"></a>Konfigurera kanalkomponenter

### <a name="development-environment"></a>Utvecklingsmiljö

Följ dessa steg för att konfigurera en utvecklingsmiljö så att du kan testa och utöka exemplet.

1. Eller hämta [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions)-databasen. Välj en korrekt version av frisläppningen enligt din SDK/programversion. För mer information, se [Hämta Retail SDK-exempel och referenspaket från GitHub och NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Öppna lösningen **SequentialSignatureNorway.sln** under **Dynamics365Commerce.Solutions\\FiscalIntegration\\SequentialSignatureNorway** och bygg den.
1. Installera CRT-tillägg:

    1. Sök efter CRT installationsprogram:

        - **Commerce Scale Unit:** I mappen **SequentialSignatureNorway\\ScaleUnit\\ScaleUnit.SequentialSignNorway.Installer\\bin\\Debug\\net461** hitta **ScaleUnit.SequentialSignNorway.Installer** installationsprogrammet.
        - **Lokal CRT på Modern POS:** I mappen **SequentialSignatureNorway\\ModernPOS\\ModernPos.SequentialSignNorway.Installer\\bin\\Debug\\net461** hitta **ModernPos.SequentialSignNorway.Installer** installationsprogrammet.

    1. Starta CRT installationsprogrammet för filnamnstillägget från kommandorad:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

        - **Lokal CRT på Modern POS:**

            ```Console
            ModernPOS.SequentialSignNorway.Installer.exe install --verbosity 0
            ```

### <a name="production-environment"></a>Produktionsmiljö

Följ stegen i [Konfigurera en byggpipeline för ett skatteintegreringsprov](fiscal-integration-sample-build-pipeline.md) för att generera och släppa Cloud Scale Unit och självbetjäningsdistributionspaket för skatteintegreringsexemplet. Mall **SequentialSignatureNorway build-pipeline.yaml** YAML-filen finns i **Pipeline\\YAML_Files** i databasen [Dynamics 365 Commerce lösningar](https://github.com/microsoft/Dynamics365Commerce.Solutions).

### <a name="enable-the-digital-signature-in-offline-mode-for-modern-pos"></a>Aktivera den digitala signaturen i offlineläge för Modern POS

Om du vill aktivera den digitala signaturen i offlineläget för Modern POS måste du följa dessa steg efter att du aktiverat Modern POS på en ny enhet.

1. Logga in på POS.
1. Kontrollera att sidan **Status för databasanslutning**, se till att offlinedatabasen är helt synkroniserad. När värdet i fältet **Pågående hämtningar** är **0** (noll) synkroniseras databasen helt.
1. Logga ut från POS.
1. Vänta en stund innan offline-databasen är helt synkroniserad.
1. Logga in på POS.
1. Kontrollera att sidan **Status för databasanslutning**, se till att offlinedatabasen är helt synkroniserad. När värdet i fältet **Väntande transaktioner i offlinedatabas** är **0** (noll) synkroniseras databasen helt.
1. Öppna Modern POS på nytt.
