---
title: Hantera affärspartnersanvändare på B2B-näthandelssajter
description: I detta ämne beskrivs hur administratörer kan lägga till, redigera och ta bort affärspartners på B2B-näthandelssajter.
author: josaw1
ms.date: 07/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 88f613be59a0c7b0d5efcdc0bef2c5a54506f9eb
ms.sourcegitcommit: 0c77dbb8547cd36fce3977ca9515fa1474efa77a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2021
ms.locfileid: "6655616"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites"></a>Hantera affärspartnersanvändare på B2B-näthandelssajter

[!include [banner](../../includes/banner.md)]

I detta ämne beskrivs hur administratörer kan lägga till, redigera och ta bort affärspartners på B2B-näthandelssajter.

B2B-näthandeswebbplatser kräver att organisationerna registrerar sig som affärspartners. När en organisation har skickat registreringsinformation till en B2B-näthandelssajt går den igenom en kvalifikationsprocess. Om organisationen har kvalificerats installeras den som affärspartner.

När en organisation har godkänts som affärspartner identifieras den organisationsanvändare som initierat begäran om att bli affärspartner som administratörsanvändare, och får då behörighet att registrera ytterligare behöriga användare av B2B-näthandelssajten. Dessa behöriga användare kan sedan göra beställningar å affärspartnerns vägnar.

## <a name="turn-on-the-b2b-e-commerce-capabilities-feature-in-commerce-headquarters"></a>Aktivera funktionen för b2B-näthandel i Commerce-administrationen

Med funktionen för B2B-näthandel i Commerce-administrationen kan organisationer registrera affärspartners och definiera administratörsanvändare. Med den här funktionen kan administratörer också skapa och hantera affärspartners och team, och tilldela dessa specifika roller. Slutligen blir det möjligt för affärspartner-användare att skapa ordermallar och använda befintliga order för att beställa om produkter.

Följ dessa steg om du vill aktivera funktionen för B2B-näthandel i Commerce-administrationen.

1. Gå till **Arbetsytor \> Funktionshantering**.
1. I fliken **Alla** filtrerar du fältet **Modul** genom att använda villkoret **Retail and Commerce**.
1. Sök efter och markera funktionen **Aktivera användning av B2B-funktioner för näthandel** och välj sedan **Aktivera nu**.

## <a name="create-a-number-sequence-and-add-it-to-commerce-shared-parameters"></a>Skapa en nummerserie och lägga till den i gemensamma parametrar för handel

Nummerserier används för att generera läsliga unika identifierare för huvuddataposter och transaktionsposter och som kräver identifierare. Mer information om nummerserier, se [Översikt över nummerserier](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).

Om du vill skapa en nummerserie och lägga till den i gemensamma parametrar för Commerce i Commerce-administrationen följer du dessa steg.

1. Gå till **Retail and Commerce \> Administrationsinställningar \> Nummerserier \> Nummerserier** och skapar sedan en nummerserie.
1. Gå till **Retail and Commerce \> Administrationsinställningar \> Parametrar \> Delade parametrar för handel** och lägger till den nya nummerserien i referensen **ID för kundhierarki**.

## <a name="set-up-the-administrator-user-for-a-new-business-partner"></a>Ställ in administratörsanvändare för en ny affärspartner

Potentiella affärspartner kan initiera registreringsprocessen till en B2B-näthandelssajt genom att skicka in registreringsbegäran via en länk på webbplatsen. När en potentiell affärspartner väljer länken kan han eller hon ange de uppgifter som krävs för att registrera sig. När en begäran har skickats visas en bekräftelsesida. Om sändningen godkänns blir begäranden (d.v.s. användaren som initierade registreringsbegäran) affärspartnerns administratörsanvändare.

Om du vill godkänna och ställa in en administratörsanvändare för en affärspartner i Commerce-administreringen följer du dessa steg.

