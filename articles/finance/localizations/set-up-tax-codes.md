---
title: Konfigurera momskoder
description: Det här avsnittet förklarar hur du ställer in momskoder i tjänsten för momsberäkning.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 8bdb194e7d8b704d1e58d3c25bf2e1f6bff1ba00
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883882"
---
# <a name="set-up-tax-codes"></a>Konfigurera momskoder

[!include [banner](../includes/banner.md)]

Det här avsnittet förklarar hur du ställer in momskoder i tjänsten för momsberäkning. Den innehåller inställningarna för ett enkelt scenario för att få momskoden att fungera och information om en del avancerad momskodfunktion för komplexa scenarier.

> [!IMPORTANT]
> Inställning av momskoder i tjänsten för momsberäkning oberoende av begreppet juridiska personer. Du kan bara slutföra den här installationen i RCS (Regulatory Configuration Service) en gång. Momskoder synkroniseras automatiskt till Microsoft Dynamics 365 Finance när du aktiverar det i tjänsten momsberäkning för en utvald juridisk entitet i Finance.

## <a name="simple-setup"></a>Enkel installation

Följ dessa steg för att använda en momskod i ett enkelt scenario, till exempel ett scenario där det bara finns en skattesats.

1. Logga in på [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).
2. Gå till **Arbetsytor** \> **Globaliseringsfunktioner** \> **Momsberäkning**.
3. Markera den funktion och version som du vill konfigurera och välj **Redigera**.
4. På fliken **Allmänt** välj **Konfigurationsversion**.
5. På fliken **Skattekoder**, välj **Lägg till** och ange skattekoden och en beskrivning.
6. Välj **Beräkningens ursprung**. En beräknings ursprung är en grupp med metoder som har definierats i versionen av skattekonfigurationen du har valt. För det här enkla scenariot väljer du **Efter nettobelopp**.
7. Välj **Spara**. Fler fält blir tillgängliga baserat på den beräkningens ursprung som du väljer.
8. På snabbfliken **Priser** väljer du **Lägg till** om du vill lägga till en skattesats för den här skattekoden.
9. Välj **Spara**.

## <a name="calculation-origin"></a>Beräkningens ursprung

Beräkningsursprunget definierar hur momsbasbeloppet och momsbeloppet beräknas. Det konfigureras av skattekonfigurationen i arbetsytan **Elektronisk rapportering**. Följande värden är tillgängliga i fältet **Beräkningsursprung**: 

- Efter nettobelopp 
- Efter bruttobelopp
- Efter antal
- Efter marginal
- Skatt på skatt

### <a name="by-net-amount"></a>Efter nettobelopp 

Om du väljer **Efter nettobelopp** i fältet **Beräkningsursprung** beräknas momsbeloppet som en procentandel av inköps- eller försäljningsbeloppet, exklusive andra momskoder.

Skattesatsen är till exempel 25 procent, fakturaraden visar en kvantitet på 10 artiklar vid 1,00 vardera och kunden får en 10-procentig radrabatt. I detta fall beräknas beloppen på följande sätt:

- **Nettobelopp:** (10 × 1,00) – 10 procent = 9,00 
- **Moms:** 9,00 × 25 procent = 2,25 
- **Totalt fakturabelopp:** = 9,00 + 2,25 = 11,25.

### <a name="by-gross-amount"></a>Efter bruttobelopp

Om du väljer metoden **Efter bruttobelopp** i fältet **Beräkningens ursprung** beräknas momsbeloppet som en procentandel av bruttoförsäljningsbeloppet. Bruttobeloppet är radnettobeloppet plus all skatt och tillägg för raden utom skatt där fältet **Beräkningens ursprung** anges till **Efter bruttobelopp**.

Skattemyndigheten har lagt särskilda avgifter på en artikel. Avgiftsbeloppen läggs till nettobeloppet innan momsen beräknas. Följande momskoder används:

- **Avgift 1** – Satsen är 10 procent och beräkningsmetoden **Efter nettobelopp** används.
- **Avgift 2** – Satsen är 20 procent och beräkningsmetoden **Efter nettobelopp** används.
- **Avgift** – Satsen är 25 procent och beräkningsmetoden **Efter bruttobelopp** används.

Om nettobeloppet är 10,00 är Avgift 1 beloppet 1,00 (10,00 × 10 procent) och Avgift 2 beloppet är 2,00 (10,00 × 20 procent). I detta fall beräknas beloppen på följande sätt: 

- **Bruttobelopp:** Nettobelopp + Avgift 1 + Avgift 2 = 10,00 + 1,00 + 2,00 = 13,00 
- **Momsbelopp:** 13,00 × 25 procent = 3,25 
- **Totala avgifter och moms:** 1,00 + 2,00 + 3,25 = 6,25 
- **Totalt fakturabelopp:** = 10,00 + 6,25 = 16,25.

