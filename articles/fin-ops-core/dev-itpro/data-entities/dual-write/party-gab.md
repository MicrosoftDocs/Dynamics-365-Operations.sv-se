---
title: Part och global adressbok
description: I det här avsnittet beskrivs funktionerna för part och global adressbok för dubbelriktad skrivning.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
ms.service: dynamics-ax-applications
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: e7bec58f8094a1448017822e7d8840368cc482b8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750798"
---
# <a name="party-and-global-address-book"></a>Part och global adressbok

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Part och global adressbok är koncept i Finance and Operations-appar. En part kan vara en organisation eller en person. Det är praktiskt att globalt lagra och hantera egenskaper för en **part**, som namn, språk, kontakter och adresser. När ett egenskapsvärde ändras på ett ställe återspeglar det på alla ställen där **parten** är involverad.

## <a name="party"></a>Part

En *part* är en person eller en organisation som arbetar i företaget. Genom att använda part-begreppet kan en person eller en organisation ha mer än en roll (arbetare, kund, leverantör eller kontakt) i en verksamhet. Rollen baseras på sammanhanget och syftet. Här följer några exempel från två fiktiva företag, Contoso och Fabrikam.

+ **Arbetare**: En medarbetare. Till exempel en medarbetare som är Contoso.
+ **Leverantör**: en leverantörs organisation, eller en enskild person som levererar varor eller tjänster till ett företag. Om Till exempel Fabrikam säljer varor till Contoso har Fabrikam rollen leverantör.
+ **Kontakt**: En person som ska kontaktas. Om Contoso till exempel köper varor från Fabrikam kan en medarbetare på Contoso kontakta kontakten på Fabrikam.
+ **Kund**: En kund är en person eller ett företag som köper saker från ett företag. Om Contoso till exempel köper varor från Fabrikam är Contoso Fabrikams kund.

Part-modellen används ofta för att representera medel till komplexa relationer mellan organisationer och personer, särskilt när en part arbetar med fler än en roll. Nedan följer några vanliga exempel:

+ En part kan vara både kund och leverantör. I till exempel Nordamerika säljer Fabrikam matvaror till Contoso och köper monterade högtalare från Contoso. I Europa säljer Fabrikam delar till Contoso, men inte med något från Contoso.
+ En part kan vara både en anställd och en kund. En medarbetare på Contoso köper till exempel elektronik från Contoso för eget bruk.
+ Det kan finnas ett flera till många-förhållande mellan en person och en organisation. Fabrikam tillhandahåller till exempel en tjänst som är ansvarig för anställning och tillämpar en placeringskoordinator. Koordinatorn matchar tjänsten för arbetsförfrågningar från flera av Fabrikams kunder. Contoso är ett av kundkontona. När Contoso behöver en kontakt kontaktar Contoso koordinatorn, som sedan underlättar förfrågningen. Koordinatorn hanterar förfrågningar för alla kunder och skapar en flera till många-relation.

Följande bild visar datamodellen för den part:

![Datamodell för parten](media/party-gab-image1.png)

> [!Tip]
> När du försöker skapa en ny kontopost använder du fältet "Part" för att söka efter posten med hjälp av namnet. Om du hittar posten behöver du bara markera posten. Systemet fyller automatiskt i alla data från den parten. Du behöver inte ange alla fält som behövs manuellt. Det här beteendet kan du hitta på konto-, kontakt- och leverantörsformulär som levereras från början.

Alla partroller för Finance and Operations-appar stöds inte av dubbelriktad skrivning. En fullständig lista över partroller finns i [översikten över den globala adressboken](../../../fin-ops/organization-administration/overview-global-address-book.md).

### <a name="global-address-book"></a>Global adressbok

Den globala adressboken är en katalog med postnummer och elektroniska adresser till organisationer och personer som ingår i ett företag.

De globala adressböckerna lagrar och hanterar så många postadresser och elektroniska adresser som behövs. Anta till exempel att Fabrikam har 50 platser. Varje plats har olika postadress, e-postadress och telefonnummer. Alla affärsinköp faktureras på huvudfakturan, men inköpen levereras direkt till den specifika växel som begärt inköpet. Den globala adressboken lagrar huvudadressen som faktureringsadress och varje adress som leveransadress för Fabrikam. Adresserna kan lagras en gång och hämtas efter behov för offerter och order.

