---
title: Aktivera incheckningsmeddelanden för kunder i kassan (POS)
description: I denna artikel beskrivs hur du aktiverar incheckningsmeddelanden för kunder i Microsoft Dynamics 365 Commerce-kassan (POS).
author: bicyclingfool
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.custom: ''
ms.assetid: ''
ROBOTS: ''
ms.openlocfilehash: 5627f529f72fe06103fa64548a7d182fc008bd83
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287661"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a>Aktivera incheckningsmeddelanden för kunder i kassan (POS)

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du aktiverar incheckningsmeddelanden för kunder i Microsoft Dynamics 365 Commerce-kassan (POS).

I sina "order redo för hämtning"-meddelanden via e-post kan organisationer skicka med en länk eller knapp som låter kunderna meddela butiken att de är på plats och väntar på att deras paket ska hämtas ut till dem. Kunderna får sedan en incheckningsbekräftelse och butiken ett meddelande som en uppgift i sitt kassaprogram. Denna uppgift fungerar som en uppmaning till en försäljare att leverera ordern till kundens fordon. Därför behöver kunden inte komma in i butiken.

Kundens incheckningsarbetsflöde kan även konfigureras för att samla in ytterligare information från kunder, till exempel deras nummer på parkeringsplatsen, fordonets märk, modell och färg, samt leveransinstruktioner. Butiken kan använda den här informationen för att underlätta orderuppfyllelsen.

## <a name="enable-customer-check-in"></a>Aktivera incheckning för kund

När incheckningsfunktionen för kund är aktiverad genererar Commerce ett orderbekräftelse-ID (även kallat kanalreferens-ID). Det genererar även orderbekräftelse-ID för order som skapas via kassakanaler (POS) eller kundtjänstkanaler. 

Följ dessa steg om du vill aktivera incheckningsfunktionen för kund i Commerce headquarters.

1. Gå till **Arbetsytor \> Funktionshantering**.
2. Sök efter funktionen **Generera ID-format för konsekvent kanalreferens för flera kanaler**. 
3. Välj funktionen och sedan **Aktivera nu** i egenskapsfönstret. 

## <a name="create-a-check-in-confirmation-page"></a>Skapa en bekräftelsesida för incheckning

På din näthandelsplats måste du skapa en ny sida som fungerar som upplevelse för incheckningsbekräftelse. Genom ytterligare konfiguration kan sidan även innehålla ett formulär som samlar in ytterligare information från kunder i syfte att underlätta uppfyllelsen av order. Information om hur du konfigurerar sida och modul finns i [modulen Kundincheckning](check-in-pickup-module.md).

## <a name="configure-the-transactional-email-template"></a>Konfigurera mallen för transaktionsmeddelande via e-post

Du måste lägga till en **Jag är här**-länk eller -knapp till mallen för det transaktionsmeddelande via e-post som kunderna erhåller när deras order är redo för hämtning. Kunderna använder den här länken eller knappen när de meddelar butiken om att de har anlänt för att hämta sin order. 

Lägg till länken eller knappen i mallen som är mappad till meddelandetypen **Packning slutförd** samt det leveransläge som du använder för drive in-leverans. Skapa en HTML-länk eller -knapp i mallen som pekar på URL:en för den incheckningsbekräftelsesida du skapat och som innehåller parameternamnen och parametervärdena, enligt följande exempel.

`<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%confirmationid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>`

Mer information om hur du konfigurerar e-postmallar finns i [Anpassa transaktionella e-postmeddelanden per leveranssätt](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>En incheckningsbekräftelseuppgift skapas i kassan (POS)

När en kund har meddelat butiken att de finns för upphämtning visar incheckningssidan ett bekräftelsemeddelande och en valfri QR-kod som innehåller kundens orderbekräftelse-ID. Samtidigt skapas en uppgift i uppgiftslistan i kassan för butiken där kunden plockar upp ordern. Uppgiften innehåller all kund- och orderinformation som krävs för att ordern ska kunna uppfyllas. Uppgiftens instruktionsfält visar all information som har samlats in från kunden via formuläret för ytterligare information.

## <a name="end-to-end-testing"></a>Komplett testning

Vid kundincheckning måste specifika parametrar och värden skickas till incheckningssidan och sedan till kundens inchecknings-API. Därför är det enklaste sättet att testa funktionen i en miljö där en testorder kan skapas och packas. På så sätt kan ett e-postmeddelande med "order redo för upphämtning" genereras med en URL som innehåller de parameternamn och värden som krävs.

Om du vill testa incheckningsfunktionen för kunder följer du dessa steg.

1. Skapa incheckningssidan för kunden och lägg sedan till och konfigurera modulen för kundincheckning. Mer information finns i [Incheckning för upphämtningsmodul](check-in-pickup-module.md). 
1. Checka in sidan och publicera den inte.
1. Lägg till följande länk till en e-postmall som startas av den packade meddelandetypen för ett upphämtningsläge för leverans. För mer information, se [Skapa e-postmallar för transaktionshändelser](email-templates-transactions.md).

    - **För förproduktionsmiljöer (UAT):** Lägg till kodfragmentet från avsnittet [Konfigurera mallen för transaktionsmeddelande via e-post](#configure-the-transactional-email-template) tidigare i denna artikel.
    - **För produktionsmiljöer:** Lägg till följande kommentarskod så att befintliga kunder inte påverkas.

        `<!-- https://[DOMAIN]/[CHECK_IN_PAGE]?channelReferenceId=%confirmationid%&channelId=%pickupchannelid%&packingSlipId=%packingslipid%&preview=inprogress -->`

1. Skapa en order där leveranssättet för upphämtning har angetts.
1. När du får e-postmeddelandet som utlöstes av den fullständiga meddelandetypen, ska du testa incheckningsflödet genom att öppna incheckningssidan där URL:en du lade till tidigare. Eftersom URL-adressen innehåller `&preview=inprogress` flagga uppmanas du att autentisera innan du kan visa sidan.
1. Ange eventuell ytterligare information som krävs för att konfigurera modulen.
1. Kontrollera att incheckningsbekräftelsevyn visas på rätt sätt.
1. Öppna kassaterminalen för den butik där ordern kommer att hämtas upp.
1. Markera panelen **Order som du vill hämta** och kontrollera att ordern visas.
1. Kontrollera att all ytterligare information som konfigurerats i incheckningsmodulen visas i informationsfönstret.

När du har verifierat att incheckningsfunktionen för kunder fungerar från slut till slut följer du dessa steg.

1. Publicera incheckningssidan.
1. Om du testar i en produktionsmiljö bör du avmarkera webbadressen i e-postmallen "order klar för upphämtning" så att länken eller knappen **Jag är här** visas. Ladda sedan upp mallen på nytt.

## <a name="additional-resources"></a>Ytterligare resurser

[Incheckning för upphämtningsmodul](check-in-pickup-module.md)

[Anpassa transaktionsmeddelanden via e-post efter leveranssätt](customize-email-delivery-mode.md)

[Skapa e-postmallar för transaktionshändelser](email-templates-transactions.md)
