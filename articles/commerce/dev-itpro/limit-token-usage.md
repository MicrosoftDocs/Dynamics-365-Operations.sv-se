---
title: Begränsa användningen av betalningstoken
description: Den här artikeln beskriver funktionen som begränsar hur betalningstoken används i Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 10/20/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-09-20
ms.openlocfilehash: 8092ab0724f33f21759aa84d25e0bdcb5b2ad5dd
ms.sourcegitcommit: 6bd8822f7aa781d596b70956bead834117cf302c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/20/2022
ms.locfileid: "9709671"
---
# <a name="limit-payment-token-usage"></a>Begränsa användningen av betalningstoken

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

Den här artikeln beskriver funktionen som begränsar hur betalningstoken används i Microsoft Dynamics 365 Commerce. Tokenanvändningen begränsas till en försäljningsorders omfattning eller, om kundens tillåtelse beviljas, lagras som ett kort i en fil.

## <a name="key-terms"></a>Nyckeltermer

| Villkor | Beskrivning |
|---|---|
| Token | En refererad XML-blob i Dynamics 365-systemet där betalningsreferenser lagras för transaktionsändamål. |
| Kort för fil | En sparad kortreferenstoken som överenskommits för framtida användning i Dynamics 365-systemet eller betalningsgateway-systemet och som är specifik för en kunds konto. |

Gränserna för användning av betalningstoken gäller för alla miljöer där en betalningsgateway-tjänst där återkommande token används. Den medföljande [Dynamics 365 betalningskoppling för Adyen](adyen-connector.md) använder återkommande betalningstoken för att utföra efterföljande orderåtgärder, såsom auktoriseringsjusteringar och återinföringar.

För att hjälpa till att kontrollera hur dessa återkommande betalningstoken används i hela systemet begränsar funktionen **Begränsa användning av betalningstoken till ordersammanhang** begränsar användningen av en återkommande token till omfattningen av en försäljningsorder i systemet. När funktionen är aktiverad ändrar den om Commerce headquarters-användargränssnittet (UI) genom att uppdatera betalningsindatasidor och begränsa möjligheten att välja tidigare kundbetalningsreferenser för användning i nya transaktionsinstanser.