### <a name="by-quantity"></a>Efter antal

När du väljer **Efter antal** i fältet **Beräkningens ursprung** beräknas momsen som ett fast belopp per enhet multiplicerat med den kvantitet som anges på dokumentraden. Beloppet per enhet anges på snabbfliken **Priser**.

Momskoden ställs till exempel in som 1,20 per enhet. På en försäljningsfakturarad säljs 25 enheter av en artikel. I det här fallet justeras momsbeloppet vid behov 25 × 1,20 = 30,00.

### <a name="by-margin"></a>Efter marginal

Om du väljer metoden **Efter marginal** i fältet **Beräkningens ursprung** beräknas momsbeloppet som en procentandel av försäljningsmarginal. Försäljningsmarginalen är försäljningsbeloppet minus kostnadsbeloppet. Den här beräkningsmetoden gäller endast försäljningstransaktioner.

Momssatsen är till exempel 25 procent, fakturaraden visar en kvantitet på 10 artiklar vid 10,00 vardera och kostnad per artikel är 6. I detta fall beräknas beloppen på följande sätt:

- **Försäljningsmarginal:** 10 × ( 10,00 – 6,00) = 40,00
- **Momsbelopp:** 40,00 × 25 procent = 10,00
- **Totalt fakturabelopp:** = 100,00 + 10,00 = 110,00.

### <a name="tax-on-tax"></a>Skatt på skatt

Om du väljer **Moms på moms** i fältet **Beräkningsursprung** beräknas momsen som en procentandel av alla andra momsbelopp på samma dokumentrad.

Till exempel följande momskoder används:

- **Avgift 1** – Satsen är 10 procent och beräkningsmetoden **Efter nettobelopp** används.
- **Avgift 2** – Satsen är 20 procent och beräkningsmetoden **Efter nettobelopp** används.
- **Moms på avgift** – Satsen är 25 procent och beräkningsmetoden **Moms på moms** används.

I detta fall beräknas beloppen på följande sätt:

- **Nettobelopp:** 10,00 
- **Avgift 1:** 10,00 × 10 procent = 1,00 
- **Avgift 2:** 10,00 × 20 procent = 2,00 
- **Moms på avgift:** 3,00 × 25 procent = 0,75
- **Summa moms:** 1,00 + 2,00 + 0,75 = 3,75 
- **Totalt fakturabelopp:** = 10,00 + 3,75 = 13,75.

## <a name="advanced-functionality"></a>Avancerad funktion

I det här avsnittet beskrivs några avancerade funktioner i momskodsinställningen för komplexa scenarier.

### <a name="tax-exemption"></a>Momsbefrielse

Om du ställer in alternativet **Är undantaget** till **Ja** på snabbfliken **Allmänt**, åsidosätts momsbeloppet alltid till 0 (noll), oavsett den faktiska momssatsen.

Du kan ställa in fältet **Momsbefrielsekod** för att ange orsaken till undantaget. 

Du kan aktivera sökning efter huvuddata för fältet **Momsbefrielsekod**. På så sätt kan du välja bland de värden för momsregistrering som har definierats i Finance. Information om hur du aktiverar sökning efter huvuddata finns i [Aktivera sökning efter huvuddata för momsberäkningskonfiguration](tax-service-set-up-environment-master-data-lookup.md).

Momssatsen är till exempel 25 procent och alternativet **Är undantag** är inställt på **Ja** för momskoden. Fakturaraden visar en kvantitet på 10 artiklar à 1,00 $ styck och kunden har rätt till en radrabatt på 10 %. I detta fall beräknas beloppen på följande sätt:

- **Nettobelopp:** (10 × 1,00) – 10 procent = 9,00 
- **Moms:** 0,00 
- **Totalt fakturabelopp:** = 9,00 + 0,00 = 9,00.

### <a name="use-tax"></a>Använd moms

Om du ställer in alternativet **Importavgift** på **Ja** på snabbfliken **Allmänt** kommer momsbeloppet att bokföras till kontot **Importavgift, skuld** istället för **leverantörssamlingskontot**.

Momssatsen är till exempel 25 procent och alternativet **Är importavgift** är inställt på **Ja** för momskoden. Fakturaraden visar en kvantitet på 10 artiklar à 1,00 $ styck och kunden har rätt till en radrabatt på 10 %. I detta fall beräknas beloppen på följande sätt:

- **Nettobelopp:** (10 × 1,00) – 10 procent = 9,00 
- **Importavgift:** 9,00 × 25 procent = 2,25
- **Totalt fakturabelopp:** = 9,00 + 0,00 = 9,00.

