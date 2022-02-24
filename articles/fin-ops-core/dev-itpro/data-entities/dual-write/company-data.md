---
title: Företagskoncept i Dataverse
description: I det här avsnittet beskrivs integreringen av företagsdata mellan Finance and Operations och Dataverse.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 08/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: bbe634b87b3cb30ed993f9b3afeb4321d70f07e6
ms.sourcegitcommit: 7e1be696894731e1c58074d9b5e9c5b3acf7e52a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/17/2020
ms.locfileid: "4744889"
---
# <a name="company-concept-in-dataverse"></a>Företagskoncept i Dataverse

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]


I Finance and Operations, är begreppet av ett *företag* både en laglig konstruktion och en affärskonstruktion. Det är också en säkerhets- och synlighetsgräns för data. Användare arbetar alltid inom ramen för ett enda företag, och de flesta av uppgifterna är sorterade efter företag.

Dataverse har inte ett likvärdigt koncept. Det närmaste konceptet är *affärsenhet*, som i första hand är en säkerhets- och synlighetsgräns för användardata. Det här konceptet har inte samma juridiska eller affärsmässiga betydelse som företagskonceptet.

Eftersom affärsenhet och företag inte är likvärdiga begrepp, är det inte möjligt att tvinga en en-till-en-mappning (1:1) mellan dem i syfte integrera Dataverse. Men eftersom användare måste som standard kunna se samma rader i appen och Dataverse har Microsoft infört en ny tabell i Dataverse som heter CDM\_Företag. Den här tabellen motsvarar företagstabellen i appen. För att garantera att synligheten för rader är likvärdig mellan appen och färdiga Dataverse rekommenderar vi följande inställningar för data i Dataverse:

+ För varje Finance and Operations-företagsrad som är aktiverad för dubbelriktad skrivning skapas en associerad cdm\_Företag-rad.
+ När en cdm\_Företag-rad skapas och aktiveras för dubbelriktad skrivning skapas en standardaffärsenhet som har samma namn. Även om ett standardteam skapas automatiskt för den affärsenheten används inte affärsenheten.
+ Ett separat ägarteam skapas med samma namn. Det är också förknippat med affärsenheten.
+ Som standard anges ägaren av en rad som skapas och dubbelriktad skrivning till Dataverse anges till teamet "DW ägare" som är länkat till den associerade affärsenheten.

Följande illustration visar ett exempel på den här datainställningen i Dataverse.

![Inställning av data i Dataverse](media/dual-write-company-1.png)

På grund av den här konfigurationen kommer alla rader som är relaterade till USMF-företaget att ägas av ett team som är länkat till USMF-affärsenheten i Dataverse. Därför kan alla användare som har åtkomst till den affärsenheten via en säkerhetsroll som är inställd på synlighet på affärsenhetsnivå nu se dessa rader. I följande exempel visas hur team kan användas för att ge rätt åtkomst till dessa rader.

+ Rollen "Säljchef" tilldelas medlemmar i teamet "USMF försäljning".
+ Användare som har rollen "Säljchef" kan komma åt alla rader i konton som är medlemmar i samma affärsenhet som de är medlemmar i.
+ "USMF försäljning"-teamet är länkat till den USMF-affärsenhet som nämndes tidigare.
+ Medlemmar i teamet "USMF försäljning" kan därför se alla konton som ägs av "USMF DW"-användaren, som skulle ha kommit från USMF-företagstabellen i Finance and Operations.

![Så här kan du använda team](media/dual-write-company-2.png)

Som föregående illustration visar är denna 1:1-mappning mellan affärsenhet, företag och team bara en utgångspunkt. I det här exemplet skapas en ny affärsenhet "Europa" manuellt i Dataverse som överordnad för både DEMF och ESMF. Denna nya rotaffärsenhet är inte kopplad till dubbelriktadskrivning. Den kan dock användas för att ge medlemmar i "EUR försäljnings"-teamet tillgång till kontodata i både DEMF och ESMF genom att ange datasynlighet till **överordnad/underordnad BU** i den associerade säkerhetsrollen.

