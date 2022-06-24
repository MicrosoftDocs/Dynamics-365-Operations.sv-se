---
title: Part och global adressbok
description: I den här artikeln beskrivs funktionerna för part och global adressbok för dubbelriktad skrivning.
author: RamaKrishnamoorthy
ms.date: 04/25/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: 91b56d091f549838092bdefe1a6a763fde79a32c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892205"
---
# <a name="party-and-global-address-book"></a>Part och global adressbok

[!include [banner](../../includes/banner.md)]



*Part* och *global adressbok* är koncept i appar för ekonomi och drift. En part kan vara en organisation eller en person. Det är praktiskt att globalt lagra och hantera egenskaper för en part, till exempel namn, språk, kontakter och adresser. När ett egenskapsvärde sedan ändras på ett ställe återspeglas ändringen på alla ställen där parten är involverad.

## <a name="party"></a>Part

En part är en person eller en organisation som är involverad i en verksamhet. När konceptet med parter används kan en person eller en organisation ha mer än en roll inom en verksamhet (till exempel medarbetare, kund, leverantör eller kontakt). Rollen baseras på sammanhanget och syftet. Här följer några exempel på roller från två fiktiva företag, Contoso och Fabrikam:

+ **Arbetare** – En medarbetare. Ett exempel är en medarbetare på Contoso.
+ **Leverantör** – en leverantörsorganisation eller en egenföretagare som levererar varor eller tjänster till ett företag. Om till exempel Fabrikam säljer varor till Contoso är Fabrikam en leverantör till Contoso.
+ **Kontakt** – En person som ska kontaktas. Om Contoso till exempel köper varor från Fabrikam kommer medarbetare på Contoso att kontakta kontakten på Fabrikam.
+ **Kund** – En kund är en person eller ett företag som köper saker från ett företag. Om Contoso till exempel köper varor från Fabrikam är Contoso Fabrikams kund.

Part-modellen används ofta för att representera medelkomplexa till komplexa relationer mellan organisationer och personer, i synnerhet när en part innehar mer än en roll. Nedan följer några vanliga exempel:

+ En part kan vara både kund och leverantör. I till exempel Nordamerika säljer Fabrikam enlektriska kablar till Contoso, samt köper monterade högtalare från Contoso. I Europa säljer Fabrikam delar till Contoso, men köper ingenting från Contoso.
+ En part kan vara både en anställd och en kund. En medarbetare på Contoso köper till exempel elektronik från Contoso för eget bruk.
+ Det kan finnas ett "flera-till-många"-förhållande (N:N) mellan en person och en organisation. Fabrikam tillhandahåller till exempel tjänstespecialister och anställer en placeringskoordinator. Placeringskoordinatorn matchar tjänstespecialisterna efter arbetsförfrågningar från flera av Fabrikams kunder. Contoso är en av Fabrikams kunder. När Contoso behöver en tjänstespecialist kontaktar man placeringskoordinatorn som sedan uppfyller begäran. Eftersom placeringskoordinatorn hanterar förfrågningar för alla kunder ingår en N:N-relation.

Följande illustration visar datamodellen för part.

![Datamodell för part.](media/party-gab-image1.png)

> [!TIP]
> När du försöker skapa en ny kontopost använder du fältet **Part** för att söka efter posten med hjälp av namnet. Om du hittar posten behöver du därför helt enkelt bara markera den. Systemet fyller sedan automatiskt i alla data från den parten. Du behöver inte ange alla fält som behövs manuellt. Detta beteende kan du hitta på de färdiga medföljande sidorna **Konto**, **Kontakt** och **Leverantör**.

Dubbelriktad skrivning stöder inte alla partroller i appar för ekonomi och drift. En fullständig lista över partroller finns i [översikten över den globala adressboken](../../../fin-ops/organization-administration/overview-global-address-book.md).

### <a name="global-address-book"></a>Global adressbok

Den globala adressboken är en katalog med postnummer och elektroniska adresser till organisationer och personer som deltar i en verksamhet.

