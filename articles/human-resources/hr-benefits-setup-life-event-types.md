---
title: Konfigurera livshändelsetyper
description: Microsoft Dynamics 365 Human Resources använder livshändelsetyper för att definiera händelser där det är tillåtet att uppdatera medarbetarnas förmånsanmälan.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart, BenefitLifeEventTypes
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c382299014e3f823bc2cd210749aae8c091c5f23
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114322"
---
# <a name="configure-life-event-types"></a>Konfigurera livshändelsetyper

Microsoft Dynamics 365 Human Resources använder livshändelsetyper för att definiera händelser där det är tillåtet att uppdatera medarbetarnas förmånsanmälan. Du kan till exempel gifta dig eller få barn. Varje livshändelsetyp-ID kan bara associeras med en livshändelsetyp. Om du till exempel skapar ett livshändelse-ID som kallas Adressändring som är associerat med livshändelsetyp Ändring av anställdas adress kan du inte skapa ett annat ID märkt Medarbetaradressändring och associera det med livshändelsetyp Ändring av anställdas adress. 

När du har skapat livhändelsetyper måste du koppla dem till plantyper. Mer information finns i [Skapa plantyper](hr-benefits-setup-plan-types.md).

   > [!NOTE]
   > När du har skapat en livhändelsetyper måste du koppla dem till plantyp. Mer information finns i [Skapa plantyper](hr-benefits-setup-life-event-types.md).

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

Du kan se en lista över planer som är kopplade till den valda livshändelsetypen. Livshändelser kopplas till en plantyp och plantyperna associeras med en plan. 

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **livshändelsetyper**.

2. Välj **Åtgärder**.

3. Välj **kopplade planer**.

## <a name="life-events"></a>Livshändelser

Du kan välja mellan följande livshändelser när du skapar en livshändelsetyp:

