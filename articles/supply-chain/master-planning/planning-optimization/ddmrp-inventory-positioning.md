---
title: Lagerplacering
description: Den här artikeln innehåller information om strategisk lagerplacering, som omfattar identifiering av avdelningspunkter i din leveranskedja, där du kan bygga upp lagerbehållning för att hjälpa till att komprimera ledtider och absorbera dem i din leveranskedja.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ReqGroup, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: bec36b5b51b937782afdb78d7009a58dcd0942f0
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186743"
---
# <a name="inventory-positioning"></a>Lagerplacering

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Strategisk lagerpositionering innebär att identifiera avdelningspunkterna i din leveranskedja, där du kan bygga upp lagerbehållning. Denna metod används framförallt för att komprimera ledtider och absorbera rubbningar i din leveranskedja. Detta gör att du kan minska "pisksnärteffekten" eftersom efterfrågevariationen inte sträcker sig hela vägen ned i leveranskedjan. (*Pisksnärteffekten* syftar på hur små variationer i efterfrågan på butiksnivå kan orsaka progressivt större variationer i efterfrågan på grossist-, leverantörs-, tillverknings- och råmaterialleverantörsnivå.)

Lagerpositionering är det första steget i efterfrågestyrd resursplanering (Demand Driven Materials Resource Planning, DDMRP).

## <a name="inventory-positioning-for-manufacturing"></a>Lagerplacering för tillverkning

Det här avsnittet innehåller ett exempel som visar hur du ska fatta beslut om lagerplacering om du tillverkar en normal kuddprodukt. Kudden har en strukturlista i flera nivåer (BOM), vilket visas i illustrationen nedan.

![Exempel på en strukturlista på flera nivåer (BOM) för en kuddprodukt.](media/ddmrp-bom-example.png "Exempel på en strukturlista med flera nivåer (BOM) för en kuddprodukt")

### <a name="choose-your-decoupling-points"></a>Välj dina avdelningspunkter

När du väljer var du vill placera dina avdelningspunkter, beakta då samtliga följande aspekter av respektive artikel i strukturlistan som kriterier:

- Extern variation
- Lagerutnyttjande och flexibilitet
- Kritiskt driftskydd
- Kundtoleranstid
- Horisontsynlighet för försäljningsorder
- Potentiell ledtid för marknad

I kuddexemplet kan du exempelvis placera din första avdelningspunkt i *skum* av följande orsaker:

- Det är svårt att hitta källan till materialet som används för att framställa kuddskummet, och tillgängligheten är osäker. Därför uppfylls kriteriet för *extern variation*.
- Dessa skumdelar kan skäras i många olika formar och storlekar i syfte att, utöver kudden, även skära ut skuminsatser för andra produkter som du tillverkar. Därför uppfylls kriteriet för *Lagerutnyttjande och flexibilitet*.

Du kan sedan placera nästa avdelningspunkt i *tygproduktpaketet*, som består av är förskuret kuddtyg. Du kan välja den här punkten eftersom du bara har en (1) tygskärningsmaskin. Därför uppfylls kriteriet *kritiskt driftskydd*.

Slutligen kan du placera din sista avdelningspunkt vid den färdigställda, bra kuddartikeln. Du kan välja denna punkt eftersom du har mycket låg *kundtoleranstid* för försäljning, samt eftersom din *synlighetshorisont för försäljningsorder* är ganska kort. Därför vill du säkerställa att du har lagerbehållning nog för att uppfylla inkommande order. Du kan också ställa in ett högre pris genom att hålla ledtiden så här kort, vilket är vad kriteriet *potentiell marknadsledtid* refererar till.

Baserat på denna analys visar följande bild hur kuddens strukturlista kommer att se ut. Gula lagersymboler markerar avdelningspunkterna.

![Exempelstrukturlista med markerade avdelningspunkter.](media/ddmrp-bom-decoupling-example.png "Exempelstrukturlista med markerade avdelningspunkter")

### <a name="calculate-your-decoupled-lead-time"></a>Beräkna din avdelade ledtid

Det här avsnittet visar hur du beräknar dina nya ledtider efter att du har infört avdelningspunkter.

I följande bild för kuddexemplet som inleddes i det föregående avsnittet visas ledtider i grå rutor längst upp till vänster om respektive strukturlistekomponent. Rutor med en röd kontur anger artiklar som driver den ackumulerade ledtiden (summan av de längsta ledtiderna på respektive nivå i strukturlistan). Denna ledtid är 21 dagar när du börjar från grunden.

![Exempelstrukturlista med ledtider.](media/ddmrp-bom-lead-times-example.png "Exempelstrukturlista med ledtider")

