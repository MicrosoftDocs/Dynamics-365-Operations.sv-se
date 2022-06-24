---
title: Person
description: Detta ämne beskriver entiteten Person för Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 49d9b5e1a1297c9528bfa82d0e8307bad3b2d1cc
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8864124"
---
# <a name="person"></a>Person


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver entiteten Person för Dynamics 365 Human Resources.

Fysiskt namn: mshr_dirpersonentity

### <a name="description"></a>beskrivning

Denna entitet tillhandahåller personlig information om den person som är kandidat.

## <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_partynumber": "String",
    "mshr_name": "String",
    "mshr_namealias": "String",
    "mshr_knownas": "String",
    "mshr_languageid": "String",
    "mshr_addressbooks": "String",
    "mshr_anniversaryday": Int,
    "mshr_anniversarymonth": Int,
    "mshr_anniversaryyear": Int,
    "mshr_birthday": Int,
    "mshr_birthmonth": Int,
    "mshr_birthyear": Int,
    "mshr_childrennames": "String",
    "mshr_gender": Int,
    "mshr_hobbies": "String",
    "mshr_initials": "String",
    "mshr_maritalstatus": Int,
    "mshr_phoneticfirstname": "String",
    "mshr_phoneticlastname": "String",
    "mshr_phoneticmiddlename": "String",
    "mshr_personalsuffix": "String",
    "mshr_personaltitle": "String",
    "mshr_professionalsuffix": "String",
    "mshr_professionaltitle": "String",
    "mshr_fullprimaryaddress": "String",
    "mshr_addresscity": "String",
    "mshr_addresscountryregionid": "String",
    "mshr_addresscountryregionisocode": "String",
    "mshr_addresscounty": "String",
    "mshr_addressdistrictname": "String",
    "mshr_addresslatitude": Decimal,
    "mshr_addresslocationid": "000003212",
    "mshr_addresslocationroles": "Home",
    "mshr_addresslongitude": Decimal,
    "mshr_addressstate": "String",
    "mshr_addressstreet": "String",
    "mshr_addressvalidfrom": "Date",
    "mshr_addressvalidto": "Date",
    "mshr_addresszipcode": "String",
    "mshr_addressisprivate": Int,
    "mshr_addressdescription": "String",
    "mshr_primarycontactemail": "String",
    "mshr_primarycontactemaildescription": "String",
    "mshr_primarycontactemailisim": Int,
    "mshr_primarycontactemailpurpose": "String",
    "mshr_primarycontactfax": "String",
    "mshr_primarycontactfaxdescription": "String",
    "mshr_primarycontactfaxextension": "String",
    "mshr_primarycontactfaxpurpose": "String",
    "mshr_primarycontactphone": "String",
    "mshr_primarycontactphonedescription": "String",
    "mshr_primarycontactphoneextension": "String",
    "mshr_primarycontactphoneismobile": Int,
    "mshr_primarycontactphonepurpose": "String",
    "mshr_primarycontacttelex": "String",
    "mshr_primarycontacttelexdescription": "String",
    "mshr_primarycontacttelexpurpose": "String",
    "mshr_primarycontacturl": "String",
    "mshr_primarycontacturldescription": "String",
    "mshr_primarycontacturlpurpose": "String",
    "mshr_primarycontactfacebook": "String",
    "mshr_primarycontactfacebookdescription": "String",
    "mshr_primarycontactfacebookisprivate": Int,
    "mshr_primarycontactfacebookpurpose": "String",
    "mshr_primarycontactlinkedin": "String",
    "mshr_primarycontactlinkedindescription": "String",
    "mshr_primarycontactlinkedinisprivate": Int,
    "mshr_primarycontactlinkedinpurpose": "String",
    "mshr_primarycontacttwitter": "String",
    "mshr_primarycontacttwitterdescription": "String",
    "mshr_primarycontacttwitterisprivate": Int,
    "mshr_primarycontacttwitterpurpose": "String",
    "mshr_partytype": "String",
    "mshr_namesequencedisplayas": "String",
    "mshr_firstname": "String",
    "mshr_lastnameprefix": "String",
    "mshr_lastname": "String",
    "mshr_middlename": "String",
    "mshr_electroniclocationid": "String",
    "mshr_dirpersonentityid": "Guid",
    "mshr_addresstimezone": Int
}
```

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **ID för personentitet**<br>mshr_dirpersonentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Systemgenererad | En systemgenererad unik identifierare för entitetsposten. |
| **Partnummer**<br>mshr_partynumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt<br>Systemgenererad | En systemgenererad unik identifierare för personen, läsbar för användaren.  |
| **Namn**<br>mshr_name<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Fältvärdet är en sammanslagning av förnamn, mellannamn, efternamnsprefix och efternamn i den ordning som anges i fältet **Namnsekvens Visa som**. |
| **Namn-alias**<br>mshr_namealias<br>*Sträng* | Skrivskydd<br>Valfritt | Ett namnalias som kan anges för personen. |
| **Känd som**<br>mshr_knownas<br>*Sträng* | Skrivskydd<br>Valfritt | Ett namn som kan användas för personen, om denne brukar gå under ett annat namn. |
| **Språk-ID**<br>mshr_languageid<br>*Sträng* | Skrivskydd<br>Valfritt | Språk-ID:t för personens primära språk, enligt definitionen i ISO 639-1-formatet. |
| **Adressböcker**<br>mshr_addressbooks<br>*Sträng* | Skrivskydd<br>Valfritt | Adressbok till vilken personen kan tilldelas. Adressböcker som har ställts in för organisationen anges i entiteten mshr_diraddressbooksentity. |
| **Jubileumsdag**<br>mshr_anniversaryday<br>*Int* | Skrivskydd<br>Valfritt | Dagen då personens jubileumsdatum inträffar. |
| **Jubileumsmånad**<br>mshr_anniversarymonth<br>*alternativuppsättningen mshr_monthsofyear* | Skrivskydd<br>Valfritt | Den månad då personens jubileumsdatum inträffar. |
| **Jubileumsår**<br>mshr_anniversaryyear<br>*Int* | Skrivskydd<br>Valfritt | Det år då personens jubileumsdatum inträffar. |
| **Födelsedag**<br>mshr_birthday<br>*Int* | Skrivskydd<br>Valfritt | Dagen då personens födelsedag inträffar. |
| **Födelsemånad**<br>mshr_birthmonth<br>*alternativuppsättningen mshr_monthsofyear* | Skrivskydd<br>Valfritt | Månaden då personens födelsedag inträffar. |
| **Födelseår**<br>mshr_birthyear<br>*Int* | Skrivskydd<br>Valfritt | Året då personens födelsedag inträffar. |
| **Barnens namn**<br>mshr_childrennames<br>*Sträng* | Skrivskydd<br>Valfritt | Sträng för namnen på personens barn. Det finns ingen obligatorisk avgränsning. |
| **Kön**<br>mshr_gender<br>*alternativuppsättningen mshr_hcmpersongender* | Skrivskydd<br>Valfritt | Personens kön. |
| **Hobbies**<br>mshr_hobbies<br>*Sträng* | Skrivskydd<br>Valfritt | Personens hobbies. |
| **Initialer**<br>mshr_initials<br>*Sträng* | Skrivskydd<br>Valfritt | Initialerna för personens namn. |
| **Civilstånd**<br>mshr_maritalstatus<br>*alternativuppsättningen mshr_hcmpersonmaritalstatus* | Skrivskydd<br>Valfritt | Personens civilstånd. |
| **Fonetiskt förnamn**<br>mshr_phoneticfirstname<br>*Sträng* | Skrivskydd<br>Valfritt | Det fonetiska uttal som gäller för personens förnamn. |
| **Fonetiskt efternamn**<br>mshr_phoneticlastname<br>*Sträng* | Skrivskydd<br>Valfritt | Det fonetiska uttal som gäller för personens efternamn. |
| **Fonetiskt mellannamn**<br>mshr_phoneticmiddlename<br>*Sträng* | Skrivskydd<br>Valfritt | Det fonetiska uttal som gäller för personens efternamn. |
| **Personligt suffix**<br>mshr_personalsuffix<br>*Sträng* | Skrivskydd<br>Valfritt | Personens personliga suffix. Giltiga värden i den mshr_dirnameaffixentity-entitet där mshr_type är suffix (200000001). |
| **Personlig titel**<br>mshr_personaltitle<br>*Sträng* | Skrivskydd<br>Valfritt | En personlig titel för personen. Giltiga värden i den mshr_dirnameaffixentity-entitet där mshr_type är titel (200000000).
| **Yrkessuffix**<br>mshr_professionalsuffix<br>*Sträng* | Skrivskydd<br>Valfritt | Ett yrkessuffix. |
| **Yrkestitel**<br>mshr_professionaltitle<br>*Sträng* | Skrivskydd<br>Valfritt | En yrkestitel. |
| **Fullständig primär adress**<br>mshr_fullprimaryaddress<br>*Sträng* | Skrivskydd<br>Valfritt | Personens fullständiga primära adress, en sammanslagning av de primära adressfälten. |
| **Adress ort**<br>mshr_addresscity<br>*Sträng* | Skrivskydd<br>Valfritt | Orten för personens primära adress. Ställ in i entiteten mshr_logisticsaddresscityentity. |
| **Land/region för adress**<br>mshr_addresscountryregionid<br>*Sträng* | Skrivskydd<br>Valfritt | Land/region för personens primära adress. Giltiga värden i entiteten mshr_logisticsaddresscountryregionentity. |
| **ISO-landskod för adress**<br>mshr_addresscountryregionisocode<br>*Sträng* | Skrivskydd<br>Valfritt | ISO-landskod för personens primära adress. |
| **Länsadress**<br>mshr_addresscounty<br>*Sträng* | Skrivskydd<br>Valfritt | Länet för personens primära adress. Ställ in i entiteten mshr_logisticsaddresscountyentity. |
| **Distriktsnamn för adress**<br>mshr_addressdistrictname<br>*Sträng* | Skrivskydd<br>Valfritt | Distriktet för personens primära adress. Ställ in i entiteten mshr_logisticsaddressdistrictentity. |
| **Latitud för adress**<br>mshr_addresslatitude<br>*Sträng* | Skrivskydd<br>Valfritt | Latituden för personens primära adress. |
| **Plats-ID för adress**<br>mshr_addresslocationid<br>*Sträng* | Skrivskydd<br>Valfritt | Den unika identifieraren för platsen där personens primära adress finns. Giltiga värden i entiteten mshr_logisticspostaladdresslocationcdsentity. |
| **Platsroller för adress**<br>mshr_addresslocationroles<br>*Sträng* | Skrivskydd<br>Valfritt | Platsroll för personens primära adress. Ställ in i entiteten mshr_logisticslocationrolecdsentity. |
| **Longitud för adress**<br>mshr_addresslongitude<br>*Sträng* |  Skrivskydd<br>Valfritt | Longituden för personens primära adress. |
| **Delstat för adress**<br>mshr_addressstate<br>*Sträng* | Skrivskydd<br>Valfritt | Delstaten för personens primära adress. Ställ in i entiteten mshr_logisticsaddressstateentity. |
| **Gatuadress**<br>mshr_addressstreet<br>*Sträng* | Skrivskydd<br>Valfritt | Gatuadressen för personens primära adress. |
| **Adressen giltig från**<br>mshr_addressvalidfrom<br>*Datum* | Skrivskydd<br>Valfritt | Det datum från vilket personens primära adress är giltig. |
| **Adressen giltig till**<br>mshr_addressvalidto<br>*Datum* | Skrivskydd<br>Valfritt | Det datum till vilket personens primära adress är giltig. |
| **Adressens postnummer**<br>mshr_addresszipcode<br>*Sträng* | Skrivskydd<br>Valfritt | Postnumret för personens primära adress. Ställ in i entiteten mshr_logisticsaddresspostalcodeentity. |
| **Adressen är privat**<br>mshr_addressisprivate<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Valfritt | Bestämmer om personens primära adress delas med andra i organisationen. |
| **Adressbeskrivning**<br>mshr_addressdescription<br>*Sträng* | Skrivskydd<br>Valfritt | Beskrivning för personens primära adress. |
| **Kontaktens primära e-postadress**<br>mshr_primarycontactemail<br>*Sträng* | Skrivskydd<br>Valfritt | Personens primära e-postadress. |
| **Beskrivning av kontaktens primära e-postadress**<br>mshr_primarycontactemaildescription<br>*Sträng* | Skrivskydd<br>Valfritt | En beskrivning av den primära e-postadressen. |
| **Kontaktens primära e-postadress är IM**<br>mshr_primarycontactemailisim<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Valfritt | Bestämmer om den primära e-postadressen är tillgänglig för snabbmeddelanden. |
| **Syfte med primär e-postadress för kontakt**<br>mshr_primarycontactemailpurpose<br>*Sträng* | Skrivskydd<br>Valfritt | Syftet med den primära e-postadressen. Ställ in i entiteten mshr_logisticslocationroleentity. |
| **Kontaktens primära faxnummer**<br>mshr_primarycontactfax<br>*Sträng* | Skrivskydd<br>Valfritt | Primärt faxnummer. |
| **Beskrivning av kontaktens primära faxnummer**<br>mshr_primarycontactfaxdescription<br>*Sträng* | Skrivskydd<br>Valfritt | Tillhandahållen beskrivning av det primära faxnumret. |
| **Kontaktens primära faxanslutning**<br>mshr_primarycontactfaxextension<br>*Sträng* | Skrivskydd<br>Valfritt | Anslutningen för det primära faxnumret. |
| **Syfte med primärt faxnummer för kontakt**<br>mshr_primarycontactfaxpurpose<br>*Sträng* | Skrivskydd<br>Valfritt | Syftet med det primära faxnumret. Ställ in i entiteten mshr_logisticslocationroleentity.
| **Kontaktens primära telefonnummer**<br>mshr_primarycontactphone<br>*Sträng* | Skrivskydd<br>Valfritt | Primärt telefonnummer. |
| **Beskrivning av kontaktens primära telefonnummer**<br>mshr_primarycontactphonedescription<br>*Sträng* | Skrivskydd<br>Valfritt | Tillhandahållen beskrivning av det primära telefonnumret. |
| **Kontaktens primära telefonanslutning**<br>mshr_primarycontactphoneextension<br>*Sträng* | Skrivskydd<br>Valfritt | Anslutningen för det primära telefonnumret. |
| **Kontaktens primära telefonnummer är ett mobilnummer**<br>mshr_primarycontactphoneismobile<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Valfritt | Bestämmer om det primära telefonnumret är en mobiltelefon. |
| **Syfte med primärt telefonnummer för kontakt**<br>mshr_primarycontactphonepurpose<br>*Sträng* | Skrivskydd<br>Valfritt | Syftet med det primära telefonnumret. Ställ in i entiteten mshr_logisticslocationroleentity. |
| **Kontaktens primära Telex**<br>mshr_primarycontacttelex<br>*Sträng* | Skrivskydd<br>Valfritt | Primärt telexnummer. |
| **Beskrivning av kontaktens primära telexnummer**<br>mshr_primarycontacttelexdescription<br>*Sträng* | Skrivskydd<br>Valfritt | Tillhandahållen beskrivning av personens primära telexnummer. |
| **Syfte med primärt telexnummer för kontakt**<br>mshr_primarycontacttelexpurpose<br>*Sträng* | Skrivskydd<br>Valfritt | Syftet med personens primära telexnummer. Ställ in i entiteten mshr_logisticslocationroleentity. |
| **Kontaktens primära webbadress (URL)**<br>mshr_primarycontacturl<br>*Sträng* | Skrivskydd<br>Valfritt | Primär webbadress (URL). |
| **Beskrivning av kontaktens primära webbadress (URL)**<br>mshr_primarycontacturldescription<br>*Sträng* | Skrivskydd<br>Valfritt | Tillhandahållen beskrivning för personens primära webbadress (URL). |
| **Syfte med primär webbadress (URL) för kontakt**<br>mshr_primarycontacturldescription<br>*Sträng* | Skrivskydd<br>Valfritt | Syftet med personens primära URL. Ställ in i entiteten mshr_logisticslocationroleentity. |
| **Primär kontakt för Facebook**<br>mshr_primarycontactfacebook<br>*Sträng* | Skrivskydd<br>Valfritt | Primärt Facebook-konto. Identifieras via användar-ID. |
| **Beskrivning av primär kontakt för Facebook**<br>mshr_primarycontactfacebookdescription<br>*Sträng* | Skrivskydd<br>Valfritt | Tillhandahållen beskrivning för personens primära Facebook-konto. |
| **Kontaktens primära Facebook-konto är privat**<br>mshr_primarycontactfacebookisprivate<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Valfritt | Bestämmer om det primära Facebook-kontot är synligt för andra användare. |
| **Syfte med primär kontakt för Facebook**<br>mshr_primarycontactfacebookpurpose<br>*Sträng* | Skrivskydd<br>Valfritt | Syftet med personens primära Facebook-konto. Ställ in i entiteten mshr_logisticslocationroleentity. |
| **Kontaktens primära LinkedIn-konto**<br>mshr_primarycontactlinkedin<br>*Sträng* | Skrivskydd<br>Valfritt | Primärt LinkedIn-konto. Identifieras via användarnamn. |
| **Beskrivning av kontaktens primära LinkedIn-konto**<br>mshr_primarycontactlinkedindescription<br>*Sträng* | Skrivskydd<br>Valfritt | Tillhandahållen beskrivning för personens primära LinkedIn-konto. |
| **Kontaktens primära LinkedIn-konto är privat**<br>mshr_primarycontactlinkedinisprivate<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Valfritt | Bestämmer om information om personens primära LinkedIn-konto delas med andra användare. |
| **Syfte med primärt LinkedIn-konto**<br>mshr_primarycontactlinkedinpurpose<br>*Sträng* | Skrivskydd<br>Valfritt | Syftet med personens primära LinkedIn-konto. Ställ in i entiteten mshr_logisticslocationroleentity. |
| **Kontaktens primära Twitterkonto**<br>mshr_primarycontacttwitter<br>*Sträng* | Skrivskydd<br>Valfritt | Personens primära Twitter-konto. Identifieras via @username. |
| **Beskrivning av kontaktens primära Twitterkonto**<br>mshr_primarycontacttwitterdescription<br>*Sträng* | Skrivskydd<br>Valfritt | Tillhandahållen beskrivning för personens primära Twitter-konto. |
| **Kontaktens primära Twitter-konto är privat**<br>mshr_primarycontacttwitterisprivate<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Valfritt | Bestämmer om information om personens primära Twitter-konto delas med andra användare. |
| **Syfte med primärt Twitter-konto**<br>mshr_primarycontacttwitterpurpose<br>*Sträng* | Skrivskydd<br>Valfritt | Syftet med personens primära Twitter-konto. Ställ in i entiteten mshr_logisticslocationroleentity. |
| **Parttyp**<br>mshr_partytype<br>*Sträng* | Skrivskydd<br>Valfritt | Personens parttyp. Kommer alltid att vara **Person** för kandidater. |
| **Namnsekvens visa som**<br>mshr_namesequencedisplayas<br>*Sträng* | Skrivskydd<br>Valfritt | Den ordning i vilken personens namnegenskaper sammanfogas för att bilda egenskapsvärdet Namn (mshr_name). |
| **Förnamn**<br>mshr_firstname<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Ange personens förnamn. |
| **Mellannamn**<br>mshr_middlename<br>*Sträng* | Skrivskydd<br>Valfritt | Personens mellannamn. |
| **Prefix för efternamn**<br>mshr_lastnameprefix<br>*Sträng* | Skrivskydd<br>Valfritt | Prefixet för personens efternamn. |
| **Efternamn**<br>mshr_lastname<br>*Sträng* | Skrivskydd<br>Valfritt | Personens efternamn. |
| **ID för elektronisk plats**<br>mshr_electroniclocationid<br>*Sträng* | Skrivskydd<br>Valfritt | ID för personens elektroniska plats. |
| **Tidszon för adress**<br>mshr_addresstimezone<br>*Int* | Skrivskydd<br>Valfritt | Tidszonen för personens primära adress. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
