---
title: Hantera affärspartnersanvändare på B2B-näthandelssajter
description: I detta ämne beskrivs hur du lägger till, redigerar och tar bort affärspartners i Microsoft Dynamics 365 Commerce B2B-näthandelssajter och i Commerce.
author: josaw1
ms.date: 04/19/2022
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
ms.openlocfilehash: ef8ae583f18048fc6a36adf38ee7be0fb5b02fcd
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686334"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites"></a>Hantera affärspartnersanvändare på B2B-näthandelssajter

[!include [banner](../../includes/banner.md)]

I detta ämne beskrivs hur du lägger till, redigerar och tar bort affärspartners i Microsoft Dynamics 365 Commerce B2B-näthandelssajter och i Commerce.

> [!NOTE]
> - Ämnet [Hantera B2B affärspartners med hjälp av kundhierarkier](partners-customer-hierarchies.md) är en förutsättning för detta dokument.
> - Se till att du initierar dokumenttypsenheten i Commerce-administration genom att öppna **Dokumenttyper** formulär på **Organisationadministration \> Dokumenthantering \> Dokumenttyper**.

B2B-näthandeswebbplatser kräver att organisationerna registrerar sig som affärspartners. När en organisation har skickat registreringsinformation till en B2B-näthandelssajt, registreringsbegäran går den igenom en kvalifikationsprocess. Om organisationen har kvalificerats installeras den som affärspartner.

När en organisation har godkänts som affärspartner identifieras den organisationsanvändare som initierat begäran om att bli affärspartner som administratörsanvändare, och får då behörighet att registrera ytterligare behöriga användare av B2B-näthandelssajten. Dessa behöriga användare kan sedan göra beställningar å affärspartnerns vägnar.

## <a name="set-up-the-administrator-user-for-a-new-business-partner"></a>Ställ in administratörsanvändare för en ny affärspartner

Potentiella affärspartner kan initiera registreringsprocessen till en B2B-näthandelssajt genom att skicka in registreringsbegäran via en länk på B2B-webbplatsen. De kan sedan använda det anpassningsbara formuläret för att tillhandahålla de detaljer som krävs för introduktion och registrering. När en begäran har skickats visas en bekräftelsesida. Om inlämningen godkänns blir företaget som begäran skickades till affärspartner och begäranden (användaren som initierade introduktionsbegäran) blir administratörsanvändare för affärspartnern.

Följ dessa steg om du vill godkänna begäran om affärspartner i Commerce-administrationen.

1. Gå till **IT för Retail and Commerce \> Distributionsschema**.
1. Kör jobbet **P-0001** om du vill hämta alla begäranden om affärspartnerregistrering i Commerce-administreringen.
1. När **P-0001**-jobbet har körts går du till **IT för Butik och handel \> Kund** och kör jobbet **Synkronisera kunder och kanalbegäran**. När det här jobbet har körts skapas de inbyggda förfrågningarna som potentiella kunder i typen **B2B-potentiell kund** i Commerce-administrationen. 
1. Gå till **Kunder \> Alla potentiella kunder** och välj den nya affärspartnerns prospektpost för att öppna sidan för prospektinformation.
1. På fliken **Allmänt** väljer du **Konvertera \> Godkänn/Avvisa** om du vill godkänna registreringsbegäran. När ett bekräftelsemeddelande visas bekräftar du att du vill fortsätta med processen samt godkänner begäran. Godkännande ändrar fältet **Status** för potentiell kund anges till **Godkänd**. Ett e-postmeddelande skickas sedan till den begärandes e-postadress för att bekräfta att deras organisation har godkänts som affärspartner. En kundhierarki skapas också där begäraren läggs till som administratör för affärspartnern.

    > [!NOTE]
    > För närvarande skickas bekräftelsemeddelandet omedelbart vid godkännande. Framtida Commerce-funktionalitet kommer dock att låta administratören utlösa e-postmeddelanden manuellt.

1. Gå till **IT för Butik och handel \> Distributionsschema** och kör jobbet **1010 (Kunder)** för att förflytta de nya kund- och kundhierarkiposterna till kanaldatabasen.