Den globala adressboken lagrar och hanterar så många postadresser och elektroniska adresser som krävs. Fabrikam har exempelvis bensinmackar på 50 olika platser. Varje plats har olika postadress, e-postadress och telefonnummer. Alla affärsinköp faktureras till den primära bensinmacken men levereras direkt till den specifika bensinmack som begärt inköpet. Den globala adressboken lagrar huvudadressen som faktureringsadress för Fabrikam och lagrar respektive bensinmack som en enskild leveransadress. Adresserna kan lagras en gång och därefter hämtas efter behov för offerter och order.

Beroende på affärssammanhanget kan en person eller en organisation ha fler än en roll, och samma postadress och elektroniska adress kan användas för alla roller. I det här fallet ska en adressändring i en roll visas hos samtliga övriga roller. De globala adressboksbutikerna och hanterar adresser globalt.

Följande bild visar datamodellen för den globala adressboken.

![Datamodell för den globala adressboken.](media/party-gab-image2.png)

## <a name="contact"></a>Kontakt

I kundengagemangsprogram är en kontakt lika med en person. Emellertid har registret **Kontakt** överbelastats för att representera en person, en portalanvändare, en B2C-kund (business-to-consumer; företag-till-konsument) eller en leverantör. Representationen är implicit, och det går inte att se någon skillnad om man inte undersöker relaterade transaktioner. Registret **Kontakt** har begränsats till att ha en 1:1-relation med registret **Konto**. Som en del av parten och den globala adressboksmodellen introducerar dubbelsidig skrivning uttryckliga egenskaper för klassificering och tillåter N:N-förhållanden mellan en kontakt som är en person och en organisation (entiteten **Konto** eller **Leverantör**).

Det finns två typer av rader för **Kontakt**::

+ **Sorterad kontakt** – En **Kontakt**-rad där fältet **Företag** har ett obligatoriskt värde.
+ **Ej sorterad kontakt** – En **Kontakt**-rad där fältet **Företag** är tomt.

Registret **Kontakt** kan lagra följande radtyper:

| Radtyp | beskrivning |
|----------|-------------|
| En person som är kund (t.ex. en säljbar kontakt eller B2C-kund) | En sorterad kontaktpost där fältet **Företag** är inte är tomt och fältet **Är kund** anges som **Ja**. |
| En person som är leverantör (till exempel en enskild firma som är leverantör). | En sorterad kontaktpost där fältet **Företag** är inte är tomt och fältet **Är leverantör** anges som **Ja**. |
| En person som är både kund och leverantör | En sorterad kontaktpost där fältet **Företag** är inte är tomt och fältet **Är kund** anges som **Ja** och fältet **Är leverantör** anges som **Ja**. En person kan vara både producent och kund för en annan produkt. Både appar för ekonomi och drift och dubbelskrivning stöder denna relation. |
| En person som är kontaktperson för en organisation men inte är kund eller leverantör. | En ej sorterad kontaktpost där fältet **Företag** är tomt och fältet **Är kund** anges som **Nej** och fältet **Är leverantör** anges som **Nej**. |

## <a name="contact-for-party-table"></a>Kontakt för partregister

Registret **Kontakt för part** lagrar och hanterar N:N-relationer mellan raderna **Konto** och **Kontakt**. Det kan filtrera de sorterade **Kontakt**-raderna från ej sorterade rader och endast associera de icke-sorterade **Kontakt**-raderna med raderna för **Konto** eller **Leverantör**.

Till exempel är Natasha Jones och Miguel Reyes noga med att tillhandahålla vård inom deras områden. Natasha betjänar Seattle-området och Miguel betjänar Kent-området. I kundengagemangsappen representeras gårdarna som kunder och veterinärerna som kontaktpersoner. En enda post för **Kontakt** för Natasha är associerad med alla gårdar som Natasha arbetar med. På liknande sätt associeras en enskild **Kontakt**-post för Miguel med alla gårdar som Miguel arbetar med.

Dessa relationer lagras i registret **Kontakt för part**. Du hittar information om de färdiga **Konto**-, **Kontakt**- och **Leverantör**-sidorna:

