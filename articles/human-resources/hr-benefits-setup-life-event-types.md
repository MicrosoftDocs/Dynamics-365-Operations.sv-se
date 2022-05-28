---
title: Konfigurera livshändelsetyper
description: Microsoft Dynamics 365 Human Resources använder livshändelsetyper för att definiera händelser i syfte att uppdatera medarbetarnas förmånsregistrering.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 64e536bad996e9a1948dad18437ec6f98ad27033
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691734"
---
# <a name="configure-life-event-types"></a>Konfigurera livshändelsetyper


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources använder **livshändelsetyper** för att definiera händelser där det är tillåtet att uppdatera medarbetarnas förmånsanmälan, exempelvis giftermål eller barnafödsel. Varje livshändelsetyp-ID kan bara associeras med en livshändelsetyp. Om du till exempel skapar ett **livshändelse-ID** som kallas **Adressändring** som är associerat med livshändelsetyp **Ändring av anställdas adress**, kan du inte skapa ett annat ID märkt **Medarbetaradressändring** och associera det med livshändelsetyp **Ändring av anställdas adress**. Om en livshändelsetyp inte är associerad med en plantyp utlöser inte livshändelsetypen någon livshändelse. Mer information finns i [Skapa plantyper](hr-benefits-setup-plan-types.md).

## <a name="create-a-life-event-type"></a>Skapa en livshändelsetyp

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **livshändelsetyper**.

2. Välj **Ny**.

3. Ange värden för de följande fälten:

   | Fält | Beskrivning |
   | --- | --- |
   | **ID för livshändelsetyp** | Unik identifierare för livshändelsen. |
   | **Beskrivning** | En beskrivning av livshändelsetypen. |
   | **Livshändelsetyp** | En katalysator för att uppdatera en medarbetares förmånsanmälan. En lista över livshändelser finns i [livshändelser](hr-benefits-setup-payment-frequencies.md?life-events) nedan. |

4. Välj **Spara**.

## <a name="view-attached-plans"></a>Visa kopplade planer

Du kan se en lista över planer som är kopplade till den valda **livshändelsetypen**. Livshändelser kopplas till en plantyp och plantyperna associeras med en plan.

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **livshändelsetyper**.

2. Välj **Åtgärder**.

3. Välj **kopplade planer**.

## <a name="life-events"></a>Livshändelser

Du kan välja mellan följande livshändelser när du skapar en livshändelsetyp:

