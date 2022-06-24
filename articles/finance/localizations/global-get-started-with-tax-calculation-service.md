---
title: Kom i gång med momsberäkning
description: Detta ämne förklarar hur du ställer in skatteberäkningen.
author: wangchen
ms.date: 03/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c2293102057ac055f0958c1c6b1de2a19cb331d5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855295"
---
# <a name="get-started-with-tax-calculation"></a>Kom i gång med momsberäkning

[!include [banner](../includes/banner.md)]

Detta ämne innehåller information om hur du kommer igång med skatteberäkningen. Avsnitten i detta ämne guidar dig genom design- och konfigurationsstegen på hög nivå i Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS), Dynamics 365 Finance samt Dynamics 365 Supply Chain Management. 

Inställningen består av tre huvudsteg.

1. I LCS installerar du tillägget för momsberäkning.
2. Ställ in funktionen för skatteberäkning i RCS. Denna inställning är inte specifika för en juridisk person. Det kan delas av juridiska personer i Finance och Supply Chain Management.
3. I Finance och Supply Chain Management ställer du in parametrar för skatteberäkningar per juridisk person.

## <a name="high-level-design"></a>Design på hög nivå

### <a name="runtime-design"></a><a name="runtime"></a> Körtidsdesign

Följande illustration visar körtidsdesignen på hög nivå för skatteberäkning. Eftersom momsberäkning kan integreras med flera Dynamics 365-program, används integrationen med Finance som ett exempel i illustrationen.

1. En transaktion, till exempel en försäljningsorder eller inköpsorder, skapas i Finance.
2. I Ekonomi används automatiskt standardvärdena för momsgruppen och artikelmomsgruppen.
3. När knappen **Moms** väljs i transaktionen, utlöses momsberäkningen. Ekonomi skickar sedan nyttolast till beräkningstjänsten.
4. Beräkningstjänsten för moms matchar nyttolasten med fördefinierade regler i momsfunktionen för att hitta en mer korrekt momsgrupp och artikelskattegrupp samtidigt.

    - Om nyttolasten kan matchas med matrisen **Tillämplighet för momsgrupp** åsidosätter den värdet för momsgruppen med det matchade momsgruppsvärdet i tillämplighetsregeln. Annars fortsätter programmet att använda momsgruppsvärdet från Finance.
    - Om nyttolasten kan matchas med matrisen **Tillämplighet för artikelmomsgrupp** åsidosätter den värdet för artikelmomsgrupp med det matchade artikelmomsgruppvärdet i tillämplighetsregeln. Annars fortsätter programmet att använda artikelmomsgruppsvärdet från Finance.

5. Skatteberäkningstjänsten bestämmer de slutliga momskoderna genom att använda skärningspunkten mellan momsgruppen och artikelmomsgruppen.
6. Beräkningstjänsten beräknar moms baserat på de slutgiltiga momskoderna som den har bestämt.
7. Momsberäkningstjänsten returnerar momsberäkningsresultatet till Finance.

![Design för körningstid för momsberäkning.](media/tax-calculation-runtime-logic.png)

### <a name="high-level-configuration"></a>Konfiguration på hög nivå

Följande steg ger en överblick över konfigurationsprocessen för Skatteberäkningstjänst.

1. I LCS installerar du tillägget för **momsberäkning** i LCS-projekt.
2. Ställ in funktionen för **skatteberäkning** i RCS.
3. Ställ in funktionen för **skatteberäkning** i RCS:

    1. Välj skattekonfigurationsversionen.
    2. Skapa taxkoder.
    3. Skapa en skattegrupp.
    4. Skapa en artikelmomsgrupp.
    5. Valfritt: Tillämplighet för momsgrupp om du vill åsidosätta standard momsgruppen som anges från huvuddata för kunder eller leverantörer.
    6. Valfritt: Tillämplighet för artikelgrupp om du vill åsidosätta standard artikelmomsgruppen som anges från artikelns huvuddata.

4. I RCS, fyll i och publicera **Momsberäkning**.
5. I Finans, välj den publicerade **Momsberäkning**.

När du har slutfört de här stegen synkroniseras följande inställningar automatiskt från RCS till Finance.

- Momskoder
- Momsgrupper
- Artikelmomsgrupper

De återstående avsnitten i det här ämnet innehåller mer detaljerade konfigurationssteg.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra de återstående procedurerna i det här ämnet måste följande förutsättningar vara uppfyllda:<!--TO HERE-->