En person eller en organisation kan spela mer än en roll baserat på affärssammanhanget. När de gör det kan deras postadresser och elektroniska adresser vara samma. I det här fallet ska en adressändring i en roll visas på den andra rollen och tvärtom. De globala adressboksbutikerna och hanterar adresser globalt.

![Datamodell för global adressbok](media/party-gab-image2.png)

## <a name="contacts"></a>Kontakter

I kundengagemangsappar är *Kontakt* en person. Emellertid har tabellen **Kontakt** överbelastats för att representera en person, en portalanvändare, en B2C-kund eller en leverantör. Representationen är en bra representation, och du kan inte skilja på det utan att undersöka relaterade transaktioner. Tabellen **Kontakt** har begränsats till att ha en 1:1 relation med tabellen **Konto**. Som en del av parten och den globala adressboksmodellen introducerar dubbelsidig skrivning introducerar uttryckliga egenskaper för klassificering och dubbelsidig skrivning tillåter N: N-förhållanden mellan **Kontakt** person och en organisation (kontoenhet eller leverantörsenhet).

Det finns två typer av rader för **Kontakt**::

+ Sorterad kontakt – Kontaktrad med ett obligatoriskt värde i fältet **Företag**.
+ Ej sorterad kontakt – Kontaktrad med tomt fält för **Företag**.

Tabellen **Kontakt** kan lagra följande typer av rader:

Radtyp | beskrivning
---|---
En person som är kund, t.ex. en säljbar kontakt eller B2C-kund. | En sorterad kontaktpost där fältet **Företag** är inte är tomt och fältet **Är kund** anges till **Ja**.
En person som till exempel är en leverantör, en enskild person som leverantör. | En sorterad kontaktpost där fältet **Företag** är inte är tomt och fältet **Är leverantör** anges till **Ja**.
En person som är både kund och leverantör. | En sorterad kontaktpost där fältet **Företag** är inte är tomt och fältet **Är kund** anges till **Ja** och fältet **Är leverantör** anges till **Ja**. En person kan vara både producent och kund för en annan produkt. Både Finance and Operations program och support för den här relationen.
En person som är kontaktperson för en organisation men inte är kund eller leverantör. | En ej sorterad kontaktpost där fältet **Företag** är inte är tomt och fältet **Är kund** anges till **Nej** och fältet **Är leverantör** anges till **Nej**.

## <a name="contact-for-party"></a>Kontakt för part

**Kontakt för part** lagrar och hanterar N:N-relationer mellan raderna **Konto** och **Kontakt**. Det kan filtrera den sorterade **Kontakt** från ej sorterade rader och endast associera de ej sorterade raderna **Kontakt** till raderna **Konto** eller **Leverantör**.

Till exempel är Natasha Jones och Miguel Reyes noga med att tillhandahålla vård inom deras områden. Natasha betjänar Seattle-området och Miguel betjänar Kent-området. I kundengagemangsapp representeras gårdarna som kunder och veterinärerna är kontaktpersoner. En enda post för **Kontakt** för Natasha är associerad med alla gårdar som Natasha arbetar med. På liknande sätt, en enda post för **Kontakt** för Miguel är associerad med alla gårdar som Miguel arbetar med.

Dessa relationer lagras i registret **Kontakt för part**. Informationen finns i de medföljande formulären:

