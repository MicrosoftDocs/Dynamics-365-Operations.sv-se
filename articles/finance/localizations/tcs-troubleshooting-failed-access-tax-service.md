---
title: Det gick inte att få åtkomst till momstjänsten
description: Det här avsnittet förklarar hur du felsöker ett fel i syfte att få åtkomst till tjänsten för momsberäkning.
author: hangwan
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: hangwan
ms.search.validFrom: 02/16/2022
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 48a75cd0c1d91c3b3d9c3fb2e6cab93a76756532
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388571"
---
# <a name="failed-to-access-tax-service"></a>Det gick inte att få åtkomst till momstjänsten

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

I det här ämnet beskrivs hur du rättar till felet "Ingen åtkomst till momstjänst" i beräkningstjänsten för moms.

## <a name="symptoms"></a>Symtom

I Microsoft Dynamics 365 Finance går du till **Moms** \> **Inställningar** \> **Komskonfiguration** \> **Parametrar för momstjänst**. På fliken **Allmänt** aktiverar du alternativet **Aktivera momsberäkning**. Om du sedan försöker välja ett värde i fältet **Namn för funktionsinställning** uppstår ett fel. Felmeddelandet anger "Det gick inte att få åtkomst till skattetjänsten".

## <a name="cause"></a>Orsak

Det här felet beror på att Ekonomi inte har åtkomst till beräkningstjänsten för moms.

## <a name="resolution"></a>Lösning 

1. Logga in på Microsoft Dynamics Lifecycle Services (LCS).
2. På sidan **Miljö**, på fliken **Miljötillägg**, letar du upp objekter **Momsberäkning** och kontrollerar dess status. Statusvärdet ska vara **Installerar** eller **Installerades**. Om tillägget för momsberäkningstjänst inte installeras visas felmeddelandet.

## <a name="mitigation"></a>Minskning

1. I LCS, på sidan **Ekonomi**, i avsnittet **Integrering av Power Platform** väljer du **Installera ett nytt tillägg**.
2. Rulla längst ned på sidan och välj tillägget **Momsberäkning** så att det installeras.
3. Återgå till din ekonomimiljö och försök få åtkomst till tjänsten Momsberäkning.

> [!NOTE]
> Innan du installerar momsberäkningstjänsten ska du kontrollera [Förutsättningar för tjänsten för momsberäkning](global-get-started-with-tax-calculation-service.md#prerequisites).
> 
> Om du inte kan installera tillägget eftersom avsnittet **Integrering av Power Platform** inte är tillgängligt, se [Översikt över tillägg](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Om du fortfarande stöter på felet efter att du installerat tillägget kontaktar du systemadministratören.
