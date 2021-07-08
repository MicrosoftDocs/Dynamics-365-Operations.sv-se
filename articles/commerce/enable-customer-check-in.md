---
title: Aktivera incheckningsmeddelanden för kunder i kassan (POS)
description: I det här ämnet beskrivs hur du aktiverar incheckningsmeddelanden för kunder Microsoft Dynamics 365 Commerce i kassan (POS).
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b42dc7766f8a69a7409c28d21b49cc96eca18dd4
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271435"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a>Aktivera incheckningsmeddelanden för kunder i kassan (POS)

[!include [banner](includes/banner.md)]

I det här ämnet beskrivs hur du aktiverar incheckningsmeddelanden för kunder Microsoft Dynamics 365 Commerce i kassan (POS).

I sina "order redo för hämtning"-meddelanden via e-post kan organisationer skicka med en länk eller knapp som låter kunderna meddela butiken att de är på plats och väntar på att deras paket ska hämtas ut till dem. Kunderna får sedan en incheckningsbekräftelse och butiken ett meddelande som en uppgift i sitt kassaprogram. Denna uppgift fungerar som en uppmaning till en försäljare att leverera ordern till kundens fordon. Därför behöver kunden inte komma in i butiken.

Kundens incheckningsarbetsflöde kan även konfigureras för att samla in ytterligare information från kunder, till exempel deras nummer på parkeringsplatsen, fordonets märk, modell och färg, samt leveransinstruktioner. Butiken kan använda den här informationen för att underlätta orderuppfyllelsen.

## <a name="enable-customer-check-in"></a>Aktivera incheckning för kund

När incheckningsfunktionen för kund är aktiverad genererar Commerce ett orderbekräftelse-ID (även kallat kanalreferens-ID). Det genererar även orderbekräftelse-ID för order som skapas via kassakanaler (POS) eller kundtjänstkanaler. 

Följ dessa steg om du vill aktivera incheckningsfunktionen för kund i Commerce-administrationen.

1. Gå till **Arbetsytor \> Funktionshantering**.
2. Sök efter funktionen **Generera ID-format för konsekvent kanalreferens för flera kanaler**. 
3. Välj funktionen och sedan **Aktivera nu** i egenskapsfönstret. 

## <a name="create-a-check-in-confirmation-page"></a>Skapa en bekräftelsesida för incheckning

På din näthandelsplats måste du skapa en ny sida som fungerar som upplevelse för incheckningsbekräftelse. Genom ytterligare konfiguration kan sidan även innehålla ett formulär som samlar in ytterligare information från kunder i syfte att underlätta uppfyllelsen av order. Information om hur du ställer in sida och modul finns i [modulen Kundincheckning](check-in-pickup-module.md).

## <a name="configure-the-transactional-email-template"></a>Konfigurera mallen för transaktionsmeddelande via e-post

Du måste lägga till en **Jag är här**-länk eller -knapp till mallen för det transaktionsmeddelande via e-post som kunderna erhåller när deras order är redo för hämtning. Kunderna använder den här länken eller knappen när de meddelar butiken om att de har anlänt för att hämta sin order. 

Lägg till länken eller knappen i mallen som är mappad till meddelandetypen **Packning slutförd** samt det leveransläge som du använder för drive in-leverans. Skapa en HTML-länk eller -knapp i mallen som pekar på URL-adressen till den incheckningsbekräftelsesida som du skapat. Här är ett exempel:

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
Mer information om hur du konfigurerar e-postmallar finns i [Anpassa transaktionella e-postmeddelanden per leveranssätt](customize-email-delivery-mode.md). 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a>En incheckningsbekräftelseuppgift skapas i kassan (POS)

När en kund har meddelat butiken att de har anlänt för en avhämtning får han eller hon ett meddelande om incheckningsbekräftelse, och en uppgift skapas i uppgiftslistan i kassan (POS) för butiken där kunden hämtar ordern. Uppgiften innehåller all kund- och orderinformation som krävs för att ordern ska kunna uppfyllas. I uppgiften visar instruktionerna i fältet all information som har samlats in från kunden via formuläret för ytterligare information. 

## <a name="additional-resources"></a>Ytterligare resurser

[Incheckning för upphämtningsmodul](check-in-pickup-module.md)
