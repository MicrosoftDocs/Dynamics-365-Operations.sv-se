---
title: Spåra kandidatkällor i Attract
description: Det här avsnittet innehåller information om att spåra källan för kandidatprofiler och ansökningar.
author: hachandr
manager: AnnBe
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 8860f508eebc377042c4e101eeb08a14a737ba0c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462577"
---
# <a name="track-candidate-sources-in-attract"></a>Spåra kandidatkällor i Attract

[!include [banner](includes/banner.md)]

> [!NOTE] 
> Funktionen som beskrivs i det här avsnittet är en del av förhandsversionen. Funktionen och dess innehåll kan ändras. Om du vill använda den här funktionen ber du en administratör att aktivera den med hjälp av **administrationsinställningar** i Attract. En framtida version kommer att tillhandahålla källspårningsrapporter. Mer information finns i [Få åtkomst till förhandsfunktioner i Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

När det gäller kandidater för ett jobb, spårar Attract automatiskt källan till sina ansökningar och ger dig värdefull information som hjälper dig att följa upp dina rekryteringsmål. Rekryterare och anställande chefer kan också välja en ansökningskälla medan de manuellt lägger till en kandidat till ett jobb eller en talangpool.

Du kan visa ansökningskällan i ansökningsaktivitetsinformationen under fliken **aktivitet** samt i ansökningshistoriken under **profil** i talangpooler. Du hittar en kandidats profilkälla i kandidatens information under fliken **profil** i både ansökningar och i talangpooler.

> [!NOTE] 
> Du hittar processmallar i [tillägget för omfattande anställning](https://docs.microsoft.com/dynamics365/unified-operations/talent/attract-comprehensive-hiring).

## <a name="pre-configured-sources"></a>Förkonfigurerade källor

Standardkällistan innehåller gemensamma ansökningskällor. Vissa källtyper såsom **jobbtavla** och **sociala nätverk** har ytterligare källinformation. Till exempel **sociala nätverk** inkluderar Facebook och Twitter. Källtypen **Hänvisning** låter dig ange en intern medarbetare som hänvisaren. Standardkällistan innehåller följande förkonfigurerade källor:

-   Attract karriärwebbplats

-   Myndighet

-   Karriärmässa

-   Företagets marknadsföring

-   Konferenser och mässor

-   Professionell association

-   Jobbtavla

    -   Indeed

    -   Seek

    -   CareerBuilder

    -   Google Jobs

    -   Xing

    -   Glassdoor

    -   Monster Jobs

-   Tidningar och publikationer

-   Sociala nätverk

    -   Facebook

    -   Twitter

-   Universitetsrekrytering

-   LinkedIn

-   Klassificerade

-   Hänvisning

-   Tillagd av rekryterare

-   Annat

## <a name="customize-the-source-list"></a>Anpassa källistan 

Du kan utöka källistan till att inkludera ytterligare ansökningskällor. Om du vill anpassa listan följer du instruktionerna i [utöka alternativuppsättningar i Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/extensibility-attract#extending-option-sets-in-attract). Redigera entiteten **TalentSource** till att inkludera ytterligare källor. 

För att undvika att negativ påverkan av användargränssnittet ska du inte redigera eller ta bort enum-värdet **TalentCategory** (inte namn) för följande:

- **Hänvisning**
- **LinkedIn**
- **Annat**

Däremot kan du utöka enum **TalentSource** för att lägga till andra typer av källor.
