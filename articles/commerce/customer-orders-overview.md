---
title: Kundorder i kassa (POS)
description: Denna artikel innehåller information om kundorder i kassan (POS). Kundorder kallas även specialorder. Artikeln innehåller en diskussion kring relaterade parametrar och transaktionsflöden.
author: josaw1
ms.date: 08/02/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.custom:
- "260594"
- intro-internal
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 6051e0a18823b354dd9940aac70a086a0f317002
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850392"
---
# <a name="customer-orders-in-point-of-sale-pos"></a>Kundorder i kassa (POS)

[!include [banner](includes/banner.md)]

Denna artikel innehåller information om hur du skapar och hanterar kundorder i kassaappen (POS). Kundorder kan användas för att fånga in försäljningar där köpare vill hämta produkter på ett senare datum, hämta produkter från en annan plats eller låta artiklarna levereras till dem. 

I en handelsvärld kännetecknad av omnikanaler erbjuder många återförsäljare möjlighet till kundorder (eller specialorder) för att uppfylla kraven för olika produkter och utföranden. Här följer några vanliga scenarier:

- En kund vill att produkterna ska levereras till en specifik adress på ett visst datum.
- En kund vill hämta produkter från en butik eller en plats som skiljer sig från den butiken eller plats där kunden har köpt produkterna.
- En kund inom en butiksplats vill beställa produkter i dag och hämta dem från samma butiksplats på ett senare datum.

Återförsäljare använder också kundorder för att minimera förlorade försäljningar som lagerfel annars kan medföra, detta eftersom varorna kan levereras eller upphämtas vid en annan tidpunkt eller på en annan plats.

## <a name="set-up-customer-orders"></a>Skapa kundorder
Innan du försöker använda funktionen kundorder i POS måste du se till att slutföra alla konfigurationer som krävs i Commerce headquarters.

### <a name="configure-modes-of-delivery"></a>Konfigurera leveranssätt