+ När du arbetar i formuläret **Konto** finns en flik med namnet **Kopplade kontakter**. På den här fliken kan du koppla en eller flera kontakter till rad **Konto**. I det här formuläret tilldelar du en kontaktperson för en organisation. När du har tilldelar kontakter kan du välja en som primär kontaktperson för kontot. Med formuläret **Snabbskapa**, du kan bara välja en kontaktperson. Beteendet är detsamma när du använder **Leverantör** och posttypen är **Organisation**.
+ När du öppnar formuläret **Kontakt** och raden är en kund eller leverantör eller båda (en sorterad kontakt) finns det en flik med namnet **Kopplade kontakter**. På den här fliken kan du koppla en eller flera kontakter. I det här formuläret tilldelar du en kontaktperson för en B2C-kund eller leverantör. När du har tilldelar kontakter kan du välja en som primär kontakt. Med formuläret **Snabbskapa**, du kan bara välja en kontaktperson.
+ När du öppnar formuläret **Kontakt** och raden är en kontaktperson (en ej sorterad kontakt) finns det en flik med namnet **Kopplade organisationer**. På den här fliken kan du koppla en eller fler kunder eller leverantörer. På det här formuläret tilldelar du en kund eller leverantör till den underliggande kontaktpersonen. Kunden eller leverantören kan vara en organisation, en person eller båda. Du kan bara välja ett värde från de fyra fälten vid en given tidpunkt.

    ![Fliken Associerade organisationer](media/party-gab-image3.png)

    + Om du väljer **Part-ID** tilldelas den underliggande kontakten till alla roller för den valda parten.
    + Om du väljer **Associerad kontakt** väljer du den bandade kontakt som är av typen person.
    + Om du väljer **Kopplat konto** eller **Leverantör** väljer du en organisation.

    Oavsett ditt val skapas associationen på partnivå och gäller för samtliga roller för parten och lagras i entiteten "Kontakt för part".

> [!Note]
> Visningsnamnet för registret **Kontakt för part** i kundengagemangsapp är **Kontakt för kund/leverantör**. 

När du öppnar raden **Kontakt** där **Är kund** är **Nej** och **Är leverantör** är **Nej** kommer du att se fliken **Associerade organisationer**. Använd den här fliken för att associera en eller flera kund- eller leverantörsorganisationer till kontakten.

När du öppnar raden **Kontakt** där **Är kund** är **Ja** eller **Är leverantör** är **Ja** kommer du att se fliken **Associerade kontakter**. Använd den här fliken för att associera en eller flera kontakter.

## <a name="postal-address"></a>Postadress

En ny flik med namnet **Adresser** har introducerats i formulären **Konto**, **Kontakt** och **Leverantör**. **Adresserna** stöder N-adresser med hjälp av ett rutnät, på det sätt som visas i bilden:

![Rutnät för postadress](media/party-gab-image4.png)

+ Kolumnlistan **Postadressroller** visar syftet med adressen.
+ Kolumnen **Är primär** visar den primära adressen.
+ Kolumnen **Adressnummer** visar adressordern.
+ Med knappen **+ Nya adresser** låter du skapa en ny adress. Du kan skapa så många adresser som du vill.

Fälten **Adress 1** och **Adress 2** på fliken **Sammanfattning** i formuläret **Konto** motsvarar respektive adresserna **leverans** och **faktura**.

![Fliken Sammanfattning för postadressen](media/party-gab-image5.png)

Fälten **Adress 1**, **Adress 2** och **Adress 3** på fliken **Sammanfattning**, formuläret **Kontakt** motsvarar respektive adresserna **Företag**, **Leverans** och **Faktura**.

## <a name="electronic-address"></a>Elektronisk adress

En ny flik med namnet **Elektroniska adresser** har introducerats i formulären **Konto**, **Kontakt** och **Leverantör**. **Adresserna** stöder N-adresser med hjälp av ett rutnät, på det sätt som visas i bilden:

![Rutnät för elektroniska postadress](media/party-gab-image6.png)

+ Kolumnen **Typ** listar adressens typ.
+ Kolumnen **Är primär** visar den primära adressen.
+ Kolumnlistan **Syfte** visar syftet med den elektroniska adressen.
+ Med knappen **+ Nya elektroniska adresser** låter du skapa en ny adress. Du kan skapa så många adresser som du vill.

Elektroniska adresser är bara tillgängliga i det här rutnätet. I kommande versioner tas alla fält för elektroniska och postadresser bort från de andra flikarna, till exempel flikarna **Sammanfattning** och **Detaljer**.

## <a name="setup-instructions"></a>Installationsanvisningar

Om du redan är en sådan kund måste du ha följande inställningsinstruktioner. I annat fall kan du hoppa över det här avsnittet.

1. Stoppa följande kartor eftersom de inte krävs av dig. Kör i stället kartan Kontakter V2 (msdyn_contactforparties).

    + CDS Kontakter V2 och Kontakter (gäller kundkontakter)
    + CDS Kontakter V2 och Kontakter (gäller leverantörskontakter)