Den här funktionen underlättar användningen av regler för vissa betalningsutfärdare som Visa. I dess [Visa Core regler och Visa produkt- och tjänstregler](https://usa.visa.com/content/dam/VCOM/download/about-visa/visa-rules-public.pdf), Visa anger att användningen av betalningstoken bör begränsas till omfattningen av en transaktion om inte kortinnehavaren samtycker till annat.

Funktionen **Begränsa användning av betalningstoken till ordersammanhang** är endast relevant om du använder en betalningsgateway-tjänst som använder återkommande referenser för betalningstoken.

## <a name="enable-the-feature"></a>Aktivera funktionen

För att aktivera funktionen **Begränsa användning av betalningstoken till ordersammanhang** i Commerce headquarters för din miljö, gå till **Arbetsytor \> Funktionshantering** och välj **Begränsa användning av betalningstoken till ordersammanhang** i listan och välj sedan **Aktivera nu**.

## <a name="limit-payment-token-usage"></a>Begränsa användningen av betalningstoken

När funktionen är aktiverad kommer sidorna för Commerce headquarters som används för att fånga betalningsmetoder uppdatera hur de refererar till kundbetalningsmetoder som finns registrerade för kunden. Den här uppdateringen kommer främst att påverka två åtgärdsområden:

- Hur ett kundkort i filen anges på uppdrag av en kund
- Hur betalningsinformation sparas mot en kund för framtida betalningsposter för försäljningsorder

När en kund gör affärer mot Commerce-kanaler, lagras betalningsdetaljer med försäljningsordersammanhang. Försäljningsordersammanhanget begränsar betalningstoken så att den inte används som betalningsreferens mot kundposten på betalningssidor för nya eller redigerade försäljningsorderbetalningar i Commerce headquarters.

### <a name="payment-form-changes"></a>Ändringar i betalningsformulär

När en kundtjänstanvändare eller Commerce headquarters-användare tar en betalning för en kund mot en försäljningsorder, visar betalningssidan information om betalningsmetodurvalet. När funktionen **Begränsa användning av betalningstoken till ordersammanhang** är aktiverad, om en användare väljer plustecknet (**+**) på betalningssidan visas endast sparade "kort på fil"-poster. Ändringar kräver att användaren av kundtjänst eller Commerce headquarters ange den fullständiga betalningsinformationen som kunden angav när de fyllde i sidan **Ange kundbetalningsinformation** för den nya försäljningsordertransaktionen.

Listan med värden i fältet **Nummer** innehåller bara kortreferenser som är associerade med kunden som har kortet i filen. Där filtreras eventuella tidigare betalningsreferenser som inte är begränsade till en försäljningsorder.

Plustecknet (**+**) under fältet **Nummer** förblir tillgänglig och kan användas för att ange den betalningsinformation som kunden angett för transaktionen som är kopplad till försäljningsordern som behandlas.

### <a name="how-cards-on-file-work"></a>Hur kort på fil fungerar

När funktionen **Begränsa användning av betalningstoken till ordersammanhang** är aktiverad, är ett registrerat kort en återkommande betalningstoken som sparas mot en kundpost och är inte begränsad till omfattningen av en försäljningsorder. Ett registrerat kort gör det möjligt att ange snabbreferens för användare i Commerce headquarters när de fyller i betalningssidan för en ny betalning för försäljningsorder. Den här tokenreferensen kan bara användas i Dynamics 365-miljön. För onlinekanaler som använder en betalningsgateway-tjänst som låter användare spara en betalningsmetod för framtida användning i betalningen iFrame-modulen lagrar betalningsgateway säkert dessa referenser som en separat referens till det registrerade Dynamics 365-kortet.

Om till exempel Dynamics 365 Commerce betalningskoppling för Adyen används i en onlinekanal, kunder som anger sina kreditkortsuppgifter i betalningen iFrame-modulen ser endast gatewaytjänstens sparade kortreferenser för deras nästa onlineköp när de är autentiserade. De ser inte Dynamics 365-kortet i miljön som ett alternativ i betalningsmodulen iFrame. När kunder lägger en order via kundtjänsten visas på liknande sätt inte deras sparade onlinekortsreferenser som alternativ för kundtjänstanvändaren. Kundtjänstanvändaren ser bara tidigare kort på filreferenser från Dynamics 365-systemet (enligt kundens avtal) för att spara för framtida order.

Användare i Commerce headquarters kan spara ett kort i filen för en kund genom att gå till **Butik och handel \> Kunder** och välja kundkontoposten. I området **Kund \> Konfigurera** kan användare som har behörighet att bearbeta betalningssidor använda inmatningssidan **Kreditkort** för att ange ett betalkort som kommer att lagras för framtida transaktioner. Den här operationen sparar tid när framtida försäljningsorderbetalningar bearbetas för kunden. Kundtjänstanvändare och Commerce headquarters-användare bör endast registrera kortet på filkortsdetaljer om kunden förbinder sig att använda kortreferensen för framtida transaktioner.

Om kryssrutan **Spara för framtida bruk** visas längst ned på betalningssidorna för Commerce headquarters kan användarna spara kortet i filen och använda det senare. Den här kryssrutan ska bara användas om kunden går med på att använda kortet i filen för framtida transaktioner. Du kan visa eller begränsa kryssrutan **Spara för framtida bruk** genom att använda alternativet **Tillåt registrerat kundkort** på fliken **Betalning** på sidan **Parametrar för kundtjänst** i Commerce headquarters. När det här alternativet är inställt på **Ja** kan användare av Commerce headquarters som har behörighet att bearbeta betalningssidor spara ett registrerat kort genom att använda kryssrutan **Spara för framtida bruk**. Om alternativet ställs in på **Nej** är kryssrutan inte tillgänglig för Commerce headquarters-användare som har behörighet att bearbeta betalningssidor. Alternativet **Tillåt registrerat kundkort** kan användas om ditt företag vill begränsa användningen av återkommande tokens i Commerce headquarters, men det ännu inte vill tillåta att ett registrerat kort sparas utan en procedur för att säkerställa att kundens samtycke beviljas.

### <a name="commerce-headquarters-pages-where-the-recurring-token-restrictions-are-enforced"></a>Commerce headquarters-sidor där de återkommande tokenbegränsningarna har tillämpas

Begränsning av token påverkar följande områden i Commerce headquarters när funktionen är aktiverad:

- Kundbetalningsinformation vid **Försäljningsorder \> Betalningar \> Ange kundbetalning**
- Kontinuitetsordrar
- Avbetalningar
- Kundreskontra för kreditkortsbetalningar

### <a name="manage-payment-tokens-archiving-or-removal"></a>Hantera betalningstoken (arkivering eller borttagning)

Betalningstoken som skapades före funktionsflaggan **Begränsa användning av betalningstoken till ordersammanhang** var aktiverad (eller medan funktionen var inaktiverad) kommer att förbli "oavgränsad" i systemet och kan refereras till i urvalslistor på Commerce headquarters betalningssida. Dessa tokens kan tas bort regelbundet på två sätt i Commerce headquarters:

- Använd sidan **Arkivera data för kreditkortstransaktion** när du vill ställa in ett jobb som regelbundet rensar eller arkiverar betalningstoken. Om du ställer in alternativet **Radera data utan arkivering** till **Ja** raderas de token som uppfyller **Lägsta transaktionsålder (i dagar)**. Mer information finns i [Arkivera data för kreditkortstransaktion](archive-cc-data.md).
- Använd den nya sidan **Rensa kreditkortstoken** (**Kundreskontra \> Förfrågningar och rapporter \> Rensa \> Rensa kreditkortstoken**), som gör att du kan köra eller ställa in ett batchjobb som tar bort betalningstoken. Ställ in följande parametrar:

    - Värdet **Lägsta tokenålder i dagar** måste vara 90 dagar eller mer.
    - Inställningar **Kör i bakgrunden** kan användas för att definiera inställningar för **Återkommande** eller **Aviseringar**.
    - En batchgrupp kan tilldelas för att köra uppgiften för en viss grupp.
    - Om alternativet **Privat** är inställt på **Ja**, kan bara användaren som skapar jobbet köra det.
    - Inställningen **Ja** för det **viktiga jobbet** säkerställer att systemet spårar jobbets status.

Borttagna tokens kan inte hämtas. Ange fältet **Lägsta tokenålder i dagar** till ett intervall som passar den längsta pågående transaktionslivslängden för din miljö (från auktorisering till insamling eller återbetalning).

## <a name="additional-resources"></a>Ytterligare resurser

[Vanliga frågor om betalningar](payments-retail.md)

[Kassamodul](../add-checkout-module.md)

[Betalningsmodul](../payment-module.md)
