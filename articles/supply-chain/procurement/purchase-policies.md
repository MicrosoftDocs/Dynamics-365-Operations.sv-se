---
title: Inköpspolicyer – översikt
description: Det här avsnittet innehåller information om inköpspolicyer. En inköpspolicy är en grupp regler som styr processen för inköpsrekvisition. Administratörer som är hjälper till med inköpspolicyer för anskaffning implementerar sin anskaffningsstrategi genom att skapa en policystruktur som stämmer överens med organisationens strategiska inköpskrav.
author: RichardLuan
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqSourcingPolicyRule, SysPolicy, SysPolicyListPage, PurchReqControlRule, RequisitionReplenishCatAccessPolicyRule, PurchReApprovalPolicyRule, RequisitionReplenishControlRule, PurchReqControlRFQRule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11614
ms.assetid: 729a304d-0f3f-4ccb-bd5b-46ee0976c57f
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8c8fa3e4b59cdb013c1c524e06085b06905715e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215899"
---
# <a name="purchasing-policies-overview"></a>Inköpspolicyer – översikt

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om inköpspolicyer. En inköpspolicy är en grupp regler som styr processen för inköpsrekvisition. Administratörer som är hjälper till med inköpspolicyer för anskaffning implementerar sin anskaffningsstrategi genom att skapa en policystruktur som stämmer överens med organisationens strategiska inköpskrav.

En inköpspolicy består av en uppsättning med policyregler. När du definierar en policyregel, väljer du först en regeltyp. Du skapar sedan en regel för regeltypen, genom att definiera inställningar, startdatum och slutdatum för regeln.  

Till exempel skapar en administratör en policy, väljer regeltypen **Katalogpolicy** och lägger sedan till en katalogpolicyregel till policyn. Den här katalogpolicyregeln anger att affärsföretagskatalogen måste användas för intern anskaffning. När inköpspolicyn har kopplats till en viss organisation, kan medarbetare för den organisationen se affärsföretagskatalogen när de skapar rekvisitioner.

## <a name="assigning-policies-to-organizations"></a>Tilldela policyer till organisationer
Innan en policy blir giltig, måste den associeras till en organisation. Inköpspolicyer associeras med hierarkisyftet **Anskaffningsintern kontroll**. Därför tillämpas endast inköpspolicyer till organisationer i hierarkier som har ett hierarkisyfte för **Anskaffningsintern kontroll**. Du kan också välja organisationer från den enkla listan över juridiska personer i tabellen CompanyInfo. Dessa juridiska personer är definierade i policyramverket som "Företag".

## <a name="determining-which-rule-to-apply"></a>Bestämning av vilken regeln som ska gälla
Beroende på hur du konfigurerar dina inköpspolicyer, kan flera regler påverka användarna i organisationen. I följande exempel visas olika sätt för att konfigurera inköpspolicyer och ange hur policyer används när en transaktion inträffar.

### <a name="example-1-simple-purchasing-policy-configuration"></a>Exempel 1: Enkel konfiguration av inköpspolicy

Organisationer som är mindre och mindre komplicerade kan ställa in inköpspolicyer efter juridisk person, och kan bara använda organisationshierarkin Företag.  

För Fabrikam, ett mindre företag, varierar inköpskraven lite i organisationen. Inköpsregler varierar bara mellan organisationens juridiska personer. Till exempel medarbetare i Fabrikam Kanada och medarbetare i Fabrikam USA köper varor och tjänster från olika kataloger och olika leverantörer. Därför konfigurerar Fabrikam dess inköpspolicyer på juridisk personnivå.  

Fabrikam skapar två inköpspolicyer. Policy A avser dess amerikanska juridiska person, 1111. Policy B avser dess kanadensiska juridiska person, 2222. När en medarbetare i juridisk person 1111 skapar en inköpsrekvisition härleds policyreglerna från policy A. Exempelvis anges produktkatalogen som medarbetaren ser i katalogpolicyregel för policy A.  