| Livshändelse | Plats | Utlösare |
| --- | --- | --- |
| **Ändring av civilstånd** | **Arbetare > Profil > Personuppgifter > Civilstånd**| Ändring av civilstånd |
| **Ändring av anställningsstatus** |**Arbetare > Anställning > Sida för anställningshistorik** | Om du skapar en ny anställningsdetalj med en annan anställningsstatus för en medarbetare med en befintlig anställningsdetalj, utlöser detta en livshändelse.  En uppdatering av en befintlig anställningsdetalj med en annan anställningsstatus utlöser också en livshändelse.  |
| **Ändring av medarbetarens adress** |**Arbetare > Profil > Adresser**</li><li>**Arbetare > Personuppgifter > Personliga kontakter > Adress**</li></ul> | Ändring i adress. Adressen måste vara **Primär** för att utlösa en livshändelse. |
| **Ändring av beroende** |<br><ul><li>**Arbetare > Profil > Personuppgifter > Personliga kontakter**/li><li>**Självbetjäning för medarbetare**</li></ul> | Lägg till en personlig kontakt som anger att de är underlydande och definierar **Giltigt från**. Uppdatera en personlig kontakts underlydande **Giltigt till**-information. Den personliga kontaktrelationen måste vara underordnad, make/maka, sambo eller före detta make/maka.  |
| **Födelse eller adoption (underlydande)** |<br><ul><li>**Arbetare > Profil > Personuppgifter > Personliga kontakter**</li><li>**Självbetjäning för medarbetare > Redigera personliga uppgifter > Personliga kontakter**</li></ul>| **Födelsedatum** eller **Datum för adoption** läggs till eller uppdateras. Barnets **Födelsedatum** krävs. |
| **Förlust av omfattning (maka/make/partner)** | Arbetare > Profil > Personuppgifter > Personalkontakter > Underlydande information > Förlust av omfattning | **Förlust av omfattning** som valts för en personlig kontakt, tillsammans med **giltighetsdatum** |
| Ändring av partners anställning | **Medarbetare > Profil > Personuppgifter > Personliga kontakter > Underordnad information > Anställd** | Skapa en personlig kontakt och ange **Anställd** som **Ja**. Uppdatera en personlig kontakt och ändra **Anställd**.  |
| **Frånvaro (maka/make/partner)** | **Arbetare > Profil > Personuppgifter > Personalkontakter > Underlydande information > Frånvaro** | Personlig kontakt skapad och **Giltighetsdatum för tjänstledighet** definierat. Den personliga kontaktens **Tjänstledighet** uppdateras. Den personliga kontaktens **Giltighetsdatum för tjänstledighet** har uppdaterats.  |
| **Ändring av omfattning (befattning)** |<br><ul><li>**Arbetare > Befattningstilldelning > Befattningstilldelningar för medarbetare**</li><li>**Befattningar > Befattningar**</li></ul>| Ändra till befattningen i tilldelningsposterna för medarbetarbefattningen. Ändra medarbetartilldelning i befattningen. |
| **Ändring av täckning (lön)** |<br><ul><li>**Arbetare > Kompensation > Fast plan**</li><li>**Medarbetare > Personlig information > Årlig inkomst av förmåner**</li></ul>| Om **Förmånshantering > Gemensamma parametrar för Personal > Förmåner > Årlig inkomst av förmåner** inte har aktiverats kommer uppdatering av **Medarbetare > Kompensation > Fast plan** att skapa en livshändelse. Om **Förmånshantering > Gemensamma parametrar för Personal > Förmåner > Årlig inkomst av förmåner** har aktiverats kommer uppdatering av **Medarbetare > Personuppgifter > Årlig inkomst av förmåner** att skapa en livshändelse. |
| **Sjukvård (medarbetare/underlydande)** | **Arbetare > Profil > Personuppgifter > Personalkontakter > Underlydande information > Giltighetsdatum för sjukvård** | Om du lägger till eller uppdaterar datumet för **Giltighetsdatum för sjukvård** för en personlig kontakt skapas denna livshändelse. |
| **Stöd enligt domstolsbeslut** | **Arbetare > Profil > Personuppgifter > Personliga kontakter > Beroende > Stöd enligt domstolsbeslut** (QMSCO/QDRO) och giltighetsdatum | När en personlig kontakt skapas kommer en livshändelse att skapas om **Domstolsbeordrat stöd** är **Ja**. Uppdatering **Domstolsbeordrat stöd** eller **Domstolsbeordrat utgångsdatum** kommer också att utlösa en livshändelse. |
| **Avliden** | **Arbetare > Profil > Personuppgifter > Avliden den** | Ett **Datum för avliden** anges eller uppdateras. |
| **Försäkringsbevis** | **Arbetare > medarbetare > Versioner > Anställningshistorik > Datumhanterare > Förmånsdetaljer** | **Bevis på försäkringsbarhet** är inställt på **Ja**. **Ett bevis på verifieringsdatum för försäkringsbarhet** definieras. |
| **Mottagare** | **Arbetare > Profil > Personuppgifter > Personliga kontakter** | En personlig kontakt läggs till och fälten **Mottagare** och **Giltighetsdatum** fylls i. Den personliga kontakten måste vara av typen **Barn**, **Partner**, **Sambo**, **Syskon**, **Familjekontakt**, **Annan kontakt** eller **Förälder**. |
| **Sjukvård för medarbetare** | **Arbetare > medarbetare > Versioner > Anställningshistorik > Datumhanterare > Förmånsdetaljer** | **Sjukvårdsberättigad** anges som **Ja**. **Datum för sjukvårdsberättigande** har ändrats. |
| **Födelsedag** | **Förmånshantering > Bearbetning av livshändelseändring** | Dessa livshändelser skapas från **Ändringsbearbetning av livshändelse**. Processen analyserar vald period och juridisk person och hittar associerade medarbetare. Den beräknar deras senaste födelsedag och skapar en livshändelse för födelsedag om en inte redan har skapats. |
| **Ändring av medarbetarens berättigande (ej USA-specifik)** |<br><ul><li>**Arbetare > Anställning**</li><li>**Arbetare > medarbetare > Versioner > Anställningshistorik**</li></ul>| Skapar en livshändelse när:<br><ul><li>Om du skapar en ny anställning, det finns en tidigare anställning och medarbetartypen ändras.</li><li>Om du skapar en ny anställningsdetalj, det finns en tidigare anställningsdetalj, och anställningstyp eller anställningskategori ändras.</li><li>En anställningspost och en annan medarbetartyp definieras.</li><li>Uppdatering av en anställningsdetaljpost och en annan anställningstyp eller kategori anges.</li></ul> |
| **Åsidosättande av nytt berättigande (inte USA-specifik)** | **Personal avancerade > Förmåner > Planer > Förmåner > Åsidosätt berättiganderegel** | Använda bearbetning av livshändelse<br>När du skapar en ny åsidosättning av förmånsplanens berättigande för en medarbetare utlöser du den här livshändelsen.<br>BenefitEligibilityRuleOverride.ValidFrom. |
| **Åsidosätt ändring av berättiganderegel (inte USA-specifik)** | **Personal avancerade > Förmåner > Planer > Förmåner > Åsidosätt berättiganderegel** | När **Giltig från** eller **Giltig till** uppdateras i en åsidosättning av förmånsplanens berättigande förmånsplan, utlöser detta livshändelsen. |
| **Åsidosätt utgång av berättiganderegel (inte USA-specifik)** | Förmånshantering > Bearbetning av livshändelseändring  | Dessa livshändelser skapas från **Ändringsbearbetning av livshändelse**. Processen analyserar vald period och juridisk person och hittar associerade åsidosättningnar av förmånsplanens berättigande. Den skapar livshändelser om åsidosättningarna har upphört att gälla. |
| **Ny förmånsplan (ej USA-specifik)** | **Personal avancerade > Förmåner > Planer > Förmåner > Ny** | Alternativ för berättigande läggs till i en aktuell plan. En ny plan med bifogade berättigandealternativ läggs till.</br></br>Personal ska köra bearbetning av berättigande för livshändelse i denna instans. |
| **Åsidosätt regeländring (inte USA-specifik)** | **Förmånshantering > Berättiganderegler** | Med hjälp av bearbetning av berättigande för livshändelse. Loggas när **BenefitEligibilityRule**-poster har fått följande värden ändrade: **UseEmplCategory**, **UseEmplStatus** eller **UseEmplType**. Uppdaterar endast transaktion för livshändelse som redan finns för en ändrad regel eller ett villkor för berättigande. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]
