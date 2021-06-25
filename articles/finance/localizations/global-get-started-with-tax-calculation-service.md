---
title: Kom i gång med skatteberäkning
description: Detta ämne förklarar hur du ställer in skatteberäkningen.
author: wangchen
ms.date: 05/17/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: e72b81d4a109db2dd8b4c6ca2ca0b030220e25f3
ms.sourcegitcommit: 60afcd85b3b5b9e5e8981ebbb57c0161cf05e54b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216729"
---
# <a name="get-started-with-the-tax-calculation-preview"></a>Kom igång med skatteberäkning (förhandsversion)

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Detta ämne innehåller information om hur du kommer igång med skatteberäkningen. Först guidar vi dig genom konfigurationsstegen i Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS) och Dynamics 365 Finance och Dynamics 365 Supply Chain Management. Därefter granskas den gemensamma processen för att använda funktionerna för skatteberäkning i transaktioner för Finance och Supply Chain Management.

Inställningen består av fyra huvudsteg:

1. Installera skatteberäkning i LCS.
2. Ställ in funktionen för skatteberäkning i RCS. Denna inställning är inte specifika för en juridisk person. Det kan delas av juridiska personer i Finance och Supply Chain Management.
3. I Finance och Supply Chain Management ställer du in parametrar för skatteberäkningar per juridisk person.
4. I Finance och Supply Chain Management skapar du transaktioner som exempelvis försäljningsorder och använder skatteberäkningen för att bestämma och beräkna skatter.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra procedurerna i detta ämne måste följande förutsättningar finnas på plats:

- Du har tillgång till ditt LCS-konto och har distribuerat ett LCS-projekt med en nivå 2-miljö (eller högre) som kör Dynamics 365 version 10.0.18 med [KB4616360](https://fix.lcs.dynamics.com/Issue/Details?kb=4616360&bugId=568738&dbType=3&qc=1f1c04ff39adad74ef871f539e8d73e14c1893ef7cc4b6e3f7d5c5864ec2781a), eller senare.
- Du har åtkomst till ditt RCS-konto.
- Du har kontaktat Microsoft för att aktivera flyget i din distribuerade Finance eller Supply Chain Management-miljö.

## <a name="set-up-tax-calculation-in-lcs"></a>Konfigurera skatteberäkning i LCS.

1. Logga in på [LCS](https://lcs.dynamics.com)
2. Slutför inställningarna för Microsoft Power Platform-integration. Mer information finns i [översikt över tillägg](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Välj en av dina distribuerade icke-produktionsmiljöer och välj sedan **Installera ett nytt tillägg**.
4. Välj **Skatteberäkning (förhandsversion)**.
5. Läs och godkänn villkoren och välj sedan **Installera**.

## <a name="set-up-tax-calculation-in-rcs"></a>Konfigurera skatteberäkning i RCS.

Stegen i det här avsnittet är inte relaterade till någon specifik juridisk person. Du måste bara genomföra den här proceduren en gång och du kan genomföra den i alla juridiska personer i RCS.

1. Logga in på [RCS](https://marketing.configure.global.dynamics.com/).
2. I arbetsytan Finance i **Elektronisk rapportering** lägger du till en ny konfigurationsleverantör. Använd ditt företagsnamn som namn på leverantören. Mer information finns i [Skapa konfigurationsleverantörer och markera dem som aktiva](../../fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Välj den konfigurationsprovider som du just skapat och välj sedan **Ställ in aktiv**.
4. Välj konfigurationsprovidern **Microsoft** och välj **Databaser**.
5. Välj **Typ** i fältet **Global**.
6. Välj **Öppen**.
7. Gå till **Skattedatamodell**, expandera filträdet och välj sedan **Skattekonfiguration**.
8. Välj den senaste versionen och sedan **Importera**.
9. Återgå till arbetsytan **Globaliseringsfunktioner (förhandsgranskning)**, välj **Funktioner**, välj panelen **Skatteberäkning** och sedan **Lägg till**.
10. Välj en av följande funktionstyper:

    - **Ny funktion** – Skapa en funktionsinställning som har tomt innehåll.
    - **Baserat på befintlig funktion** – Skapa en funktion från en befintlig funktion och kopiera innehållet från de befintliga funktionsinställningarna.

11. Ange ett namn på och en beskrivning för den nya funktionen och välj sedan **Skapa funktion**.

    När funktionen har skapats skapas ett utkast av den automatiskt.

12. Välj utkastversion för funktionen och **redigera**. Sidan **Inställning av skatteberäkning** fylls i.
13. Välj **Konfigurationsversion**. Du bör se den konfigurationsversion som du importerade i steg 8.

    Microsoft tillhandahåller en standardkonfiguration för tillägget för skatteberäkning. Den här konfigurationen täcker de flesta kraven för skatteberäkningsbeteenden. Den kommer att uppdateras baserat på återrapportering från marknaden. Om du måste utöka konfigurationen för att uppfylla specifika krav, se [Hur man bygger tillägg i skattetjänst](./tax-service-add-data-fields-tax-integration-by-extension.md) för information om hur du skapar och väljer din egen skattekonfiguration.

    När du har valt **Konfigurationsversion** visas flera ytterligare flikar:

    - **Skattekoder** – Denna flik är obligatorisk. Den används för att underhålla huvuddata för skattekoder. Alla skattekoder som skapas på den här fliken synkroniseras automatiskt till Finance när du aktiverar den aktuella versionen av skattefunktionsinställningarna för den juridiska personen.
    - **Tillämplighet för skattekoder** – Denna flik är obligatorisk. Den används för att definiera en matris som bestämmer skattekod, skattegrupp och artikelskattegrupp. Skattekoden som fastställs används för att beräkna skattebeloppet. Värdena för fälten **Skattekod**, **Skattegrupp** och **Artikelmomsgrupp** returneras till Finance.
    - **Tillämplighet för skatteregistreringsnummer för kund** – Denna flik är valfri. Om du har flera skatteregistreringsnummer för en enda kund kan skatteberäkningen automatiskt bestämma korrekt skatteregistreringsnummer. I matrisen på den här fliken definierar du de regler som tillägget använder för att bestämma. Annars fortsätter Finance och Supply Chain Management att använda standardregistreringsnumret på skatteunderlag för försäljningstransaktioner.
    - **Tillämplighet för skatteregistreringsnummer för leverantör** – Denna flik är valfri. Om du har flera skatteregistreringsnummer för en enda leverantör kan skatteberäkningen automatiskt bestämma korrekt skatteregistreringsnummer. I matrisen på den här fliken definierar du de regler som tillägget använder för att bestämma. Annars fortsätter Finance och Supply Chain Management att använda standardregistreringsnumret på skatteunderlag för inköpstransaktioner.
    - **Tillämplighet för listkod** – Denna flik är valfri. Det kan hjälpa till att automatiskt bestämma värdet på fältet **Listkod** genom mer flexibla och konfigurerbara regler. I matrisen på den här fliken kan du definiera de regler som tillägget använder för att bestämma. Annars fortsätter Finance och Supply Chain Management att använda standardkod på skatteunderlag.

14. På fliken **Skattekoder**, välj **Lägg till** och ange skattekoden och en beskrivning.
15. Välj **Skattekomponent**. Skattekomponenten är en grupp med beräkningsmetoder för skatt som har definierats i den tidigare versionen av den valda skattekonfigurationen. Följande skattekomponenter är tillgängliga:

    - Efter nettobelopp 
    - Efter bruttobelopp
    - Efter antal
    - Efter marginal
    - Skatt på skatt

16. Välj **Spara**. Fler fält blir tillgängliga baserat på den skattekomponent som du väljer.
17. Använd följande alternativ för att identifiera skattekodens karaktär:

    - Är undantagen
    - Är importavgift
    - Är återförd avgift
    - Exkludera från beräkning av basbelopp

    För ett skattescenario ställer du in en enda skattekod som har en positiv skattesats och markerar den som **Är importavgift**.

    För ett scenario med återförd skatt ställer du in två skatteskoder, varav en har en positiv skattesats och den andra har en negativ skattesats men samma skattevärde. Markera den negativa skattekoden som **Är återförd skatt**. För mer information om lösningen för återförd mmoms i Finance, se [Mekanism för återförd moms för VAT/GST-schema](emea-reverse-charge.md).
    
    För vissa skattetyper som ska uteslutas från beräkningen av skatteunderlagbeloppet för transaktioner inklusive priser, som tull i vissa länder, markerar du kryssrutan **Exkludera från beräkning av basbelopp**.

    Behåll skattesatser och skattebeloppsgränser för den här skattekoden.

18. Upprepa steg 14 till och med 17 för att lägga till alla andra skattekoder som krävs.
19. På fliken **Tillämplighet för skattekoder** markerar du de kolumner som krävs för att fastställa rätt skattekod, och väljer sedan **Lägg till**.
20. Ange eller välj värden för varje kolumn. Fälten **Skattekod**, **Skattegrupp** och **Artikelskattegrupp** kommer att vara resultatet av denna matris.
21. Upprepa steg 19 till och med 20 om du vill ställa in tillämplighet för skatteregistreringsnummer för kund, skatteregistreringsnummer för leverantör och listkoder.
22. Markera **Spara** och stäng sedan sidan.
23. Välj **Ändra status** \> **Slutför**. När statusen har ändrats till **Slutför** kan versionen inte längre redigeras.
24. Välj **Ändra status** \> **Publicera**. Den här versionen av skattefunktionens inställningar förs över till den globala databasen och visas för varje juridisk person i Finance.

## <a name="dynamics-365-setup"></a>Inställningar för Dynamics 365

När du har slutfört inställningarna i RCS, enligt beskrivningen i föregående avsnitt, kommer du att ha en publicerade version av skattefunktionen. Följ dessa steg för att konfigurera skatteberäkning i Finance.

Inställningarna i det här avsnittet görs av en juridisk person. Du måste konfigurera denna för varje juridisk person som du vill aktivera skatteberäkning för i Finance.

1. I Finance, gå till **Skatt** \> **Inställningar** \> **Skattinställning** \> **Inställning av skatteberäkning (förhandsversion)**.
2. Ange följande fält på fliken **Allmänt**:

    - **Aktivera skatteberäkning** – Markera den här kryssrutan om du vill aktivera skatteberäkningstillägget för den juridiska personen. Om detta inte är aktiverat för den aktuella juridiska personen fortsätter den juridiska personen att använda den befintliga skattemotorn för att bestämma och beräkna skatten.
    - **Funktionsinställningar** – Välj en publicerad skattefunktionsinställning och -version för den juridiska personen. Mer information om hur du ställer in och slutför en publicerad skattefunktion finns i föregående avsnitt i det här ämnet.
    - **Affärsprocess** – Välj de affärsprocesser som ska aktiveras.
    - **Aktivera justering av skattekod** – Ange det här alternativet till **Ja** för att aktivera skattekodsjusteringar på momssidan.

3. På fliken **Beräkning**, definiera den förväntade avrundningsregeln för den juridiska enheten.
4. På fliken **Felhantering**, definiera den förväntade felhanteringsmetoden för den juridiska enheten. Det finns tre alternativ för respektive resultatkod:

    - Nr
    - Varning
    - Fel

5. Spara inställningarna.
6. Upprepa steg 1 till och med 5 för varje ytterligare juridisk person.

## <a name="transaction-processing"></a>Bearbetning av transaktion

När du har slutfört alla inställningsprocedurer kan du använda skatteberäkningen för att bestämma och beräkna skatter i Finance. Stegen för att bearbeta transaktioner förblir desamma. Följande transaktioner stöds i Finance-version 10.0.18:

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