> [!IMPORTANT]
> Om både alternativet **Är momsbefriad** och **Är importavgift** anges till **Ja** på en momskod kommer koden att erkännas som moms befriad för försäljningstransaktioner och importavgift för inköpstransaktioner.

### <a name="reverse-charges"></a>Återföringsavgifter

Om du ställer in alternativet **Är återförd avgift** till **Ja** på snabbfliken **Allmänt** konfigureras momssatsen som negativ. För ett scenario med återförd skatt rekommenderar vi att du ställer två momskoder: en som har en positiv skattesats och den andra har en negativ skattesats men samma skattevärde. Båda momskoderna ska ha samma satsvärde och alternativet **Är återförd avgift** bör anges till **Ja** på momskoden som har en negativ momssats. För mer information om lösningen för återförd mmoms i Finance, se [Mekanism för återförd moms för VAT/GST-schema](emea-reverse-charge.md).

Till exempel fastställs två momskoder på en fakturarad. En momssats är 25 procent. Den andra momssatsen är till exempel -25 procent och alternativet **Är återförd avgift** är inställt på **Ja** för den andra momskoden. Fakturaraden visar en kvantitet på 10 artiklar med en kvantitet på 1,00 styck. I detta fall beräknas beloppen på följande sätt:

- **Nettobelopp:** (10 × 1,00) = 10,00 
- **Momskod 1:** 10,00 × 25 procent = 2,50
- **Momskod 2:** 10 × -25 procent = -2,50
- **Totalt fakturabelopp** = 10,00 + 2,50 -2,50 = 10,00

### <a name="exclusion-from-base-amount-calculations"></a>Exkludera från beräkning av underlagsbelopp

Om du ställer in alternativet **Uteslut från basbeloppsberäkning** till **Ja** på snabbfliken **Allmänt** kommer det beräknade momsbeloppet för momskoden att uteslutas från momsbasbeloppet i scenariot inklusive priser.

För mer information, se [Beräkna moms på priser när Priser inkl. moms är aktiverat](global-exclude-from-tax-base-amount-calculation.md).

### <a name="rates"></a>Priser

På snabbfliken **Sats** kan du definiera olika momssatser för olika intervall av skattebasbelopp. För att beräkna momsbeloppet använder beräkningstjänsten alltid den sats som matchar basbeloppet för moms.

Momssatser kan till exempel konfigureras på det sätt som visas i följande tabell.

| Minimibelopp | Maxtid | Momssats   |
| -------------- | -------------- | ---------- |
| 0              | 1 000          | 10 procent |
| 1 000          | 5 000          | 15 procent |
| 5 000          | 10,000         | 20 procent |
| 10,000         | 0              | 30 procent |

I detta fall beräknas momsbeloppet på följande sätt:

- Om momsbasbeloppet är 300,00 är momssatsen 10 procent och momsbeloppet är 300,00 × 10 procent = 30,00.
- Om momsbasbeloppet är 3 000,00 är momssatsen 15 procent och momsbeloppet är 3 000,00 × 15 procent = 450,00.
- Om momsbasbeloppet är 6 000,00 är momssatsen 20 procent och momsbeloppet är 6 000,00 × 10 procent = 1 200,00.
- Om momsbasbeloppet är 20 000,00 är momssatsen 30 procent och momsbeloppet är 20 000,00 × 30 procent = 6 000,00.

> [!NOTE]
> Om momsbasbeloppet kan matcha både maxbeloppet på en rad och minimibeloppet på den andra raden använder basbeloppet den momssats som matchar minimibasbeloppet. Om momsbasbeloppet är 1 000,00 är momssatsen 15 procent och momsbeloppet är 1 000,00 × 15 procent = 150,00.

### <a name="limits"></a>Gränser

På snabbfliken **Gränser** kan du definiera momsgränser om du vill åsidosätta det beräknade momsbeloppet om momsbeloppet ligger inom intervallet för minimum-/maximum.

- Om det beräknade momsbeloppet är större än eller lika med det högsta momsbelopp som konfigureras på snabbflikarna **Gränser** är det slutgiltiga momsbeloppet lika med det högsta momsbeloppet.
- Om det beräknade momsbeloppet är mindre än det minsta momsbelopp som konfigurerats på snabbflikarna **Gränser** är det slutliga momsbeloppet 0 (noll).

Till exempel konfigureras momsgränserna på följande sätt:

- **Minsta momsbelopp:** 100 
- **Högsta momsbelopp:** 1,000

Om det beräknade momsbeloppet är 2 000, det slutliga momsbeloppet 1 000.

Om det beräknade momsbeloppet är 500, det slutliga momsbeloppet 500.

Om det beräknade momsbeloppet är 80, det slutliga momsbeloppet 0 (noll).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