> [!NOTE]
> Om du vill vara säker på att de nya kundposterna skickas till kanaldatabasen måste minst en av adressböckerna som associeras med kunden inkluderas i kundadressboken som är kopplad till onlinebutiken. Du kan automatisera den här processen genom att konfigurera adressboken som standardkund för onlinebutiken så att systemet kopierar adressboksvärdet till alla nya kunder.

Efter kundhierarkin synkroniseras poster till med kanaldatabasen kan begäranden logga in på B2B-näthandelssajten med den e-postadress som han eller hon angav när han/hon skickade begäran. Användarna kan använda inloggningsflödet för att definiera lösenordet för sitt konto. För information om hur du aktiverar Azure Active Directory (Azure AD) B2C-identitetsleverantörspost som ska kopplas till B2B-kundposten som skapades vid prospektgodkännande, se [Aktivera automatisk länkning](../identity-record-linking.md).

## <a name="notify-b2b-prospects-when-they-are-approved-or-rejected"></a>Meddela potentiella B2B-kunder när de godkänns eller avvisas

När du godkänner eller avvisar en begäran om registrering av potentiell B2B-kund, kan du automatiskt skicka ett e-postmeddelande till potentiell kund.

Om du vill ställa in e-postmeddelanden i Commerce-administration för händelser av typen **godkänd potentiell B2B-kund** eller **avvisad potentiell B2B-kund** följer du dessa steg.

