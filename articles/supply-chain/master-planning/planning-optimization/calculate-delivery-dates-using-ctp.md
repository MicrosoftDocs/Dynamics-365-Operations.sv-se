---
title: Beräkna leveransdatum för försäljningsorder med hjälp av CTP
description: Med funktionen CTP (capable to promise) kan du ge kunder realistiska datum för när du kan lova vissa varor. I den här artikeln beskrivs hur du ställer in och använder CTP för varje planeringsmotor (Planeringsoptimering och den inbyggda motor).
author: t-benebo
ms.date: 07/20/2022
ms.topic: article
ms.search.form: SalesAvailableDlvDates, SalesTable, CustParameters, InventItemOrderSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-07-20
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 9a2d8a66fe7e68ebd5729a401af3f0efe04051b1
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229946"
---
# <a name="calculate-sales-order-delivery-dates-using-ctp"></a>Beräkna leveransdatum för försäljningsorder med hjälp av CTP

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

Med funktionen CTP (capable to promise) kan du ge kunder realistiska datum för när du kan lova vissa varor. För varje försäljningsrad kan du ange ett datum med hänsyn till befintlig lagerbehållning, produktionskapacitet och transporttider.

CTP utökar funktionen [disponibelt att lova](../../sales-marketing/delivery-dates-available-promise-calculations.md) (ATP) genom att beakta kapacitetsinformation. Tillgängligt att använda material tar bara hänsyn till materialtillgänglighet och förutsätter oändlig kapacitet, men CTP tar hänsyn till tillgänglighet för både material och kapacitet. Därför ger det en mer realistisk bild av om efterfrågan kan tillgodoses inom en viss tidsram.

CTP fungerar lite olika, beroende på vilken huvudplaneringsmotor du använder (Planeringsoptimering eller den inbyggda motorn). I denna artikel beskrivs hur du konfigurerar varje motor. CTP för planeringsoptimering har för närvarande bara stöd för en delmängd av CTP-scenarierna som stöds av den inbyggda motorn.

## <a name="turn-on-ctp-for-planning-optimization"></a>Aktivera CTP för planeringsoptimering

