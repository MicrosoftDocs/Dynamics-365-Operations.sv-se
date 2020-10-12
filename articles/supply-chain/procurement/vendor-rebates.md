---
title: Leverantörsrabatter
description: Detta avsnitt innehåller en översikt över de vanligaste åtgärderna när du arbetar med leverantörsrabatter. Leverantörsrabatter hjälper förgöra anspråk på intjänade rabatter.
author: omulvad
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TAMVendRebateAgreement
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 2012
ms.openlocfilehash: acf7df09b467e0b0b0463946be018ff199d7153e
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834270"
---
# <a name="vendor-rebates"></a>Leverantörsrabatter

[!include [banner](../includes/banner.md)]

Leverantörsrabatter hjälper förgöra anspråk på intjänade rabatter.

Detta avsnitt innehåller en översikt över de vanligaste åtgärderna när du arbetar med leverantörsrabatter. Översikten beskriver följande uppgifter:

- Granska informationen i ett rabattavtal
- Identifiera order som är berättigade till rabatter, och generera anspråk på rabatten.
- Granska och godkänn anspråk.

## <a name="audience-and-purpose"></a>Publik och syfte

Informationen i detta avsnitt riktar sig till beslutsfattare inom företag som innehar positioner som exempelvis inköpschef, ekonomichef och redovisningschef, och som har ansvar för följande:

- Förhandla om leverantörspriser, rabatter och rabattavtal.
- Hantera personal som behandlar rabattanspråk samlar in betalningar.
- Lagerbeställningar till bästa möjliga pris.

Personer på dessa positioner söker metoder att uppnå olika mål. Nedan följer några exempel:

- Hantera olika typer av leverantörskampanjer och rabattvillkor på ett flexibelt sätt.
- Minska den administrativa belastningen och antalet misstag kopplade till övervakning av kampanjresultat och behandling av ansökningar.
- Förbättra kassaflödesprognoserna genom periodisering för framtida försäljning.
- Ha en kvantifierad grund för pågående och framtida rabattförhandlingar med leverantörer.

## <a name="review-details-of-a-vendor-rebate-agreement"></a>Granska informationen i ett rabattavtal för leverantörer

Ett rabattavtal för leverantörer är ett kontrakt med en leverantör som anger de förhandlade villkor enligt vilka företaget berättigas till monetär ersättning i utbyte mot att uppnå förinställda inköpsmål. Rabattavtal för leverantörer registreras på sidan **Rabattavtal**.

För att öppna sidan **Rabattavtal för leverantörer** markerar du **Anskaffning och inköp** &gt; **Leverantörsrabatter** &gt; **Rabattavtal**.

![Inköpsavtal](media/purchase-agreement.PNG)

På sidan **Rabattavtal för leverantörer** på sidan kan du visa information om de förhandlade villkoren i ett leverantörsavtal.

Avtalets rubrik anger de allmänna villkor som kvalificerar ett företag för rabatter. Rubrikinformationen anger att en leverantör beviljar en rabatt när en viss produkt köps i en viss kvantitet. I rubriken kan du också ange måttenhet och beräkningsdatumets typ.

- På fliken **Översikt** om du har rader med **Artikelkod** angett till *register* för att ange artikeln, gäller avtalet för den specifika artikeln. Om du har rader med **artikelkod** inställd på *grupp* eller *alla* för att ange artiklarna, kommer rabattavtal för leverantörer att bearbetas individuellt per artikel kvalificering för artikelkoden, inte över alla artiklar som är kvalificerade för artikelkoden.

- På fliken **Allmänt**, i fältet **Rabattalternativ för måttenhet** kan du definiera huruvida en måttenhet bör vara ett villkor för att inköpsorderraden ska vara kvalificerad för ett rabattanspråk.

    - **Konvertera** – En inköpsorderrad är berättigad till en leverantörsrabatt i enlighet med rabattavtalet. Du får en rabatt oavsett den måttenhet som används på raden.
    - **Exakt matchning** – För att en inköpsrad ska bli berättigad för rabatt måste den ha samma måttenhet som anges i avtalet.

- I fältet **Allmänt**, i fältet **Beräkningsdatumets typ**, markerar du det datum som används för att avgöra om köpet sker inom rabattavtalets giltighetsperiod.

    - **Skapades** – Använd det datum då inköpsorderna skapades.
    - **Begärd leverans** – Använd begärt leveransdatum.

Du kan ange rabattavtalet för leverantör mer detaljerat på avtalsraderna.

