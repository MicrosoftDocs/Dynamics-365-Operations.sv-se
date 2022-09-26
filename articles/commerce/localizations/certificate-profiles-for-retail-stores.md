---
title: Användardefinierade certifikatprofiler för butiker
description: Denna artikel innehåller en översikt över de certifikatprofiler som är tillgängliga i Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 09/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: v-chgriffin
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.search.industry: Retail
ms.search.form: RetailFormLayout, RetailParameters
ms.openlocfilehash: 5baf043a43210d819b605546089e981c86922ca9
ms.sourcegitcommit: 4f28f262cfb8f047cb5c0070261aa0748835e74b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2022
ms.locfileid: "9558448"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a>Användardefinierade certifikatprofiler för butiker

[!include [banner](../includes/banner.md)]

Denna artikel innehåller en översikt över de certifikatprofiler som är tillgängliga i Microsoft Dynamics 365 Commerce. Den här funktionen utökar funktionen [Hantera hemligheter för butikskanaler](../dev-itpro/manage-secrets.md) genom att lägga till stöd för lokala certifikat.

Medan POS körs i offlineläge kan den inte komma åt certifikaten som lagras i nyckelvalvet i Microsoft Azure Key Vault. Det lokala certifikatet ska användas i stället. Följande funktioner stöds:

- Använda lokala certifikat i scenarier med Key Vault reserv
- Använda lokala certifikat utan Key Vault (t.ex. i en lokal installation)
- Gradvis uppdatering av certifikat, där vissa butiker och terminaler använder en ny version av certifikatet, men andra butiker och terminaler fortsätter att använda den tidigare versionen

Med funktionen för certifikatprofiler kan du ange ett standardcertifikat och ange ordningen för sökning efter certifikat i samma certifikatprofil. Den här funktionen ger också en liknande installationsmetod för lokala certifikat och certifikat för nyckelvalv. Du kan lägga till företagsspecifika inställningar för certifikat, men det unika identifieraren för mellan företag för varje certifikat kan användas i Commerce-kanal.

### <a name="scenarios"></a>Scenarier

Funktionen för certifikatprofiler stöder följande scenarier i Commerce-kanaler:

- Använda lokala certifikat i scenarier med Key Vault reserv. Här följer några exempel på dessa reservscenarier:

    - Det går inte att komma åt nyckelvalvlagret.
    - Ett certifikat hittas inte i nyckelvalvlagret.
    - POS körs i offline-läge.

- Använda lokala certifikat men utan att lagra dem i Key Vault (t.ex. i en lokal installation).
- Gör en gradvis uppdatering av certifikat, där en ny version av certifikatet bara används i butiker eller på terminaler där den nya versionen redan är tillgänglig.
- Använd samma certifikat i flera företag.

## <a name="set-up-certificate-profiles"></a>Ställ in certifikatprofiler

I proceduren nedan beskrivs hur du konfigurerar certifikatprofiler.

### <a name="set-up-key-vault"></a>Ställ in Key Vault

Innan du kan använda ett digitalt certifikat som lagras i Key Vault-lagring måste följande steg utföras.

1. Skapa ett Key Vault-lagringskonto. Vi rekommenderar att du distribuerar lagerkonto i samma geografiska region som Commerce Scale Unit.
1. Ladda upp det digitala certifikatet till Key Vault-lagringskontot.
1. Auktorisera programobjektserverns (AOS) program att läsa hemligheter av från Key Vault-lagringskontot.

Mer information om hur du arbetar med Key Vault finns i [Komma igång med Azure Key Vault](/azure/key-vault/key-vault-get-started).

### <a name="set-up-system-parameters"></a>Ställ in systemparametrar

Innan du konfigurerar certifikatprofiler i handelskanalerna måste du aktivera Commerce för att kunna använda båda certifikaten som är lagrade i Key Vault och certifikatprofiler.

Så här ställer du in systemparametrar i Commerce headquarters.

