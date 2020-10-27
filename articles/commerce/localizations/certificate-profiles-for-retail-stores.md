---
title: Användardefinierade certifikatprofiler för butiker
description: Det här ämnet ger en översikt över hur certifikat används i butiker.
author: josaw
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 0b8bf49a8eb78d0557ef105b40dd4cb5f0d24ce4
ms.sourcegitcommit: 83ec80382bfeb693d5c5949b6f65296bd50eed12
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/09/2020
ms.locfileid: "3973943"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a>Användardefinierade certifikatprofiler för butiker

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

## <a name="overview"></a>Översikt

Det här avsnittet innehåller en översikt över de certifikatprofiler som är tillgängliga i Microsoft Dynamics 365 Commerce. Den här funktionen utökar funktionen [Hantera hemligheter för butikskanaler](../dev-itpro/manage-secrets.md) genom att lägga till stöd för lokala certifikat.

Medan kassan körs i offlineläge kan den inte komma åt certifikaten som lagras i nyckelvalvet. Det lokala certifikatet ska användas i stället. Följande funktioner stöds:

- Använda lokala certifikat i scenarier med nyckelvalvsreserv
- Använda lokala certifikat utan nyckelvalv (t.ex. i en lokal installation)
- Gradvis uppdatering av certifikat, där vissa butiker och terminaler använder en ny version av certifikatet, men andra butiker och terminaler fortsätter att använda den tidigare versionen

Med funktionen för certifikatprofiler kan du ange ett standardcertifikat och ange ordningen för sökning efter certifikat i samma certifikatprofil. Den här funktionen ger också en liknande installationsmetod för lokala certifikat och certifikat för nyckelvalv. Du kan lägga till företagsspecifika inställningar för certifikat, men det unika identifieraren för mellan företag för varje certifikat kan användas i Commerce-kanal.

### <a name="scenarios"></a>Scenarier

Funktionen för certifikatprofiler stöder följande scenarier i Commerce-kanaler:

- Använda lokala certifikat i scenarier med nyckelvalvsreserv. Här följer några exempel på dessa reservscenarier:

    - Det går inte att komma åt nyckelvalvlagret.
    - Ett certifikat hittas inte i nyckelvalvlagret.
    - Kassan körs i offline-läge.

- Använda lokala certifikat men utan att lagra dem i nyckelvalv (t.ex. i en lokal installation).
- Gör en gradvis uppdatering av certifikat, där en ny version av certifikatet bara används i butiker eller på terminaler där den nya versionen redan är tillgänglig.
- Använd samma certifikat i flera företag.

## <a name="set-up-certificate-profiles"></a>Ställ in certifikatprofiler

I proceduren nedan beskrivs hur du ställer in certifikatprofiler. Innan du använder certifikatprofiler i Commerce-kanalerna följer du stegen nedan för att konfigurera inställningarna.

1. I arbetsytan **funktionshantering** aktiverar du funktionen **Användardefinierade certifikatprofiler för butiker**.
2. Öppna **Systemadministration \> Inställningar \> Certifikatprofiler**.
3. Skapa en post och ange fältet **Certifikatprofil**, **Namn** och **Beskrivning** för den.

    > [!NOTE]
    > Certifikatprofilen är en unik identifierare för ett certifikat för alla företag och Commerce-komponenter.

3. På fliken **Juridiska personer**, lägg till en rad och välj den juridiska enhet (företag) som den aktuella certifikatprofilen ska användas till. Om certifikatprofilen ska användas för flera juridiska personer upprepar du det här steget för att lägga till en rad för varje ytterligare juridisk person.
4. Välj **Inställningar** för att öppna sidan **Inställningar för certifikatprofil**, där du kan ange företagsspecifika inställningar för certifikatprofilen.

### <a name="certificate-profile-settings"></a>Certifikatprofilinställningar

När du väljer **inställningar** för certifikatprofilrader visas sidan **Inställningar för certifikatprofil**. På den här sidan kan du ange vilka certifikat som kan användas när den aktuella certifikatprofilen anropas i Commerce-kanalen. Du kan även ange i vilken ordning som certifikatet ska genomsökas.

> [!NOTE]
> Fältet **prioritet** ställs automatiskt in. Värdet **1** representerar högsta prioritet. När en ny rad läggs till på sidan **Inställningar för certifikatprofil**, anges prioriteten till ett nummer som är en högre än prioriteten för den föregående raden. Om du vill ändra prioriteten för en viss rad markerar du raden och väljer sedan antingen **Flytta upp** om du vill öka prioriteten eller **Flytta ned** för att minska prioriteten.