+ På sidan **Konto** kan du använda fliken **Associerade kontakter** för att koppla en eller fler kontakter med raden **Konto**. På detta sätt tilldelar du kontaktpersoner för en organisation. Du kan sedan välja en kontakt som primär kontaktperson för kontot. Om du använder sidan **Snabbskapa** kan du bara välja en kontaktperson. Beteendet är detsamma när du använder sidan **Leverantör** och posttypen är **Organisation**.
+ Om raden är en kund, en leverantör eller båda (en sorterad kontakt) på sidan **Kontakt** kan du använda fliken **Associerade kontakter** för att koppla en eller flera kontakter. På detta sätt tilldelar du en kontaktperson för en B2C-kund eller leverantör. Du kan sedan välja en kontakt som primär kontaktperson. Om du använder sidan **Snabbskapa** kan du bara välja en kontaktperson.
+ Om raden är en kontaktperson (en osorterad kontakt) på sidan **Kontakt** kan du använda fliken **Associerade organisationer** för att koppla en eller flera kunder eller leverantörer. På så sätt tilldelar du kunder eller leverantörer till den underliggande kontaktpersonen. Kunden eller leverantören kan vara en organisation, en person eller båda. Du kan bara välja ett värde på ett av de fyra fälten vid en given tidpunkt:

    + Om du väljer ett värde i fältet **Part-ID** tilldelas den underliggande kontakten till alla roller för den valda parten.
    + Om du väljer ett värde i fältet **Associerad kontakt** väljer du den sorterade kontakten för typen **Person**.
    + Om du väljer ett värde i fältet **Associerat konto** eller **Associerad leverantör** väljer du en organisation.

    ![Fliken Associerade organisationer på kontaktsidan.](media/party-gab-image3.png)

    Oavsett val skapas associationen på partnivå, gäller för samtliga roller för parten och lagras i entiteten **Kontakt för part**.

> [!NOTE]
> Visningsnamnet för registret **Kontakt för part** i kundengagemangsprogrammen är **Kontakt för kund/leverantör**.

När du öppnar en **Kontakt**-rad där både fältet **Är kund** och **Är leverantör** angetts som **Nej** visas fliken **Associerade organisationer**. Använd den här fliken om du vill koppla en eller flera kund- eller leverantörsorganisationer till kontakten.

När du öppnar en **Kontakt**-rad där antingen fältet **Är kund** eller **Är leverantör** angetts som **Ja** visas fliken **Associerade kontakter**. På den här fliken kan du koppla en eller flera kontakter.

## <a name="postal-addresses"></a>Postadresser

En ny flik med namnet **Adresser** har introducerats på sidorna **Konto**, **Kontakt** och **Leverantör**. Denna flik har stöd för flera postadresser via ett rutnät, på det sätt som visas i illustrationen nedan.

![Rutnät för postadresser.](media/party-gab-image4.png)

Rutnätet innehåller följande kolumner:

+ **Roller för postadress** – Syftet med postadressen.
+ **Är primär** – Ett värde som anger om adressen är den primära adressen.
+ **Adressnummer** – Adressordern.

Du kan använda knappen **Ny adress** ovanför rutnätet för att skapa så många postadresser du vill.

Fälten **Adress 1** och **Adress 2** på fliken **Sammanfattning** på sidan **Konto** motsvarar adresserna **Leverans** respektive **Faktura**.

![Fliken Sammanfattning för postadresser.](media/party-gab-image5.png)

Fälten **Adress 1**, **Adress 2** och **Adress 3** på fliken **Sammanfattning** på sidan **Kontakt** motsvarar adresserna för **Företag**, **Leverans** respektive **Faktura**.

## <a name="electronic-addresses"></a>Elektroniska adresser

En ny flik med namnet **Elektroniska adresser** har introducerats på sidorna **Konto**, **Kontakt** och **Leverantör**. Denna flik har stöd för flera elektroniska adresser via ett rutnät på det sätt som visas i illustrationen nedan.

![Rutnät för elektroniska adresser.](media/party-gab-image6.png)

Rutnätet innehåller följande kolumner:

+ **Typ** – Typen av elektronisk adress.
+ **Är primär** – Ett värde som anger om adressen är den primära adressen.
+ **Syfte** – Syftet med den elektroniska adressen.