När en medarbetare i den juridiska personen 2222 skapar en inköpsrekvisition härleds policyreglerna från policy B.  

**Obs!** Om en medarbetare för juridisk person 1111 köper en artikel på uppdrag av en medarbetare för juridisk person 2222, används policyreglerna för juridisk person 2222 (dvs. policyreglerna från policy B).

### <a name="example-2-complex-purchasing-policy-configuration"></a>Exempel 2: Komplex konfiguration av inköpspolicy

I föregående exempel definieras alla inköpsregler i en enkel organisationshierarki, organisationshierarkin Företag. Det kan dock hända att en komplex organisation definierar policyer för flera organisationshierarkier.  


Contoso är ett stort företag som kräver komplexa inköpsregler för att kontrollera rekvisitionprocessen. Contoso har definierat regler för två olika organisationshierarkier: Avdelning och Global inköpskontroll.  

Policy 123 definieras för organisationshierarkinAvdelning för Försäljning Storbritannien - försäljningavdelning. I policy 123 anger inköpsrekvisitionkontrollregeln de begränsningar som måste framtvingas för minsta orderkvantiteter. I denna regel markeras alternativet **Framtvinga restriktioner för minsta orderkvantitet**.  

Policy 456 definieras för organisationshierarkin Global inköpskontroll för försäljnings- och marknadsavdelningen. I policy 456 anger inköpsrekvisitionkontrollregeln inte de begränsningar som måste aktiveras för minsta orderkvantiteter. I denna regel avmarkeras alternativet **Framtvinga restriktioner för minsta orderkvantitet**.  

Sam arbetar i Försäljning Storbritannien - försäljningavdelning på Contosos brittiska kontor. I principerna för båda organisationshierarkierna Avdelning och Global inköpskontroll gäller för hans avdelning. När han skapar en inköpsrekvisition, måste systemet fastställa vilken policy som ska användas. Systemadministratören ställer in inköpspolicyparametrarna för att ange att inköpspolicyer måste tillämpas i följande prioritetsordning:

1.  Global inköpskontroll
2.  Avdelning
3.  Företag

Därför tillämpas policy 456 på den inköpsrekvisition som Sam skapar, och ingen minsta orderkvantitet krävs för inköpsrekvisitionen.

## <a name="policy-rules"></a>Policyregler
### <a name="catalog-policy-rule"></a>Policyregel för katalog

Katalogpolicyregeln avgör vilken anskaffningskatalog som användare ser när de skapar inköpsrekvisitioner. Om en användare har beviljats behörighet att beställa produkter på uppdrag av en annan användare, använder rekvisitionem den katalogpolicyregel som definierats för beställarens juridiska person och driftenhet för att fastställer vilken katalog som ska visas på anskaffningsplatsen. Innan du kan definiera en katalogpolicyregel måste du skapa och publicera en anskaffningskatalog.

### <a name="category-access-policy-rule"></a>Policyregel för kategoriåtkomst

Kategoripolicyregeln för åtkomst avgör vilka kategorier som användare har åtkomst till när de skapar inköpsrekvisitioner. Om ingen regel anges, kan alla anskaffningkategorier läggas till i inköpsrekvisitionen.

1.  Markera alternativet **Inkludera överordnad regel** om du vill använda kategoripolicyregeln för åtkomst för den överordnade organisationen till kategorin.
2.  Välj de kategorier som regeln gäller för i fönstret **Tillgängliga kategorier**. När du väljer en kategori läggs alla kategorier som är högre i hierarkin, även till listan **Valda kategorier**.
3.  Om du vill använda regeln på alla underkategorier för den valda kategorin, välj alternativet **Inkludera underkategorier**.

### <a name="category-policy-rule"></a>Kategoripolicyregel