- Du måste ha tillgång till ditt LCS-konto samt ha distribuerat ett LCS-projekt med en nivå 2-miljö (eller högre) som kör Dynamics 365 version 10.0.21 eller senare.
- Du måste skapa en RCS-miljö för organisationen och ha åtkomst till ditt konto. Mer information om hur du skapar en RCS-miljö finns i [Översikten över Regulatory Configuration Service](rcs-overview.md).
- Följande funktioner måste aktiveras i arbetsytan **Funktionshantering** för din distribuerade Finance- eller Supply Chain Management-miljö, baserat på verksamhetens behov:

    - Skatteberäkningstjänst
    - Stöd för flera momsregistreringsnummer
    - Moms i överföringsorder

- Följande funktioner måste vara aktiverade i arbetsytan **Funktionshantering** i den distribuerade RCS-miljön.

    - Globaliseringsfunktioner

- Följande roller bör tilldelas i egenskap av lämpliga för användarna i din RCS-miljö:

    - Utvecklare för elektronisk rapportering
    - Utvecklare av globaliseringsfunktioner
    - Skattemotorutvecklare
    - Funktionskonsult för skattemotor
    - Utvecklare av skattetjänst

## <a name="set-up-tax-calculation-in-lcs"></a>Konfigurera skatteberäkning i LCS.