Om du däremot använder de avdelningspunkter som du tidigare valt kommer avdelade artiklar alltid att finnas i lager. Därför har dessa en ledtid på 0 (noll). Den nya ledtiden för kudden är nu bara fem dagar – två dagar för att köpa tråd och tre dagar för att framställa kudden. Denna ledtid kallas för den *avdelade ledtiden*.

![Exempel på avdelad ledtid.](media/ddmrp-bom-decoupled-lead-time-example.png "Exempel på avdelad ledtid")

## <a name="strategic-inventory-positioning-in-a-retail-model"></a>Strategisk lagerplacering i en butiksmodell

Eftersom återförsäljare endast har färdiga produkter i lager är strukturlistor inte något problem. Återförsäljare kan emellertid fortfarande använda DDMRP genom att ställa in strategisk lagerplacering och buffertnivåer baserat på lagringsplatser i distributionsnätverket.

I följande illustration visas ett exempel på ett företag som har ett distributionscenter i Seattle och butiker i Boston, Atlanta och Portland.

![Avdelningspunkter baserade på plats i en butiksmodell.](media/ddmrp-retail-decoupl-points-example.png "Avdelningspunkter baserade på plats i en butiksmodell")

Du kanske bestämmer att överföringstiden för att flytta en filtprodukt mellan distributionscentret och butikerna bryter mot din *kundtoleranstid*, detta eftersom dina kunder förväntar sig att filten ska finnas i lager i samband med deras besök. I det här fallet ställer du in en avdelningspunkt för filtartikeln för var och en av de tre butikerna. Varje butik kommer att ha olika buffertnivåer baserat på dess ledtider, efterfrågemönster och så vidare.

## <a name="implement-inventory-positioning-in-dynamics-365-supply-chain-management"></a>Implementera lagerplacering i Dynamics 365 Supply Chain Management

I det här avsnittet beskrivs hur du implementerar din lagerplaceringsstrategi i Microsoft Dynamics 365 Supply Chain Management.

### <a name="set-up-item-coverage-groups-that-create-decoupling-points"></a>Konfigurerar artikeldisponeringsgrupper som skapar avdelningspunkter

Artiklar blir till avdelningspunkter när de tillhör en disponeringsgrupp som har konfigurerats med ett värde för **Disponeringskod** som är lika med *Avdelningspunkt*. Därför är det första steget i processen med att ställa in DDMRP att bestämma vilka disponeringsgrupper som du måste implementera för din DDMRP-strategi och sedan skapa dem genom att följa dessa steg.

1. Gå till **huvudplanering \> inställningar \> täckning \> disponeringsgrupper**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en disponeringsgrupp.
1. Ange information som identifierar disponeringsgruppen och välj sedan den kalender som ska användas.
1. I fliken **Allmänt** anger du fältet **Disponeringskod** som *Avdelningspunkt*. Den här inställningen medför att alla artiklar som tillhör denna disponeringsgrupp behandlas som avdelningspunkter för DDMRP. Det aktiverar även alla DDMRP-inställningar för den här gruppen på det sätt som beskrivs senare i proceduren.
1. På fliken **Övrigt**, i avsnittet **DDMRP-parametrar**, ställer du in följande fält:

    - **Ledtidsfaktor** – Ange en faktor (som ett decimalvärde mellan 0 och 1) för att kontrollera vilken inverkan ledtiden bör ha när minimi- och maximilagernivåerna beräknas för artiklar i den här disponeringsgruppen. Ju längre ledtid en artikel har, desto lägre bör ledtidsfaktorn vara. En lägre ledtidsfaktor ger lägre lägsta och högsta lagernivåer, och orsakar därför mindre och mer frekventa order. DDMRP-metoden rekommenderar ett värde på mellan 0,20 och 0,40 för artiklar som har långa ledtider, mellan 0,41 och 0,60 för artiklar som har medellånga ledtider, och mellan 0,61 och 1,00 för artiklar som har korta ledtider. Mer information finns i [Buffertprofil och nivåer](ddmrp-buffer-profile-and-levels.md).
    - **Variantfaktor** – Ange en faktor (som ett decimalvärde mellan 0 och 1) för att kontrollera vilken inverkan varierande efterfrågan bör ha när minimilagernivåerna beräknas för artiklar i den här disponeringsgruppen. I allmänhet gäller att ju mer variabel en artikels efterfrågan är, desto högre blir dess variantfaktor. En högre variantfaktor leder till en högre minimilagernivå. DDMRP-metoden rekommenderar ett värde på mellan 0,00 och 0,40 för artiklar som har låg variation, mellan 0,41 och 0,60 för artiklar som har medelvariation, och mellan 0,61 och 1,00 för artiklar som har hög variation. Mer information finns i [Buffertprofil och nivåer](ddmrp-buffer-profile-and-levels.md).
    - **Min-, max- och beställningsperiod** – Ange hur ofta buffertvärden ska beräknas (*dagligen* eller *veckovis*).