Kategoripolicyregeln definierar hur användarna kan välja leverantörer för varje kategori. Den definierar också krav för mottagnings- och faktureringprocesserna.

### <a name="re-approval-rule-for-purchase-orders"></a>Regel för omgodkännande av inköpsorder

Den omgodkännande regeln är en valfri regel som definierar villkoren för omgodkännande när en inköpsorder ändras. De valda fälten utvärderas i arbetsflödet för inköpsordern när villkoret "Kräver omgodkännande av inköpsorder" anges i arbetsflödet.

> [!NOTE]
> Redovisningsfördelningen kommer alltid att återställas när en godkänd inköpsorder med aktiverad ändringshantering ändras. Du bör därför vara uppmärksam om att om du vill undvika att en inköpsorder godkänns på nytt när vissa fält ändras; fältet Accounting distribution.changed bör INTE inkluderas som ett markerat fält för återgodkännande. 

### <a name="purchase-requisition-rfq-rule"></a>Anbudsförfrågningsregel för inköpsrekvisition

Anbudsförfrågningsregeln för inköpsrekvisition definierar kriterier för att begära en anbudsförfrågan för en inköpsrekvisitionsrad. När en rad uppfyller villkoren visas stämpeln ”informell anbudsförfrågan” eller ”formell anbudsförfrågan” på rekvisitionraden.

### <a name="purchase-requisition-control-rule"></a>Kontrollregel för inköpsrekvisition

Kontrollregeln för inköpsrekvisitioner för rekvisitioner av typen **förbrukning** är en valfri regel. När du skapar regler av den här typen, kan du ange alternativ på olika flikar:

-   På fliken **Arbetsflödeskörning** kan du konfigurera de fält som måste anges på rekvisitionraden för att inköpsrekvisitionen ska skickas in för godkännande.
-   På fliken **Orderkvantiteter** kan du konfigurera de fält som krävs på inköpsrekvisitionen under vissa villkor. Du kan också framtvinga orderkvantiteter.
-   På fliken **Datum** kan du konfigurera om redovisningdatumet är samma som det begärda datumet
-   På fliken **Adress** kan du ange om användaren får skapa nya adresser i systemet som ska användas för inköpsrekvisitionen.

### <a name="requisition-purpose-rule"></a>Rekvisitionssyftesregel

Rekvisitionsyfteregeln är en valfri regel som bestämmer vilken typ av rekvisitionsyfte som tillåts för en viss juridisk person. Om inte ett annat syfte anges i regeln har rekvisitioner automatiskt ett syfte med **Förbrukning** när de skapas.

### <a name="replenishment-category-access-policy-rule"></a>Åtkomstpolicyregel för återanskaffningskategori

Åtkomstpolicyn för återanskaffningskategori är en valfri regel som bestämmer produkterna, som är tillgängliga för att uppfylla rekvisitionbegäran för en viss juridisk person när rekvisitionsyftet är **Återanskaffning**.

### <a name="replenishment-control-rule"></a>Kontrollregel för återanskaffning

Kontrollregeln för återanskaffning är en valfri regel som definierar de fält som måste anges på rekvisitionraden för att inköpsrekvisitionen ska skickas in för godkännande när rekvisitionsyftet är **Återanskaffning**.

### <a name="purchase-order-creation-and-demand-consolidation-rule"></a>Skapande av inköpsorder och konsolideringsregel för efterfrågan

Inköpsorderskapande och efterfrågekonsolideringsregeln definierar policyreglerna som ska användas när en inköpsorder skapas från en godkänd inköpsrekvisition. När du skapar regler av den här typen, kan du ange alternativ på olika flikar:

-   På fliken **Uppdelning av inköpsorder** kan du definiera kriterier för uppdelning av inköpsrekvisitionsrader till separata inköpsorder.
-   På fliken **Pris-/rabattöverföring** kan du definiera när du vill omberäkna prisavtalet när en inköpsorder skapas:
    -   **Bara om det inte finns något handelsavtal** – Priser och rabatter överförs från inköpsrekvisitionen bara om det inte finns något tillämpligt handelsavtal eller baspris. Om ett handelsavtal eller baspris finns för artikeln eller leverantören, är priser och rabatter omräknat baserat på handelsavtalet eller baspriset och gäller för inköpsordern. Om inget annat anges är detta standardbeteendet.
    -   **Alltid** – Priser och rabatter alltid överförs från inköpsrekvisitionen.

    Du kan även tillåta beställaren att ändra metoden för pris- och rabattöverföringen för enskilda inköpsrekvisitionsrader, oavsett vilken pris/rabattöverföringsregel som definieras. Välj alternativet **Tillåt manuell åsidosättning per inköpsrekvisitionsrad**, om du vill aktivera den här funktionen.
-   På fliken **Överföring av artikelbeskrivning** kan du överföra artikelbeskrivningen från inköpsrekvisitionen, när den har hämtats från en anbudsförfrågan.
-   På fliken **Pristolerans** kan du definiera pristoleransreglerna som används för att dirigera tillbaka de godkända inköpsrekvisitionerna genom granskningsprocessen, när priset på en artikel i en intern katalog ökar. Ange maxbeloppet som nettobeloppet i en radartikel i en inköpsrekvisition kan öka, mellan den tidpunkt då inköpsrekvisitionen godkänns och tid när inköpsordern skapas. Nettobeloppet beräknas genom att använda följande formel: (\[Kvantitet × (enhetspris – rabatt) ÷ prisenhet\] + inköpstillägg) × (100 – rabatt i procent) ÷ 100 Inköpsrekvisitionsrader som överstiger pristoleransen som du anger hålls för manuell hantering. Reglerna som du konfigurerar på fliken **Bearbetningsfel** bestämmer hur inköpsrekvisitionsraderna bearbetas.
-   På fliken **Bearbetningsfel** kan du konfigurera den bearbetningsregeln som tillämpas på en inköpsrekvisition, om den inte klarar validering under skapandet av inköpsordern, på grund av ett leverantörfel eller ett pristoleransfel. Välj ett av följande alternativ:
    -   **Ingen åtgärd** – Inköpsrekvisitionraderna återstår på sidan **Bokför godkända inköpsrekvisitioner för leverans**. Inköpsrekvisitionsradernas status är fortsatt **Godkänd**. Du måste lösas fel innan en inköpsorder kan skapas för rader i inköpsrekvisitionen.
    -   **Annullera inköpsrekvisitionsraden** – Inköpsrekvisitionsraderna annulleras. Beställaren kan skapa en ny inköpsrekvisition för annullerade raderna, om han/hon ändå vill begära radartiklarna.
    -   **Skapa en ny inköpsrekvisitionsrad** – Inköpsrekvisitionsraderna annulleras. Nya inköpsrekvisitioner skapas sedan som bara innehåller raderna i inköpsrekvisitionen som inte klarade validering. De nya inköpsrekvisitionerna som skapas har status **Utkast**. Dessa inköpsrekvisitioner kan skickas tillbaka för granskning, efter att valideringfelen har lösts. Förberedaren för inköpsrekvisitionsraderna uppmanas om att raderna annullerades, och att nya Inköpsrekvisitioner har skapats för inköpsrekvisitionsraderna som misslyckades.