1. Logga in på [LCS](https://lcs.dynamics.com)
2. Slutför inställningarna för Microsoft Power Platform-integrering. Mer information finns i [översikt över tillägg](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
3. Välj en av dina distribuerade miljöer och välj sedan **Installera ett nytt tillägg**.
4. Välj **Momsberäkning**.
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
8. Välj korrekt [momskonfigurationsversion](global-tax-calcuation-service-overview.md#versions), baserat på din Finance-version, och välj sedan **Importera**.
9. I arbetsytan **Globaliseringsfunktioner** väljer du **Funktioner** > panelen **Skatteberäkning** och sedan **Lägg till**.
10. Välj en av följande funktionstyper:

    - **Ny funktion** – Skapa en funktionsinställning som har tomt innehåll.
    - **Baserat på befintlig funktion** – Skapa en funktion från en befintlig funktion och kopiera innehållet från de befintliga funktionsinställningarna.

11. Ange ett namn på och en beskrivning för den nya funktionen och välj sedan **Skapa funktion**.

    När funktionen har skapats skapas ett utkast av den automatiskt. Du kan välja **Hämta denna version** basera om utkastversionen till en slutförd version.

12. Välj utkastversion för funktionen och **redigera**. Sidan **Inställning av skatteberäkning** fylls i.
13. Välj **Konfigurationsversion**. Du bör se den konfigurationsversion som du importerade i steg 8.

    Microsoft tillhandahåller en standardkonfiguration för momsberäkning. Den här konfigurationen täcker de flesta kraven för skatteberäkningsbeteenden. Den kommer att uppdateras baserat på återrapportering från marknaden. Om du måste utöka konfigurationen för att uppfylla specifika krav, se [Hur man bygger tillägg i skattetjänst](./tax-service-add-data-fields-tax-integration-by-extension.md) för information om hur du skapar och väljer din egen skattekonfiguration.

14. När du har valt **Konfigurationsversion** visas flera ytterligare flikar. Följ den ordning som visas här för att slutföra de obligatoriska inställningarna på fliken.

    **Obligatoriska inställningar**

    - **Skattekoder** – underhålla huvuddata för momskoder. Alla momskoder som skapas på den här fliken synkroniseras automatiskt till Finance när du aktiverar den aktuella versionen.
    - **Momsgrupp** – Ange huvuddata för momsgruppen och momskoderna under gruppen.
    - **Artikelmomsgrupp** – Ange huvuddata för artikelmomsgruppen och momskoderna under gruppen.

    **Valfria inställningar**

    - **Tillämplighet för momsgrupp** – Definiera en matris som bestämmer momsgruppen. Om inga tillämplighetsregler i den här matrisen matchar det beskattningsbara dokumentet från Dynamics 365, används standardvärdet för momsberäkning på den beskattningsbara dokumentraden.
    - **Tillämplighet för artikelmomsgrupp** – Definiera en matris som bestämmer artikelmomsgruppen. Om inga tillämplighetsregler i den här matrisen matchar det beskattningsbara dokumentet från Dynamics 365, används standardvärdet för momsberäkning på den beskattningsbara dokumentraden.
    - **Tillämpbarhet för kundens momsregistreringsnummer** – Om du har flera momsregistreringsnummer för en viss kund kan momsberäkningen automatiskt bestämma korrekt momsregistreringsnummer. I matrisen på den här fliken definierar du de regler som ska användas för beslutet. Annars fortsätter Finance och Supply Chain Management att använda standardregistreringsnumret på skatteunderlag för försäljningstransaktioner.
    - **Tillämpbarhet för leverantörens momsregistreringsnummer** – Om du har flera momsregistreringsnummer för en viss leverantör kan momsberäkningen automatiskt bestämma korrekt momsregistreringsnummer. I matrisen på den här fliken definierar du de regler som ska användas för beslutet. Annars fortsätter Finance och Supply Chain Management att använda standardregistreringsnumret på skatteunderlag för inköpstransaktioner.
    - **Tillämpbarhet för listkod** – Bestäm värdet för fältet **Listkod** automatiskt genom mer flexibla och konfigurerbara regler. I matrisen på den här fliken definierar du de regler som ska användas för beslutet. Annars fortsätter Finance och Supply Chain Management att använda standardkod på skatteunderlag.

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
    - Exkludera från beräkning av underlagsbelopp

    För ett scenario för importavgifter ställer du in en enda skattekod som har en positiv skattesats och markerar den som **Är importavgift**.

    För ett scenario med återförd skatt ställer du in två skatteskoder, varav en har en positiv skattesats och den andra har en negativ skattesats men samma skattevärde. Markera den negativa skattekoden som **Är återförd skatt**. För mer information om lösningen för återförd mmoms i Finance, se [Mekanism för återförd moms för VAT/GST-schema](emea-reverse-charge.md).

    För vissa skattetyper som ska uteslutas från beräkningen av skatteunderlagsbeloppet för transaktioner inklusive priser (exempelvis tull i vissa länder/regioner), markerar du kryssrutan **Exkludera från beräkning av underlagsbelopp**. Mer information om denna parameter finns i [Beräkna moms ovanpå priset när Priserna är inkl. moms är aktiverat](global-exclude-from-tax-base-amount-calculation.md).

    Behåll skattesatser och skattebeloppsgränser för den här skattekoden.

18. Upprepa steg 14 till och med 17 för att lägga till alla andra skattekoder som krävs.
19. På fliken **Momsgrupp** väljer du kolumnen **Momsgrupp**, lägger till den i matrisen som indatavillkor och lägger sedan till rader i syfte att bibehålla huvuddata för momsgrupp.

    Här är ett exempel:

    | Skattegrupp    | Momskoder           |
    | ------------ | ------------------- |
    | DEU_Domestic | DEU_VAT19; DEU_VAT7 |
    | DEU_EU       | DEU_Exempt          |
    | BEL_Domestic | BEL_VAT21; BEL_VAT6 |
    | BEL_EU       | BEL_Exempt          |

20. På fliken **Artikelmomsgrupp** väljer du kolumnen **Artikelmomsgrupp**, lägger till den i matrisen som indatavillkor och lägger sedan till rader i syfte att bibehålla huvuddata för artikelmomsgrupp.

    Här är ett exempel:

    | Artikelmomsgrupp | Momskoder                                    |
    | -------------- | -------------------------------------------- |
    | Full           | DEU_VAT19; BEL_VAT21; DEU_Exempt; BEL_Exempt |
    | Reducerad        | DEU_VAT7; BEL_VAT6; DEU_Exempt; BEL_Exempt   |

21. På fliken **Tillämplighet för momsgrupp** markerar du de kolumner som krävs för att fastställa rätt momsgrupp, och väljer sedan **Lägg till**. Ange eller välj värden för varje kolumn. Fältet **Momsgrupp** blir utdataresultatet för den här matrisen. Om denna flik inte är konfigurerad kommer momsgruppen på transaktionsraden att användas.

    Här är ett exempel:

    | Affärsprocess | Leverera från | Skeppa till | Skattegrupp    |
    | ---------------- | --------- | ------- | ------------ |
    | Försäljning            | DEU       | DEU     | DEU_Domestic |
    | Försäljning            | DEU       | FRA     | DEU_EU       |
    | Försäljning            | BEL       | BEL     | BEL_Domestic |
    | Försäljning            | BEL       | FRA     | BEL_EU       |
    
    > [!NOTE]
    > Om standardmomsgruppen på de beskattningsbara dokumentraderna är korrekt, lämnar du denna matris tom. Mer information finns i avsnittet [Körningsdesign](#runtime) senare i detta avsnitt.

22. På fliken **Tillämplighet för artikelmomsgrupp** markerar du de kolumner som krävs för att fastställa rätt momskod, och väljer sedan **Lägg till**. Ange eller välj värden för varje kolumn. Fältet **Artikelmomsgrupp** blir utdataresultatet för den här matrisen. Om denna flik inte är konfigurerad kommer artikelmomsgruppen på transaktionsraden att användas.

    Här är ett exempel:

    | Artikelkod | Artikelmomsgrupp |
    | --------- | -------------- |
    | D0001     | Full           |
    | D0003     | Reducerad        |

    > [!NOTE]
    > Om standardmomsgruppen för artiklar på de beskattningsbara dokumentraderna är korrekt, lämnar du denna matris tom. Mer information finns i avsnittet [Körningsdesign](#runtime) senare i detta avsnitt.

    Mer information om hur momskoder bestäms i Momsberäkning finns i [Bestämningslogik för momsgrupp och artikelmomsgrupp](global-sales-tax-group-determination.md).

23. Konfigurera tillämplighet för momsregistreringsnummer för kund, momsregistreringsnummer för leverantörer, samt listkoder baserat på verksamhetsbehoven.
24. Markera **Spara** och stäng sedan sidan.
25. Välj **Ändra status** \> **Slutför**. När statusen har ändrats till **Slutför** kan versionen inte längre redigeras.
26. Välj **Ändra status** \> **Publicera**. Den här versionen av skattefunktionens inställningar förs över till den globala databasen och visas för varje juridisk person i Finance.

## <a name="set-up-tax-calculation-in-dynamics-365"></a>Konfigurera momsberäkning i Dynamics 365

När du har slutfört inställningarna i RCS kommer du att ha en publicerad version av momsfunktionen. Följ dessa steg för att konfigurera skatteberäkning i Finance.

Inställningarna i det här avsnittet görs av en juridisk person. Du måste konfigurera denna för varje juridisk person som du vill aktivera skatteberäkning för i Finance.

1. I Finance går du till **Moms** \> **Inställningar** \> **Momsinställning** \> **Parametrar för momsberäkning**.
2. Ange följande fält på fliken **Allmänt**:

    - **Aktivera tjänsten för momsberäkning** – Markera denna kryssruta om du vill aktivera momsberäkningen för den juridiska personen. Om detta inte är aktiverat för den aktuella juridiska personen fortsätter den juridiska personen att använda den befintliga skattemotorn för att bestämma och beräkna skatten.
    - **Funktionsinställningar** – Välj en publicerad skattefunktionsinställning och -version för den juridiska personen. Mer information om hur du ställer in och slutför en publicerad skattefunktion finns i föregående avsnitt i det här ämnet.
    - **Affärsprocess** – Välj de affärsprocesser som ska aktiveras.

3. På fliken **Beräkning**, definiera den förväntade avrundningsregeln för den juridiska enheten. Mer information om avrundningslogiken finns i [Avrundningsregler för momsberäkning](https://go.microsoft.com/fwlink/?linkid=2166988).
4. På fliken **Felhantering**, definiera den förväntade felhanteringsmetoden för den juridiska enheten. Tre alternativ är möjliga:

    - Nej
    - Varning
    - Fel

    Du kan ställa in en felhanteringsmetod för respektive resultatkod i avsnittet **Detaljer**. Om vissa resultatkoder inte synkroniseras från beräkningstjänsten för moms kan du också ställa in en standardmetod i avsnittet **Allmänt**.

5. På fliken **Multipel momsregistrering** kan du aktivera momsdeklarering, EU-försäljningslista samt Intrastat separat så att dessa används i ett scenario med flera olika momsregistreringar. Mer information om momsrapportering för flera momsregistreringar finns i [Rapportering för flera momsregistreringar](emea-reporting-for-multiple-vat-registrations.md).
6. Spara inställningarna och upprepa föregående steg för respektive ytterligare juridisk person. När en ny version publiceras och du vill tillämpa den ställer du in fältet **Funktionsinställningar** på fliken **Allmänt** på sidan **Parametrar för momsberäkning** (se steg 2).
