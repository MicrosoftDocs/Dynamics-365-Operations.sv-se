---
title: Kom i gång med skatteberäkning
description: Detta ämne förklarar hur du ställer in skatteberäkningen.
author: wangchen
ms.date: 10/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxIntegrationTaxServiceParameters
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: intro-internal
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2f26f8e5eafe29e88c26d3fb6cfa950466ec6be9
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647444"
---
# <a name="get-started-with-tax-calculation"></a>Kom i gång med momsberäkning

[!include [banner](../includes/banner.md)]

Detta ämne innehåller information om hur du kommer igång med skatteberäkningen. Det guidar dig genom konfigurationsstegen i Microsoft Dynamics Lifecycle Services (LCS), Regulatory Configuration Service (RCS), Dynamics 365 Finance och Dynamics 365 Supply Chain Management. Därefter granskas den gemensamma processen för att använda funktionerna för skatteberäkning i transaktioner för Finance och Supply Chain Management.

Inställningen består av fyra huvudsteg:

1. I LCS installerar du tillägget för momsberäkning.
2. Ställ in funktionen för skatteberäkning i RCS. Denna inställning är inte specifika för en juridisk person. Det kan delas av juridiska personer i Finance och Supply Chain Management.
3. I Finance och Supply Chain Management ställer du in parametrar för skatteberäkningar per juridisk person.
4. I Finance och Supply Chain Management skapar du transaktioner som exempelvis försäljningsorder och använder skatteberäkningen för att bestämma och beräkna skatter.

## <a name="prerequisites"></a>Förutsättningar

Innan du kan slutföra procedurerna i detta ämne måste följande förutsättningar finnas på plats för respektive miljötyp:

Följande förutsättningar måste uppfyllas:

- Du måste ha tillgång till ditt LCS-konto samt ha distribuerat ett LCS-projekt med en nivå 2-miljö (eller högre) som kör Dynamics 365 version 10.0.21 eller senare.
- Du måste skapa en RCS-miljö för organisationen och ha åtkomst till ditt konto. Mer information om hur du skapar en RCS-miljö finns i [Översikten över Regulatory Configuration Service](rcs-overview.md).
- Följande funktioner måste aktiveras i arbetsytan **Funktionshantering** för din distribuerade Finance- eller Supply Chain Management-miljö, baserat på verksamhetens behov:

    - Skatteberäkningstjänst
    - Stöd för flera momsregistreringsnummer
    - Moms i överföringsorder

- Följande funktioner måste vara aktiverade i arbetsytan **Funktionshantering** i den distribuerade RCS-miljön.

    - Globaliseringsfunktioner

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
8. Välj korrekt momskonfigurationsversion, baserat på din Finance-version, och välj sedan **Importera**.

    | Slutversion | Momskonfiguration                       |
    | --------------- | --------------------------------------- |
    | 10.0.18         | Momskonfiguration - Europa 30.12.82     |
    | 10.0.19         | Momsberäkningskonfiguration 36.38.193 |
    | 10.0.20         | Momsberäkningskonfiguration 40.43.208 |
    | 10.0.21         | Momsberäkningskonfiguration 40.48.215 |

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

22. På fliken **Tillämplighet för artikelmomsgrupp** markerar du de kolumner som krävs för att fastställa rätt momskod, och väljer sedan **Lägg till**. Ange eller välj värden för varje kolumn. Fältet **Artikelmomsgrupp** blir utdataresultatet för den här matrisen. Om denna flik inte är konfigurerad kommer artikelmomsgruppen på transaktionsraden att användas.

    Här är ett exempel:

    | Artikelkod | Artikelmomsgrupp |
    | --------- | -------------- |
    | D0001     | Full           |
    | D0003     | Reducerad        |

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

## <a name="transaction-processing"></a>Bearbetning av transaktion

När du har slutfört alla inställningsprocedurer kan du använda momsberäkningen för att bestämma och beräkna moms i Finance. Stegen för att bearbeta transaktioner förblir desamma. Följande transaktioner stöds i Finance-version 10.0.21:

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