- I fältet **Ackumulera inköp efter** kan du ange beräkningen av rabattanspråket. Beloppet kan tilldelas beror på högst (vecka, månad, år, livstid eller en anpassad period). Värdet för **Faktura** anger att ett rabattanspråk bestäms varje gång en inköpsorderrad faktureras.
- I fältet **Från** kan du ange grunden för rabattberäkningen.

    - **Brutto** – Rabatten beräknas baserat på varans bruttopris.
    - **Netto** – Rabatten beräknas baserat på varans nettopris (dvs. priset efter det att andra rabatter har tillämpats).

- Fälten **Periodiserad redovisning för rabattprogram** och **Utgiftskonto för rabattprogram** anger kontonummer som erhåller periodiserade rabattbelopp under ett mellanliggande skede mellan godkännande och bearbetning.
- När alternativet **Godkännande krävs** har angetts som **Ja** måste begäran om rabatt godkännas innan den kan periodiseras eller betalas ut.
- Fältet **Brytningstyp för rabattrad** anger grunden för rabatterna.

    - **Kvantitet** – Rabatterna är volymbaserade.
    - **Belopp** – Rabatterna är beloppsbaserade.

- I snabbfliken **Rader** ser du hur olika kvantitetsnivåer kan ställas in för att ge olika rabatter. I illustrationen ovan anger till exempel fälten **Från-värde** och **Till-värde** att en produktkvantitet på mellan 10 och 19 enheter berättigar till en rabatt på 15 USD per enhet.

    > [!NOTE]
    > Värdet **Från-värde** är inkluderande, medan värdet **Till-värde** är exkluderande. Exempelvis anges **Brytningstyp för rabattrad** som **Kvantitet**, och du anger **1** i fältet **Från-värde** och **3** i fältet **Till-värde**. I så fall gäller rabattbeloppet när du köper en eller två artiklar, men inte när du köper tre artiklar.

- I fältet **Godkännandestatus för arbetsflöde** anger värdet **Godkänd** att avtalet kan tillämpas på inköpsorder som uppfyller villkoren i avtalet.

## <a name="identify-orders-that-qualify-for-rebates-and-generate-rebate-claims"></a>Identifiera order som är berättigade till rabatter, och generera rabattanspråk

När inköpsorder skickas till en leverantör som företaget har ett rabattavtal med, identifierar programmet eventuella framtida utbetalningar av leverantörskrediter. Om inköpsordern berättigar till rabatt, genereras ett rabattanspråk för varje orderrad så fort en inköpsfaktura har bokförts. Detta är en automatisk process. Du kan senare granska de förväntade rabatterna och se effekten av dessa rabatter på produktens kostnad och vinstmarginal.

### <a name="view-details-of-rebates-that-are-applied-to-a-purchase-order-line-per-the-vendor-rebate-agreement"></a>Visa information om rabatter som tillämpas på en inköpsorderrad i enlighet med rabattavtalet för leverantör

1. På sidan **Inköpsorder** markerar du en orderrad och sedan **Inköpsorderrad** &gt; **Visa** &gt; **Prisinformation**.
2. På sidan **Prisinformation** markerar du snabbfliken **Rabatter**.

Rabattinformationen visas också i fältet **Leverantörsrabatt** i avsnittet **Marginalberäkning** på sidan **Prisinformation**.

> [!NOTE]
> På sidan **Anskaffnings- och inköpsparametrar**, på fliken **Priser**, kontrollera att alternativet **Aktivera prisinformation** har engetts som **Ja**. Om alternativet har angetts som **Nej** kan du inte visa rabatterna.

## <a name="review-and-approve-claims"></a>Granska och godkänn anspråk

Rabattanspråk som genereras representerar framtida betalningar som kan förväntas från leverantören. Innan en kreditfaktura utfärdas till leverantören, vill avtalets ägare vanligtvis granska anspråken och godkänna dem. Tänk emellertid på att statusen för ett anspråk avgör huruvida anspråket är redo att gå igenom godkännandeprocessen.

### <a name="the-status-of-claims-and-the-effect-on-the-approval-process"></a>Status för anspråk och effekten på godkännandeprocessen

När ett anspråk genereras ändras dess status till **Ska beräknas** om rabatten beviljas på ackumulerad basis, eller **Beräknad** om rabatten ges per faktura. Om statusen för ett anspråk är **Ska beräknas** måste anspråket genomgå en beräkningsprocess som hanteras med hjälp av funktionen Ackumulera. Endast anspråk med statusen **Beräknad** kan ingå i godkännandeprocessen.

