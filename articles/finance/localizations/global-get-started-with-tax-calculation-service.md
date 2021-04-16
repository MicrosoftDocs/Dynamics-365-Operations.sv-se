---
title: Kom igång med tillägget för momsberäkning
description: Det här avsnittet förklarar hur du ställer in tillägget för momsberäkning.
author: wangchen
ms.date: 03/10/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 835ae33fba31d4bccb218969aa9aa61eaa7a3061
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832603"
---
# <a name="get-started-with-the-tax-calculation-add-in-preview"></a>Kom igång med tillägget för momsberäkning (förhandsversion)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Det här avsnittet innehåller information om hur du kommer igång med tillägget för momsberäkning. Först guidar vi dig genom konfigurationsstegen i Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS) och Dynamics 365 Finance och Dynamics 365 Supply Chain Management. Därefter granskas den gemensamma processen för att använda tillägget för momsberäkning i transaktioner för Finance och Supply Chain Management.

Inställningen består av fyra huvudsteg:

1. I LCS installerar du tillägget för momsberäkning.
2. Ställ in funktionen för momsberäkning i RCS. Denna inställning är inte specifika för en juridisk person. Det kan delas av juridiska personer i Finance och Supply Chain Management.
3. I Finance och Supply Chain Management ställer du in parametrar för momsberäkningar per juridisk person.
4. I Finance och Supply Chain Management skapar du transaktioner som försäljningsorder och använder tillägget för momsberäkningar för att bestämma och beräkna moms.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra procedurerna i detta ämne måste följande förutsättningar finnas på plats:

- Du har tillgång till ditt LCS-konto och har distribuerat ett LCS-projekt med en nivå 2-miljö (eller högre) som kör Dynamics 365 version 10.0.18 eller senare.
- Du har åtkomst till ditt RCS-konto.
- Du har kontaktat Microsoft för att aktivera flyget i din distribuerade Finance eller Supply Chain Management-miljö.

## <a name="set-up-the-tax-calculation-add-in-in-lcs"></a>Ställ in tillägget för momsberäkning i LCS