1. Skapa e-postmallar för e-postmeddelanden som kommer att skickas till potentiella kunder när aviseringstypen **godkänd potentiell B2B-kund** eller **avvisad potentiell B2B-kund** utlöses.  För information om de platshållare som meddelandetyper stöder, se [Meddelandetyper](../email-templates-transactions.md#notification-types). Information om hur du skapar e-postmeddelanden finns i [Skapa ett postmeddelanden](../email-templates-transactions.md#create-an-email-template).
1. Lägg till meddelandetyper för **godkänd potentiell B2B-kund** och **avvisad potentiell B2B-kund** i e-postprofilen och mappa dem till de e-postmallar som du har skapat. Mer information om meddelandeprofiler finns i [Konfigurera profil för e-postmeddelande](../email-notification-profiles.md).

## <a name="onboard-additional-business-partner-users"></a>Registrera fler affärspartneranvändare

Administratören för affärspartneranvändare kan registrera ytterligare affärspartneranvändare till B2B-näthandelssajten efter behov.

Följ de här stegen om du vill registrera fler affärspartneranvändare till en B2B-näthandelssajt.

1. Logga in som administratör på B2B-näthandelssajten.
1. Gå till **Mitt konto \> Organisationsanvändare \> Visa information** och välj **Lägg till en användare**.
1. Ange erforderlig information som behövs och välj sedan **Spara**. Statusen för den nye användaren blir **Väntande**.

När jobben **P-0001** och **Synkronisera kunder och kanalbegäran** har körts kommer en kundpost av typen **Person** att skapas i Commerce-administrationen. Denna kundpost associeras även med den relevanta affärspartnerns kundhierarkipost. Dessutom skickas ett e-postmeddelande till den nya användarens e-postadress, där denne meddelas att han/hon har lagts till som användare i affärspartnerorganisationen och nu kan logga in på B2B-näthandelssajten.

Kör jobbet **1010 (Kunder)** om du vill synkronisera den nye affärspartneranvändaren med kanaldatabasen.

När kundposten synkroniseras får statusvärdet för användaren på B2B-näthandelssajten värdet **Aktiv**, och den nye användaren kan sedan logga in på B2B-näthandelssajten med sin e-postadress. Användarna kan använda inloggningsflödet för att definiera lösenordet för sitt konto. För information om hur du aktiverar Azure AD B2C-identitetsleverantörspost som ska kopplas till B2B-kundposten som skapades i Commerce-administration, se [Aktivera automatisk länkning](/dynamics365/commerce/identity-record-linking.md).

## <a name="edit-business-partner-user-details"></a>Redigera användarinformation för affärspartner

Om du vill redigera information om affärspartnersanvändare följer du dessa steg.

1. Logga in som administratör på B2B-näthandelssajten.
1. Gå till **Mina konton \> Organisationsanvändare \> Visa information**, välj knappen **Redigera** (pennsymbol), utför erforderliga ändringar och välj sedan **Spare**. Ändringarna aktiveras först när jobben **P-0001**, **Synkronisera kunder och kanalbegäran** och **1010 (Kunder)** har körts.

## <a name="remove-a-business-partner-user"></a>Ta bort en affärspartneranvändare

En administratör kan vid behov ta bort befintliga användare från en affärspartnerorganisation från listan över användare som har åtkomst till B2B-näthandelssajten.
Följ de här stegen om du vill ta bort en affärspartnersanvändare.
- Logga in som administratör på B2B-näthandelssajten.
- Gå till **Mitt konto > Organisationsanvändare \> Visa information** och välj knappen **Ta bort** ("X"-symbol). När ett bekräftelsemeddelande visas bekräftar du att du vill ta bort användaren. Ändringarna aktiveras först när jobben **P-0001**, **Synkronisera kunder och kanalbegäran** och **1010 (Kunder)** har körts.

> [!NOTE]
> När du tar bort en användare från listan över användare som har åtkomst till B2B-näthandelssajten, tas motsvarande kundpost bort från affärspartnerns kundhierarkipost. Kundposten själv kommer dock inte att tas bort från Commerce-administrationen.

## <a name="onboard-existing-customers-as-business-partners-on-the-b2b-e-commerce-website"></a>Integrera befintliga kunder som affärspartner på B2B-näthandelssajten

Administratörer kan registrera affärspartners och användare direkt i Commerce-administrationen. Den här kapaciteten kan användas för att registrera dina befintliga affärspartners på B2B-näthandelssajten.

Följ dessa steg om du vill registrera affärspartner och användare i Commerce-administrationen.

1. Skapa eller välj en kund av typen **Organisation** för att lägga till som affärspartner.
1. Skapa eller välj en kund av typen **Person** som du vill lägga till som administratör eller användare för affärspartnern. Se till att primära e-postadresser är kopplade till kunderna. Dessa e-postadresser används för att logga in på webbplatsen. 

    > [!NOTE]
    > Systemet måste kunna hitta en unik kundpost för användare som ska kunna logga in på webbplatsen. Om systemet hittar fler än en kund som har samma primära e-postadress hos den juridiska personen, kan användaren inte logga in på webbplatsen.

1. Skapa ett kundhierarki-ID.
1. Ange sedan ett namn i fältet **Namn**.
1. I fältet **Organisation** anger du kunden för affärspartnerorganisationen.
1. På snabbfliken **Hierarki** väljer du **Lägg till**.
1. I fältet **Namn** välj en kund från typen **Person**.
1. Välj rollen **Admin** för kunden som ska anges som administratör.
1. Upprepa den här processen om du vill lägga till fler kunder i hierarkin.

## <a name="additional-information"></a>Ytterligare information

- Alla jobb som nämns i detta ämne kan konfigureras till att köras enligt ett schema i ett batchformat. Affärspartners förväntas konfigurera batchjobb vid behov.
- För närvarande kan endast en användare/kundpost väljas som administratörsanvändare, och den rollen kan bara ändras i Commerce-administrationen. Det finns inget stöd för självbetjäningsfunktioner som gör att affärspartners kan utse flera administratörer eller byta administratörer från B2B-näthandelssajter.
- Även om utgiftsgränser kan definieras för användare har tvingande utgiftsgränser under orderpostprocessen ännu inte implementerats.
- All affärslogik och validering för en användares upplevelse på en B2B-näthandelssajt baseras på konfigurationen av den kundpost som mappas till användaren i Commerce-administrationen.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera en näthandelsplats för B2B](set-up-b2b-site.md)

[Hantera B2B-affärspartners med hjälp av kundhierarkier](partners-customer-hierarchies.md)

[Konfigurera betalsätt för kundkonto för B2B-näthandelssajter](payment-method.md)

[Ange produktkvantitetsgränser för B2B-näthandelssajter](quantity-limits.md)

[Nummerserier – översikt](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