1. På sidan **Systemparametrar** ställer du in alternativet **Använd avancerat certifikatarkiv** till **Ja**.
1. I arbetsytan **funktionshantering** aktiverar du funktionen **Användardefinierade certifikatprofiler för butiker**.

### <a name="set-up-key-vault-parameters"></a>Ställ in parametrar för Key Vault

På sidan **Key Vault-parametrar** måste du ange följande parametrar för åtkomst till Key Vault-lagringen:

- **Namn** och **beskrivning** – Namnet på och beskrivningen av Key Vault-lagringskonto.
- **Key Vault-URL** – URL för Key Vault-lagringskonto.
- **Key Vault-klient** – Ett interaktivt klient-ID för Azure Active Directory (Azure AD) appen som är kopplad till Key Vault-lagringskonto för autentisering. Den här klienten ska ha åtkomst att läsa från lagringskonto.
- **Key Vault hemlig nyckel** – En hemlig nyckel som är associerad med programmet Azure AD som används för autentisering i Key Vault-lagringskonto.
- **Namn**, **Beskrivning** och **Hemlig referens** – Namnet, beskrivningen och referensen till intyget.

Mer information finns i [Konfigurera Azure Key Vault-klienten](../../finance/localizations/setting-up-azure-key-vault-client.md).

### <a name="configure-a-certificate-profile"></a>Konfigurera en intygsprofil

För att konfigurera en certifikatprofil i Commerce headquarters, följ dessa steg.

1. Öppna **Systemadministration \> Inställningar \> Certifikatprofiler**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en post.
1. Ange värden i fälten **Certifikatprofiler**, **Namn** och **Beskrivning**.

    > [!NOTE]
    > Certifikatprofilen är en unik identifierare för ett certifikat för alla företag och Commerce-komponenter.

1. På snabbfliken **Juridiska personer** väljer du **Lägg till** för att lägga till en rad.
1. Under fliken **Juridisk person**, välj den juridiska enhet (företag) som den aktuella certifikatprofilen ska användas till.

    Om certifikatprofilen ska användas för flera juridiska personer upprepar du steg 4 och 5 för att lägga till en rad för varje ytterligare juridisk person.

