---
title: Skriv ut på nytt och annullera påfyllnadsetiketter
description: I det här avsnittet beskrivs hur du makulerar och skriver ut om befintliga påfyllnadsetiketter.
author: GarmMSFT
manager: PJacobse
ms.date: 07/09/2020
ms.topic: reprint-and-void-wave-labels
ms.service: dynamics-ax-applications
ms.search.form: WHSWaveLabel, WHSWaveLabelTemplate, WHSWaveLabelLayoutRow, WHSWaveTableListPage, WHSWorkException, WHSMobileDisplayWaveLabelListLookup, WHSWaveLabelLayout, WHSWaveLabelType, WHSWaveLabelTemplateGroup
audience: Application User
ms.reviewer: PJacobse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-07-09
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: af92334af28824b3fcebde5f046bd7c6da459885
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016664"
---
# <a name="reprint-and-void-wave-labels"></a>Skriv ut på nytt och annullera påfyllnadsetiketter

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du hanterar etiketter som genereras med påfyllnadsbearbetning. (Detaljerad beskrivning och konfigurationsinstruktioner finns i [Konfigurera utskrift av påfyllnadsetikett](../warehousing/configure-wave-label-printing.md) .)

Du kan när som helst skriva ut påfyllnadsetiketterna igen. Du kan till exempel behöva skriva ut en enstaka etikett om en befintlig etikett har försvunnit eller skadats. Alternativt kan en lagerarbetare eller ansvarig behöva skriva ut en hel rulle med etiketter om antalet och/eller sammansättningen av en hel serie påfyllnadsetiketter har ändrats (t.ex. på grund av lagerbrist eller andra orsaker). Även om bara antalet kartonger har ändrats måste hela rullen skrivas ut igen för att behålla det totala antalet korrekt i avsnittet "kartong X av Y" i varje etikett.

Funktionen skriv ut påfyllnadsetiketter igen stöder följande funktioner:

- Skriv ut etiketterna på både lagerstället och den avancerade klienten.
- Annullera etiketter och skriv ut dem samtidigt igen. (Till exempel är möjligheten att annullera etiketter inbäddad i korta plockningsscenarier.)
- Rensa historik för påfyllnadsetikett.

I det här avsnittet finns en samling scenarier som kan visas, till exempel hur du arbetar med funktionen för att skriva ut påfyllnadsetiketter.

> [!IMPORTANT]
> Om du vill arbeta i de scenarier som presenteras i det här avsnittet måste du först aktivera och konfigurera de relevanta egenskaperna för påfyllnadsutskrift enligt beskrivningen i [Konfigurera utskrift av påfyllnadsetiketter](../warehousing/configure-wave-label-printing.md). Flera av scenarierna i det här avsnittet kräver också att du först arbetar igenom scenarierna i det avsnittet för att skapa nödvändiga exempeldata.

## <a name="scenario-1-reprint-labels-from-the-web-client"></a>Scenario 1: skriva ut etiketter från webbklienten

Du kan visa och skriva ut påfyllnadsetiketter på följande sidor. I åtgärdsfönstret, på varje sida, på fliken **Leveranser** , i gruppen **Relaterad information** , väljer du **påfyllnadsetiketter**.

- Alla leveranser \> leveransinformation
- Alla laster \> Läs in information
- Alla påfyllnader
- Påfyllnadsetiketter
- Etiketthistorik för påfyllnad

Om du vill skriva ut en påfyllnadsetikett från webbklienten följer du stegen nedan.

