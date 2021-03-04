---
title: Konfigurera företagsinformation i Attract
description: I det här avsnittet beskrivs hur du konfigurerar företagsinformation och profilering för Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 12/07/2018
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
ms.openlocfilehash: db3ec965f3a52810d5f310697b9ed830c3abe681
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462647"
---
# <a name="configure-company-information-in-attract"></a>Konfigurera företagsinformation i Attract

[!include [banner](includes/banner.md)]

Administratörscenter i Microsoft Dynamics 365 Talent: Attract innehåller konfigurationsinställningar, integrationsalternativ och inställningsalternativ för Attract program.

## <a name="company-information"></a>Företagsinformation

Ange ett visningsnamn för företaget och lägg till en företagslogotyp. Visningsnamn och logotyp kan sedan användas i jobbinlägg och under integrationsupplevelsen.

## <a name="linkedin-integration"></a>LinkedIn-integration

Konfigurera integration med LinkedIn Recruiter System Connect(RSC). När du har anslutit till LinkedIn med LinkedIn-inloggningsinformationen kan du synkronisera en kandidats LinkedIn-profil, program, intervjuarnas feedback och anställningsteamets anteckningar. En fullständig licens för LinkedIn-rekryterare krävs. Mer information om LinkedIn Recruiter finns i [Recruiter System Connect (RSC) – Vanliga frågor](https://www.linkedin.com/help/recruiter/answer/90483).

## <a name="user-permissions"></a>Användarbehörigheter

Tilldela roller till användarna i din organisation. Följande roller finns: **Admin**, **Rekryterar**, **Anställande chef** och **Skrivskyddad**. Mer information om användarbehörigheter finns i [Säkerhets- och rollhantering i Attract](./security-attract.md).

## <a name="feature-management"></a>Funktionshantering

När nya funktioner läggs till kan de bli tillgängliga i en förhandsversion. Förhandsversionsfunktioner uppfyller inte alla tjänstkrav. Genom att ta emot dem godkänner du att dela data med externa system. Du kanske upptäcker att din organisation inte kräver alla nya funktioner som publiceras. Du kan aktivera och inaktivera förhandsversion av funktioner beroende på ditt företags behov.

## <a name="template-management"></a>Mallhantering

A processmall innehåller de aktiviteter som ska ingå i anställningsprocessen för ett jobb. Din organisation kan tillåta att alla teammedlemmar eller bara administratörer kan skapa anställningsprocessmallar. För att låta teammedlemmar skapa sina egna anställningsprocessmallar aktiverar du funktionen Mallhantering. Mer information om processmallar finns i [Skapa en processmall i Attract](./process-templates-attract.md).

## <a name="email-template-settings"></a>Inställningar för e-postmall

Organisationer kan skapa e-postmallar för olika scenarier. Du kan välja en rubrikbild som ska inkluderas i e-postmallar. Det valda sidhuvudet visas sedan i alla e-postmallar. Du kan lägga till en länk till företagets sekretesspolicy och användningsvillkor för kommunikation i sidfotmallen. Mer information finns i [E-postmallar](./email-templates.md).

## <a name="offer-process"></a>Erbjudandeprocess

Du kan konfigurera godkännandeprocessen för jobberbjudanden. Du kan till exempel ange om ett erbjudande måste godkännas innan det skickas till en kandidat. Du kan också kräva att godkännare lämnar en kommentar med sitt beslut om erbjudande.

Det finns två godkännandearbetsflöden: **parallella** och **sekventiella**.

- **Parallella** – godkännanden skickas till alla granskare samtidigt.
- **Sekventiella** – godkännanden skickas till godkännarna i en viss ordning.

Du kan också konfigurera alternativ som är relaterade till kandidatens erfarenhet. Till exempel låter ett alternativ dig ange om kandidater kan avvisa ett anbud utan ytterligare diskussion. Om du ställer in alternativet **tillåta kandidater att avvisa ett anbud utan ytterligare diskussion** till **Nej**, kommer knappen **Avvisa erbjudande** vara tillgänglig för kandidater. Om du ställer in det här alternativet till **Ja**, kan kandidater avvisa erbjudandet genom att välja en orsak och sedan välja **Avvisa erbjudande**.

Du kan också ställa in och tillämpa utgångsdatum för erbjudanden. Om du ställer in alternativet **Kräv ett förfallodatum för alla erbjudanden** till **Ja**, kommer erbjudandet att upphöra att gälla efter det antal timmar eller dagar som du anger.

Mer information om hantering av erbjudandet finns i [Ställ in erbjudandehantering](./offer-setup.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]