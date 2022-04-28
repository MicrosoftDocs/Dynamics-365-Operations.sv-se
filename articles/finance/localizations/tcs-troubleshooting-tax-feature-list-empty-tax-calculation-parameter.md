---
title: Tom momsfunktionslista i parametrar för momsberäkning
description: Detta ämne förklarar hur du felsöker ett problem där listan med momsfunktioner på sidan Parametrar för momsberäkning är tom.
author: wangchen
ms.date: 03/04/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: ef8158c2ada18e7d132eebbedef559b3f80ab19f
ms.sourcegitcommit: 2977e92a76211875421e608555311c363cfbdc25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2022
ms.locfileid: "8612301"
---
# <a name="empty-tax-feature-list-in-tax-calculation-parameters"></a>Tom momsfunktionslista i parametrar för momsberäkning

[!include [banner](../includes/banner.md)]


## <a name="symptom"></a>Symptom

Du har publicerat en funktion i Regulatory Configuration Service (RCS) så att du kan använda den i Microsoft Microsoft Dynamics 365 Finance. När du öppnar Ekonomi, gå till **Moms** \> **Inställningar** \> **Inställningar för moms** \> **Beräkningsparametrar för moms** och förösk välja ett värde i fältet **Namn på funktionsinställningar** (fältet är tomt).

## <a name="reason"></a>Orsak

Detta problem uppstår vanligtvis eftersom Ekonomimiljön och RCS-miljön inte finns under samma klientorganisation.

### <a name="rcs-tenant"></a>RCS-klientorganisation

Följ de här stegen om du vill söka efter ID:t för din RCS-klientorganisation.

1. Kopiera den fullständiga URL-adressen till RCS. URL-adressen kan till exempel vara `https://rcs-rts-sf-ed22b5aeea8-int-westus2.configure.global.int.dynamics.com/namespaces/817ff7a0-0d77-4aba-9360-3c9749e2c5de/?cmp=dat&mi=RCSFeatureDomainsWorkspace`.
2. Öppna ett webbläsarfönster för InPrivate, klistra in URL-adressen till RCS i adressfältet och välj sedan **Retur**. Du dirigeras till inloggningssidan, där du kan hitta ID:t för RCS-klienotrganisationen. Om till exempel URL:en för inloggningssidan är `https://login.microsoftonline.com/d335a570-a05b-4bc5-8eb3-c42c65f9560d`, är klient-ID:t den information som visas efter `https://login.microsoftonline.com/` eller **d335a570-a05b-4bc5-8eb3-c42c65f9560d**.

### <a name="finance-environment-tenant-id"></a>Klientorganisations-ID för Ekonomi-miljö

Om du vill söka efter klient-ID:t för din Ekonomimiljö följer du samma steg som du följde för att söka efter RCS-klientorganisationen. Kopiera och klistra emellertid in den fullständiga URL-adressen för din Ekonomimiljö istället för den fullständiga URL-adressen för RCS.

## <a name="resolution"></a>Lösning

Om dessa två klientorganisations-ID:n är olika stöter du på problemet som beskrivs i detta ämne. Om de är desamma stöter du på ett orelaterat problem. I så fall rekommenderar vi att du kontaktar Microsoft Support.

### <a name="solution-1"></a>Lösning 1

Logga in din RCS-miljö i samma klientorganisation som din Ekonomimiljö är inloggad i. Skapa och publicera sedan momsfunktionen.

### <a name="solution-2"></a>Lösning 2

Dela momsfunktionen med Ekonomiklientorganisationen i RCS.

1. I RCS, gå till **Globaliseringsfunktioner** \> **Momsberäkning**.
2. Välj den funktion som ska delas och välj sedan fliken **Organisationer** och sedan **Dela med**.
3. I fältet **Domännamn för organisation** anger du ett namn. Ange till exempel **contoso.onmicrosoft.com**.
4. Välj **dela**.

![Dela med nedrullningsbar dialogruta för extern organisation.](media/ShareTaxFeature.png)