1. Gå till **lagerstyrning \> utgående påfyllningar \> leveranspåfyllningar \> alla påfyllningar**.
1. Välj den påfyllnad som du vill skriva ut etiketter från.
1. I Åtgärdsfönstret, på fliken **påfyllning** , i gruppen **skriv ut** , markerar du **påfyllnadsetiketter**.
1. Följ ett av eller båda stegen nedan:

    - För att skriva ut en etikett igen, välj en skrivare i fältet **Skrivarnamn**. (Lämna fältet tomt om du bara vill uppdatera detaljerna för påfyllnadsetiketter utan att skriva ut etiketten igen).
    - Markera kryssrutan **Uppdatera information om påfyllnadsetiketter**. (Låt kryssrutan vara avmarkerad om du bara vill skriva ut den föregående etiketten igen.)

    > [!NOTE]
    > Varje gång en påfyllnadsetikett skrivs ut eller skrivs ut igen konverteras dess data genom motsvarande påfyllnadsetikettens layout och alla platshållare ersätts med verkliga värden. Den resulterande strängen lagras som en post i påfyllnadsetikettens historik. Om kryssrutan **Uppdatera information om påfyllnadsetikett** är avmarkerad används det lagrade zebraprogrammeringspråket (ZPL) när en etikett ska skrivas ut igen. Om kryssrutan **Uppdatera information om påfyllnadsetikett** är markerad genereras en ny sträng. De befintliga påfyllnadsetiketterna räknas också om och eventuella överflödiga etiketter (t.ex. om de relaterade arbetsraderna har annullerats eller ändrats) markeras som **annullerade** och skrivs inte ut på nytt.

1. Välj **OK** för att bekräfta valet.

## <a name="scenario-2-reprint-labels-from-the-warehousing-app"></a>Scenario 2: skriva ut etiketter från lagerstyrningsappen

Detta scenario gäller normalt om en etikettrulle har försvunnit eller skadats. Det innehåller ett exempel som visar hur du konfigurerar menyalternativ för mobila enheter som gör att arbetstagarna kan skriva ut en och flera etiketter på en gång. Det visar sedan hur du använder de nya menyalternativen när du arbetar med en mobil enhet.

### <a name="set-up-the-required-menu-items-and-menu-for-the-mobile-device"></a>Konfigurera de menyalternativ och den meny som krävs för den mobila enheten

Innan arbetarna kan skriva ut etiketter på en mobil enhet måste du ställa in menyalternativ för att kunna använda den här funktionen och sedan lägga till dessa artiklar på menyn för lagerställeappen.

#### <a name="create-new-mobile-device-menu-items"></a>Skapa nya menyalternativ för mobila enheter

Följ dessa steg för att skapa en ny samling med menyalternativ för att skriva om etiketter från modulen för lagerstyrning.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Skapa ett menyalternativ och ange följande värden för det:

    - **Menyalternativnamn:** *Skriv ut en påfyllnadsetikett igen*
    - **Titel:** *Skriv ut en påfyllnadsetikett igen*
    - **Läge:** *Indirekt*
    - **Aktivitetskod:** *Skriv ut en påfyllnadsetikett igen*

1. Skapa ett andra menyalternativ och ange följande värden för det:

    - **Menyalternativnamn:** *Skriv ut etiketter (objekt)*
    - **Titel:** *Skriv ut en påfyllnadsetikett igen (artikel)*
    - **Läge:** *Indirekt*
    - **Aktivitetskod:** *Skriv ut flera påfyllnadsetiketter igen*
    - **Visa grupperingsalternativ för arbetslista:** *Ja*
    - **Fält för systemgruppering:** *leverans-ID*
    - **Etikett för systemgruppering:** *leverans-ID*
    - **Utskriftsläge:** *produkt*

1. I åtgärdsfönstret, välj **Fältlista** om du vill öppna en sida där du kan välja vilka fält som ska visas för att hjälpa arbetarna att identifiera rätt etikettrulle.
1. Du kan visa upp till sju fält. Använd listrutorna för att välja fältet som visas på varje tillgänglig befattning. Lämna alla fält som du inte behöver tomma. 

    Här är ett exempel:

    - **Displayfält:** *LabelItemId*
    - **Displayfält 2:** *LabelItemName*
    - **Displayfält 3:** *InventQty*
    - **Displayfält 4:** *LabelUnitId*

1. Stäng sidan.
1. Skapa ett tredje menyalternativ och ange följande värden för det:

    - **Menyalternativnamn:** *Skriv ut etiketter (uppräkning)*
    - **Titel:** *Skriv ut en påfyllnadsetikett igen (uppräkning)*
    - **Läge:** *Indirekt**
    - **Aktivitetskod:** *Skriv ut flera påfyllnadsetiketter igen*
    - **Visa grupperingsalternativ för arbetslista:** *Ja*
    - **Fält för systemgruppering:** *leverans-ID*
    - **Etikett för systemgruppering:** *leverans-ID*
    - **Utskriftsläge:** *uppräkning*