1. På fliken **Övrigt**, i avsnittet **Genomsnittlig daglig användning**, ställer du in följande fält:

    - **Genomsnittlig daglig användning baserad på** – Välj vilka tidsperioder beräkningen av genomsnittlig daglig användning (ADU) ska baseras på. Välj ett av följande värden:

        - *Tidigare* – Titta bara på tidigare användning för det antal dagar som har angetts i fältet **Tidigare period (dagar)**. ADU beräknas som den totala efterfrågan för en artikel under beräkningsperioden (i lagerenheter) delat med antalet dagar i beräkningsperioden.
        - *Hädanefter* – Titta bara på prognostiserad framtida användning (inklusive prognoser) för det antal dagar som har angetts i fältet **Kommande period (dagar)**. ADU beräknas som den totala efterfrågan för en artikel under beräkningsperioden (i lagerenheter) delat med antalet dagar i beräkningsperioden. 
        - *Blandad*– Titta på både tidigare och framtida användning. Inställningar i fältet **Tidigare period (dagar)**, fältet **Kommande period (dagar)** och blandningsalternativen gäller. 

            *Blandad ADU* = (\[*Tidigare viktning* × *Tidigare ADU*\] + \[*Framåtviktning* × *Framåt-ADU*\]) ÷ (*Tidigare viktning* + *Framåtviktning*)

    - **Tidigare period (dagar)** – Ange antalet tidigare dagar (inklusive idag) som systemet bör ta hänsyn till när det beräknar ADU för artiklar i den här disponeringsgruppen. Den här inställningen används bara om fältet **Genomsnittlig daglig användning baserad på** är inställt på *Tidigare* eller *Blandad*.
    - **Kommande period (dagar)** – Ange antalet kommande dagar (från och med idag och fram till och med angiven dag) som systemet bör ta hänsyn till när det beräknar ADU för artiklar i den här disponeringsgruppen. Den här inställningen används bara om fältet **Genomsnittlig daglig användning baserad på** är inställt på *Kommande* eller *Blandad*.
    - **Relativ vikt för tidigare period för blandad daglig användning** – Ange den vikt (som ett procenttal) som ska användas på den tidigare perioden när blandat ADU beräknas. Den här inställningen används bara om fältet **Genomsnittlig daglig användning baserad på** är inställt på *Blandad*.
    - **Relativ vikt för kommande period för blandad daglig användning** – Ange den vikt (som ett procenttal) som ska användas på den kommande perioden när blandat ADU beräknas. Den här inställningen används bara om fältet **Genomsnittlig daglig användning baserad på** är inställt på *Blandad*.

1. På alla övriga flikar och fält anger du detaljerade inställningar som ska användas för att beräkna behovet för artiklar som är kopplade till denna disponeringsgrupp.

### <a name="set-an-item-as-a-decoupling-point"></a>Ange en artikel som avdelningspunkt

Följ dessa steg om du vill ange en artikel som en avdelningspunkt.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Sök efter och välj en frisläppt artikel som du vill konfigurera för DDMRP.
1. I åtgärdsfönstret, på fliken **Plan**, väljer du **Artikeldisponering**.
1. På sidan **Artikeldisponering** kanske redan flera artikeldisponeringsposter visas, som var och en gäller för olika kombinationer av lagrings- och produktdimensioner. Du kan välja en befintlig artikeldisponeringspost som gäller för de dimensioner där du vill skapa en avdelningspunkt. Du kan också välja **Ny** i åtgärdsfönstret om du vill skapa en ny artikeldisponeringspost.
1. Konfigurera artikelns disponeringspost som vanligt. Du måste åtminstone ange den webbplats och det lagerställe där avdelningspunkten ska gälla.
1. Välj fliken **Allmänt** medan avsett post är fortsatt markerad.
1. Markera kryssrutan **Använd specifika inställningar**.
1. Ange fältet **Disponeringsgrupp** som en disponeringsgrupp som har konfigurerats att skapa de avdelningspunkter (enligt beskrivningen i föregående avsnitt).
1. Artikeln är nu konfigurerad som en avdelningspunkt. När du använder DDMRP konfigurerar du vanligtvis även inställningar här som påverkar buffertstorlekar och beställningskvantitet. Du kan emellertid slutföra den konfigurationen senare. Mer information om inställningarna finns i [Konfigurera buffertar för en avdelningspunktartikel](ddmrp-buffer-profile-and-levels.md#set-up-buffers).

> [!NOTE]
> Om du vill planera artiklar som inte är avdelningspunkter följer du samma steg som när behovsplanering för standardmaterial (MRP) används.
