---
title: Installera Adventure Works-tema
description: I det här avsnittet beskrivs hur du installerar Adventure Works-tema i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9c94dd8ead32f58a25a396376840101d9c2c9b08
ms.sourcegitcommit: 0c77dbb8547cd36fce3977ca9515fa1474efa77a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2021
ms.locfileid: "6655858"
---
# <a name="install-the-adventure-works-theme"></a>Installera Adventure Works-tema

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du installerar Adventure Works-tema i Microsoft Dynamics 365 Commerce. 

> [!IMPORTANT]
> Adventure Works-temat och modulerna finns tillgängliga från och med Dynamics 365 Commerce-version 10.0.20. De är tillgängliga från Microsoft AppSource.

## <a name="prerequisites"></a>Förutsättningar

Innan du installerar Adventure Works-temat måste du ha en Dynamics 365 Commerce-miljö (Commerce version 10.0.20 eller senare) som inkluderar Retail Cloud Scale Unit (RCSU), Commerce online Software Development Kit (SDK) och Commerce modulbiblioteket. Information om hur du installerar Commerce SDK och modulbiblioteket finns i [SDK och uppdateringarna av modulbiblioteket](e-commerce-extensibility/sdk-updates.md). 

## <a name="installation-steps"></a>Installationssteg

### <a name="install-the-adventure-works-theme-in-your-application"></a>Installera Adventure Works-tema i programmet

Paketet Adventure Works-tema finns i flödet **dynamics365-commerce** som **@msdyn365-commerce-theme/adventureworks-theme-kit**. Även om temapaketet Adventure Works är en del av flödet, finns det dock under ett annat namnområde. Därför måste du följa dessa steg för att lägga till registerposter för namnområdet.

1. Uppdatera filen **.npmrc** så att den innehåller följande registerpost (om posten inte redan ingår):

    `@msdyn365-commerce-theme:registry=https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/`

1. Uppdatera filen **.yarnrc** så att den innehåller följande registerpost (om posten inte redan ingår):

    `"@msdyn365-commerce-theme:registry" "https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/"`  
    
Om du vill installera paketet i den lokala miljön kör du följande kommando från kommandotolken. Det här kommandot uppdaterar paket.json-filen automatiskt så att den inkluderar beroendet.

`yarn add @msdyn365-commerce-theme/adventureworks-theme-kit`

I filen **package.json** bör du uppdatera temaversionen till en specifik version.

> [!IMPORTANT]
> - Temaversionen ska matcha modulbiblioteksversionen för att säkerställa att alla funktioner fungerar som förväntat. 
> - Minimiversionen för modulbiblioteket för Commerce och SDK bör vara 10.0.20 (9.31). 

### <a name="add-the-font-files-for-the-adventure-works-theme"></a>Lägga till teckensnittsfiler för Adventure Works-tema

När Adventure Works-ämnet har installerats i programmet måste du lägga till de teckensnittsfiler som krävs för det. Du slutför det här steget genom att kopiera alla teckensnittsfiler från **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks\public\webfonts** till partnerappen offentliga katalogsökväg **\public\webfonts**.

### <a name="set-up-the-resources-for-the-adventure-works-theme"></a>Ange resurser för Adventure Works-tema

Nästa steg är då att uppdatera den standardresurs som behövs för ämnet. För att slutföra detta steg kopierar du innehållet från den globala.json-filen under **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks\resources\modules** till partnerappen global.json file under **\src\resources\modules**. Om målkatalogen **\src\resources** målkatalogen finns inte, den kan kopieras i sin helhet från **\node_modules@msdyn365-commerce-theme\adventureworks-theme-kit\src\modules\adventureworks** källkatalog till målkatalogen **\src**.

### <a name="pull-updates-and-validate-the-theme"></a>Hämta uppdateringar och validera ämnet

För information om hur du hämtar de senaste SDK, modulbiblioteket och andra beroendeuppdateringar, se avsnittet "Dra uppdateringar" i[SDK och uppdatering av modulbibliotek](e-commerce-extensibility/sdk-updates.md#pull-updates).

När de senaste beroendena har dragits av kan du köra kommandot **yarn start** för att starta nodservern i din utvecklingsmiljö och testa det nya Adventure Works-temat. Bläddra lokalt i programmet genom att använda frågesträngsparametern `?theme=adventureworks` (till exempel `https://localhost:4000/?theme=adventureworks`).

## <a name="additional-resources"></a>Ytterligare resurser

[Adventure Works-tema](adventure-works-theme.md)

[Modulbibliotek – översikt](starter-kit-overview.md)

[Uppdateringar av SDK och modulbibliotek](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