Du kan använda knappen **Ny elektronisk adress** ovanför rutnätet för att skapa så många postadresser du vill.

Under leadkvalificeringsprocessen kan du både ange ett företagtelefonnummer och ett mobiltelefonnummer. Företagstelefonnumret betraktas som primärt telefonnummer om **IsMobile=No**, och mobiltelefonnumret betraktas som sekundärt nummer om **IsMobile=Yes**.

> [!TIP]
> Använd flikarna **Adresser** och **Elektroniska adresser** i formulären **Konto** och **Kontakt** om du vill hantera postadresser och elektroniska adresser. På så sätt ser du till att adressdata synkroniseras till appar för ekonomi och drift.

## <a name="setup"></a>Konfigurera

1. Öppna din appmiljö för kundengagemang.

2. Installera alla nödvändiga lösningar, enligt beskrivningen i [Separat dubbelriktad skrivning programorkestrering-paket](separated-solutions.md).

3. Installera [lösningar för dubbelskrivningspart och global adressbok](https://aka.ms/dual-write-gab).

4. Öppna appen Ekonomi och drift. Navigera till modulen Datahantering och välj fliken dubbelskrivning. Administrationssidan för dubbelskrivning öppnas.

5. Använd båda lösningar som är installerade i steg 2 och 3 med hjälp av funktionen [Använd lösning](link-your-environment.md).

6. Stoppa följande kartor eftersom de inte krävs av dig. Kör istället `Contacts V2 (msdyn_contactforparties)`-kartan.

    + CDS Kontakter V2 och Kontakter (gäller kundkontakter)
    + CDS Kontakter V2 och Kontakter (gäller leverantörskontakter)

7. Följande enhetsmappningar uppdateras för partfunktionen, så den senaste versionen måste tillämpas på dessa mappningar.

    Mappa | Uppdatera till den här versionen | Ändringar
    ---|---|---
    `CDS Parties (msdyn_parties)`| 1.0.0.2 | Detta är en ny karta som har lagts till som en del av den här utgåvan.
    `Contacts V2 (msdyn_contactforparties)`| 1.0.0.6 | Detta är en ny karta som har lagts till som en del av den här utgåvan.
    `Customers V3 (accounts)` | 1.0.0.5 |Tog bort `PartyNumber` och andra partrelaterade fält som namn, personliga uppgifter, postadressfält samt elektronisk kontaktadress.
    `Customer V3 (contacts)` | 1.0.0.5 | Tog bort `PartyNumber` och andra partrelaterade fält som namn, personliga uppgifter, postadressfält samt elektronisk kontaktadress.
    `Vendors V2 (msdyn_vendors)` | 1.0.0.6 | Tog bort `PartyNumber` och andra partrelaterade fält som namn, personliga uppgifter, postadressfält samt elektronisk kontaktadress.
    `CDS Sales quotation headers (quotes)` | 1.0.0.7 | Ersatte kontaktpersonen med referensen `ContactforParty`.
    `Sales invoice headers V2 (invoices)` | 1.0.0.4 | Ersatte kontaktpersonen med referensen `ContactforParty`.
    `CDS Sales order headers (salesorders)` | 1.0.0.5 | Ersatte kontaktpersonen med referensen `ContactforParty`.
    `CDS Party postal address locations (msdyn_partypostaladdresses)` | 1.0.0.1  | Detta är en ny karta som har lagts till som en del av den här utgåvan.
    `CDS postal address history V2 (msdyn_postaladdresses)` | 1.0.0.2 | Detta är en ny karta som har lagts till som en del av den här utgåvan.
    `CDS postal address locations (msdyn_postaladdresscollections)` | 1.0.0.0 | Detta är en ny karta som har lagts till som en del av den här utgåvan.
    `Party Contacts V3 (msdyn_partyelectronicaddresses)` | 1.0.0.0 | Detta är en ny karta som har lagts till som en del av den här utgåvan.
    `Complimentary Closings (msdyn_compliemntaryclosings)` | 1.0.0.0 | Detta är en ny karta som har lagts till som en del av den här utgåvan.
    `Decision making roles (msdyn_decisionmakingroles)` | 1.0.0.0 | Detta är en ny karta som har lagts till som en del av den här utgåvan.
    `Loyalty levels (msdyn_loyaltylevels)` | 1.0.0.0 | Detta är en ny karta som har lagts till som en del av den här utgåvan.
    `Contact person titles (msdyn_salescontactpersontitles)` | 1.0.0.0 | Detta är en ny karta som har lagts till som en del av den här utgåvan.
    `Personal character types (msdyn_personalcharactertypes)` | 1.0.0.0 | Detta är en ny karta som har lagts till som en del av den här utgåvan.
    `Salutations (msdyn_salutations)` | 1.0.0.0 | Detta är en ny karta som har lagts till som en del av den här utgåvan.
    `Employment job functions (msdyn_employmentjobfunctions)` | 1.0.0.0 | Detta är en ny karta som har lagts till som en del av den här utgåvan.
    `CDS Address roles (msdyn_addressroles)` | 1.0.0.0 | Detta är en ny karta som har lagts till som en del av den här utgåvan.

8. Innan du kör kartorna ovan måste du uppdatera integreringsnycklarna manuellt enligt beskrivningen i följande steg. Välj sedan **Spara**.

    | Mappa | Nycklar |
    |-----|------|
    | Konto |  accountnumber [kontonummer]<br>msdyn_company.cdm_companycode [Företag (Företagskod)] |
    | Kontakt | msdyn_contactpersonid [kontonummer/ID för kontaktperson]<br>msdyn_company.cdm_companycode [Företag (Företagskod)] |
    | Kontakt för kund/leverantör | msdyn_contactforpartynumber [Kontakt för partsnummer]<br>msdyn_associatedcompanyid.cdm_companycode [associerat företag (företagskod)] |
    | Leverantör | msdyn_vendoraccountnumber [leverantörskontonummer]<br>msdyn_company.cdm_companycode [Företag (Företagskod)]|

9. I Dataverse har teckengränserna för dubblettidentifieringsregler ökat från 450 till 700 tecken. Med den här gränsen kan du lägga till en eller flera nycklar till dubblettidentifieringsreglerna. Expandera regeln för dubblettidentifiering för registret **Konton** genom att ställa in följande fält.

    | Fält | Värde |
    |-------|-------|
    | Namn | Konton med samma kontonamn. |
    | beskrivning | Identifierar kontoposter som har samma värde i attributet Kontonamn. |
    | Basposttyp | Konto |
    | Matchande posttyp | Konto |
    | Kontonamn (fält) | Exakt matchning |
    | Företag (fält) | Exakt matchning |
    | Relationstyp (fält) | Exakt matchning |
    | Part-ID (fält) | Exakt matchning |
    | Välj (fält) | (tomt) |

    ![Dubblettregel för konton.](media/duplicate-rule-1.PNG)

10. Expandera regeln för dubblettidentifiering för registret **Kontakter** genom att ställa in följande fält.

    | Fält | Värde |
    |-------|-------|
    | Namn | Kontakter med samma för- och efternamn. |
    | beskrivning | Identifierar kontaktposter som har samma värden i fälten För- och Efternamn. |
    | Basposttyp | Kontakt |
    | Matchande posttyp | Kontakt |
    | Förnamn (fält) | Exakt matchning |
    | Efternamn (fält) | Exakt matchning |
    | Företag (fält) | Exakt matchning |
    | Part-ID (fält) | Exakt matchning |
    | Välj (fält) | (tomt) |

    ![Dubblettregel för kontakter.](media/duplicate-rule-2.PNG)

11. Om du redan är en befintlig användare med dubbelriktad skrivning följer du instruktionerna i [Uppgradera till modellen för part och global adressbok](upgrade-party-gab.md) och uppgradera dina uppgifter. **Fortsätt inte till steg 12 utan att genomföra det här steget.** Om du är en ny användare av dubbelskrivning kan du gå vidare till steg 12.

12. Om du redan är en befintlig användare med dubbelskrivning slutför du steg 11 och kan sedan köra mappningarna i följande ordning. Om du är en ny kund med dubbelskrivning kan du fortsätta direkt. Om du får ett felmeddelande där det står "Projektvalideringen misslyckades. Målfält saknas..." öppnar du mappningen och väljer **Uppdatera register** innan du kör mappningen.

    Appar för ekonomi och drift | Kundengagemangsapp  
    ----------------------------|------------------------
    [CDS-parter](mapping-reference.md#220) | msdyn_parties
    [Platser för postadressen för CDS](mapping-reference.md#234) | msdyn_postaladdresscollections
    [Historik över postadressen för CDS V2](mapping-reference.md#235) | msdyn_postaladdresses
    [Platser för CDS-partens postadress](mapping-reference.md#233) | msdyn_partypostaladdresses
    [Partkontakter V3](mapping-reference.md#236) | msdyn_partyelectronicaddresses
    [Kunder V3](mapping-reference.md#101) | konton
    [Kunder V3](mapping-reference.md#116) | kontakter
    [Leverantörer V2](mapping-reference.md#202) | msdyn_vendors
    [Kontaktpersonens titlar](mapping-reference.md#223) | msdyn_salescontactpersontitles
    [Avslutningsfraser](mapping-reference.md#222) | msdyn_complimentaryclosings
    [Tilltal](mapping-reference.md#228) | msdyn_salutations
    [Roller för beslutsfattare](mapping-reference.md#224) | msdyn_decisionmakingroles
    [Anställningsfunktioner](mapping-reference.md#225) | msdyn_employmentjobfunctions
    [Lojalitetsnivåer](mapping-reference.md#226) | msdyn_loyaltylevels
    [Typer av personliga egenskaper](mapping-reference.md#227) | msdyn_personalcharactertypes
    [Kontakter V2](mapping-reference.md#221) | msdyn_contactforparties
    [CDS-försäljningsofferrubrik](mapping-reference.md#215) | anbudsförfrågningar
    [CDS-försäljningsorderrubrik](mapping-reference.md#217) | salesorders
    [Försäljningsfakturahuvuden V2](mapping-reference.md#118) | fakturor
    [CDS-adressroller](mapping-reference.md#301) | msdyn_addressroles

> [!NOTE]
> Kartan `CDS Contacts V2 (contacts)` är den karta som du stoppade i steg 1. När du försöker köra andra kartor visas dessa två kartor kanske i listan med underordnade kartor. Kör inte dessa kartor.
>
> Om parten och den globala adressboken är installerade måste du inaktivera plugin-programmet `Microsoft.Dynamics.SCMExtended.Plugins.Plugins.LeadPrimaryContactPostCreate: QualifyLead of lead`. Om du avinstallerar lösningen för part och global adressbok måste du återaktivera insticksprogrammet.
>
> Fältet `msdyn_*partynumber` (ett textfält med en enda rad) som ingår i registren **Konto**, **Kontakt** och **Leverantör** ska inte användas i fortsättningen. Etikettnamnet har prefixet **(inaktuell)** i förtydligande syfte. Använd istället fältet **msdyn_partyid**. Fältet är en sökning för registret **msdyn_party**.
>
> Registernamn | Gammalt fält | Nytt fält
> --------|-------|--------
> Konto | `msdyn_partynumber` | `msdyn_partyid`
> Kontakt | `msdyn_partynumber` | `msdyn_partyid`
> msdyn_vendor | `msdyn_vendorpartynumber` | `msdyn_partyid`

## <a name="templates"></a>Mallar

En samling tabellkartor fungerar tillsammans för interaktion mellan part och global adressbok, som visas i följande tabell.

| Appar för ekonomi och drift | Kundengagemangsapp | Beskrivning |
|----------------------------|-------------------------|-------------|
| [Kontaktpersonens titlar](mapping-reference.md#223) | msdyn\_salescontactpersontitles |
| [Kunder V3](mapping-reference.md#101) | konton |
| [Kunder V3](mapping-reference.md#116) | kontakter |
| [CDS-parter](mapping-reference.md#220) | msdyn\_parties |
| [Platser för CDS-partens postadress](mapping-reference.md#233) | msdyn\_partypostaladdresses |
| [Historik över postadressen för CDS V2](mapping-reference.md#235) | msdyn\_postaladdresses |
| [Platser för postadressen för CDS](mapping-reference.md#234) | msdyn\_postaladdresscollections |
| [CDS-försäljningsofferrubrik](mapping-reference.md#215) | anbudsförfrågningar |
| [CDS-försäljningsorderrubrik](mapping-reference.md#217) | salesorders |
| [Avslutningsfraser](mapping-reference.md#222) | msdyn\_complimentaryclosings |
| [Kontakter V2](mapping-reference.md#221) | msdyn\_contactforparties |
| [Roller för beslutsfattare](mapping-reference.md#224) | msdyn\_decisionmakingroles |
| [Anställningsfunktioner](mapping-reference.md#225) | msdyn\_employmentjobfunctions |
| [Lojalitetsnivåer](mapping-reference.md#226) | msdyn\_loyaltylevels |
| [Partkontakter V3](mapping-reference.md#236) | msdyn\_partyelectronicaddresses |
| [Typer av personliga egenskaper](mapping-reference.md#227) | msdyn\_personalcharactertypes |
| [Försäljningsfakturahuvuden V2](mapping-reference.md#118) | fakturor |
| [Tilltal](mapping-reference.md#228) | msdyn\_salutations |
| [Leverantörer V2](mapping-reference.md#202) | msdyn\_vendors |
| [CDS-adressroller](mapping-reference.md#301) |msdyn\_addressroles|

Mer information finns i [Mappningsreferens för dubbelskrivning](mapping-reference.md).

## <a name="address-roles-as-a-multi-select-drop-down-list"></a>Adressroller som en listrutan med flera urval
En postadress eller en elektronisk adress kan användas för mer än ett syfte. En postadress kan till exempel fungera som både faktureringsadress och leveransadress. I så fall kan användaren välja både **Faktura** och **Leverans** i listrutan, vilket visas i illustrationen nedan. 

![Listrutan Syfte/Roll.](media/purpose.png)

## <a name="known-issues-and-limitations"></a>Kända problem och begränsningar

+ När du skapar en kund tillsammans med en adress och sparar denna i appar för ekonomi och drift kanske adressen inte synkroniseras med registret **Adress**. Detta beror på ett ordningsföljdsproblem med plattformar med dubbelskrivning. Som en lösning måste du skapa kunden först och spara den. Lägg sedan till adressen.
+ När en kundpost har en primär adress i appar för ekonomi och drift och du skapar en ny kontakt för den kund ärver kontaktposten en primär adress från den associerade kundposten. Detta inträffar även för leverantörskontakt. Dataverse stöder för närvarande inte detta beteende. Om dubbelskrivning är aktiverad synkroniseras en kundkontakt som ärvs med en primär adress från appen för ekonomi och drift med Dataverse tillsammans med dess adress.
+ I appar för ekonomi och drift kan du skapa en kontaktpost från formuläret **Lägg till kontakt**. När du försöker skapa en ny kontakt från formuläret **Visa kontalt**, misslyckas åtgärden. Detta är ett känt problem.

    ![Känt problem med Lägg till kontakt.](media/party-gab-contact-issue.png)

+ **Initial synkronisering** stöder inte tidsfälten **Tillgänglig från** och **Tillgänglig till** i **ContactForParty**, detta eftersom DIXF omvandlar värdet till en heltalssträng. Konverteringen utlöser felet `Cannot convert the literal '<say 08:00:00>' to the expected type edm.int32`.
+ Du kan inte ange en framåtdaterad postadress med hjälp av en app för ekonomi och drift med dubbelskrivning, detta eftersom Dataverse inte stöder giltighetsdatum. Om du anger en framåtdaterad postadress med hjälp av en app för ekonomi och drift synkroniseras denna helt och hållet med Dataverse, och du får omedelbart se adressen i användargränssnittet. Eventuella uppdateringar av den här posten resulterar i ett fel eftersom den är daterad i framtiden och inte i nutid i appen för ekonomi och drift.
