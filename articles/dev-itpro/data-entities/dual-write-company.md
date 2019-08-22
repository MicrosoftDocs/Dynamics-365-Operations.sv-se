---
title: Företagskoncept i Common Data Service
description: I det här avsnittet beskrivs integreringen av företagsdata mellan Finance and Operations och Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 6eddd87c3ad3ea9de8aec2874b0514faa65374f1
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789249"
---
## <a name="company-concept-in-common-data-service"></a>Företagskoncept i Common Data Service

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

I Microsoft Dynamics 365 for Finance and Operations, är begreppet av ett *företag* både en laglig konstruktion och en affärskonstruktion. Det är också en säkerhets- och synlighetsgräns för data. Användare arbetar alltid inom ramen för ett enda företag, och de flesta av uppgifterna är sorterade efter företag.

Common Data Service har inte ett likvärdigt koncept. Det närmaste konceptet är *affärsenhet*, som i första hand är en säkerhets- och synlighetsgräns för användardata. Det här konceptet har inte samma juridiska eller affärsmässiga betydelse som företagskonceptet i Finance and Operations.

Eftersom affärsenhet och företag inte är likvärdiga begrepp, är det inte möjligt att tvinga en en-till-en-mappning (1:1) mellan dem i syfte integrera Common Data Service. Men eftersom användare måste som standard kunna se samma poster i Finance and Operations och Common Data Service har Microsoft infört en ny entitet i Common Data Service som heter CDM \_-företag. Den här entiteten motsvarar företagsentiteten i Finance and Operations. För att garantera att synligheten för poster är likvärdig mellan Finance and Operations och färdiga Common Data Service rekommenderar vi följande inställningar för data i Common Data Service:

+ För varje Finance and Operations-företagspost som är aktiverad för dubbelriktad skrivning skapas en associerad CDM \_-företagspost.
+ När en CDM \_-företagspost skapas och aktiveras för dubbelriktad skrivning skapas en standardaffärsenhet som har samma namn. Även om ett standardteam skapas automatiskt för den affärsenheten används inte affärsenheten.
+ Ett separat ägarteam skapas med samma namn. Det är också förknippat med affärsenheten.
+ Som standard anges ägaren av en post som skapas i Finance and Operations och dubbelriktad skrivning till Common Data Service anges till teamet "DW ägare" som är länkat till den associerade affärsenheten.

Följande illustration visar ett exempel på den här datainställningen i Common Data Service.

![Inställning av data i Common Data Service](media/dual-write-company-1.png)

På grund av den här konfigurationen kommer alla Finance and Operations-poster som är relaterade till USMF-företaget att ägas av ett team som är länkat till USMF-affärsenheten i Common Data Service. Därför kan alla användare som har åtkomst till den affärsenheten via en säkerhetsroll som är inställd på synlighet på affärsenhetsnivå nu se dessa poster. I följande exempel visas hur team kan användas för att ge rätt åtkomst till dessa poster.

+ Rollen "Säljchef" tilldelas medlemmar i teamet "USMF försäljning".
+ Användare som har rollen "säljchef" kan komma åt alla kontoposter som är medlemmar i samma affärsenhet som de är medlemmar i.
+ "USMF försäljning"-teamet är länkat till den USMF-affärsenhet som nämndes tidigare.
+ Medlemmar i teamet "USMF försäljning" kan därför se alla konton som ägs av "USMF DW"-användaren, som skulle ha kommit från USMF-företagsentiteten i Finance and Operations.

![Så här kan du använda team](media/dual-write-company-2.png)

Som föregående illustration visar är denna 1:1-mappning mellan affärsenhet, företag och team bara en utgångspunkt. I det här exemplet skapas en ny affärsenhet "Europa" manuellt i Common Data Service som överordnad för både DEMF och ESMF. Denna nya rotaffärsenhet är inte kopplad till dubbelriktadskrivning. Den kan dock användas för att ge medlemmar i "EUR försäljnings"-teamet tillgång till kontodata i både DEMF och ESMF genom att ange datasynlighet till **överordnad/underordnad BU** i den associerade säkerhetsrollen.

Ett sista ämne att diskutera är hur dubbelriktadskrivning avgör vilket ägargrupp det ska tilldela poster till. Det här beteendet styrs av fältet **standardägargrupp** i CDM \_-företagsposten. När en CDM \_-företagspost är aktiverad för dubbelriktad skrivning skapar ett plugin-program automatiskt den associerade affärsenheten och ägargruppen (om den inte redan finns) och anger fältet **standardägargrupp**. Administratören kan ändra det här fältet till ett annat värde. Men administratören kan inte rensa fältet så länge entiteten är aktiverad för dubbelriktad skrivning.

![Fält för standardägargrupp](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a>Företagsstrimling och initiering

Common Data Service-integrering ger företagsparitet genom att använda en företagsidentifierare för strimla data. Som framgår av följande illustration utökas alla företagsspecifika entiteter så att de har en många-till-en-relation (N:1) med CDM \_-företagsentiteten.

![N:1-relation mellan en företagsspecifik entitet och entiteten cdm_Company](media/dual-write-bootstrapping.png)

+ För poster blir värdet skrivskyddat när ett företag har lagts till och sparats. Därför bör användare se till att de väljer rätt företag.
+ Endast poster som har företagsdata är kvalificerade för dubbelriktadskrivning mellan Finance and Operations och Common Data Service.
+ För befintliga Common Data Service-data kommer en administratörsledd initieringsupplevelse snart att vara tillgänglig.