CTP för den inbyggda huvudplaneringsmotorn är alltid tillgänglig. Om du vill använda CTP för Planeringsoptimering måste den dock inaktiveras för ditt system. Administratörer kan använda inställningarna [funktionshantering](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *huvudplanering*
- **Funktionsnamn:** *(förhandsversion) CTP för planeringsoptimering*

## <a name="how-ctp-compares-to-atp"></a>Så här jämförS CTP med ATP

CTP och ATP liknar varandra, men CTP kan ofta ge ett mer exakt resultat, vilket visas i följande exempel.

Artikel A är en artikel som består av artiklarna B och C och lagerhållningskvantiteten för artikel A är 0 (noll). Om du gör en kontroll av produkter att använda som bara tar med material i lager blir kvantiteten tillgängliga att vara 0 (noll). Om du däremot gör en CTP-kontroll kontrollerar systemet tillgängligheten för artiklar B och C, kontrollerar resurser som behövs för att få dem till artikel A och beräknar hur många av artikel A som kan göras. Dessutom kan CTP-beräkningen kontrollera resurser och material som krävs för att göra fler av artiklar B och C, och använda dem för att skapa mer av artikel A.

En CTP-beräkning som tar hänsyn till både material och resurser kan visa en större kvantitet än en beräkning som bara kontrollerar material, särskilt när den artikel som kontrolleras är en artikel som monteras på beställning. Med andra ord baseras CTP-funktionen på nedbrytningsfunktionen och kan köras för en vald försäljningsorderrad vid beräkning av förväntat leveransdatum.

## <a name="how-ctp-differs-depending-on-the-master-planning-engine-that-you-use"></a>Hur CTP skiljer sig beroende på vilken huvudplaneringsmotor du använder

I följande tabell sammanfattas skillnaderna mellan CTP för Planeringsoptimering och CTP för den inbyggda huvudplaneringsmotorn.

| Element | Planeringsoptimering | Inbyggd huvudplaneringsmotor |
|---|---|---|
| **Inställning för leveransdatumkontroll** för order, orderrader och produkter | *CTP för planeringsoptimering* | *CTP* |
| Beräkningstid | Beräkningen initieras genom att du kör en dynamisk plan som en tidsplanerad uppgift. | Beräkningen utlöses omedelbart varje gång du registrerar eller uppdaterar en försäljningsorderrad. |
| Fältvärde **Status för CTP för planeringsoptimering** | <p>Värdet *Inte klar* visas för order och orderrader där den dynamiska planen inte har körts sedan order och rader skapades eller senast uppdaterades.</p><p>Värdet *Klar* visas för order och rader där CTP har använts för att beräkna bekräftade leveransdatum genom att köra den dynamiska planen.</p> | Värdet *Klar* visas alltid. |

## <a name="set-default-delivery-date-control-methods"></a><a name="default-methods"></a>Ange kontrollmetoder för standardleveransdatum

Systemet kan använda flera olika metoder för att beräkna uppskattningar av leveransdatum för varje order och orderrad. Du bör ställa in den kontrollmetod för leveransdatum som du oftast vill använda som global standardmetod. Du kan också ställa in individuella åsidosättningar för varje produkt. Du kan senare åsidosätta standardmetoderna för varje order och/eller orderrad efter behov.

### <a name="set-the-global-default-delivery-date-control"></a><a name="global-default"></a>Ange global kontroll för standardleveransdatum

Standardmetoden för leveransdatumkontroll används på alla nya orderrader där åsidosättningen inte gäller. Så här väljer du bort en.:

1. Gå till **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.
1. På fliken **Leveranser** på snabbfliken **Leveranskontroll** i fältet **Leveransdatumkontroll** väljer du den metod som du vill använda som standardmetod för ditt företag:

    - *Ingen* – Beräkna inte leveransdatum.
    - *Produktionstid för försäljning* – Produktionstiden för försäljning är tiden mellan det att försäljningsordern skapas och artiklarna levereras. Beräknat för leveransdatum baseras på ett standardantal dagar och beaktar inte lagertillgänglighet, känd efterfrågan eller planerad tillgång.
    - *ATP* – ATP är den kvantitet av en artikel som finns tillgänglig och därför kan utlovas en kund vid ett specifikt datum. ATP-beräkning inkluderar det obekräftade lagret, ledtider, planerade inleveranser och utleveranser.
    - *ATP + utleveransmarginal*– Leveransdatum är lika med ATP-datumet plus utleveransmarginal för artikeln. Utleveransmarginalen är den tid som krävs för att förbereda artiklar som ska levereras.
    - *CTP* – Använd den CTP-beräkning som tillhandahålls av den inbyggda huvudplaneringsmotorn. Om du använder Planeringsoptimering tillåts inte *CTP*-leveransdatumkontrollmetoden och, om den väljs, orsakar detta ett fel när beräkningen körs.
    - *CTP för planeringsoptimering* – Använd den CTP-beräkning som anges i Planeringsoptimering. Det här alternativet har ingen effekt om du använder den inbyggda huvudplaneringsmotorn.

### <a name="set-delivery-date-control-overrides-for-individual-products"></a>Ställ in åsidosättningar för leveransdatumkontroll för enskilda produkter

Du kan tilldela åsidosättningar för specifika produkter där du vill använda en annan kontrollmetod för leveransdatum än den som har ställts in som global standardmetod.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj den produkt som ska ställas in.
1. I åtgärdsfönstret, på fliken **Hantera lager** i gruppen **Orderinställningar**, väljer du **Standardorderinställningar**.
1. På sidan **Standardorderinställningar** på snabbfliken **Försäljningsorder** ange alternativet **Åsidosätt leveranskontroll** till *Ja*.
1. I fältet **Leveransdatumkontroll**, välj den metod som ska användas för den valda produkten. Samma alternativ som beskrivs i avsnittet [Ställ in global kontroll av standardleveransdatum](#global-default) är tillgängliga.

## <a name="schedule-ctp-for-planning-optimization-calculations"></a><a name="batch-job"></a>Planera CTP för beräkning av planeringsoptimering

När du använder CTP för Planeringsoptimering måste du köra en dynamisk plan för att aktivera systemet för att utföra CTP-beräkningarna och sedan ställa in bekräftade transport- och inleveransdatum för alla relevanta order. Planen måste inkludera alla artiklar som bekräftade transport- och inleveransdatum krävs för. (När du använder CTP som den inbyggda planeringsmotorn utförs CTP-beräkningarna omedelbart lokalt. Därför behöver du inte köra en dynamisk plan för att se CTP-resultatet.)

För att säkerställa att datumen är tillgängliga i tid för alla användare rekommenderar vi att du ställer in batchjobb så att de kör de relevanta planerna återkommande. Ett batchjobb som är inställt på att köra en dynamisk plan var 30:e minut ställer in bekräftad leverans och tar emot datum var 30:e minut. Därför måste användare som registrerar och importerar order vänta högst 30 minuter för att få fram bekräftad leverans och ta emot datum.

Om du vill ställa in ett batchjobb som kör en dynamisk plan med jämna mellanrum följer du dessa steg.

1. Gå till **Huvudplanering \> Huvudplanering \> Kör \> Huvudplanering**.
1. I dialogrutan **Huvudplan** på snabbfliken **Parametrar** ställ in fältet **Huvudplanering** till den dynamiska plan som du vill köra.
1. På snabbfliken **Kör i bakgrunden** ange alternativet **Batchbearbetning** till *Ja*.
1. Välj **Återkommande** och ställ in schemat efter behov.
1. Välj **OK** för att spara schemat.
1. Välj **OK** för att skapa batchjobb och stänga dialogrutan.

## <a name="use-ctp-for-built-in-master-planning"></a>Använd CTP för inbyggd huvudplanering

### <a name="create-a-new-order-by-using-ctp-for-built-in-master-planning"></a>Skapa en ny order med hjälp av CTP för inbyggda huvudplaneringar

Varje gång du lägger till en ny försäljningsorder eller orderrad tilldelas den en kontrollmetod för standardleveransdatum. Orderrubriken börjar alltid med den globala standardmetoden. Om en åsidosättning har tilldelats till en beställd artikel, använder den åsidosättningen på den nya orderraden. Annars använder den nya orderraden också den globala standardmetoden. Därför bör du ställa in dina standardmetoder så att de matchar den metod för kontroll av leveransdatum som du oftast använder. När du har skapat en order kan du åsidosätta standardmetoden på orderrubriken och/eller orderradsnivån när det behövs. Mer information finns i [Ange metoder för standardleveransdatumkontroll](#default-methods) och [Ändra befintliga försäljningsorder så att de använder CTP](#change-orders).

### <a name="view-confirmed-delivery-dates-when-you-use-ctp-for-built-in-master-planning"></a>Visa bekräftade leveransdatum när du använder CTP för inbyggda huvudplaneringar

Om du använder den inbyggda huvudplaneringsmotorn används CTP-beräkningar på order- och/eller orderrader där fältet **Leveransdatumkontroll** är inställt på *CTP*.

För försäljningslinjer som använder CTP för inbyggd huvudplanering ställer systemet automatiskt in fälten **Bekräftat transportdatum** och **Bekräftat mottagningsdatum** varje gång du sparar en försäljningsrad. Om du senare gör en relevant ändring av en försäljningsrad (till exempel genom att ändra kvantiteten eller webbplatsen), kommer datumen omedelbart att räknas om.

- Om du vill visa bekräftade leveransdatum för en försäljningsorderrad öppnar du försäljningsordern och väljer försäljningsraden. På snabbfliken **Radinformation** på fliken **Leverans** granska värdena **Bekräftat leveransdatum** och **Bekräftat inleveransdatum**.
- Om du vill visa bekräftade leveransdatum för en hel order öppnar du försäljningsordern och väljer vyn **Rubrik**. På snabbfliken **Leverans** granska värden **Bekräftat leveransdatum** och **Bekräftat inleveransdatum**.

## <a name="use-ctp-for-planning-optimization"></a>Använd CTP för planeringsoptimering

### <a name="create-a-new-order-by-using-ctp-for-planning-optimization"></a>Skapa en ny order med hjälp av CTP för Planeringsoptimering

Varje gång du lägger till en ny försäljningsorder eller orderrad tilldelas den en kontrollmetod för standardleveransdatum. Orderrubriken börjar alltid med den globala standardmetoden. Om en åsidosättning har tilldelats till en beställd artikel, använder den åsidosättningen på den nya orderraden. Annars använder den nya orderraden också den globala standardmetoden. Därför bör du ställa in dina standardmetoder så att de matchar den metod för kontroll av leveransdatum som du oftast använder. När du har skapat en order kan du åsidosätta standardmetoden på orderrubriken och/eller orderradsnivån när det behövs. Mer information finns i [Ange metoder för standardleveransdatumkontroll](#default-methods) och [Ändra befintliga försäljningsorder så att de använder CTP](#change-orders).

### <a name="view-confirmed-delivery-dates-when-using-ctp-for-planning-optimization"></a>Visa bekräftade leveransdatum vid användning av CTP för planeringsoptimering

Om du använder den Planeringsoptimering används CTP-beräkningar på order- och/eller orderrader där fältet **Leveransdatumkontroll** är inställt på *CTP för planeringsoptimering*.

För försäljningsrader som använder CTP för planeringsoptimering, fältet **Bekräftat transportdatum** och **Bekräftat inleveransdatum** kommer att vara tomma tills du kör lämplig dynamisk plan (vanligtvis genom att använda ett periodiskt batchjobb). De ställs sedan in automatiskt. Mer information finns i [Planera CTP för beräkning av planeringsoptimering](#batch-job).

Fältet **CTP för planeringsoptimeringsstatus** anger om bekräftade datum ännu har beräknats för varje rad som använder CTP för Planeringsoptimering. Fältet visar värdet *Inte klart* för rader och order där de bekräftade leveransdatumen antingen ännu inte har beräknats eller inte längre gäller på grund av andra ändringar. Det visar värdet *Klar* för rader och order som har beräknats. Du kan visa status för varje rad och för hela ordern.

- Om du vill visa status för en försäljningsorderrad öppnar du försäljningsordern och väljer försäljningsraden. På snabbfliken **Raddetaljer** på fliken **Leverans**, granska värdet **CTP för planeringsoptimeringsstatus**. Fälten **bekräftat transportdatum** och **bekräftat inleveransdatum** för raden visas också på den här fliken när de har beräknats.
- Om du vill visa status för en hel order öppnar du försäljningsordern och väljer vyn **Rubrik**. På snabbfliken **Leverans** granska värdet **Status för CTP för planeringsoptimering**. **Bekräftat transportdatum** och **bekräftat inleveransdatum** för order visas också på den här fliken när de har beräknats.

<!-- KFM: The following text may be untrue and needs to be reviewed with the PM for next revision:

The sales orders that are *Ready* or *Not ready* are shown in the **All sales orders** list page. You can check the sales order that are *Ready* or *Not ready* from the sales order list page by filtering on this new status field.

-->

> [!NOTE]
> - Om du uppdaterar en försäljningsorderrad efter att CTP för Planeringsoptimering har beräknat bekräftade datum för den, rensar systemet dessa datum till nästa gång lämplig dynamisk plan körs.
> - Om du redigerar en relaterad inställning som kan påverka befintliga bekräftade datum (till exempel genom att ändra ledtider, reservationer eller markeringar), bör du avmarkera de bekräftade datumen för relevanta befintliga order. Denna åtgärd medför att status för varje relevant rad ändras till *Inte klar*. Den här ändringen leder i sin tur till att systemet räknar om de bekräftade datumen nästa gång den dynamiska planen körs.

## <a name="change-existing-sales-orders-so-that-they-use-ctp"></a><a name="change-orders"></a>Ändra befintliga försäljningsorder så att de använder CTP

Du kan när som helst ändra **Leveransdatumkontroll** för en öppen order. Du kan ändra värdet på rubriknivå och/eller för varje rad efter behov.

### <a name="change-to-ctp-at-the-order-header-level"></a>Ändra till CTP på orderrubriksnivå

<!-- KFM: Would be nice to mention how changing this setting on the header affects the individual lines. -->

Följ de här stegen om du vill ändra en order så att den använder CTP på orderrubriknivå.

1. Gå till **Kundreskontra \> Order \> Alla försäljningsorder**.
1. Öppna den försäljningsorder som du vill skapa eller skapa en ny.
1. Välj **Rubrik** för att öppna rubrikinformationen på sidan **Försäljningsorderinformation**.
1. På snabbfliken **Leverans** ange fältet **Leveransdatumkontroll** till ett av följande värden, beroende på vilken planeringsmotor du använder:

    - *CTP* – Använd den CTP-beräkning som tillhandahålls av den inbyggda huvudplaneringsmotorn. Om du använder Planeringsoptimering är leveransdatumkontrollmetoden *CTP* inte tillåten. Om du väljer det här värdet inträffar därför ett fel när beräkningen körs.
    - *CTP för planeringsoptimering* – Använd den CTP-beräkning som anges i Planeringsoptimering. Den här inställningen har ingen effekt om du använder den inbyggda huvudplaneringsmotorn.

<!-- KFM: Additional dialogs are shown here. Review these with the PM and expand this procedure at next revision. -->
1. Välj **OK** om du vill applicera dina ändringar.

### <a name="change-to-ctp-at-the-order-line-level"></a>Ändra till CTP på orderradnivå

Om du har skapat en orderrad med en annan kontrollmetod för leveransdatum, kan du när som helst ändra till CTP. Ändringar som du gör på radnivå påverkar inte några andra rader. De kan dock leda till att den övergripande orderleveransdatumen flyttas framåt eller bakåt, beroende på hur varje uppdaterad radberäkning ändras. <!-- KFM: Confirm this intro at next revision -->

Följ de här stegen om du vill ändra en order så att den använder CTP för inbyggd huvudplanering på linjenivå, följ dessa steg.

1. Gå till **Kundreskontra \> Order \> Alla försäljningsorder**.
1. Öppna den försäljningsorder som du vill skapa eller skapa en ny.
1. På sidan **Försäljningsorderinformation** på snabbfliken **Försäljningsorderrad** markerar du den försäljningsorderrad som du vill ställa in.
1. På snabbfliken **Raddetaljer** på fliken **Leverans** ange fältet **Leveransdatumkontroll** till ett av följande värden, beroende på vilken planeringsmotor du använder:

    - *CTP* – Använd den CTP-beräkning som tillhandahålls av den inbyggda huvudplaneringsmotorn. Om du använder Planeringsoptimering är leveransdatumkontrollmetoden *CTP* inte tillåten. Om du väljer det här värdet inträffar därför ett fel när beräkningen körs.
    - *CTP för planeringsoptimering* – Använd den CTP-beräkning som anges i Planeringsoptimering. Den här inställningen har ingen effekt om du använder den inbyggda huvudplaneringsmotorn.

    Dialogrutan **Tillgängliga transport- och inleveransdatum** visas och visar tillgängliga transport- och inleveransdatum. Den här dialogrutan fungerar på samma sätt för orderrader som för orderrubriken, vilket beskrivs i föregående avsnitt.

1. Klicka på **Spara** i åtgärdsfönstret.