Ett sista avsnitt att diskutera är hur dubbelriktadskrivning avgör vilket ägarteam det ska tilldela rader till. Det här beteendet styrs av kolumnen **Standardägargrupp** i cdm\_Företag-raden. När encdm\_Företag-rad är aktiverad för dubbelriktad skrivning skapar ett plugin-program automatiskt den associerade affärsenheten och ägarteamet (om det inte redan finns) och ställer in kolumnen **Standardägargrupp**. Administratören kan ändra det här kolumnen till ett annat värde. Men administratören kan inte rensa kolumnen så länge tabellen är aktiverad för dubbelriktad skrivning.

> [!div class="mx-imgBorder"]
![Kolumn för standardägargrupp](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Företagsstrimling och initiering

Dataverse-integrering ger företagsparitet genom att använda en företagsidentifierare för strimla data. Som framgår av följande illustration utökas alla företagsspecifika tabeller så att de har en många-till-en-relation (N:1) med cdm\_Företag-tabellen.

> [!div class="mx-imgBorder"]
![N:1-relation mellan en företagsspecifik tabell och tabellen cdm_Company](media/dual-write-bootstrapping.png)

+ För rader blir värdet skrivskyddat när ett företag har lagts till och sparats. Därför bör användare se till att de väljer rätt företag.
+ Endast rader som har företagsdata är kvalificerade för dubbelriktad skrivning mellan appen och Dataverse.
+ För befintliga Dataverse-data kommer en administratörsledd initieringsupplevelse snart att vara tillgänglig.


## <a name="autopopulate-company-name-in-customer-engagement-apps"></a>Fyll i företagets namn automatiskt i kundengagemangsappar

Det finns flera sätt att fylla i företagsnamnet automatiskt i kundengagemangsappen.

+ Om du är systemadministratör kan du ställa in standardföretaget genom att navigera till **Avancerade inställningar > System > Säkerhet > Användare**. Öppna formuläret **användare** och i avsnittet **organisationsinformation** i värdet **företag till standard på formulär**.

    :::image type="content" source="media/autopopulate-company-name-1.png" alt-text="Ange standardföretag i avsnittet organisationsinformation.":::

+ Om du har **Skriv** åtkomst till tabellen **SystemUser** på nivån **affärsenhet** kan du ändra standardföretaget i valfritt formulär genom att välja ett företag i listrutan **företag**.

    :::image type="content" source="media/autopopulate-company-name-2.png" alt-text="Ändra företagsnamnet på ett nytt konto.":::

+ Om du har **Skriv**-åtkomst till data i fler än ett företag kan du ändra standardföretaget genom att välja en rad som tillhör ett annat företag.

    :::image type="content" source="media/autopopulate-company-name-3.png" alt-text="När du väljer en rad ändras standardföretaget.":::

+ Om du är systemets konfigurator eller administratör och vill fylla i företagsdata automatiskt i ett anpassat formulär, kan du använda [formulärhändelser](https://docs.microsoft.com/powerapps/developer/model-driven-apps/clientapi/events-forms-grids). Lägg till en JavaScript-referens till **msdyn_/DefaultCompany.js** och använd följande händelser. Du kan t. ex. använda ett formulär som är utanför rutan, till exempel formuläret **konto**.

    + **OnLoad**-händelse för formuläret: Ställ in kolumnen **defaultCompany**.
    + **OnChange**-händelse för kolumnen **företag**: Ställ in kolumnen **updateDefaultCompany**.

## <a name="apply-filtering-based-on-the-company-context"></a>Använd filtrering baserat på företagets kontext

Om du vill använda filtrering baserat på företagets kontext i dina anpassade formulär eller anpassade uppslagskolumner som lagts till i standardformulären öppnar du formuläret och använder avsnittet **filtrering av relaterade poster** för att använda företagsfiltret. Du måste ställa in detta för varje uppslagskolumn som kräver filtrering baserat på det underliggande företaget för en viss rad. Inställningen visas för **kontot** i följande bild.

:::image type="content" source="media/apply-company-context.png" alt-text="Använd företagets kontext":::