1. Logga in på [LCS](https://lcs.dynamics.com)
2. Slutför inställningarna för Microsoft Power Platform-integration. Mer information finns i [översikt över tillägg](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Välj en av dina distribuerade icke-produktionsmiljöer och välj sedan **Installera ett nytt tillägg**.
4. Välj **Momsberäkning (förhandsgranskning)**.
5. Läs och godkänn villkoren och välj sedan **Installera**.

## <a name="set-up-the-tax-calculation-add-in-in-rcs"></a>Ställ in tillägget för momsberäkning i RCS

Stegen i det här avsnittet är inte relaterade till någon specifik juridisk person. Du måste bara genomföra den här proceduren en gång och du kan genomföra den i alla juridiska personer i RCS.

1. Logga in på [RCS](https://marketing.configure.global.dynamics.com/).
2. I arbetsytan Finance i **Elektronisk rapportering**, lägg till ny konfigurationsleverantör. Använd ditt företagsnamn som namn på leverantören. Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Välj den konfigurationsprovider som du just skapat och välj sedan **Ställ in aktiv**.
4. Välj konfigurationsprovidern **Microsoft** och välj **Databaser**.
5. Välj **Typ** i fältet **Global**.
6. Välj **Öppen**.
7. Gå till **Skattedatamodell**, expandera filträdet och välj sedan **Momskonfiguration - Europa**.
8. Välj den senaste versionen och sedan **Importera**.
9. Återgå till arbetsytan **Globaliseringsfunktioner (förhandsgranskning)**, välj **funktioner**, välj **Momsberäkning** och välj sedan **Lägg till**.
10. Välj en av följande funktionstyper:

    - **Ny funktion** – Skapa en funktionsinställning som har tomt innehåll.
    - **Baserat på befintlig funktion** – Skapa en funktion från en befintlig funktion och kopiera innehållet från de befintliga funktionsinställningarna.

11. Ange ett namn på och en beskrivning för den nya funktionen och välj sedan **Skapa funktion**.

    När funktionen har skapats skapas ett utkast av den automatiskt.

12. Välj utkastversion för funktionen och **redigera**. Sidan **Inställning av momsberäkning** fylls i.
13. Välj **Konfigurationsversion**. Du bör se den konfigurationsversion som du importerade i steg 8.

    Microsoft tillhandahåller en standardkonfiguration för tillägget för momsberäkning. Den här konfigurationen täcker de flesta kraven för momsberäkningsbeteenden. Den kommer att uppdateras baserat på återrapportering från marknaden. Om du måste utöka konfigurationen för att uppfylla specifika krav, se [Hur man bygger tillägg i momstjänst](https://go.microsoft.com/fwlink/?linkid=2138483) för information om hur du skapar och väljer din egen momskonfiguration.

    När du har valt **Konfigurationsversion** visas flera ytterligare flikar:

    - **Momskoder** – Den här fliken är obligatorisk för momsberäkningstjänsten. Den används för att underhålla huvuddata för momskoder. Alla momskoder som skapas på den här fliken synkroniseras automatiskt till Finance när du aktiverar den aktuella versionen av momsfunktionsinställningarna för den juridiska personen.
    - **Tillämplighet momskoder** – Den här fliken är obligatorisk för momsberäkningstillägget. Den används för att definiera en matris som bestämmer momskod, momsgrupp och artikelmomsgrupp. Momskoden som fastställs används för att beräkna momsbeloppet. Värdena för fälten **Momskod**, **Momsgrupp** och **Artikelmomsgrupp** returneras till Finance.
    - **Tillämplighet för momsregistreringsnummer för kund** – Den här fliken är valfri för momsberäkningstillägget. Om du har flera momsregistreringsnummer för en kund kan tillägget för momsberäkning automatiskt bestämma korrekt momsregistreringsnummer. I matrisen på den här fliken definierar du de regler som tillägget använder för att bestämma. Annars fortsätter Finance och Supply Chain Management att använda standardregistreringsnumret på momsunderlag för försäljningstransaktioner.
    - **Tillämplighet för momsregistreringsnummer för leverantör** – Den här fliken är valfri för momsberäkningstillägget. Om du har flera momsregistreringsnummer för en leverantör kan tillägget för momsberäkning automatiskt bestämma korrekt momsregistreringsnummer. I matrisen på den här fliken definierar du de regler som tillägget använder för att bestämma. Annars fortsätter Finance och Supply Chain Management att använda standardregistreringsnumret på momsunderlag för inköpstransaktioner.
    - **Tillämplighet för listkoder** – Den här fliken är valfri för momsberäkningstillägget. Det kan hjälpa till att automatiskt bestämma värdet på fältet **Listkod** genom mer flexibla och konfigurerbara regler. I matrisen på den här fliken definierar du de regler som tillägget använder för att bestämma. Annars fortsätter Finance och Supply Chain Management att använda standardkod på momsunderlag.

14. På fliken **Momskoder**, välj **Lägg till** och ange momskoden och en beskrivning.
15. Välj **Momskomponent**. Momskomponenten är en grupp med beräkningsmetoder för moms som har definierats i den tidigare versionen av den valda momskonfigurationen. Följande momskomponenter är tillgängliga:

    - Efter nettobelopp 
    - Efter bruttobelopp
    - Efter antal
    - Efter marginal
    - Moms på moms

16. Välj **Spara**. Fler fält blir tillgängliga baserat på den momskomponent som du väljer.
17. Använd följande alternativ för att identifiera momskodens karaktär:

    - Är undantagen
    - Är importavgift
    - Är återförd avgift
    - Exkludera i beräkning av basbelopp

    För ett momsscenario ställer du in en enda momskod som har en positiv momssats och markerar den som **Är importavgift**.

    För ett scenario med återförd moms ställer du in två momskoder, varav en har en positiv momssats och den andra har en negativ momssats men samma momsvärde. Markera den negativa momskoden som **Är återförd moms**. För mer information om lösningen för återförd moms i Finance, se [Mekanism för återförd moms för VAT/GST-schema](emea-reverse-charge.md).
    
    För vissa momstyper som ska uteslutas i beräkningen av momsbasbeloppet för transaktioner inklusive priser, som tull i vissa länder, markerar du kryssrutan **Exkludera i beräkning av basbelopp**.

    Behåll momssatser och momsbeloppsgränser för den här momskoden.

18. Upprepa steg 14 till och med 17 för att lägga till alla andra momskoder som krävs.
19. På fliken **Tillämplighet för momskoder** markerar du de kolumner som krävs för att fastställa rätt momskod, och väljer sedan **Lägg till**.
20. Ange eller välj värden för varje kolumn. Fälten **Momskod**, **Momsgrupp** och **Artikelmomsgrupp** kommer att vara resultatet av denna matris.
21. Upprepa steg 19 till och med 20 om du vill ställa in tillämplighet för momsregistreringsnummer för kund, momsregistreringsnummer för leverantör och listkoder.
22. Markera **Spara** och stäng sedan sidan.
23. Välj **Ändra status** \> **Slutför**. När statusen har ändrats till **Slutför** kan versionen inte längre redigeras.
24. Välj **Ändra status** \> **Publicera**. Den här versionen av momsfunktionens inställningar förs över till den globala databasen och visas för varje juridisk person i Finance.

## <a name="dynamics-365-setup"></a>Inställningar för Dynamics 365

När du har slutfört inställningarna i RCS, enligt beskrivningen i föregående avsnitt, kommer du att ha en publicerade version av momsfunktionen. Följ dessa steg för att konfigurera momsberäkningstillägget i Finance.

Inställningarna i det här avsnittet görs av en juridisk person. Du måste konfigurera den för varje juridisk person som du vill aktivera tillägget momsberäkning för i Finance.

1. I Finance, gå till **Moms** \> **Inställningar** \> **Momsinställning** \> **Inställning av momsberäkningstillägg (förhandsversion)**.
2. Ange följande fält på fliken **Allmänt**:

    - **Aktivera momsberäkningstillägget** – Markera den här kryssrutan om du vill aktivera momsberäkningstillägget för den juridiska personen. Om momsberäkningstillägget inte är aktiverat för den aktuella juridiska personen, fortsätter den juridiska personen att använda den befintliga skattemotorn för att bestämma och beräkna moms.
    - **Funktionsinställningar** – Välj en publicerade momsfunktionsinställning och -version för den juridiska personen. Mer information om hur du ställer in och slutför en publicerade momsfunktionen finns i föregående avsnitt i det här avsnittet.
    - **Affärsprocess** – Välj de affärsprocesser som ska aktiveras för momsberäkningstillägget.
    - **Aktivera justering av momskod** – Ange det här alternativet till **Ja** för att aktivera momskodsjusteringar på momssidan.

3. På fliken **Beräkning**, definiera den förväntade avrundningsregeln för den juridiska enheten.
4. På fliken **Felhantering**, definiera den förväntade felhanteringsmetoden för den juridiska enheten. Det finns tre alternativ för varje resultatkod från momsberäkningstillägget:

    - Nr
    - Varning
    - Fel

5. Spara inställningar av momsberäkningstillägget.
6. Upprepa steg 1 till och med 5 för varje ytterligare juridisk person.

## <a name="transaction-processing"></a>Bearbetning av transaktion

När du har slutfört alla inställningsprocedurer kan du använda momsberäkningstillägget för att bestämma och beräkna moms i Finance. Stegen för att bearbeta transaktioner förblir desamma. Följande transaktioner stöds i Finance-version 10.0.18:

- Försäljningsprocess

    - Försäljningsoffert
    - Försäljningsorder
    - Bekräftelse
    - Plocklista
    - Följesedel
    - Försäljningsfaktura
    - Kreditfaktura
    - Returorder
    - Huvudtillägg
    - Radtillägg

- Inköpsprocess

    - Inköpsorder
    - Bekräftelse
    - Inleveranslista
    - Produktinleverans
    - Inköpsfaktura
    - Huvudtillägg
    - Radtillägg
    - Kreditfaktura
    - Returorder
    - Inköpsrekvisition
    - Avgift för inköpsrekvisitionsrad
    - Anbudsförfrågan
    - Avgift för anbudsförfråganhuvudet
    - Avgift för rader i anbudsförfrågan

- Lagerprocess

    - Överföringsorder - leverera
    - Överföringsorder - ta emot