2. Följande enhetsmappningar uppdateras för partfunktionen, så den senaste versionen måste tillämpas på dessa mappningar.

Mappa | Uppdatera till den här versionen | Ändringar
---|---|---
Kunder V3 (konton) | 1.0.0.5 |Har tagit bort partsnumret och andra partrelaterade fält som namn, personliga uppgifter, postadresssfält, fält för elektronisk kontaktadress osv.
Kund V3 (kontakter) | 1.0.0.5 | Har tagit bort partsnumret och andra partrelaterade fält som namn, personliga uppgifter, postadresssfält, fält för elektronisk kontaktadress osv.
Leverantörer V2 (msdyn_vendors) | 1.0.0.6 | Har tagit bort partsnumret och andra partrelaterade fält som namn, personliga uppgifter, postadresssfält, fält för elektronisk kontaktadress osv.
CDS försäljningsofferrubrik (offerter) | 1.0.0.6 | Ersätt kontaktpersonen med ContactforParty-referens.
Försäljningsfakturahuvuden V2 (fakturor) | 1.0.0.4 | Ersätt kontaktpersonen med ContactforParty-referens.
CDS försäljningsorderrubriker (försäljningsorder) | 1.0.0.5 | Ersätt kontaktpersonen med ContactforParty-referens.
Kontakter V2 (msdyn_contactforparties) | 1.0.0.2 | Det här är en ny karta. Om du har en tidigare version av partlösningen måste du uppdatera den här kartan till den senaste versionen som nämns.
Postadressplatser för CDS-part (msdyn_partypostaladdresses) | 1.0.0.1  | Detta är en ny karta som läggs till i föregående parts förhandsgranskning.
CDS-postadress historik V2 (msdyn_postaladdresses) | | Detta är en ny karta som läggs till i föregående parts förhandsgranskning.
Postadressplatser för CDS (msdyn_postaladdresscollections) | | Detta är en ny karta som läggs till i föregående parts förhandsgranskning.
Partikontakter V3 (msdyn_partyelectronicaddresses) | | Detta är en ny karta som har lagts till som en del av den här utgåvan.

## <a name="templates"></a>Mallar

En samling tabellkartor fungerar tillsammans för interaktion mellan part och global adressbok, som visas i följande tabell.

Finance and Operations-app | Kundengagemangsapp     | beskrivning
----------------------------|-----------------------------|------------
[Kontaktpersonens titlar](mapping-reference.md#223) | msdyn_salescontactpersontitles |
[Kunder V3](mapping-reference.md#101) | konton |
[Kunder V3](mapping-reference.md#116) | kontakter |
[CDS-parter](mapping-reference.md#220) | msdyn_parties |
[Platser för CDS-partens postadress](mapping-reference.md#233) | msdyn_partypostaladdresses |
[Historik över postadressen för CDS V2](mapping-reference.md#235) | msdyn_postaladdresses |
[Platser för postadressen för CDS](mapping-reference.md#234) | msdyn_postaladdresscollections |
[CDS-försäljningsofferrubrik](mapping-reference.md#215) | anbudsförfrågningar |
[CDS-försäljningsorderrubrik](mapping-reference.md#217) | salesorders |
[Avslutningsfraser](mapping-reference.md#222) | msdyn_complimentaryclosings |
[Kontakter V2](mapping-reference.md#221) | msdyn_contactforparties |
[Roller för beslutsfattare](mapping-reference.md#224) | msdyn_decisionmakingroles |
[Anställningsfunktioner](mapping-reference.md#225) | msdyn_employmentjobfunctions |
[Lojalitetsnivåer](mapping-reference.md#226) | msdyn_loyaltylevels |
[Partkontakter V3](mapping-reference.md#236) | msdyn_partyelectronicaddresses |
[Typer av personliga egenskaper](mapping-reference.md#227) | msdyn_personalcharactertypes |
[Försäljningsfakturahuvuden V2](mapping-reference.md#118) | fakturor |
[Tilltal](mapping-reference.md#228) | msdyn_salutations |
[Leverantörer V2](mapping-reference.md#202) | msdyn_vendors |

Mer information finns i [Mappningsreferens för dubbel skrivning](mapping-reference.md).