När du lägger till en ny rad på sidan **Inställningar för certifikatprofil** anger du följande fält:

- **Platstyp** – Välj den plats där certifikatet lagras. Det finns två möjliga värden för det här fältet: **lokalt certifikat** och **nyckelvalv**.
- **Nyckelvalv certifikat** – det här fältet är obligatoriskt om du ställer in fältet **platstyp** på **nyckelvalv**. Använd den för att ange hemlighet för nyckelvalv certifikat.

    > [!NOTE]
    > Innan du använder ett nyckelvalv i certifikatprofiler måste du ladda upp ett certifikat till nyckelvalvlagret och följa instruktionerna i [Konfigurera Azure Key Vault-klienten](https://docs.microsoft.com/dynamics365/finance/localizations/setting-up-azure-key-vault-client).

- **Butiksnamn** – det här fältet är valfritt och det är bara tillgängligt om du anger fältet **platstyp** till **lokalt certifikat**. Använd den för att ange ett standardnamn för butiken som ska användas för att söka efter lokala certifikat.
- **Butiksplats** – det här fältet är valfritt och det är bara tillgängligt om du anger fältet **platstyp** till **lokalt certifikat**. Använd den för att ange ett standardplats för butiken som ska användas för att söka efter lokala certifikat.

    > [!NOTE]
    > Standardnamnet på butiken och lagringsplatsen läggs till för att förenkla processen att söka i lokala certifikat i Commerce Runtime. X509StoreProvider har en lista med mappar där certifikat lagras. Om standardnamnet på butiken och standardplatsen för arkivet inte anges försöker X509StoreProvider hitta ett certifikat i de andra mapparna i listan.

- **Tumavtryck** – det här fältet krävs och det är bara tillgängligt om du anger fältet **platstyp** till **lokalt certifikat**. Använd den för att ange tumavtryck för certifikatet.
- **Kommentarer** – det här fältet är valfritt och låter användarna ange noteringar.

### <a name="workflow-searching-certificates-in-the-commerce-runtime"></a>Arbetsflöde: söka efter certifikat i Commerce Runtime

Här är det grundläggande arbetsflödet som används för att söka efter ett certifikat när en certifikatprofil anropas i Commerce Runtime.

1. Systemet identifierar om certifikatprofilen har företagsspecifika inställningar för den aktuella juridiska personen.
1. Systemet försöker hitta certifikatet med hjälp av värdena på sidan **Inställningar för certifikatprofil** för den rad där fältet **prioritet** anges till **1**.

    - Om fältet **platstyp** är inställt på **nyckelvalv** används värdet för fältet **hemlighet för nyckelvalvcertifikat** för att söka efter certifikatet på sidan **parametrar för nyckelvalv**. Certifikatet söks sedan igenom i nyckelvalvlagret.
    - Om fältet **platstyp** är inställt på **lokalt certifikat**, X509StoreProvider först en sökning efter certifikatet med hjälp av standardnamnet på butiken och lagringsplatsen, om dessa parametrar har angetts. Därefter genomsöks alla andra mappar i listan med mappar.

1. Om certifikatet inte hittas upprepas processen för raden där fältet **prioritet** är inställt på **2** och så vidare.

> [!NOTE]
> Om certifikatprofilen inte har några inställningar för den aktuella juridiska personen, eller om certifikatsökningen inte lyckas för alla rader på sidan **Inställningar för certifikatprofil**, hittas inte certifikatet.

#### <a name="caching-the-results-of-certificate-searches"></a>Cachelagra resultaten av certifikatsökningar

Resultaten av certifikatsökningar cachelagras. Standard förfallotiden för en cache är en timme. Den här tiden kan dock anpassas och kan ställas in på ett maximalt värde på 24 timmar.

### <a name="gradual-update"></a>Gradvis uppdatering

Om en ny version av certifikatet introduceras, men det inte kan uppdateras i alla butiker samtidigt, kan funktionen för certifikatprofil uppdateras gradvis.

1. Sök efter en certifikatprofil och raden som ska uppdateras och välj sedan **inställningar**.
1. Lägg till en rad och ange inställningar som är relaterade till den senaste versionen av certifikatet.
1. Öka värdet **prioritet** för den nya raden. Använd knappen **Flytta upp** om du vill flytta raden så att den ligger ovanför raden för den föregående versionen av samma certifikat.

> [!NOTE]
> I Commerce Runtime kommer den nya versionen av certifikatet att anropas först. Om certifikatet ännu inte har uppdaterats i en specifik butik eller på en specifik terminal kommer den föregående versionen att anropas.
