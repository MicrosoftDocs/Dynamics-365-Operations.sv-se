---
title: ID-nummer tar emot via mobilappen för distributionslagerhantering
description: I det här avsnittet beskrivs hur du ställer in mobilappen för distributionslagerhantering så att du kan använda en mottagningsprocess med ID-nummer som tar emot en process som tar emot fysiskt lager.
author: perlynne
ms.date: 04/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSParameters, WHSRFMenuItem, WHSLicensePlate, WHSPackingStructure
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-03-31
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: a6bfa77f6d55e3b0a7a678ec552040a47514e4872a0a05e9f6e522eab2a5c11f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6735025"
---
# <a name="license-plate-receiving-via-the-warehouse-management-mobile-app"></a>ID-nummer tar emot via mobilappen för distributionslagerhantering

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in mobilappen för distributionslagerhantering för lager så att du kan använda en mottagningsprocess med ID-nummer som tar emot en process som tar emot fysiskt lager.

Du kan använda den här funktionen för att snabbt registrera inleveranser av ankommande lager som är relaterat till en leveransavisering (ASN). Systemet skapar automatiskt ett ASN när lagerstyrningsprocesser används för att leverera en överföringsorder. För inköpsorderprocessen kan ett ASN registreras manuellt, eller importeras automatiskt med hjälp av en inkommande ASN-dataenhetsprocess.

ASN-data är kopplade till laster och försändelser via *förpackningsstrukturer*, där lastpallar (överordnade ID-nummerar) kan innehålla lådor (kapslade ID-nummer).

> [!NOTE]
> Om du vill minska antalet lagertransaktioner när förpackningsstrukturer som har kapslade ID-nummer används registrerar systemet den fysiska lagerbehållningen på den överordnade ID-numret. För att den fysiska lagerbehållningen ska kunna initieras från den överordnade ID-numret till de kapslade ID-nummerna, baserat på förpackningsstrukturens data, måste den mobila enheten tillhandahålla ett menyobjekt som baseras på processen för att skapa arbete *paketet för att skapa kapslade ID-nummer*.

## <a name="warehousing-mobile-device-app-processing"></a>Hantering av program för mobila enheter för lagerhållning

När en arbets tagare skannar ett inkommande ID-nummer initierar systemet en inleveransprocess för ID-nummer. Utifrån den här informationen registreras innehållet i ID-nummer (data som kommer från ASN) fysiskt på inlastningsplatsen. De flöden som följer är beroende av affärsprocessens behov.

## <a name="work-policies"></a>Arbetspolicyer

Som med (till exempel) *Rapportera som färdig* mobilenhetens menyalternativprocess, kommer inleveransprocessens ID-nummer ge stöd för flera arbetsflöden baserat på den definierade inställningen.

### <a name="work-policies-with-work-creation"></a>Arbetspolicyer med arbetsskapande

När du registrerar inkommande artiklar med en arbetspolicy som skapar arbete, genererar systemet och sparar poster för inlagrat arbete för varje registrering. Om du använder arbetsprocessen *Plats och mottagning av registreringsskylt* hanteras registrering och artikelinförsel som en enskild operation med hjälp av ett enda menyalternativ på en mobil enhet. Om du använder processen *Inleverans av ID-nummer* kommer processerna för mottagande och inleverans hanteras som två olika lageroperationer, var och en med sitt eget menyalternativ för mobila enheter.

### <a name="work-policies-without-work-creation"></a>Arbetspolicyer utan arbetsskapande

Du kan använda inleveransprocess för ID-nummer utan att skapa arbete. Om du definierar arbetspolicyer principer som har en arbetsordertyp av *Överföringsinleverans* och/eller *Inköpsorder* och du använder processen för *Inleverans av ID-nummer (och inlagrad)*, kommer följande två mobilapprocesser för lagerställe inte att skapa arbete. De registrerar i stället bara det ingående fysiska lagret på ID-numret vid inkommande inleverans.

- *Inleverans av registreringsskylt*
- *Plats och mottagning av registreringsskylt*

> [!NOTE]
> - Du måste definiera minst en plats för en arbetspolicy i avsnittet **lagerplatser**. Du kan inte ange samma plats för flera arbetspolicyer.
> - Alternativet **Skriv ut etikett** för menyalternativ för lagring av mobila enheter kommer inte att skriva ut en ID-nummeretikett utan att skapa arbete.

