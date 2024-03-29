---
title: Skapa och hantera kundportal användare (innehåller video)
description: I denna artikel beskrivs hur du skapar användarkonton för kundportal och konfigurerar behörigheter för dem.
author: Henrikan
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: ec4f20daac39e1728ab46db159059e51a0cae0a6
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103784"
---
# <a name="create-and-manage-customer-portal-users"></a>Skapa och hantera kundportal användare

[!include [banner](../includes/banner.md)]


I den medföljande implementeringen finns det inget sätt för dig att själv registrera webbplatser som skapats med hjälp av kundportalen. För att kunna logga in och använda en webbplats måste användarna vara inbjudna av administratören. Microsoft har avsiktligt blockerat möjligheten för användarna att själv registrera sig.

Innan en användare kan använda en webbplats måste en kontaktpost skapas för användaren. Den här posten anger vilket kundkonto och vilken juridisk person som användaren tillhör. Denna information är viktig för att användaren ska kunna skapa och visa försäljningsorder.

När användare själv registrerar sig skapas kontaktposter automatiskt för dem. Därför kan du inte se till att en användare väljer rätt kundkonto och juridisk person. Med inbjudan kan en administratör, å andra sidan, tilldela rätt kundkonto och juridisk person till kontaktposten innan en inbjudan skickas. Om du tänker anpassa lösningen så att användarna kan registrera sig själv bör du tänka på vilka konsekvenser du är.

## <a name="video"></a>Video
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4ADkI]

Videon [Bjud in kunder att registrera sig och använda kundportalen](https://youtu.be/drGUYHX9QIQ) (visas ovan) finns med på [spellistan för Ekonomi och Drift](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) som finns på YouTube.

## <a name="prerequisite-setup"></a>Nödvändiga inställningar

Kontakter i Power Apps-portaler lagras som poster i tabellen **kontakter** i Microsoft Dataverse. Vid dubbelriktad skrivning synkroniseras dessa poster med Microsoft Dynamics 365 Supply Chain Management efter behov.

![Systemdiagram för kundportalkontakter.](media/customer-portal-contacts.png "Systemdiagram för kundportalkontakter")

Innan du börjar bjuda in nya kunder måste du kontrollera att du har aktiverat mappning av tabellen **Kontakt** i dubbelriktad skrivning.

## <a name="the-invitation-process"></a>En inbjudningsprocess

Om du vill bjuda in en befintlig kontakt till kundportalen följer du stegen i [Bjud in kontakter till portalerna ](/powerapps/maker/portals/configure/invite-contacts) i Power Apps-portal dokumentationen.

Innan du bjuder in en kund att gå med i kundportalen, se till att kunden är det [kontaktpost](/powerapps/maker/portals/configure/configure-contacts) är bättre och ställa på följande sätt:

1. Ange fältet **Företag** till den juridiska person i som du vill att kunden ska tillhöra i Supply Chain Management.
2. Ange fältet **Kontonummer** till kundens kontonummer som du vill att användaren ska ha i Supply Chain Management.

När en kontakt har skapats bör du kunna se den i Supply Chain Management.

Mer information finns i [Konfigurera en kontakt för användning på en portal](/powerapps/maker/portals/configure/configure-contacts) i dokumentationen till Power Apps-portalerna.

## <a name="out-of-box-web-roles-and-table-permissions"></a>Medföljande webbroller och tabellbehörigheter

Användarroller i Power Apps-portaler definieras av [webbroller](/powerapps/maker/portals/configure/create-web-roles) och [tabellbehörigheter](/powerapps/maker/portals/configure/assign-entity-permissions). Ett par roller har definierats för medföljande kundportalen. Du kan skapa nya roller och du kan ändra eller ta bort befintliga roller.

### <a name="out-of-box-web-roles"></a>Medföljande webbroller

I det här avsnittet beskrivs de webbroller som levereras med kundportalen.

Mer information om hur du ändrar medföljande användarrollerna finns i [skapa webbroller för portaler](/powerapps/maker/portals/configure/create-web-roles) och [lägga till postbaserad säkerhet med hjälp av tabellbehörigheter för portaler](/powerapps/maker/portals/configure/assign-entity-permissions) i dokumentationen för Power Apps-portaler.

#### <a name="administrator"></a>Administratör

Administratören läser och underhåller webbplatsen. Den här personen kommer att etablera och konfigurera kundportalen. Administratören har kvar portalens IT- och säkerhetsaspekter och ser till att allt fungerar utan problem. Administratören kan också anpassa och/eller ändra portalen genom att lägga till nya funktioner, skapa nya roller och mycket mer.

#### <a name="customer-representative"></a>Kundrepresentant

En kundrepresentant arbetar för ett kundföretag och ansvarar för hanteringen av de order som företaget placerar. Kundrepresentanten kan se alla order som har placerats för företaget och de användare som har placerat dem. Dessutom kan kundrepresentanten se information om det övergripande kontot och vilka kontakter som kan göra beställningar på uppdrag av detta konto.

#### <a name="authorized-users"></a>Behöriga användare

Behöriga användare kan göra beställningar och visa statusen för de order som de har placerat. De kan dock inte visa status för order som andra användare i företaget har placerat.

#### <a name="unauthorized-users"></a>Behöriga användare

Obehöriga användare kan inte visa data. De kan bara se allmän information, till exempel villkor och information om företaget som kör kundportalen.

#### <a name="example"></a>Exempel

Följande tabell visar vilka försäljningsorder som användarna i respektive webbroll kan se i systemet.

| Försäljningsorder | Administratör | Kundrepresentant för kund&nbsp;X | Behöriga användare: Jane | Behöriga användare: Sam | Behöriga användare: May |
|---|---|---|---|---|---|
| Kund&nbsp;X-beställare:&nbsp;Jane | Ja | Ja | Ja | Nej | Nej |
| Kund&nbsp;X-beställare:&nbsp;Sam | Ja | Ja | Nej | Ja | Nej |
| Kund&nbsp;Y-beställare:&nbsp;May | Ja | Nej | Nej | Nej | Nej |

> [!NOTE]
> Även om både Sam och Jane är kontakter som arbetar för kund X, kan de bara se de order som de själva har placerat och inget annat. Även om May kan ha en order i systemet, kan hon inte se ordningen i kundportalen eftersom hon är en obehörig användare. (Dessutom måste hon ha placerat ordern via en annan kanal än kundportalen.)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
