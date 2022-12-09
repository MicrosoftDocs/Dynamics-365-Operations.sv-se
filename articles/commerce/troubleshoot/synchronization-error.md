---
title: Problem med asynkron ordersynkronisering
description: I den här artikeln beskrivs vanliga orsaker till att asynkrona order skapas fel i Microsoft Dynamics 365 Commerce och ger felsökningssteg som hjälper systemanvändare och partner att förstå vad som gick fel.
author: Shajain
ms.date: 11/30/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: 27bccced3c07149fe1842524660447a49f86f3fc
ms.sourcegitcommit: 2804b05214c87f76457608b5db072582ff339852
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/01/2022
ms.locfileid: "9815767"
---
# <a name="asynchronous-order-synchronization-issues"></a>Problem med asynkron ordersynkronisering

[!include [banner](../../includes/banner.md)]

I den här artikeln beskrivs vanliga orsaker till att asynkrona order skapas fel i Microsoft Dynamics 365 Commerce och ger felsökningssteg som hjälper systemanvändare och partner att förstå vad som gick fel.

## <a name="symptom"></a>Symtom

Asynkrona order som skapas från Dynamics 365 Commerce e-handel eller kassa (POS) återspeglas inte i Commerce headquarters.

## <a name="troubleshooting"></a>Felsökning

Skapande av order kan misslyckas i administration av olika anledningar, beroende på vilken fas ordergenereringen misslyckas under. Följande felsökningssteg går igenom de möjliga rotorsakerna.

### <a name="validate-that-the-transaction-related-to-the-asynchronous-order-has-reached-headquarters"></a>Validera att transaktionen som hör till den asynkrona ordern har nått fram till huvudkontoret

För e-handelsorder, i administration går du till **Butik och handel \> Förfrågningar och rapporter \> Onlinebutikstransaktioner**. Om du har ett bekräftelsenummer för ordern filtrerar du transaktionerna genom att ange bekräftelsenumret i fältet **Kanalreferens-ID** . Om du inte har bekräftelsenumret filtrerar du transaktionerna genom att ange kundkontonumret.

För kassaorder öppnar du sidan **Butikstransaktioner** och filtrerar posterna efter inleveransnummer eller kundkontonummer. Om transaktionen inte går att hitta kör du transaktionsjobbet för **P-0001**-kanalen , som synkroniserar transaktioner från kanaler till huvudkontor. Om **P-0001**-jobbet misslyckas öppnar du en supportbegäran för jobbfelet.  Om **P-0001**-jobbet lyckas, men transaktionerna fortfarande inte visas i administration, öppnar du en supportbegäran som innehåller relevant information.
 
### <a name="check-the-synchronization-status-if-the-transaction-is-present-in-headquarters-but-isnt-linked-with-a-sales-order"></a>Kontrollera synkroniseringsstatusen om transaktionen finns i administration men inte är kopplad till en försäljningsorder

Om transaktionen finns i administration, men försäljningsordern inte har skapats, öppnar du sidan **Transaktioner för online-butik** och väljer snabbflik för **synkroniseringsstatus**. Om jobbet **Synkronisera order** har försökt att synkronisera den här transaktionen ska fältet **Pågående orderstatus** visa status **Lyckats** eller **Misslyckats**. Om statusen har **lyckats** måste försäljningsorder fältet finnas med på transaktionen. Om statusvärdet är **misslyckat** kan du visa felinformationen i fältet **Information om orderfel** på snabbfliken **Synkroniseringsstatus**. Om inget av dessa statusar visas har inget försök gjorts till att bearbeta transaktionen. I det här fallet kan du välja **Synkronisera order** längst upp på sidan för att köra synkroniseringsjobbet.

Se till att jobbet **Synkronisera order** är tidsplanerat att köras periodiskt, så att asynkrona transaktioner kan skapas som order i administration.

Följande avsnitt innehåller information om vissa vanliga fel och de föreslagna korrigeringarna.

#### <a name="the-order-error-details-field-shows-the-following-error-message-number-sequence-has-been-exceeded"></a>I fältet för orderfelinformation visas följande felmeddelande: "Nummerserien har överskridits"

Nummerserier används för att skapa försäljningsorder i administration. Om alla nummer som tillåts för en nummerserie inte visas, genereras det här felmeddelandet automatiskt i systemet. Den nummerserie som används för att skapa försäljningsorder hittar du på **Kundfordringar parametrar \> Nummerserier \> Försäljningsorder**. Du rättar till felet genom att korrigera den befintliga nummerserien eller ersätta den med en ny nummerserie.

#### <a name="the-order-error-details-field-shows-the-following-error-message-there-must-be-a-default-payment-service-to-process-credit-card-transactions"></a>Fältet Information om orderfel visas följande felmeddelande: "Det måste finnas en standardbetalningstjänst för att bearbeta kreditkortstransaktioner"

Du rättar till felet genom att bekräfta att en standardbetalning har definierats i huvudkontoret. Om ingen standardbetalning är definierad måste du definiera en. Gå till **Kundreskontra \> Betalningsinställning \> Betalningstjänster** och se till att alternativet **Standardföretag för nya kreditkort** anges **Ja** för en betalningstjänst.
    
#### <a name="the-order-error-details-field-shows-an-account-structure-error-message"></a>Felinformationsfältet för order visar ett felmeddelande om kontostrukturen

Texten i felmeddelandet för kontostrukturen kan variera, vilket följande exempel visar. Felen har dock en gemensam rotorsak som är relaterad till kontostrukturkonfigurationen.

- "Bokföringsresultat för journalbatchnummer 0009656328 verifikation ARP-000959899 1,00 för verifikationsverifikation som ARP-000959899 i företaget usrt kommer att bokföras som en över- eller underbetalning"
- "Bokföringsresultat för journalbatchnummer 0009656328 Verifikation ARP-000959899 Verifikation ARP-000959901 Kontostruktur, för kombinationen 618160, giltigt inte för redovisning av delat huvudkonto för företag"
- "Bokföringsresultat för journalbatchnummer 0009656328 Verifikation ARP-000959899 Verifikation ARP-000959901 Rapporterat från företagets konton"
- "Bokföringsresultat för journalbatchnummer 0009656328 verifikation ARP-000959899 bokföring har annullerats"
    
Du rättar till dessa fel genom att granska kontostrukturerna så att de är korrekta. Mer information finns i [Konfigurera kontostruktur](/dynamics365/finance/general-ledger/configure-account-structures).
    
När felet är åtgärdat, välj den misslyckade transaktionen och välj sedan **Synkronisera order** längst upp på sidan för att köra synkroniseringsjobbet.
    
#### <a name="other-types-of-errors-that-might-require-the-transaction-data-to-be-fixed"></a>Andra typer av fel som kan kräva att transaktionsdata fastställs

Om du vill åtgärda andra typer av fel som kanske kräver att transaktionsdata korrigeras, kan du använda funktionen "redigera och granska transaktioner". Mer information finns i [Redigera och granska transaktioner](../edit-order-trans.md).