1. I åtgärdsrutan, välj **Fältlista** och använd sedan rullgardinslistorna för att välja de fält som ska visas för att hjälpa arbetare att identifiera rätt etikettrulle (till exempel *LabelItemId* , *LabelItemName* , *InventQty* , *LabelUnitId* och *NumberOfLabels* ).
1. Stäng sidan.
1. Skapa ett fjärde menyalternativ och ange följande värden för det:

    - **Menyalternativnamn:** *Skriv ut etiketter (efter sista)*
    - **Titel:** *Skriv ut en påfyllnadsetikett igen (efter sista)*
    - **Läge:** *Indirekt*
    - **Aktivitetskod:** *Skriv ut flera påfyllnadsetiketter igen*
    - **Visa grupperingsalternativ för arbetslista:** *Ja*
    - **Fält för systemgruppering:** *leverans-ID*
    - **Etikett för systemgruppering:** *leverans-ID*
    - **Utskriftsläge:** *senaste bra påfyllnadsetikett-ID*

1. I åtgärdsrutan, välj **Fältlista** och använd sedan rullgardinslistorna för att välja de fält som ska visas för att hjälpa arbetare att identifiera rätt etikettrulle (till exempel *LabelItemId* , *LabelItemName* , *InventQty* , *LabelUnitId* och *NumberOfLabels* ).
1. Stäng sidan.

#### <a name="set-up-the-mobile-device-menu"></a>Ställ in meny för mobila enheter

Följ dessa steg för att lägga till nya menyalternativ på menyn för lagerstyrningsapp.

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.
1. Välj en befintlig **utgående** meny.
1. Leta upp de objekt på utskriftsmenyn som du just skapade i listan till vänster och använd sedan högerpilen för att lägga till dem i listan till höger.
1. Stäng sidan.

### <a name="use-cases"></a>Användningsfall

I de användningsfall som anges här ges exempel som visar hur du använder de olika menyalternativen för mobila enheter som du har ställt in för att arbetare ska kunna skriva ut påfyllnadsetiketter på en gång.

Innan du börjar arbeta under dessa användningsfall måste följande förutsättningar vara på plats:

- Demonstrationsdata måste installeras och du måste välja den juridiska personen **USMF**.
- Utskrift av påfyllnadsetiketter måste konfigureras och en del etiketter måste genereras enligt beskrivningen i [Konfigurera utskrift av påfyllnadsetiketter](../warehousing/configure-wave-label-printing.md).

#### <a name="use-case-21-a-single-wave-label-is-scratched-and-must-be-reprinted"></a>Användnings fall 2.1: en påfyllnadsetikett är fristående och måste skrivas ut på nytt.

1. Logga in på lagerstyrningsappen en användare som har åtkomst till lagerställe *62*. (I standarddemodata kan du logga in med *62* som användar-ID och *1* som lösenord.)
1. Gå till **utgående \> skriv ut en påfyllnadsetikett igen**.
1. Ange eller sök igenom påfyllnadsetikett-ID.
1. Välj vilken skrivare som ska skrivas ut på igen.
1. Bekräfta åtgärden genom att välja **OK**.

#### <a name="use-case-22-several-labels-for-boxes-of-the-same-item-were-damaged-and-must-be-reprinted-each-label-has-a-product-bar-code-but-no-enumeration-or-sscc-number"></a>Användnings fall 2.2: flera etiketter för lådor med samma objekt har skadats och måste skrivas ut på igen. Varje etikett har en produktstreckkod, men ingen uppräknings- eller SSCC-nummer.

1. Logga in på lagerstyrningsappen en användare som har åtkomst till lagerställe *62*. (I standarddemodata kan du logga in med *62* som användar-ID och *1* som lösenord.)
1. Gå till **utgående \> skriv ut etiketter igen (artikel)**.
1. Ange eller sök igenom leverans-ID.
1. Välj den panel som har rätt etikettrulle att skriva ut på.
1. Skanna produktstreckkoden från en befintlig etikett för att bekräfta att rätt rad har valts.
1. Ange antalet etiketter som ska skrivas ut igen.
1. Välj vilken skrivare som ska skrivas ut på igen.
1. Bekräfta åtgärden genom att välja **OK**.

