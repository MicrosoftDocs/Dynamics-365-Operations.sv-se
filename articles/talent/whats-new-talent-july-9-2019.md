---
title: Nyheter och ändringar i Dynamics 365 Talent (9 juli 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 07/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-07-09
ms.dyn365.ops.version: Talent
ms.openlocfilehash: feb39966d98fa7bde9a6bfad26b07fbd224da59b
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528050"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-july-9-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (9 juli 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

### <a name="coming-soon-in-attract"></a>Kommer snart i Attract

#### <a name="job-approvals-appear-on-the-home-page"></a>Jobbgodkännanden visas på startsidan

Godkännanden visas i avsnittet **Godkännanden** på instrumentpanelen. Godkännare kan granska godkännanden under **tilldelade dig**, som visar jobb-ID, jobbtitel, andra godkännare och datum när jobbet tilldelades. Användare som skickar ett jobb för godkännande kan granska sina jobb under **Begärdaav dig** vilket visar de godkännare som fortfarande måste godkänna det överförda jobbet.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2374.

### <a name="platform-update-28-for-finance-and-operations"></a>Plattformsuppdatering 28 för Finance and Operations

Mer information om plattformsuppdatering 28 för Finance and Operations finns i [Förhandsgranskningsfunktioner i Dynamics 365 Finance and Operations-plattformsuppdatering 28 (juli 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-28).

### <a name="entity-support-for-custom-fields-in-common-data-service"></a>Entitetsstöd för anpassade fält i Common Data Service 

Följande entiteter stöder anpassade fält: 

- **Fast kompensationsplan**
- **Kompensationsreferenspunkt**
- **Ställ in kompensationsreferenspunkt**
- **Inkomstkod för lön**
- **Löneperiod**
- **Händelse för fast kompensation**
- **Kompensationsrutnät**

Så här visar du alla uppdaterade entiteter i Talent:

1. Välj **systemadministration**, välj **länkar** och välj sedan **konfiguration av Common Data Service**.
2. Välj listrutan **CDS-entitetsnamn**. Alla entiteter i listan finns i den senaste versionen. 

###  <a name="full-name-added-to-worker-entity-in-common-data-service"></a>Fullständigt namn tillagt i entiteten Arbetare i Common Data Service

Fältet **Fullständigt namn** har lagts till entiteten **Arbetare**.

### <a name="full-time-equivalent-higher-than-10"></a>Heltidslön är högre än 1,0

En varning visas nu om ett högre värde än 1,0 anges för en heltidsanställd på en befattning. 

### <a name="a-warning-no-longer-displays-on-the-worker-page-when-there-is-no-future-dated-employment"></a>En varning visas inte längre på sidan Arbetare sida när det inte finns någon framtida, daterad anställning

Du får inte längre ett meddelande som anger att en framtida anställning finns när du navigerar till sidan **Arbetare** från listan med **befintliga anställda** i arbetsytan **personalhantering**. 

### <a name="unable-to-delete-a-business-process-in-talent"></a>Det går inte att ta bort en affärsprocess i Talent

Du kan nu ta bort affärsprocesserna i arbetsytan **Affärsprocess**

### <a name="leave-balance-no-longer-displays-zero-for-plans-with-no-accruals-when-using-balance-as-of-accrual-period"></a>Ledighetssaldo visar inte längre noll för planer utan periodiseringar vid användning av saldo vid periodiseringsperiod

Planer som har konfigurerats utan periodiseringar kan nu visa ett saldo.

## <a name="in-preview"></a>I förhandsgranskning

### <a name="preview-features-are-enabled-only-in-sandbox-instances"></a>Förhandsgranskningsfunktioner aktiveras endast i begränsade instanser

När du etablerar en ny instans av Talent kan du ange om instanstypen är **produktion** eller **begränsat läge**. Med instanser **Begränsat läge** kan tidig test av nya funktioner göras. Alla befintliga Talent-instanser kommer att uppdateras till instanstypen **produktion**. Om du vill uppdatera en av dina befintliga förekomster till instanstypen **Begränsat läge** kontaktar du [Support](https://docs.microsoft.com/dynamics365/unified-operations/talent/talent-support) för att initiera ändringsbegäran.

Mer information om hur du ändringar publiceras finns i [Etablera Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).

### <a name="restrict-leave-types-in-time-off-requests"></a>Begränsa tjänstledighetstyperna i ledighetsansökningar

Organisationer kan erbjuda många olika typer av tjänstledighet till medarbetarna. Det är dock inte lämpligt att låta medarbetarna skicka ut ledighetsbegäranden för vissa tjänstledighetstyper. Dessa tjänstledighets typer kan hanteras av personal i stället. Med den här versionen kan du konfigurera vilka tjänstledighetstyper som medarbetare kan skicka ut ledighetsansökningar för. 

## <a name="coming-soon-in-core-hr"></a>Kommer snart i Core HR

### <a name="view-extended-information-for-performance-in-manager-self-service"></a>Visa utökad information för prestandan i Självbetjäning för chefer

Med ett nytt alternativ kan cheferna visa prestandan för både deras direktrapporter och de utökade rapporterna. För närvarande kan linjechefer tilldela och uppdatera resultatmål och utfärda nya recensioner som deras anställda hanterar gemensamt. Dessutom kan direktchefer och deras medarbetare underhålla och uppdatera prestandajournaler för att säkerställa att processen för resultatöversynen går smidigt. När den här ändringen har implementerats kan chefer visa och underhålla prestandarelaterad information för sina utökade rapporter utöver deras underställda. 

### <a name="entities-supporting-custom-fields"></a>Entiteter ger stöd för anpassade fält

Följande entiteter kommer att aktiveras för anpassade fält i Common Data Service: 

- **Tjänstledighetstyp**
- **Bankkonto för arbetare**
- **Arbetskalender**