Om du vill göra den här funktionen tillgänglig i systemet måste du aktivera funktionen för att *Förbättringar i Inleverans med ID-nummer* [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="receive-inventory-on-a-location-that-doesnt-track-license-plates"></a>Ta emot lager på en plats som inte spårar ID-nummer

Det går att använda ett lagerställe som är tilldelat till en platsprofil även om **Använd spårning av ID-nummer** inte är aktiverad. När du tar emot lager kan du därför direkt registrera lagerbehållningen på en plats utan att skapa arbete.

## <a name="add-mobile-device-menu-items-for-each-receiving-location-in-a-warehouse"></a>Lägg till menyartiklar för mobila enheter för varje mottagningsplats på ett lagerställe

Funktionen *Förbättringar i Inleverans med ID-nummer* gör att du kan ta emot alla platser i ett lagerställe genom att lägga till platsspecifik mottagning av menyartiklar för ID-nummer (och inlagrad) till modulen för lagerhantering. Tidigare har systemet endast tagit emot den standardplats som har definierats för varje lagerställe. Om den här funktionen är aktiverad innehåller menyalternativen för mobila enheter för mottagning av skyltar (och inlagrad) ger du alternativet **Använd standarddata**, vilket gör att du kan välja en anpassad "till"-plats för varje menyalternativ. (Det här alternativet är redan tillgängligt för andra typer av menyalternativ.)

Om du vill göra den här funktionen tillgänglig i systemet måste du aktivera funktionen för att *Förbättringar i Inleverans med ID-nummer* [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="show-or-skip-the-receiving-summary-page"></a>Visa eller hoppa över sidan för sammanfattning av inleveranser

Du kan använda funktionen *kontrollera om du vill visa en sida för sammanfattning av inleveranser* för att dra nytta av ett ytterligare detaljerat mobilappen för distributionslagerhantering som en del av inleveransprocessen av ID-numret.

När den här funktionen är aktiverad visas ett menyalternativ för mobila enheter för inleverans av ID-nummer eller inleverans av ID-nummer och artikelinförsel ger inställningen **sidan för sammanfattning av inleveranser**. Den här inställningen har följande alternativ:

- **Visa en detaljerad sammanfattning** – under inleverans av ID-nummer ser arbetarna en extra sida med den fullständiga ASN-informationen.
- **Hoppa över sammanfattningen** – arbetarna ser inte hela ASN-informationen. Lagerarbetarna inte heller ange en dispositionskod eller lägga till undantag under inleveransprocessen.

Om du vill göra den här funktionen tillgänglig i systemet måste du aktivera funktionen *kontrollera om du vill visa en sida för sammanfattning av inleveranser på mobila enheter* i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="prevent-transfer-ordershipped-license-plates-from-being-used-at-warehouses-other-than-the-destination-warehouse"></a>Förhindra överföringsorder – de levererade ID-numren används inte på andra lagerställen än lagerstället vid destinationen

En inleveransprocess av ID-nummer kan inte användas om ett ASN innehåller ett ID-nummer som redan finns och som har fysiska behållningsdata på ett annat lagerställe än det där registrering av ID-numret.

För scenarion för överföringsorder där transportlager inte spårar ID-nummer (och därför inte heller spårar fysisk lagerbehållning per ID-nummer) kan du använda funktionen *Förhindra överföringsorder för de levererade ID-numren att användas på andra lagerställen än lagerstället vid destinationen* för att förhindra att fysiska lageruppdateringar av ID-nummer som är under transport.

Om du vill göra den här funktionen tillgänglig på ditt system måste du aktivera funktionen *Förhindra överföringsorder för de levererade ID-numren att användas på andra lagerställen än lagerstället vid destinationen* i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Om du vill hantera funktionerna när den här funktionen är tillgänglig följer du stegen nedan.

1. Gå till **Lagerstyrning \> Inställningar \> Parametrar för lagerstyrning**.
1. På fliken **allmänt** i snabbfliken **ID-nummer** ställer du in fältet **ID-nummerpolicy för transitlager** till något av följande värden:

    - **Tillåt återanvändning av ej spårat ID-nummer** – systemet fungerar på samma sätt som när funktionen *Förhindra överföringsorder för de levererade ID-numren att användas på andra lagerställen än lagerstället vid destinationen* inte är tillgänglig. Det här värdet är standardinställningen när du först aktiverar funktionen.
    - **Förhindra återanvändning av ej spårat ID-nummer** – endast uppdateringar av lager som är relaterade till ett levererat ID-nummer är tillåtna vid lagerstället på destinationen tills överföringsordern har inlevererats.

## <a name="more-information"></a>Mer information

Mer information om menyartiklar för mobila enheter finns i [ställa in mobila enheter för lagerarbete](configure-mobile-devices-warehouse.md).

Mer information om produktionsscenariot *Rapportera som slutförd* se [Policyer för lagerarbete – översikt](warehouse-work-policies.md).

Mer information om inkommande belastningshantering finns i [Lagerhantering av inkommande laster för inköpsorder](inbound-load-handling.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]