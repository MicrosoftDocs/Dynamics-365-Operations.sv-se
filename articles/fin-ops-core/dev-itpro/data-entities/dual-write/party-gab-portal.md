---
title: Använda Power Portal med datamodellen för part
description: I det här avsnittet beskrivs ändringarna av Power Portal-webbrollerna på grund av partens datamodell i nedskrivningen.
author: RamaKrishnamoorthy
ms.date: 03/22/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-22
ms.openlocfilehash: a2ea914344341ee26138e853727c551bdd5d733e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833100"
---
# <a name="using-power-portal-with-the-party-data-model"></a>Använda Power Portal med datamodellen för part

[!INCLUDE[banner](../../includes/banner.md)]

[!INCLUDE[rename-banner](~/includes/cc-data-platform-banner.md)]

Lösningen för dubbelriktad skrivning för programorkestrering version 2.0.999.0 innehåller senare datamodelländringar av parten och den globala adressboken för konto- och kontaktregistren. Ändringarna tillåter relationer mellan många som stöder avancerade affärsscenarier. Dessa ändringar stöds inte av portalwebbrollerna, inklusive kundportalen, som levereras out-of-the-box eller som fanns i din miljö innan du installerade webbplatsskrivning. För att webbrollerna ska fungera som förväntat måste du skapa nya webbroller med hjälp av den nya datamodellen. 

Sammanfattningen är att det sätt på vilket register samverkar har ändrats, men registerbehörigheterna i kundportalen har inte ändrats. I det här avsnittet beskrivs hur du skapar nya webbroller som arbetar med den nya avancerade datamodellen.

Detta diagram visar tabellförhållandet **utan** partiets och den globala adressbokens datamodell:

   ![utan partmodell](media/without-party-model.PNG)

Detta diagram visar tabellförhållandet **med** partiets och den globala adressbokens datamodell:

   ![med partmodell](media/with-party-model.png)

## <a name="create-a-new-table-permission"></a>Skapa en ny registerbehörighet

Gör på följande sätt om du vill skapa de nya registerbehörigheterna:

1. Logga in på [Power Apps](https://make.powerapps.com) och gå till programmen.
2. Välj ett portalhanteringsprogram.
3. I sidfältet, välj **Säkerhet > Registerbehörigheter**.

    Du måste skapa tre nya behörigheter:

    + Kontakt till partanslutning
    + Part till kontoanslutning
    + Anslutning mellan konto och beställning

4. Skapa och spara en ny behörighet för anslutningen till kontaktpersonen och ange följande parametrar:

    + **Namn**: Part till kontoanslutning (eller ditt val)
    + **Registernamn**: msdyn_contactforparty
    + **Webbplats**: kundportal
    + **Område**: Kontakt
    + **Behörigheter**: Välj alla
    + **Webbroller**: Autentiserade användare, kundrepresentant (eller ditt val)

5. Skapa och spara en ny behörighet för part till konto-anslutning och ange följande parametrar:

    + **Namn**: Part till kontoanslutning (eller ditt val)
    + **Registernamn**: konto
    + **Webbplats**: kundportal
    + **Område**: Överordnad
    + **Behörigheter**: Välj alla
    + **Överordnad registerbehörighet**: kontakt till part-anslutning

6. Skapa och spara en ny behörighet för konto till order-anslutning och ange följande parametrar:

    + **Namn**: Konto till order-anslutning (eller ditt val)
    + **Registernamn**: försäljningsorder
    + **Webbplats**: kundportal
    + **Område**: Överordnad
    + **Behörigheter**: Välj alla
    + **Överordnad registerbehörighet**: part till konto-anslutning

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