> [!NOTE]
> Om alternativet **Godkännande krävs** i ett avtal om leverantörsrabattavtal har angetts som **Nej**, kommer alla anspråk som skapas att få statusen **Godkänd**. Godkännandet är obligatorisk för anspråk som beviljas på ackumulerad basis.

### <a name="approve-claims-and-view-postings-and-invoice-details"></a>Godkänn anspråk och visa information om bokföringsposter och fakturor

När ett anspråk har godkänts kan det bearbetas av Leverantörsreskontra (A/P). En kreditnota (leverantörsfaktur) för rabattanspråkets belopp genereras automatiskt. Krediten kan sedan läggas till i leverantörssaldot, och A/P-teamet kan inkludera den i den kvittningsprocessen.

1. Markera **Anskaffning och inköp** &gt; **Leverantörsrabatter** &gt; **Rabattanspråk** för att öppna ett rabattanspråk.
2. Stäng rabattanspråket.
3. Markera begäran och markera sedan **Godkänn** i åtgärdsfönstret.
4. På anspråkssidan, i fältet **Leverantör**, markerar du den leverantör som du är behörig att få en rabatt från, och väljer sedan **OK**.

    En periodiseringsjournal för rabatt bokförs för anspråksbeloppet. Denna bokföringspost debiterar kontot för ackumulerad kundreskontrarabatt för den förväntade leverantörskrediten, och krediterar den förväntade intäkten till det preliminära kontot för mottagna, ackumulerade leverantörsrabatter.

    ![Meddelande](media/message.png)

5. Markera raden i rabattlistan och markera sedan **Rabattransaktioner** i åtgärdsfönstret för att visa och navigera till journalbatchnumret för bokföringen av rabattperiodiseringen.

    För att flytta anspråken till den vanliga A/P-processen, måste A/P-ansvarig nu slutföra rabattanspråket genom att köra processfunktionen.

6. I åtgärdsfönstret markerar du **Behandla**, och sedan **Filter**. I fältet **Kriterier** för fältet **Leverantörskonto** markerar du den leverantör för vilken du vill behandla rabattanspråk, väljer övriga relevanta filter och sedan **OK**.

    Meddelandefält och det faktum att statusen ändras till **Slutförd** anger att följande händelser har inträffat:

    - En bokföringspost om rabattperiodisering har vänt på de tidigare tillfälliga beloppen på kontona för periodiseringsfordran och -utgifter.
    - En leverantörsfaktura (kreditfaktura) för rabattbeloppet har skapats.

        > [!NOTE]
        > Inställningen för alternativet **Manuell fakturabokföring** på fliken **Rabattprogram** på sidan **Anskaffnings- och inköpsparametrar** avgör huruvida en leverantörsfaktura bokförs manuellt eller automatiskt i samband med behandling av anspråk.

    - I samband med att leverantörsfakturan bokförs (automatiskt eller manuellt) har leverantörens utbetalningskonto debiterats, och kontot för mottagna rabatter och avdrag har krediterats.

        > [!NOTE] 
        > Kontonumret för rabatter och avdrag anges för den anskaffningskategori som används för rabatten på inköpsfakturaraden. Anskaffningskategorin anges i sin tur på fliken **Rabattprogram** på sidan **Anskaffnings- och inköpsparametrar**.

7. I rabattlistan markerar du raden innan du väljer **Rabattransaktioner** i åtgärdsfönstret för att visa och navigera till journalbatchnumret för bokföringen av denna rabattperiodisering samt numret på leverantörsfakturan.
8. Markera raden för leverantörsfakturatransaktionen och markera sedan **Leverantörsfaktura** i åtgärdsfönstret. Om leverantörsfakturan har bokförts visas fakturajournalen. I annat fall visas leverantörsfakturan som en väntande leverantörsfaktura som kräver manuell bokföring.

    Fakturaraden anger information om leverantörsfakturan för anskaffningskategorin **Provisioner och rabatter**.

9. På sidan **Alla leverantörer** väljer du den leverantör som du erhåller en rabatt från, och i åtgärdsfönstret markerar du **Transaktioner**. Hitta raden för fakturan. Rabattbeloppet har nu lagts till i leverantörssaldot.

## <a name="summary"></a>Sammanfattning

Processen för att hantera leverantörsrabatter omfattar flera manuella spårningsuppgifter som ofta är omständliga. Genom att automatisera dessa uppgifter kan hanteringsfunktionen för leverantörsrabatter hjälpa dig att ta dig igenom följande processer:

- Generera korrekta rabattanspråk
- Periodisering av förväntad fordran och interimintäkt i redovisningen
- Uppdatering av leverantörssaldot och intäktsutdraget med de avdrag som förfaller