-   På fliken **Manuellt skapande av inköpsorder** kan du definiera de parametrar som bestämmer om en inköpsrekvisition måste bearbetas manuellt, eller om den kan automatiskt konverteras till en inköpsorder. Parametrarna kan gälla för interna katalogartiklar, externa katalogartiklar eller artiklar som inte finns i kataloger. Välj ett av följande alternativ:
    -   **Skapa inköpsorder manuellt** – Skapar inköpsorder manuellt för alla inköpsrekvisitioner.
    -   **Skapa inköpsorder automatiskt** – Skapar inköpsorder automatiskt för alla godkända inköpsrekvisitioner. Inga inköpsrekvisitioner hålls för manuell inköpsorderskapelse.
    -   **Skapa inköpsorder automatiskt utom under dessa villkor** – Skapar inköpsorder manuellt för inköpsrekvisitioner som matchar de kriterier som du definierar. Alla andra inköpsrekvisitioner som har godkänts, konverteras automatiskt till inköpsorder. Om du väljer **Skapa inköpsorder automatiskt utom under dessa villkor** kan du lägga till anskaffningkategorier och leverantörer för att ange vilka godkända inköpsrekvisitionsrader som hålls för manuell bearbetning. Det här alternativet kan gälla för interna katalogartiklar, externa katalogartiklar eller artiklar som inte finns i kataloger. När du väljer en anskaffningkategori markeras även alla underkategorier för anskaffningkategorin. Välj alternativet **Alla** för en viss typ av inköpsrekvisitionsrad och håll alla rader på radtypen för manuell bearbetning.

    Om du vill skapa inköpsorder automatiskt från godkända inköpsrekvisitioner när batchjobbet för inköpsorderutveckling körs, markerar du kryssrutan **Skapa inköpsorder automatiskt som ett batchjobb** . Det här alternativet gäller bara för inköpsrekvisitioner som inte kräver bearbetning manuellt. Genom att köra automatisk inköpsorderutvecklingen som ett batchjobb kan du tidsplanera den här aktiviteten vid tid när resurser begränsas mindre. Om alternativet **Förskottsbetalning krävs** på inköpsrekvisitionsrader, välj alternativet **När rekvisitionen har ställts in för förskottsbetalning** för att hålla godkända inköpsrekvisitioner för manuell bearbetning. Inköpsrekvisitioner som är aktiverade för manuell bearbetning kan filtreras, så att du kan bara visar de inköpsrekvisitionsrader som kräver förskottsbetalning.
-   På fliken **Efterfråganskonsolidering** kan du definiera de parametrar som avgör om inköpsrekvisitioner som bearbetas manuellt, kan betraktas för inköpsrekvisitionkonsolidering. Parametrarna kan gälla för interna katalogartiklar, externa katalogartiklar eller artiklar som inte finns i kataloger. Välj ett av följande alternativ:
    -   **Tillåt inte efterfråganskonsolidering** – Inga godkända inköpsrekvisitionsrader är valbara för efterfråganskonsolidering. Det här alternativet är markerat som standard och gäller endast för inköpsrekvisitionsrader som måste bearbetas manuellt för inköpsorderskapelse.
    -   **Tillåt alltid efterfråganskonsolidering** – Alla godkända inköpsrekvisitionsrader är valbara för efterfråganskonsolidering. **Obs!** Om du väljer alternativet **Tillåt alltid efterfråganskonsolidering** på fliken **Efterfråganskonsolidering** men du väljer alternativet **Automatiskt skapande av inköpsorder** på fliken **Manuellt skapande av inköpsorder** kommer alla inköpsrekvisitioner att hållas för manuell bearbetning.
    -   **Tillåt efterfråganskonsolidering under dessa villkor** – Definiera kriterierna som avgör om godkända inköpsrekvisitionsrader är valbara för efterfråganskonsolidering. För varje typ av inköpsrekvisitionsraden kan du ange kriterierna efter anskaffningkategori och leverantör. Om du väljer **Tillåt efterfråganskonsolidering under dessa villkor** kan du ange kriterierna efter anskaffningskategori och leverantör, För varje typ av inköpsrekvisitionsrad. När du väljer en anskaffningkategori markeras även alla underkategorier för anskaffningkategorin. Om du väljer alternativet **Alla** för en viss radtyp, är alla inköpsrekvisitionsrader för den radtyp valbara för begärankonsolidering.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]