1. Gå till **IT för Retail and Commerce \> Distributionsschema**.
1. Kör jobbet **P-0001** om du vill hämta alla begäranden om affärspartnerregistrering i Commerce-administreringen.
1. När **P-0001**-jobbet har körts går du till **IT för Retail and Commerce \> Kund** och kör jobbet **Synkronisera kunder och affärspartner från asynkront läge**. När det här jobbet har körts skapas de inbyggda förfrågningarna som potentiella poster i Commerce-administrationen. Fältet **Typ-ID** för dessa poster ställs in som **Potentiell B2B-kund**.
1. Gå till **Kunder \> Alla potentiella** och öppna sidan för potentiella kunder.
1. Välj posten för potentiell kund för den nya affärspartnern om du vill öppna detaljsidan för potentiell kund.
1. På fliken **Allmänt** väljer du **Konvertera \> Godkänn/Avvisa** om du vill godkänna eller avvisa registreringsbegäran. När ett bekräftelsemeddelande visas bekräftar du att du vill fortsätta med processen samt godkänner begäran. Ett e-postmeddelande skickas sedan till den begärandes e-postadress för att bekräfta att deras organisation har godkänts som affärspartner.

    När du har godkänt ansökan får fältet **Status** för potentiell kund statusen **Godkänd**. Två nya kundposter skapas dessutom i systemet: en kundpost av **typen Organisation** för affärspartnerorganisationen, samt en kundpost av **typen Person** för begäranden. En kundhierarkipost för affärspartnern skapas också. <!--(Please refer to the Org modeling of B2B customer section in this document for more information)-->

1. Gå till **IT för Retail and Commerce \> Distributionsschema** och kör jobbet **1010** (**Kunder**) för att förflytta de nya kund- och kundhierarkiposterna till kanaldatabasen.

När en begäran har godkänts och kund- och kundhierarkiposterna har synkroniserats med kanaldatabasen kan begäranden logga in på B2B-näthandelssajten med den e-postadress som han eller hon angav när han/hon skickade begäran. Användarna kan använda inloggningsflödet för att definiera lösenordet för sitt konto. Om du vill aktivera identitetsprovider (Azure AD B2C) post som ska länkas till B2B-kundposten som skapades vid registrering eller inloggning, följ instruktionerna i [Aktivera automatisk länkning av identitetsposter till kundkonton](../identity-record-linking.md).

## <a name="onboard-additional-business-partner-users"></a>Registrera fler affärspartneranvändare

Administratören för affärspartneranvändare kan registrera ytterligare affärspartneranvändare till B2B-näthandelssajten efter behov.

Följ de här stegen om du vill registrera fler affärspartneranvändare till en B2B-näthandelssajt.

1. Logga in som administratör på B2B-näthandelssajten.
1. Gå till **Mitt konto \> Organisationsanvändare \> Visa information** och välj **Lägg till en användare**.
1. Ange erforderlig information som behövs och välj sedan **Spara**. Statusen för den nye användaren blir **Väntande**.

    När jobben **P-0001** och **Synkronisera kunder och affärspartners från asynkront läge** körs, kommer en kundpost av typen **Persontyp** att skapas i Commerce-administrationen. Denna kundpost associeras även med den relevanta affärspartnerns kundhierarkipost. Dessutom skickas ett e-postmeddelande till den nya användarens e-postadress, där denne meddelas att han/hon har lagts till som användare i affärspartnerorganisationen och nu kan logga in på B2B-näthandelssajten.

1. Kör jobbey **1010** (**Kunder**) om du vill synkronisera den nye affärspartneranvändaren med kanaldatabasen.

När kundposten synkroniseras får statusvärdet för användaren på B2B-näthandelssajten värdet **Aktiv**, och den nye användaren kan sedan logga in på B2B-näthandelssajten med sin e-postadress. Användarna kan använda inloggningsflödet för att definiera lösenordet för sitt konto. Om du vill aktivera identitetsprovider (Azure AD B2C) post som ska länkas till B2B-kundposten som skapades vid registrering eller inloggning, följ instruktionerna i [Aktivera automatisk länkning av identitetsposter till kundkonton](../identity-record-linking.md).