| Livshändelse | Plats | Utlösare |
| --- | --- | --- |
| **Ändring av civilstånd** | Arbetare > Profil > Personuppgifter > Civilstånd| Ändring av civilstånd |
| **Ändring av anställningsstatus** | <ul><li>Arbetare > Anställning</li><li>Sida för anställningshistorik</li></ul> | Ändring av anställningsstatus |
| **Ändring av medarbetarens adress** | <ul><li>Arbetare > Profil > Adresser </li><li>Arbetare > Personuppgifter > Personliga kontakter > Adress</li></ul> Tillagd, redigerad eller borttagen adress |
| **Ändring av beroende** | <ul><li>Arbetare > Profil > Personuppgifter > Personalkontakter > Lägga till eller ta bort en beroende</li><li>Självbetjäning för medarbetare</li></ul> | Tillagd eller borttagen beroende. Den personliga kontaktrelationen måste vara underordnad, make/maka, sambo eller före detta make/maka. Uppdatering av **giltigt från**-datum utlöser livshändelsen. Om du inte uppdaterar det datumet kommer ingen livshändelse att utlösas. |
| **Födelse eller adoption (beroende)** | <ul><li>Arbetare > Profil > Personuppgifter > Personalkontakter > Information om beroende</li><li>Självbetjäning för medarbetare</li></ul> | Fältet **Datum för adoption** ifyllt. Barnets födelsedatum krävs. |
| **Förlust av omfattning (maka/make/partner)** | Arbetare > Profil > Personuppgifter > Personalkontakter > Information om beroende > Förlust av omfattning | **Förlust av omfattning** som valts för en personlig kontakt, tillsammans med **giltighetsdatum** |
| Ändring av partners anställning | Arbetare > Profil > Personuppgifter > Personalkontakter > Information om beroende > Anställd. | <ul><li>Post för information för beroende skapad rutan **Personlig kontakt anställd** = Ja</li><li>Rutan **Personlig kontakt anställd** ändrades (Ja eller Nej)</li></ul> |
| **Frånvaro (maka/make/partner)** | Arbetare > Profil > Personuppgifter > Personalkontakter > Information om beroende > Frånvaro | <ul><li>Post för information om beroende har skapats och **EhrLOAEffectiveDate** har fyllts i.</li><li>**personPrivateDetails.EhrIsLOA** har ändrats (Ja eller Nej)</li><li>**personPrivateDetails.EhrLOAEffectiveDate** har ändrats</li></ul> |
| **Ändring av omfattning (befattning)** | <ul><li>Arbetare > Befattningstilldelning > Befattningstilldelningar för arbetare</li><li>Befattningar > Befattningar</li></ul> | <ul><li>Ändra till befattningen i tilldelningsposterna för arbetaren</li><li>Ändra arbetartilldelning i befattningen</li></ul> |
| **Sjukvård (medarbetare/beroende)** | Arbetare > Profil > Personuppgifter > Personalkontakter > Information om beroende > Giltighetsdatum för sjukvård | Utlöses inte automatiskt när en personlig kontakt inträder i ett giltighetsdatum. |
| **Stöd enligt domstolsbeslut** | Arbetare > Profil > Personuppgifter > Personliga kontakter > Beroende > Stöd enligt domstolsbeslut (QMSCO/QDRO) och giltighetsdatum | Automatiska uppdateringar utlöses inte. Det påverkar inte berättigande, det registrerar en livshändelse. |
| **Avliden** | Arbetare > Profil > Personuppgifter > Avliden den | Datum för avliden den anges |
| **Försäkringsbevis** | <ul><li>Arbetare > Arbetare > Versioner > Anställningshistorik > Datumhanterare > Förmånsdetaljer</li><li> Arbetare > Anställning > Förmånsinformation > Verifieringsdatum</li></ul> | <ul><li>En arbetare registrerar ett verifieringsdatum</li><li>En arbetare ställer in fältet EvidenceOfInsurability till **Ja**</li></ul> |
| **Mottagare** | Arbetare > Profil > Personuppgifter > Personliga kontakter | En personlig kontakt läggs till och rutan **Mottagare** och **Giltighetsdatum** fylls i. Den personliga kontakten måste vara av typen **Barn**, **Spouse**, **DomesticPartner**, **Syskon**, **FamilyContact**, **OtherContact**, **Förälder**, **BeneficiaryEstate**, **BeneficiaryOrg** eller **BeneficiaryTrust**. |
| **Sjukvård för medarbetare** | Arbetare > Arbetare > Versioner > Anställningshistorik > Datumhanterare > Förmånsdetaljer | <ul><li>**EhrMedicareEligibilityDate** har ändrats</li><li>**MedicareEligibile** har värdet **Ja**</li></ul> |
| **Födelsedag** | Arbetare > Profil > Personuppgifter > Personalkontakter > Information om beroende > Födelsedatum | Födelsedatum läggs till eller uppdateras (ej efter bearbetning av ändring i livshändelse). Exempel: om **Berättigandealternativ för personlig kontakt** för ett barn anges till ålder: 26 i Inställningar > Förmåner > Berättigandealternativ för personlig kontakt och om personalkörning av bearbetning av livshändelse varje dag efter det beroende fyller 26, visas ett meddelande som varnar dem om att beroende inte längre är berättigad till täckning. |
| **Ändring av arbetarens berättigande (ej USA-specifik)** | <ul><li>Arbetare > Anställning</li><li>Arbetare > Arbetare > Versioner > Anställningshistorik</li></ul> | <ul><li>Medarbetartyp, medarbetarkategori eller ändring av fem användardefinierbara berättigandefält</li><li>**HcmEmploymentDetail.EhrEmploymentType** ändringar (behandlas endast för *ändrade* anställningsdetaljposter, behandlas inte för *nya* anställningsposter som omanställningar och avslut)</li></ul> |
| **Åsidosättande av nytt berättigande (inte USA-specifik)** | Personal avancerade > Förmåner > Planer > Förmåner > Åsidosätt berättiganderegel | Använda bearbetning av livshändelse | EhrBenefitEligibilityRuleOverride.ValidFrom |
| **Åsidosätt ändring av berättiganderegel (inte USA-specifik)** | Personal avancerade > Förmåner > Planer > Förmåner > Åsidosätt berättiganderegel | Användning av bearbetning av livshändelse (fångar endast ändringar i fälten **ValidFrom** och **ValidTo** åsidosätt berättiganderegel) |
| **Åsidosätt utgång av berättiganderegel (inte USA-specifik)** | Personal avancerade > Förmåner > Planer > Förmåner > Åsidosätt berättiganderegel | Använda bearbetningar av ändring i livshändelse. Om du t.ex. redigerar en plans berättiganderegel, åsidosätt utgångsdatum till 17:00, valfri tid efter 17:00 eller följande dagar och sedan kör bearbetning av livshändelse vid ändring, visas ett meddelande om att åsidosättning av berättiganderegler har upphört att gälla. |
| **Ny förmånsplan (ej USA-specifik)** | Personal avancerade > Förmåner > Planer > Förmåner > Ny | <ul><li>Alternativ för berättigande läggs till i en aktuell plan</li><li>En ny plan med bifogade berättigandealternativ läggs till</li></ul></br></br>Personal ska köra bearbetning av berättigande för livshändelse i denna instans. |
| **Åsidosätt regeländring (inte USA-specifik)** | Personal avancerade > Förmåner > Regler/alternativ > Berättiganderegel | Med hjälp av bearbetning av berättigande för livshändelse. Loggas när **EhrBenefitEligibilityRule** poster har ändrats följande värden: **UseEmplCategory**, **UseEmplStatus** eller **UseEmplType**. Uppdaterar endast transaktion för livshändelse som redan finns för en ändrad regel eller ett villkor för berättigande. |


[!INCLUDE[footer-include](../includes/footer-banner.md)]