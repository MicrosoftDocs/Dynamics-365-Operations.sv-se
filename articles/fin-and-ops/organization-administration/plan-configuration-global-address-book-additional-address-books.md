---
title: Planera för att ställa in den globala adressboken och andra adressböcker
description: Det här avsnittet innehåller en beskrivning av övervägandena och besluten som måste fattas under planeringsprocessen innan du konfigurerar den globala adressboken och alla ytterligare adressböcker i Microsoft Dynamics 365 for Finance and Operations. Vissa av besluten kräver att du bekräftar besluten som har fattats för andra produktområden såsom organisationshierarkin.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 20795cb8dd752a32f6c57fdb8f369691e41139b3
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1545772"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a>Planera för att ställa in den globala adressboken och andra adressböcker

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en beskrivning av övervägandena och besluten som måste fattas under planeringsprocessen innan du konfigurerar den globala adressboken och alla ytterligare adressböcker i Microsoft Dynamics 365 for Finance and Operations. Vissa av besluten kräver att du bekräftar besluten som har fattats för andra produktområden såsom organisationshierarkin.

## <a name="global-address-book"></a>Global adressbok

Innan du börjar att arbeta med den globala adressboken måste du bestämma standardvärdena för den. Dessa standardvärden används sedan för eventuella ytterligare adressböcker som du skapar.

**Beslut:**

- Med vilken sekvens visas namnen för partposter av typen **Person**? En sekvens ar till exempel förnamn, mellannamn och efternamn.
- Ska partposter tas bort från adressboken när rollposten tas bort? Om till exempel en kundpost raderas, ska även partposten raderas?
- När en ny post skapas får användare ett meddelande om en dublettpost finns i den globala adressboken?
- Ska det universella datanumret i systemet (DUNS) inkluderas i partpostens information?
- Om DUNS-numret inkluderas i en partpost, ska numrets unikhet kontrolleras?
- När en partpost skapas i den globala adressboken, vill du ha en standardparttyp, person eller organisation?
- Vilka användarroller får åtkomst till privata adresser och kontaktinformation för partposter?

## <a name="additional-address-books"></a>Ytterligare adressböcker

När du har skapat den globala adressboken, kan du skapa ytterligare adressböcker efter behov, till exempel en separat adressbok för varje företag i organisationen eller för varje affärsområde. Exempelvis är Fabrikam en internationell organisation som har flera företag och flera affärsområden. Fabrikam planerar att skapa en adressbok för varje affärsområde. För affärsområden som finns på fler än en plats, till exempel det pneumatiska verktygsföretaget, planerar Fabrikam att skapa en adressbok för varje plats. Chris, IT-chefen på Fabrikam, har skapat följande lista över adressböcker som krävs. Listan beskriver även partposterna som varje adressbok måste inkludera.

- **Kontrakt med offentlig sektor (PubSC)** – Partposter för alla parter som ingår i Fabrikams avtal med den offentliga sektorn.
- **Kontrakt med privat sektor (PriSC)** – Partposter för alla parter som ingår i Fabrikams avtal med den privata sektorn.
- **Elektroniska verktyg (ET)** – Partposter för alla parter som ingår i inköp eller försäljning av elektroniska verktyg eller annat som samverkar med de elektroniska verktygen, som tillhandahålls av eller köps in för Fabrikam i företaget Fabrikam-Japan.
- **Pneumatiska verktyg (PTJPN)** – Partposter för alla parter som ingår i inköp eller försäljning av pneumatiska verktyg eller annat som samverkar med de pneumatiska verktygen, som tillhandahålls av eller köps in för Fabrikam i företaget Fabrikam-Japan.
- **Pneumatiska verktyg (PTUSA)** – Partposter för alla parter som ingår i inköp eller försäljning av pneumatiska verktyg eller annat som samverkar med de pneumatiska verktygen, som tillhandahålls av eller köps in för Fabrikam i företaget Fabrikam-US.

**Beslut:**

- Hur många ytterligare adressböcker ska du skapa?

### <a name="address-book-security"></a>Adressbokssäkerhet

Du kan skapa adressböcker när som helst och du kan även ange säkerhetsparametrar för adressböckerna när som helst. Du måste inte att ange säkerhetsprivilegier för en adressbok, men om du inte gör det kan alla anställda i organisationen den visa alla partposter i den adressboken. Du kan ange säkerhetsprivilegier för partposter med adressböcker. Säkerhetsprivilegier baseras på team. Det här garanterar att endast anställda som tilldelas till en grupp har åtkomst till en adressbok kan visa partposterna i den adressboken. Du måste du välja team som har åtkomst till varje adressbok. För varje adressbok kan du ange säkerhetsprivilegier som tillåter eller förhindrar åtkomst för specifika team. Om du beviljar ett team åtkomst till en adressbok kan alla medlemmarna i teamet visa posterna i den adressboken. Om du inte beviljar ett team åtkomst till en adressbok kan inga medlemmar i teamet visa posterna eller innehållet i den adressboken.

**Beslut:**

- Vilka team ska ha åtkomst till varje ny adressbok som du skapar?