Om du vill använda kundorder måste du konfigurera leveranssätt som butikskanalen kan använda. Du måste definiera minst ett leveranssätt som kan användas när orderrader levereras till en kund från en butik. Du måste också definiera minst ett leveranssätt som kan användas när orderrader hämtas från butiken. Leveranssätt definieras på sidan **leveranssätt** i Commerce headquarters. För mer information om hur du konfigurerar leveranssätt för Commerce-kanaler, se [Definiera leveranssätt](./configure-call-center-delivery.md#define-delivery-modes).

![Sidan för leveranssätt.](media/customer-order-modes-of-delivery.png)


### <a name="set-up-fulfillment-groups"></a>Ställ in uppfyllelsegrupper

Vissa butiker eller lagerställen kanske inte kan uppfylla kundorder. Genom att konfigurera uppfyllelsegrupper kan en organisation ange vilka butiker och lagerställen som ska visas som alternativ för användare som skapar kundorder i POS. Uppfyllelsegrupper konfigureras på sidan **uppfyllelsegrupper** . Organisationer kan skapa så många uppfyllelsegrupper som behövs. När en uppfyllelsegrupp har definierats länkar du den till en butik genom att välja **Tilldelning för uppfyllandegrupp** i fliken **Konfigurera** i åtgärdsfönstret på sidan **Butiker**.

I Commerce version 10.0.12 och senare kan organisationer ange huruvida lagerstället eller de kombinationer av lagerställen och butiker som har definierats i uppfyllelsegrupper kan användas för leverans, för upphämtning eller för både leverans och upphämtning. Detta medger ökad flexibilitet för företaget när detta ska avgöra vilka lagerställen som kan väljas när en kundorder skapas för artiklar som ska levereras, kontra vilka butiker som kan väljas när en kundorder skapas för artiklar som ska hämtas upp. Om du vill använda dessa konfigurationsalternativ aktiverar funktionen **Möjlighet att ange platser som "leverans" eller "upphämtning" aktiverad inom en uppfyllelsegrupp**. Om ett lagerställe som är länkat till en uppfyllelsegrupp inte är en butik kan det endast konfigureras som en leveransplats. Den kan inte användas när order för upphämtning har konfigurerats i POS.

![Sidan för uppfyllelsegrupper.](media/customer-order-fulfillment-group.png)

### <a name="configure-channel-settings"></a>Konfigurera kanalinställningar

När du arbetar med kundorder i POS måste du tänka på några av inställningarna för butikskanalen. Dessa inställningar finns på sidan **butiker** i Commerce headquarters.

- **Lagerställe** – Det här fältet anger det lager som kommer att användas vid minskning av lager för kontant- och transport- och kundhämtningsorder kopplade till denna butik. Vi rekommenderar att unika lagerställen används för varje butikskanal för att förhindra att affärslogikproblem uppstår i olika butiker.
- **Fraktlager** – Det här fältet anger det lager som kommer att användas vid minskning lager för kundorder som ska skickas från den valda butiken. Om funktionen **Möjlighet att ange platser som "Frakt" eller "Hämtning" aktiverat inom Uppfyllningsgrupp** har aktiverats i din miljö kan kassaanvändare välja ett specifikt lager att skicka från i kassa istället för att välja en butik att skicka från. När den funktionen är aktiverad används därför inte längre leveranslagerstället eftersom användaren plockar det specifika lagerstället som ordern skickas från när ordern skapas.
- **Tilldelning av uppfyllelsegrupp** – Välj den här knappen (på fliken **Inställningar** i åtgärdsfönstret) om du vill länka de uppfyllelsegrupper som refereras till visa alternativ för upphämtningsplatser eller leveransursprung när kundorder skapas i kassa.
- **Använd målbaserad moms** – detta alternativ anger om leveransadressen används för att bestämma vilken momsgrupp som ska användas på orderrader som levereras till kundens adress.
- **Använd kundbaserad moms** – det här alternativet anger om momsgruppen som definieras för kundens leveransadress används för att momsorder för kund som skapas i POS för leverans till kundens hem.

![Konfiguration för butikskanal på sidan Butiker.](media/customer-order-all-stores.png)

### <a name="set-up-customer-order-parameters"></a>Ställ in orderparametrar för kund

Innan du försöker skapa kundorder i POS måste du konfigurera lämpliga parametrar i Commerce headquarters. Dessa parametrar hittar du på fliken **kundorder** på sidan **Commerce-parametrar** .

- **Standard ordertyp** – du kan ange den ordertyp som tilldelas som standard till kundorder som har skapats i POS. Dessa kundorder kan vara antingen försäljningsorder eller offertorder. Oavsett standard ordertypen kan användarna fortfarande skapa både försäljningsorder och kundorder från kassa.
- **Standardinsättningsprocent** – Ange den procentandel av ordens totala belopp som kunden måste betala som en insättning innan en order kan bekräftas. Beroende på deras behörighet kan butiksintressena åsidosätta beloppet genom att använda åtgärden **Insättningsåsidosättning** i POS om åtgärden har konfigurerats för den aktuella transaktionens skärmlayout.
- **Upphämtningsläge** – Ange vilket leveranssätt som ska användas på försäljningsorderraderna som har konfigurerats för upphämtning i POS.
- **Framställt leveranssätt** – Ange det leveranssätt som ska användas på försäljningsorderrader som anses som utförda orderrader när en blandad kundvagn, där vissa rader kommer att hämtas eller levereras och andra rader utförs av kunden omedelbart.
- **Annulleringsavgift i procent** – Om en avgift ska användas när en kundorder annulleras, ange då avgiftsbeloppet.
- **Kod för annulleringsavgift** – Ange den debiteringskod för kundreskontra som ska användas när en annulleringsavgift tillämpas på annullerade kund order via POS. Avgiftskoden anger den ekonomiska bokföringslogiken för annulleringsbeloppet.
- **Leveransavgiftskod** – om alternativet **Använd avancerade automatiska tillägg** är inställt på **Ja** har den här parameterinställningen ingen effekt. Om alternativet är inställt på **Nej** kommer användarna att uppmanas att ange leveransavgift manuellt när de skapar kundorder i POS. Använd den här parametern om du vill mappa en avgiftskod för kundreskontra som ska kopplas till order när användarna anger en leveransavgift. Avgiftskoden anger den ekonomiska bokföringslogiken för leveransavgift.
- **Använd avancerade automatiska omkostnader** – Ställ in det här alternativet på **Ja** för att använda systemberäknade automatiska omkostnader när kundorder skapas i POS. Dessa automatiska debiteringar kan användas för att beräkna fraktavgifter eller andra order- eller artikelspecifika tillägg. För mer information om hur du konfigurerar och använder avancerade automatiska tillägg finns i [Avancerade automatiska avgifter för flera kanaler](./omni-auto-charges.md).

![Fliken kundorder på sidan Commerce-parametrar.](media/customer-order-parameters.png)

### <a name="update-transaction-screen-layouts-in-pos"></a>Uppdatera skärmlayouter för transaktioner i POS

Kontrollera att POS [skärmlayout](./pos-screen-layouts.md) är konfigurerad så att den stöder skapande och hantering av kundorder och att alla nödvändiga kassaåtgärder har konfigurerats. Nedan följer några av de kassaåtgärder som rekommenderas för att skapa och hantera kundorder:
- **Leverera alla produkter** – den här åtgärden används för att ange att alla rader i transaktionsvagnen ska levereras till en destination.
- **Leverera valda produkter** – den här åtgärden används för att ange att valda rader i transaktionsvagnen ska levereras till en destination.
- **Hämta alla produkter** – den här åtgärden används för att ange att alla rader i transaktionsvagnen ska hämtas från en vald butiksplats.
- **Hämta valda produkter** – den här åtgärden används för att ange att valda rader i transaktionsvagnen ska hämtas från en vald butiksplats.
- **Utföra alla produkter** – den här åtgärden används för att ange att alla rader i transaktionsvagnen ska utföras. Om den här åtgärden används i POS konverteras kundordern till en hämtköpstransaktioner.
- **Utför valda produkter** – den här åtgärden används för att ange att valda rader i transaktionsvagnen utförs av kunden vid inköpstillfället. Den här åtgärden är endast användbar i ett scenario med [hybridorder](./hybrid-customer-orders.md) .
- **Återkalla order** – den här åtgärden används för att söka efter och hämta kundorder så att kassaanvändare kan redigera, avbryta eller utföra slutförda åtgärder på dem efter behov.
- **Ändra leveranssätt** – den här åtgärden kan användas för att snabbt ändra leveranssättet för rader som redan har konfigurerats för leverans, utan att användarna måste gå igenom flödet "leverera alla produkter" eller "leverera valda produkter" igen.
- **Åsidosättning av insättningar** – denna åtgärd kan användas för att ändra insättningsbeloppet som kunden ska betala för den valda kundordern.

![Åtgärder i fönstret för kassatransaktion.](media/customer-order-screen-layout.png)

## <a name="work-with-customer-orders-in-pos"></a>Arbeta med kundorder i POS

> [!NOTE]
> Intäktsredovisningsfunktionen stöds för närvarande inte för användning i Commerce-kanaler (näthandel, POS, kundtjänst). Artiklar som konfigurerats med intäktsredovisning bör inte läggas till i order som skapats i Commerce-kanaler. 

### <a name="create-a-customer-order-for-products-that-will-be-shipped-to-the-customer"></a>Skapa en kundorder för produkter som ska levereras till kunden

1. I fönstret kassatransaktion lägger du till en kund i transaktionen.
2. Lägg till produkter i kundvagnen.
3. Välj **Leverera valda** eller **Leverera alla** för att leverera produkterna till en adress på kundkontot.
4. Välj alternativet för att skapa en kundorder.
5. Bekräfta eller ändra platsen "leverera från", bekräfta eller ändra leveransadressen och välj en leveransmetod.
6. Ange kundens leveransdatum som önskas.
7. Använd betalningsfunktionerna om du vill betala för alla beräknade belopp som förfaller, eller använd åtgärden **Insättningsåsidosättning** för att ändra förfallna belopp och sedan använda betalning.
8. Om den fullständiga ordersumman inte har betalats anger du ett kreditkort som ska hämtas för saldot som förfaller på ordern när den faktureras.

### <a name="create-a-customer-order-for-products-that-the-customer-will-pick-up"></a>Skapa en kundorder för produkter som kunden ska hämta

1. I fönstret kassatransaktion lägger du till en kund i transaktionen.
2. Lägg till produkter i kundvagnen.
3. Välj **Hämta valda** eller **Hämta alla** för att initiera konfigurationen av orderupphämtningen.
4. Välj det lagerställe där kunden ska hämta de valda produkterna.
5. Välj ett datum då artikeln ska hämtas upp.
6. Använd betalningsfunktionerna om du vill betala för alla beräknade belopp som förfaller, eller använd åtgärden **Insättningsåsidosättning** för att ändra förfallna belopp och sedan använda betalning.
7. Om det fullständiga orderbeloppet inte har betalats väljer du om kunden ska betala vid ett senare tillfälle (vid upphämtning), eller om ett kreditkort ska ställas i token nu och sedan användas och registreras vid tidpunkten för upphämtningen.

### <a name="edit-an-existing-customer-order"></a>Redigera en befintlig kundorder

Detaljhandelsorder som skapas i både online- eller butikskanalen kan återkallas och redigeras via POS efter behov.

> [!IMPORTANT]
> Det är inte alla butiksorder som kan redigeras via POS-programmet. Order som skapas i en kundtjänstkanal kan inte redigeras via POS om inställningen [Aktivera slutförande av order](./set-up-order-processing-options.md#enable-order-completion) är aktiverad för kundtjänstkanalen. För att säkerställa en korrekt betalningsprocess måste order som har sitt ursprung i en kundtjänstkanal och som använder funktionen för att aktivera slutförande av order redigeras via programmet i Commerce headquarters.

> [!NOTE]
> Vi rekommenderar att du inte redigerar order och offerter i kassan som har skapats av en icke-kundtjänstanvändare i Commerce headquarters. Dessa order och offerter använder inte Commerce-prismotorn, så om de redigeras i kassan, kommer Commerce-prismotorn att sätta pris igen.


I version 10.0.17 och senare kan användarna redigera berättigade order via POS-programmet, även om ordern är delvis uppfylld. Order som är helt fakturerade kan dock fortfarande inte redigeras via POS. Du kan aktivera denna funktion genom att slå på funktionen **Redigera delvis uppfyllda order i kassan** i arbetsytan **Funktionshantering**. Om den här funktionen inte är aktiverad, eller om du använder version 10.0.16 eller tidigare, kan användarna bara redigera kundorder i POS om ordern är helt öppen. Om funktionen är aktiverad kan du begränsa vilka butiker som kan redigera delvis uppfyllda order. Alternativet att inaktivera denna funktion för specifika butiker kan konfigureras via **Funktionsprofilen** på snabbfliken **Allmänt**.


1. Markera **återkalla order**.
2. Använd **Sök** för att ange filter för att hitta ordern och välj sedan **Verkställ**.
3. Markera ordern i resultatlistan och välj **Redigera**. Om knappen **Redigera** inte är tillgänglig är ordern i ett läge där den inte kan redigeras.
4. Gör nödvändiga ändringar av kundordern från transaktionsvagnen. Vissa ändringar kan vara förbjudna under redigeringen.
5. Slutför redigeringsprocessen genom att välja en betalningsåtgärd.
6. Om du vill avsluta redigeringsprocessen utan att spara ändringarna kan du använda åtgärden **Annullera transaktion**.

#### <a name="pricing-impact-when-orders-are-edited"></a>Prissättningspåverkan när order redigeras

När order placeras i kassan eller på en näthandelsplats för Commerce, åtar sig kunderna ett belopp. Detta belopp inkluderar ett pris och kan även omfatta en rabatt. En kund som lägger en order och sedan kontaktar kundtjänsten för att senare ändra ordern (t.ex. för att lägga till en artikel) har särskilda förväntningar på hur rabatter ska tillämpas. Även om erbjudandena på de befintliga orderraderna har förfallit, förväntar sig kunden att rabatterna som ursprungligen användes för raderna börjar gälla. Om ingen rabatt var i kraft när ordern ursprungligen gjordes, men rabatten har tillämpats sedan dess, förväntar kunden sig att den nya rabatten tillämpas på den ändrade ordern. Annars kanske kunden bara annullerar den befintliga ordern och sedan skapar en ny order där den nya rabatten tillämpas. Som det här scenariot visar måste priser och rabatter som kunderna har åtagit sig att behålla. Samtidigt måste kassaanvändare och kundtjänstanvändare ha flexibiliteten att räkna om priser och rabatter för försäljningsorderrader efter behov.

När order återkallas och redigeras i kassan betraktas priser och rabatter för de befintliga orderraderna som "låsta". Med andra ord ändras de inte, även om vissa orderrader annulleras eller ändras, eller så läggs nya orderrader till. Om du vill ändra priser och rabatter för befintliga försäljningsrader, måste kassaanvändaren välja **Omberäkna**. Prislåset tas sedan bort från de befintliga orderraderna. Innan Commerce version 10.0.21 finns den här kapaciteten inte tillgänglig i kundtjänsten. Eventuella ändringar på orderrader gör istället att priser och rabatter räknas om.

I Commerce version 10.0.21, en ny funktion som heter **Förhindra oavsiktlig prisberäkning för handelsorder** är tillgänglig i arbetsytan **Funktionshantering**. Den här funktionen är aktiverad som standard. När den är aktiverad är en ny **prislåst** egenskap tillgänglig för alla näthandelsorder. När order har slutförts för order som placeras från en kanal aktiveras egenskapen automatiskt (det vill säga kryssrutan markeras) för alla orderrader. Commerce-prissättningsmotorn exkluderar sedan dessa orderrader från alla pris- och rabattberäkningar. Om ordern redigeras exkluderas därför orderraderna som standard från pris- och rabattberäkningen. Däremot kan kundtjänstanvändare inaktivera egenskapen (det vill säga avmarkera kryssrutan) för en orderrad och sedan välja **Omberäkna** för att inkludera de befintliga orderraderna i prissättningsberäkningarna.

Även om de tillämpar en manuell rabatt på en befintlig försäljningsrad måste kundtjänstanvändare inaktivera den **prislåsta** egenskapen för försäljningsraden innan de använder den manuella rabatten.

Kundtjänstanvändare kan också inaktivera egenskapen **Prislås** för orderrader på en gång genom att välja **Ta bort prislås** i gruppen **Beräkna** på fliken **Försäljning** i åtgärdsfönstret på sidan **försäljningsorder**. I detta fall tas prislåset bort från alla orderrader utom rader som inte kan redigeras (med andra ord rader som har statusen **Delvis fakturerad** eller **Fakturerad**). När ändringarna i ordern har slutförts och skickats visas sedan prislåset på nytt för alla orderrader.

> [!IMPORTANT]
> När funktionen **Förhindra oavsiktlig prisberäkning för handelsorder aktiveras**, ignoreras inställningen av handelsavtalsutvärderingen i prissättningsarbetsflödena. Med andra ord visar inte dialogrutorna för handelsavtalsutvärdering det **prisrelaterade** avsnittet. Detta inträffar eftersom både inställningen av handelsavtalsutvärderingen och prislåsfunktionen har ett liknande syfte: att förhindra oavsiktliga prisändringar. Användarerfarenheten för handelsavtalsutvärdering fungerar dock inte bra för stora order där användarna måste välja en eller flera orderrader för omvärdering.

> [!NOTE]
> Egenskapen **Prislåst** kan bara inaktiveras för en eller flera valda rader när **kundtjänst** modulen används. Kassans beteende förblir oförändrat. Med andra ord kan kassaanvändaren inte låsa upp priser för valda orderrader. De kan dock välja **Omberäkna** om du vill ta bort prislåset från alla befintliga orderrader.

### <a name="cancel-a-customer-order"></a>Annullera en kundorder

1. Markera **återkalla order**.
2. Använd **Sök** för att ange filter för att hitta ordern och välj sedan **Verkställ**.
3. Markera ordern i resultatlistan och välj **Avbryt**. Om knappen **Avbryt** inte är tillgänglig är ordern i ett läge där den inte längre kan avbrytas.
4. Om du har konfigurerat annulleringsavgifter bekräftar du dem. Du kan justera annulleringsavgifterna innan du bekräftar dem om det behövs. 
5. I transaktionsvagnen slutför du annulleringen genom att välja en betalningsåtgärd. Om insättningar som betalats överskrider annulleringsavgiften kan återbetalningen betalas ut.
6. Om du vill avsluta annulleringsprocessen utan att spara ändringarna kan du använda åtgärden **Annullera transaktion**.

## <a name="finalizing-the-customer-order-shipment-or-pickup-from-pos"></a>Slutför kundorder utleverans eller hämtning från kassa

När en order har skapats hämtas artiklarna av kunden från en butiksplats eller levereras, beroende på orderns konfiguration. Mer information om den här processen finns i [dokumentationen för butiksorder uppfyllelse](./order-fulfillment-overview.md).

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Asynkront transaktionsflöde för kundorder

Kundorder kan skapas från POS i antingen synkront eller asynkront läge. Om du märker prestandaproblem eller fördröjningar av användare när du skapar kundorder i POS bör du överväga att aktivera asynkront orderskapande.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Aktivera skapande av kundorder i asynkront läge

1. I Commerce headquarters på sidan **Funktionsprofiler** välj funktionalitetsprofilen som motsvarar den butik som du vill konfigurera.
2. I snabbfliken **Allmänt** anger du alternativet för **Skapa kundorder i asynkront läge** som **Ja**.

När alternativet **Skapa kundorder i asynkront läge** är inställt på **Ja**, skapas kundorder alltid i asynkront läge, även om tjänsten för Retail Transaction Service (RTS) är tillgänglig. Om du anger detta alternativ som **Nej**, skapas kundorder alltid i synkront läge med hjälp av RTS. När kundorder skapas i asynkront läge hämtas de och skapas som detaljhandelstransaktioner i Commerce headquarters från Commerce hämtningsjobb (P). Motsvarande försäljningsorder för detaljhandelstransaktionerna skapas i Retail när **Synkronisera order** körs antingen manuellt eller via en batchprocess.

## <a name="additional-resources"></a>Ytterligare resurser

[Kombinerade kundorder](hybrid-customer-orders.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