## <a name="edit-business-partner-user-details"></a>Redigera användarinformation för affärspartner

Om du vill redigera information om affärspartnersanvändare följer du dessa steg.

1. Logga in som administratör på B2B-näthandelssajten.
1. Gå till **Mina konton \> Organisationsanvändare \> Visa information**, välj knappen **Redigera** (pennsymbol), utför erforderliga ändringar och välj sedan **Spare**. Ändringarna aktiveras först när jobben **P-0001**, **Synkronisera kunder och affärspartner från asynkront läge** och **1010** (**Kunder**) har körts.

## <a name="remove-a-business-partner-user"></a>Ta bort en affärspartneranvändare

En administratör kan vid behov ta bort befintliga användare från en affärspartnerorganisation från listan över användare som har åtkomst till B2B-näthandelssajten.

Följ de här stegen om du vill ta bort en affärspartnersanvändare.

1. Logga in som administratör på B2B-näthandelssajten.
1. Gå till **Mitt konto \> Organisationsanvändare \> Visa information** och välj knappen **Ta bort** ("X-symbol"). När ett bekräftelsemeddelande visas bekräftar du att du vill ta bort användaren. Ändringen aktiveras först när jobben **P-0001**, **Synkronisera kunder och affärspartner från asynkront läge** och **1010** (**Kunder**) har körts.

> [!NOTE]
> När du tar bort en användare från listan över användare som har åtkomst till B2B-näthandelssajten, tas motsvarande kundpost bort från affärspartnerns kundhierarkipost. Kundposten själv kommer dock inte att tas bort från Commerce-administrationen.

## <a name="onboard-business-partner-and-users-in-commerce-headquarters"></a>Registrera affärspartner och användare i Commerce-administrationen

Administratörer kan registrera affärspartners och användare direkt i Commerce-administrationen.

Följ dessa steg om du vill registrera affärspartner och användare i Commerce-administrationen.

1. Skapa en kundpost av **typen Organisation** för affärspartnerorganisationen.
1. Skapa kundposter av **typen Person** för affärspartneranvändare. Se till att en primär e-postadress anges för respektive kund.
1. För respektive kundpost av **typen Person** som måste betecknas som en administratörsanvändare för affärspartnerorganisationen anger du, på snabbfliken **Butik**, alternativet **B2B-administratör** som **Ja**.
1. Skapa ett kundhierarki-ID. Ange sedan ett namn i fältet **Namn**.
1. I fältet **Organisation** anger du kunden för affärspartnerorganisationen.
1. Välj **Lägg till** och sedan en kund i fältet **Namn**.
1. Upprepa den här processen om du vill lägga till fler kunder i hierarkin.

## <a name="additional-information"></a>Ytterligare information

- Alla jobb som nämns i detta ämne kan konfigureras till att köras enligt ett schema i ett batchformat. Affärspartners förväntas konfigurera batchjobb vid behov.
- För närvarande kan endast en användare/kundpost väljas som administratörsanvändare, och den rollen kan bara ändras i Commerce-administrationen. Det finns inget stöd för självbetjäningsfunktioner som gör att affärspartners kan utse flera administratörer eller byta administratörer från B2B-näthandelssajter.
<!--- The modules and labels of the different fields referenced in the screenshots for e-commerce are only for illustration purposes. Customers have complete control on the placement of the B2B related modules and the labels.-->
- Även om utgiftsgränser kan definieras för användare har tvingande utgiftsgränser under orderpostprocessen ännu inte implementerats.
- All affärslogik och validering för en användares upplevelse på en B2B-näthandelssajt baseras på konfigurationen av den kundpost som mappas till användaren i Commerce-administrationen.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera en B2B-näthandelssajt](set-up-b2b-site.md)

[Skapa org-modellhierarkier för B2B-organisationer](org-model.md)

[Konfigurera betalsätt för kundkonto för B2B-näthandelssajter](payment-method.md)

[Ange produktkvantitetsgränser för B2B-näthandelssajter](quantity-limits.md)

[Nummerserier – översikt](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