1. Välj **Inställningar** för att öppna sidan **Inställningar för certifikatprofil**, där du kan ange företagsspecifika inställningar för certifikatprofilen. Ange vilka certifikat som kan användas när den aktuella certifikatprofilen anropas i Commerce-kanalen. Lägg till så många intyg som du behöver och ställ in prioriteter för dem. Om ett certifikat med högre prioritet inte är tillgängligt, används nästa intyg baserat på prioritet. Mer information finns i [Arbetsflöde: Söka efter intyg i avsnittet Commerce Runtime](#workflow-searching-certificates-in-the-commerce-runtime).

    > [!NOTE]
    > Fältet **prioritet** ställs automatiskt in. Värdet **1** representerar högsta prioritet. När en ny rad läggs till på sidan **Inställningar för certifikatprofil**, anges prioriteten till ett nummer som är en högre än prioriteten för den föregående raden. Om du vill ändra prioriteten för en viss rad markerar du raden och väljer sedan antingen **Flytta upp** om du vill öka prioriteten eller **Flytta ned** för att minska prioriteten.

1. När du lägger till en ny rad på sidan **Inställningar för certifikatprofil** anger du följande fält:

    - **Platstyp** – Välj den plats där certifikatet lagras. Det finns två möjliga värden för det här fältet: **lokalt certifikat** och **nyckelvalv**.
    - **Nyckelvalv certifikat** – det här fältet är obligatoriskt om du konfigurerar fältet **platstyp** på **nyckelvalv**. Använd den för att ange hemlighet för nyckelvalv certifikat.
    - **Butiksnamn** – det här fältet är valfritt och det är bara tillgängligt om du anger fältet **platstyp** till **lokalt certifikat**. Använd den för att ange ett standardnamn för butiken som ska användas för att söka efter lokala certifikat.
    - **Butiksplats** – det här fältet är valfritt och det är bara tillgängligt om du anger fältet **platstyp** till **lokalt certifikat**. Använd den för att ange ett standardplats för butiken som ska användas för att söka efter lokala certifikat.

        > [!NOTE]
        > Standardnamnet på butiken och lagringsplatsen läggs till för att förenkla processen att söka i lokala certifikat i Commerce Runtime. X509StoreProvider har en lista med mappar där certifikat lagras. Om standardnamnet på butiken och standardplatsen för arkivet inte anges försöker X509StoreProvider hitta ett certifikat i de andra mapparna i listan. Mer information om tillgängliga värden för butiksnamnet och butiksplatsen finns i [StoreName uppräkning](/dotnet/api/system.security.cryptography.x509certificates.storename) och [StoreLocation uppräkning](//dotnet/api/system.security.cryptography.x509certificates.storelocation).

    - **Tumavtryck** – det här fältet krävs och det är bara tillgängligt om du anger fältet **platstyp** till **lokalt certifikat**. Använd den för att ange tumavtryck för certifikatet.

        > [!IMPORTANT]
        > Du måste se till att användaren som kör programmet som måste använda det lokala certifikatet (till exempel Modern POS i offlineläget) minst har skrivskyddat åtkomst till den privata nyckeln för intyget.

    - **Kommentarer** – det här fältet är valfritt och låter användarna ange noteringar.

## <a name="workflow-searching-certificates-in-the-commerce-runtime"></a>Arbetsflöde: söka efter certifikat i Commerce Runtime

Här är det grundläggande arbetsflödet som används för att söka efter ett certifikat när en certifikatprofil anropas i Commerce Runtime.

1. Systemet identifierar om certifikatprofilen har företagsspecifika inställningar för den aktuella juridiska personen.
1. Systemet försöker hitta certifikatet med hjälp av värdena på sidan **Inställningar för certifikatprofil** för den rad där fältet **prioritet** anges till **1**.

    - Om fältet **platstyp** är inställt på **nyckelvalv** används värdet för fältet **hemlighet för nyckelvalvcertifikat** för att söka efter certifikatet på sidan **parametrar för nyckelvalv**. Certifikatet söks sedan igenom i nyckelvalvlagret.
    - Om fältet **platstyp** är inställt på **lokalt certifikat**, X509StoreProvider först en sökning efter certifikatet med hjälp av standardnamnet på butiken och lagringsplatsen, om dessa parametrar har angetts. Därefter genomsöks alla andra mappar i listan med mappar.

1. Om certifikatet inte hittas upprepas processen för raden där fältet **prioritet** är inställt på **2** och så vidare.

> [!NOTE]
> Om certifikatprofilen inte har några inställningar för den aktuella juridiska personen, eller om certifikatsökningen inte lyckas för alla rader på sidan **Inställningar för certifikatprofil**, hittas inte certifikatet.

### <a name="caching-the-results-of-certificate-searches"></a>Cachelagra resultaten av certifikatsökningar

Resultaten av certifikatsökningar cachelagras. Standard förfallotiden för en cache är en timme. Den här tiden kan dock anpassas och kan ställas in på ett maximalt värde på 24 timmar.

## <a name="gradual-update"></a>Gradvis uppdatering

Om en ny version av certifikatet introduceras, men det inte kan uppdateras i alla butiker samtidigt, kan funktionen för certifikatprofil uppdateras gradvis.

1. Sök efter en certifikatprofil och raden som ska uppdateras och välj sedan **inställningar**.
1. Lägg till en rad och ange inställningar som är relaterade till den senaste versionen av certifikatet.
1. Öka värdet **prioritet** för den nya raden. Använd knappen **Flytta upp** om du vill flytta raden så att den ligger ovanför raden för den föregående versionen av samma certifikat.
> [!NOTE]
> I Commerce Runtime kommer den nya versionen av certifikatet att anropas först. Om certifikatet ännu inte har uppdaterats i en specifik butik eller på en specifik terminal kommer den föregående versionen att anropas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
