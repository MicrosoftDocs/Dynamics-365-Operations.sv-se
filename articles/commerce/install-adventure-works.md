---
title: Installera Adventure Works-tema
description: I denna artikel beskrivs hur du installerar Adventure Works-tema i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 12/10/2021
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
ms.openlocfilehash: 18c2612b8b6b4ed8195ff8e71d6e0495f7e80950
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8854910"
---
# <a name="install-the-adventure-works-theme"></a>Installera Adventure Works-tema

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du installerar Adventure Works-tema i Microsoft Dynamics 365 Commerce. 

> [!IMPORTANT]
> Adventure Works-temat och modulerna finns tillgängliga från och med Dynamics 365 Commerce-version 10.0.20. De är tillgängliga från Microsoft AppSource.

## <a name="prerequisites"></a>Förutsättningar

Innan du installerar Adventure Works-temat måste du ha en Dynamics 365 Commerce-miljö (Commerce version 10.0.20 eller senare) som inkluderar Retail Cloud Scale Unit (RCSU), Commerce online Software Development Kit (SDK) och Commerce modulbiblioteket. Information om hur du installerar Commerce SDK och modulbiblioteket finns i [Ställ in en utvecklingsmiljö](e-commerce-extensibility/setup-dev-environment.md). 

## <a name="installation-steps"></a>Installationssteg

### <a name="install-the-adventure-works-theme-in-your-application"></a>Installera Adventure Works-tema i programmet

Paketet Adventure Works-tema finns i flödet **dynamics365-commerce** som **@msdyn365-commerce-theme/adventureworks-theme-kit**. Även om temapaketet Adventure Works är en del av flödet, finns det dock under ett annat namnområde. Därför måste du följa dessa steg för att lägga till registerposter för namnområdet.

1. Uppdatera filen **.npmrc** så att den innehåller följande registerpost (om posten inte redan ingår):

    `@msdyn365-commerce-theme:registry=https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/`

1. Uppdatera filen **.yarnrc** så att den innehåller följande registerpost (om posten inte redan ingår):

    `"@msdyn365-commerce-theme:registry" "https://pkgs.dev.azure.com/commerce-partner/Registry/_packaging/dynamics365-commerce/npm/registry/"`  
    
Om du vill installera paketet i din lokala miljö kör du kommandot `yarn add THEME_PACKAGE@VERSION` från kommandotolken där **THEME_PACKAGE** är temapaketet (@msdyn365-commerce-theme/adventureworks-theme-kit) och **VERSION** är versionsnumret för det modulbibliotek som används. Det är viktigt att versionerna av temapaketet och modulbiblioteket stämmer överens. För att hitta rätt versionsnummer för modulbiblioteket att använda öppnar du filen package.json och letar reda på värdet för **startpaket** under avsnittet **beroendet**. I följande exempel använder filen package.json version 9.32 av modulbiblioteket som mappar till Dynamics 365 Commerce versionen 10.0.22.  

```json
"dependencies": {
    "@msdyn365-commerce-modules/starter-pack": "9.32",
}
```

I följande exempel visas hur du kör kommandot `yarn add` för att lägga till version 9.32 av tema Adventure Works. Det här kommandot uppdaterar paket.json-filen automatiskt så att den inkluderar beroendet.

`yarn add @msdyn365-commerce-theme/adventureworks-theme-kit@9.32`

Information om hur du uppdaterar modulbiblioteksversionen finns i [SDK- och modulens biblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md). 

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