#### <a name="use-case-23-several-labels-for-boxes-werent-printed-because-of-a-printer-jam-because-the-labels-have-enumeration-you-can-define-the-carton-range-to-reprint"></a>Användningsfall 2.3: flera etiketter för lådor skrevs inte ut på grund av ett skrivarstopp. Eftersom etiketterna har uppräkning kan du definiera kartongen att skriva ut på en rad.

1. Logga in på lagerstyrningsappen en användare som har åtkomst till lagerställe *62*. (I standarddemodata kan du logga in med *62* som användar-ID och *1* som lösenord.)
1. Gå till **utgående \> skriv ut etiketter igen (uppräkning)**.
1. Ange eller sök igenom leverans-ID.
1. Välj den panel som har rätt etikettrulle att skriva ut på.
1. Ange den första lådan som du vill skriva ut en etikett för igen..
1. Ange den sista lådan som du vill skriva ut en etikett för igen.. Du kan också lämna det här fältet tomt om du vill skriva ut etiketter igen för alla lådor eller den angivna första lådan.
1. Välj vilken skrivare som ska skrivas ut på igen.
1. Bekräfta åtgärden genom att välja **OK**.

#### <a name="use-case-24-several-labels-for-boxes-werent-printed-because-of-a-printer-jam-the-last-good-label-has-a-wave-label-id-that-is-printed-as-a-bar-code"></a>Användningsfall 2.4: flera etiketter för lådor skrevs inte ut på grund av ett skrivarstopp. Den sista godkända etiketten har ett påfyllnadsetiketts-ID som skrivs ut som en streckkod.

1. Logga in på lagerstyrningsappen en användare som har åtkomst till lagerställe *62*. (I standarddemodata kan du logga in med *62* som användar-ID och *1* som lösenord.)
1. Gå till **utgående \> skriv ut etiketter igen (efter sista)**.
1. Ange eller sök igenom leverans-ID.
1. Välj den panel som har rätt etikettrulle att skriva ut på.
1. Ange eller skanna påfyllnadsetiketts-ID för den senaste bra påfyllnadsetiketten. Appen identifierar nästa etikett i sekvensen som den första lådan som en etikett skrivs ut för igen.
1. Ange den sista lådan som du vill skriva ut en etikett för igen.. Du kan också lämna det här fältet tomt om du vill skriva ut etiketter igen för alla lådor eller den angivna första lådan.
1. Välj vilken skrivare som ska skrivas ut på igen.
1. Bekräfta åtgärden genom att välja **OK**.

## <a name="scenario-3-short-pick-and-reprint"></a>Scenario 3: kortplockning och utskrift igen

Innan du börjar arbeta med detta scenario måste följande förutsättningar vara på plats:

- Demonstrationsdata måste installeras och du måste välja den juridiska personen **USMF**.
- Utskrift av påfyllnadsetiketter måste konfigureras och en del etiketter måste genereras enligt beskrivningen i [Konfigurera utskrift av påfyllnadsetiketter](../warehousing/configure-wave-label-printing.md).

### <a name="set-up-work-exceptions"></a>Konfigurera arbetsavvikelser

Arbetsundantag styr funktionen för kortplockning. Följ dessa steg för att skapa ett arbetsundantag.

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsundantag**.
1. Skapa en post med följande inställningar:

    - **Arbetsundantagskod:** *kortplockning och utskrift*
    - **Undantagstyp:** *kortplockning*
    - **Föreslå skriv ut påfyllnadsetiketter igen:** *Ja*

### <a name="void-and-reprint-after-a-short-pick"></a>Annullera och skriv ut igen efter en kortplockning

1. Logga in på lagerstyrningsappen en användare som har åtkomst till lagerställe *62*. (I standarddemodata kan du logga in med *62* som användar-ID och *1* som lösenord.)
1. Öppna ett arbetsbearbetningsflöde för arbetet med försäljningsorder som skapades när påfyllnadsetiketterna ursprungligen skrevs ut.
1. Välj **kortplockning**.
1. Välj den arbetsundantagskod som du har skapat för det här scenariot.
1. Om du har valt rätt undantag ska kryssrutan **annullera och skriv ut igen** vara tillgänglig. Markera rutan och bekräfta. När det är bekräftat räknas den serie som identifieras av fältet **etikettversions-ID** omberäknas baserat på den ändrade kvantiteten för arbetsraden. Sedan skrivs den om på den angivna skrivaren.
