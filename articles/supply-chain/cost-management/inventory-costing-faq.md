---
title: Vanliga frågor om kostnadsredovisning för lager
description: Denna artikel besvarar några vanliga frågor om lagerkostnadsredovisning i Microsoft Dynamics 365 Supply Chain Management.
author: rachel-profitt
ms.date: 05/03/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-03
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 467839b1d0ca6788a92ae60d46686374d0a58046
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8850856"
---
# <a name="inventory-costing-faq"></a>Vanliga frågor om kostnadsredovisning för lager

[!include [banner](../includes/banner.md)]

Denna artikel besvarar några vanliga frågor om lagerkostnadsredovisning i Microsoft Dynamics 365 Supply Chain Management.

## <a name="inventory-close-adjustments-and-recalculation"></a>Lagerstängning, justeringar och omberäkning

### <a name="is-the-inventory-close-required"></a>Krävs lagerstängning?

Om du tänker använda funktionen för lagerarkivering, krävs lagerstängning. Om du inte tänker använda funktionen lagerarkivering rekommenderar vi starkt att du fortfarande kör lagerstängningen, oavsett vilka kostnadsmodeller som du använder.

### <a name="how-often-should-the-inventory-close-be-run"></a>Hur ofta ska lagerstängning köras?

Lagerstängning ska köras minst en gång per redovisningsperiod. Om till exempel din redovisning är inställd på en kalendermånadsbaserad räkenskapskalender, bör du köra lagerstängning en gång per månad.

### <a name="is-the-inventory-recalculation-required"></a>Krävs lageromberäkning?

Nej, lageromberäkning krävs inte. Om du använder en periodisk kostnadsmodell, till exempel först in, först ut (FIFO), sist in, först ut (LIFO) eller ett viktat medelvärde, bör du överväga om du vill köra lageromberäkningen. Det kan ge mer exakt kostnadsredovisning i de heuristiska modeller som du har valt.

### <a name="how-often-should-the-inventory-recalculation-be-run"></a>Hur ofta ska lageromberäkning köras?

Om du planerar att köra lageromberäkningen rekommenderar vi att du kör den dagligen som en batchprocess. Om din organisation inte kräver ofta rapportering av lagervärden för periodiska kostnadsmodeller, kan du överväga att köra lagerberäkningen mindre ofta.

### <a name="when-should-i-use-the-on-hand-inventory-adjustment-on-the-closing-and-adjustments-page"></a>När ska jag använda lagerbehållningsjustering på sidan Stängning och justeringar?

Justeringen av lagerjustering kan endast köras efter att en lagerstängning har slutförts. Den körs vanligtvis för datumet efter den senaste stängningen. Justerad behållning kan endast justera lager som fortfarande finns i lager på det datum när du kör justeringen.

### <a name="when-should-i-use-the-inventory-transaction-adjustment-on-the-closing-and-adjustments-page"></a>När ska jag använda justering av lagertransaktioner på sidan Stängning och justeringar?

Du bör använda justering av lagertransaktioner innan du kör en lagerstängning. Den används vanligtvis för att korrigera ett felaktigt kvitto. Du kan inte bokföra justering av lagertransaktioner efter att en lagerstängning har körts och transaktionen kvittats.

### <a name="are-purchase-order-returns-treated-like-other-issues-during-the-inventory-close"></a>Behandlas inköpsorderreturer som andra problem under lagerstängingen?

Ja. En inleverans av en inköpsorder är en utleverans som kvittas mot en inleverans i den heuristiska modell som du väljer för artikeln. Om du använder en periodisk kostnadsmodell kan du använda markering för att åsidosätta den heuristiska kostnaden.

### <a name="what-happens-to-sales-order-returns-during-the-inventory-close"></a>Vad händer med returer av försäljningsorder under lagerstängning?

När du kör lagerstängeringen behandlas en försäljningsorderretur som en inleverans till lagret. Problem kvittas mot lagret, baserat på den heuristiska modell som du väljer för artikeln.

### <a name="what-cost-price-is-used-on-a-sales-order-return"></a>Vilket självkostnadspris används på en försäljningsorderretur?

När du skapar en retur som är relaterad till en försäljningsorder kopieras värdet i fältet **Enhetspris** från den ursprungliga försäljningsordern och fältet **Retursjälvkostnad** ställs in på den justerade självkostnaden från den ursprungliga lagertransaktionen för försäljningsorderraden som returneras. Om alternativet **Värde öppet** för den relaterade lagertransaktionen ställs in på *Ja*, kan lagerstängeringen orsaka uppdateringar av utleveranskostnaden på den ursprungliga försäljningsordern. Fältet **Självkostnadspris** för retur uppdateras inte i det här scenariot. När du bokför en returorders följesedel kontrollerar systemet självkostnaden och använder den uppdaterade kostnaden på returlagertransaktionen.

För en retur av en standardkostnadsartikel som hör till en försäljningsorder används standardkostnaden från tidpunkten för den ursprungliga försäljningsordern, även om en ny standardkostnad är aktiv för artikeln.

När du skapar en retur som inte är relaterad till en försäljningsorder, ställs fältet **Självkostnadspris** för retur in på det aktiva artikelpris som du har för artikeln på den webbplats som du skapar returordern för. Om du inte har en aktiv självkostnad i en kostnadsversion för artikeln blir värdet 0 (noll). Om du lämnar värdet som 0 (noll) får du en varning om att returens parti-ID eller returs självkostnadspris inte har angetts.

### <a name="what-is-the-expected-performance-of-the-inventory-close"></a>Vad är den förväntade prestandan för lagerstängningen?

Många faktorer kan påverka prestandan vid en lagerstängning. Dessa faktorer inkluderar det totala antalet artiklar, det totala antalet transaktioner för perioden, de lagermodeller som du använder och antalet batchhjälpare som du konfigurerar i parametrarna för hantering av lager och lagerställen. Du kan förvänta dig att stängningen kan ta så lite som ett par minuter eller så mycket som flera timmar. Det finns ingen specifik information om hur lång tid stängningen bör ta att köra. Du bör definiera dina icke-funktionella affärsbehov för prestandan hos lagerstängningen och arbeta nära din partner för att definiera schemat för lagerstängning. Om du upplever en oväntat låg prestanda för lagerstängningsprocessen bör du öppna en supportbegäran.

## <a name="costing-sheet-and-indirect-costs"></a>Kostnadsredovisning och indirekta kostnader

### <a name="which-costing-models-support-the-costing-sheet"></a>Vilka kostnadsmodeller stöder kostnadsredovisningen?

Även om kostnadsredovisningen oftast används i organisationer som använder standardkostnadsredovisning, kan du använda den med alla kostnadsmodeller som finns i Supply Chain Management.

### <a name="can-i-have-multiple-costing-sheets-for-various-parts-of-my-organization"></a>Kan jag ha flera kostnadsredovisningar för olika delar av organisationen?

Nej Du kan bara ha en kostnadsredovisning per juridisk person.

### <a name="can-i-have-different-costing-sheets-for-each-site"></a>Kan jag ha olika kostnadsredovisningar för varje webbplats?

Nej, jag kan inte ha olika kostnadsredovisningar för varje webbplats. Du kan bara skapa en kostnadsredovisning för varje juridisk person. Du kan dock konfigurera totala noder, kostnadsgrupper eller indirekta kostnadsnoder per webbplats. Denna konfiguration är en manuell process och du måste underhålla hierarkin och artikeltilldelningarna i kostnadsredovisningen när förändringar av organisationen eller verksamheten sker. Om en enskild artikel tillverkas eller köps in på mer än en webbplats finns det ingen mekanism som gör att du kan behandla artikeln på olika sätt i kostnadsredovisningen för varje webbplats. Observera också att alla indirekta kostnadskoder har en sats eller ett tillägg som definieras i din kostnadsversion. Kostnaderna som du definierar är alltid webbplatsspecifika.

### <a name="can-i-deactivate-and-activate-versions-of-the-costing-sheet"></a>Kan jag inaktivera och aktivera versioner av kostnadsredovisningen?

Även om ingen detaljerad versionshistorik används för kostnadsredovisningen, kan du ändra kostnadsredovisningen och sedan, när du är klar, spara och validera den. Det finns ingen mekanism som gör att du kan gå tillbaka till en tidigare version av kostnadsredovisningen eller visa de ändringar som har gjorts i kostnadsredovisningen. Om du startar ändringar och inte vill att de ska gälla kan du stänga sidan utan att spara och validera ändringarna. Du uppmanas att kasta ändringarna.

### <a name="can-i-create-indirect-costs-for-each-item"></a>Kan jag skapa indirekta kostnader för varje artikel?

I kostnadsredovisningen kan du skapa indirekta kostnadskoder där fältet **Nodtyp** är inställt på *Tillägg*, *Avgift* eller *Utdataenhetsbaserad*. Du kan sedan definiera satsen eller tillägget så att den är specifik för ett artikelnummer. På snabbfliken **Avgift** eller **Tilläggsavgift**, lägg till en rad i rutnätet. Ställ in fältet **Giltigt för** till *Register* och **Relation** till det specifika artikelnumret.

### <a name="can-i-create-an-indirect-cost-that-isnt-related-to-a-specific-item"></a>Kan jag skapa en indirekt kostnad som inte är relaterad till en specifik artikel?

Ja. Du kan skapa en indirekt kostnadskod där fältet **Nodtyp** är inställt på *Utdataenhetsbaserad*. Du kan sedan konfigurera fältet **Undertyp** till *Kvantitet*, *Vikt* eller *Volym* om du vill ange kvantitet, vikt eller volym för artikeln som du producerar. Den kurs som du anger på snabbfliken **Avgift** används för den undertyp som du har valt. Du kan till exempel konfigurera fälten **Undertyp** till *Kvantitet* och **Avgift** till *1,00 USD* och sedan skapa en tillverknings- eller batchorder för kvantiteten 10. I detta fall läggs den indirekta kostnaden som ska läggas till den färdiga varan 10,00 USD.

### <a name="can-i-use-the-costing-sheet-to-split-my-production-costs-by-hours-and-materials"></a>Kan jag använda kostnadsredovisningen för att dela upp mina produktionskostnader efter timmar och material?

Ja. Du kan skapa noder för **summa** i kostnadsredovisningen för att skilja kostnaderna åt efter valfri gruppering som du väljer. Du kan till exempel skapa noden **Summa** som kallas *Timmar* och en annan som kallas *Material*. Under noden **Timmar** lägger du till varje kodgrupp som hör till dina timmar. Under noden **Material** lägger du till varje kostnadsgrupp som hör till dina material.

## <a name="dimension-groups"></a>Dimensionsgrupper

### <a name="can-i-manage-cost-at-the-batch-or-serial-number-level"></a>Kan jag hantera kostnader på batch- eller serienummernivå?

Ja, om du använder en periodisk kostnadsmodell som FIFO, LIFO, LIFO-datum, viktat medelvärde eller datum för viktat medelvärde, kan du aktivera alternativet **Ekonomiskt lager** för dimensionen **batch** eller **serienummer** i spårningsdimensionsgruppen om du vill spåra kostnader på detaljerad nivå.

### <a name="can-i-manage-costs-at-the-location-level"></a>Kan jag hantera kostnader på platsnivå?

Nej, du kan inte aktivera alternativet **Ekonomiskt lager** för dimensionen **Plats** i lagringsdimensionsgruppen. Om din organisation måste spåra kostnader på en mer detaljerad nivå bör du överväga om du kan skapa virtuella lagerställen och sedan välja alternativet **Ekonomiskt lager** för dimensionen **lagerställe** i lagringsdimensionsgruppen.

### <a name="should-i-enable-the-use-warehouse-management-processes-option-for-the-storage-dimension-group"></a>Ska jag aktivera alternativet Använd lagerhanteringsprocesser för lagringsdimensionsgruppen?

Om du tror att du kanske vill använda de avancerade lagerstyrningsfunktionerna i framtiden, bör du aktivera alternativet **Använd lagerstyrningsprocesser**. När du har sparat en lagringsdimensionsgrupp kan du inte längre ändra inställningen för alternativet **Använd lagerstyrningsprocesser** för den. Om du bestämmer dig för att använda lagerstyrningsprocesser senare måste du skapa ett nytt lagerställe där alternativet aktiveras. Det finns ingen automatiserad process som du kan använda för att flytta allt lager från ett lagerställe till ett annat, eller för att kopiera relaterade konfigurationer till ett nytt lagerställe.

### <a name="can-i-enable-the-use-warehouse-management-processes-for-the-storage-dimension-group-even-if-im-not-planning-to-use-advanced-warehousing"></a>Kan jag aktivera Använd lagerstyrningsprocesser för lagringsdimensionsgruppen även om jag inte planerar att använda avancerad lagring?

Ja, även om du inte planerar att använda de avancerade lagerstyrningsfunktionerna, kan du aktivera alternativet **Använd lagerstyrningsprocesser** för lagringsdimensionsgruppen. Om du vill skapa och bearbeta transaktioner måste du slutföra den minsta konfigurationen, till exempel reservationshierarkier och enhetssekvensgrupper. Inställningarna för avancerad lagring ignoreras dock i allmänhet när du manuellt bearbetar plocklistor, följesedlar och produktinleveranser (till exempel på försäljningsorder- och inköpsordersidor).

### <a name="when-should-i-enable-the-physical-inventory-option-for-a-storage-or-tracking-dimension-group"></a>När ska jag aktivera alternativet Fysiskt lager för en lagrings- eller spårningsdimensionsgrupp?

Du bör aktivera alternativet **Fysiskt lager** för lagring och spårning av dimensionsgrupper när du måste föra detaljerade lagerposter baserade på den dimensionen. Vanligtvis spåras alla dimensioner som är aktiva även fysiskt. Därför spåras eventuell inleverans, utleverans eller förflyttning av lagret av den valda dimensionen. Om en dimension inte är obligatorisk (t.ex. licens så är det obligatoriskt) kan du aktivera alternativet **Tom inleverans tillåten** och **Tom utleverans tillåten** för att ge användare möjlighet att ta emot, utleverans eller flytta lager även om dimensionen inte har angetts.

### <a name="when-should-i-enable-the-financial-inventory-option-for-a-storage-or-tracking-dimension-group"></a>När ska jag aktivera alternativet Ekonomiskt lager för en lagrings- eller spårningsdimensionsgrupp?

Du bör aktivera alternativet **Ekonomiskt lager** för lagring och spårning av dimensionsgrupper när du måste föra detaljerade ekonomiska poster baserade på den dimensionen. Dimensionerna **Webbplats** spåras alltid ekonomiskt, medan andra dimensioner är valfria för ekonomisk spårning. Om du använder en periodisk kostnadsmodell som FIFO, LIFO eller viktat medelvärde kommer aktivering av **Ekonomiskt lager** för en dimension indikerar att du kommer att göra avräkningar endast i de fall där kvittot och emissionen har samma dimensionsvärden. Om du till exempel aktiverar alternativet **Ekonomiskt lager** för dimensionen **Lagerställe**, har du olika kostnader i varje lagerställe och in- och utleveranser från olika lagerställen kan inte kvittas.

### <a name="can-i-make-changes-to-a-product-storage-or-tracking-dimension-group-after-transactions-exist"></a>Kan jag göra ändringar i en produkt, lagring eller spårning av dimensionsgrupp efter det att det finns transaktioner?

När du har skapat en artikelmodellgrupp kan du ändra inställningen av fälten **Disponera per dimension**, **För inköpspriser** och **För försäljningspriser** om kryssrutan **Aktiv** markerats för en dimension i artikelmodellgruppen. Inga andra ändringar är tillåtna. Du kan till exempel inte aktivera eller inaktivera alternativen **Aktiv**, **Tom utleverans tillåten**, **Tom inleverans tillåten**, **Fysiskt lager** och **Ekonomiskt lager**.

### <a name="can-i-change-the-product-storage-or-tracking-dimension-group-for-a-released-product"></a>Kan jag ändra produkt, lagring eller spårning av dimensionsgrupp för en frisläppt produkt?

Om lagerbehållningen för en produkt är 0 (noll) och alternativet **Värde öppet** har värdet *Nej* för alla lagertransaktioner kan du ändra lagrings- och spårningsdimensionsgrupperna på sidan Frisläppt produktion. Du kan inte ändra produktgruppen när posten har skapats.

## <a name="item-model-groups"></a>Artikelmodellgrupper

### <a name="when-should-i-enable-the-stocked-product-option"></a>När ska jag aktivera alternativet Produkt i lager?

Du bör aktivera alternativet **Produkt i lager** för alla artiklar som spåras i lagret. När det här alternativet aktiveras, hålls detaljerade lagertransaktioner som spårar inleverans och utleverans av artikeln. Det här alternativet är normalt aktiverat för materiella artiklar som du har på lagerstället. Du bör också aktivera det här alternativet om du planerar att lägga till en icke-materiella artikel, till exempel en serviceartikel i dina strukturlistor eller formler. Om du inte aktiverar alternativet **Produkt i lager** spåras inga lagertransaktioner i lagerredovisningen och kostnaden för artiklarna utgiftsbeläggs vanligtvis i redovisningen. Det här alternativet används ofta för t.ex. butiksleveranser eller tjänster som inte ingår i dina strukturlistor eller formler.

### <a name="when-should-i-enable-the-post-physical-inventory-option"></a>När ska jag aktivera alternativet Bokför fysiskt lager?

Alternativet **Bokför fysiskt lager** aktiveras normalt när alternativet **Produkt i lager** är aktiverat. När du aktiverar detta alternativ spårar systemet den fysiska uppdateringen av artikeln i lagertransaktionen. Det här alternativet används för prestanda med parametrar i Leverantörsreskontra, Kundreskontra och Produktionskontroll som anger att den fysiska uppdateringen ska skapa en verifikation. Normalt aktiverar du detta alternativ när du vill att redovisningen ska uppdateras när du uppdaterar lagret fysiskt. Om Supply Chain Management inte är ditt registersystem för ekonomi, kanske du vill inaktivera det här alternativet.

### <a name="when-should-i-enable-the-post-financial-inventory-option"></a>När ska jag aktivera alternativet Bokför ekonomiskt lager?

Alternativet **Bokför ekonomiskt lager** aktiveras normalt när alternativet **Produkt i lager** är aktiverat. Det här alternativet används för prestanda med parametrar i Leverantörsreskontra, Kundreskontra och Produktionskontroll som anger att den ekonomiska uppdateringen ska skapa en verifikation. Normalt aktiverar du detta alternativ när du vill att redovisningen ska uppdateras när du uppdaterar lagret ekonomiskt (till exempel genom att fakturera försäljningsorder och inköpsorder eller avsluta en tillverkningsorder). Om Supply Chain Management inte är ditt registersystem för ekonomi, kanske du vill inaktivera det här alternativet.

### <a name="when-should-i-enable-the-post-to-deferred-revenue-account-on-sales-delivery-option"></a>När ska jag aktivera alternativet Bokför på konto för uppskjuten intäkt vid försäljningsleverans?

Du använder alternativet **Bokför på konto för uppskjuten intäkt vid försäljningsleverans** när du vill ange om du vill redovisa intäkten i redovisningen när du bokför en följesedel för en försäljningsorder. Det här alternativet används vanligtvis när du har en lång fördröjning mellan följesedeln och fakturan på en försäljningsorder, eller när det inte går att fakturera alla försäljningsorder under den perioden. Normalt inaktiverar du det här alternativet om du bokför försäljningsorderfakturor direkt efter att du bokför följesedeln. På detta sätt undviker du att generera extra redovisningsbokföringar som omedelbart kommer att återföras när du fakturerar en försäljningsorder.

### <a name="when-should-i-enable-the-accrue-liability-on-product-receipt-option"></a>När ska jag aktivera alternativet Periodisera skulder på produktinleverans?

I de flesta organisationer vill du aktivera alternativet **Periodisera skulder vid produktinleverans** för alla varumodellgrupper, oavsett om du har en lagerförd produkt eller en ej lagerförd produkt. Det här alternativet används när en periodisering ska bokföras i redovisningen baserat på produktens inleveranspris. Eftersom det vanligtvis finns en fördröjning mellan bokföringen av produktkvittot för en inköpsorder och bokföringen av fakturan, måste de flesta organisationer erkänna skulden på balansräkningen för att följa lokala bestämmelser såsom allmänt accepterad redovisningspraxis (GAAP). Om Supply Chain Management inte är ditt registersystem för ekonomi, kanske du vill inaktivera det här alternativet. Om din organisation använder anskaffningskategorier på inköpsorder kan du kontrollera periodiseringsbehovet genom att aktivera alternativet **Periodisera inköpskostnad vid inleverans** för kategoripolicyregeln på sidan **Inköpspolicy**.

### <a name="how-can-i-prevent-a-user-from-posting-a-purchase-order-product-receipt-if-a-receipt-registration-isnt-yet-posted"></a>Hur kan jag förhindra en användare från att bokföra en inleverans av en inköpsorderprodukt om en kvittoregistrering inte har bokförts än?

Du kan förhindra en användare från att bokföra en inleverans av en inköpsorderprodukt om en inköpsorderregistrering ännu inte har uppstått genom att aktivera alternativet **Registreringskrav** för artikelmodellgruppen. Det här alternativet används vanligtvis i organisationer där en mottagningsprocess med två steg används, eller i scenarier där du måste registrera ett batch- eller serienummer, till exempel för de artiklar som du tar emot. Alternativet **Registreringskrav** gäller för *alla* lagerinleveranser för en artikel, inte bara för inköpsorder. Det gäller till exempel för en lagerjournal som har en positiv kvantitet och en tillverkningsorderrapport som färdig journal.

### <a name="how-can-i-prevent-a-user-from-posting-a-purchase-order-invoice-if-a-product-receipt-isnt-yet-posted"></a>Hur kan jag förhindra en användare från att bokföra inköpsorderfaktura om ett produktkvitto ännu inte har bokförts?

Du kan förhindra en användare från att skicka en inköpsorderproduktfaktura om ett inköpsorderproduktkvittot ännu inte har inträffat genom att aktivera alternativet **Inleveransbehov** för artikelmodellgruppen. Det här alternativet används normalt i organisationer där inleveranser måste redovisas fysiskt i redovisningen för periodiseringar. Alternativet **Inleveransbehov** gäller för *alla* lagerinleveranser för en artikel, inte bara för inköpsorder. Det gäller till exempel för en lagerjournal som har en positiv kvantitet och en tillverkningsorderrapport som färdig journal. Om din organisation använder anskaffningskategorier på inköpsorder kan du kontrollera kravet av ett kvitto genom att aktivera alternativet **Inleveransbehov** för kategoripolicyregeln på sidan **Inköpspolicy**.

### <a name="how-can-i-prevent-a-user-from-posting-a-sales-order-packing-slip-if-a-sales-order-picking-list-isnt-yet-posted"></a>Hur kan jag förhindra en användare från att bokföra en följesedel för försäljningsorder om en plocklista för försäljningsorder inte har bokförts än?

Du kan förhindra en användare från att posta en följesedel eller faktura för försäljningsorder om en plocklista för försäljningsorder ännu inte har inträffat genom att aktivera alternativet **Plockkrav** för artikelmodellgruppen. Det här alternativet används normalt i organisationer som utför en fysisk plockningsprocess i lagerstället (till exempel genom att använda den mobila lagerställeenheten för plockning). Alternativet **Plockkrav** gäller för *alla* lagerutleveranserna för en artikel, inte bara för försäljningsorder. Det gäller till exempel för en lagerjournal som har en negativ kvantitet och en plocklistejournal för tillverkningsorder.

### <a name="how-can-i-prevent-a-user-from-posting-a-sales-order-invoice-if-the-sales-order-packing-slip-isnt-yet-posted"></a>Hur kan jag förhindra en användare från att bokföra en faktura för försäljningsorder om en följesedel för försäljningsorder inte har bokförts än?

Du kan förhindra en användare från att posta en försäljningsfaktura om en följesedel för försäljningsorder ännu inte har inträffat genom att aktivera alternativet **Avdragskrav** för artikelmodellgruppen. Det här alternativet används vanligtvis i organisationer som utför en fysisk förpackningsprocess i lagerstället (till exempel genom att använda mobilappen Warehouse Management för att packa eller genom att generera ett dokument som ska ingå med de artiklar som levereras). Alternativet **Avdragskrav** gäller för *alla* lagerutleveranserna för en artikel, inte bara för försäljningsorder. Det gäller till exempel för en lagerjournal som har en negativ kvantitet och en plocklistejournal för tillverkningsorder.

### <a name="can-i-prevent-items-that-are-registered-from-being-sold"></a>Kan jag förhindra att artiklar som registreras säljs?

När en artikel registreras i ditt lager i Supply Chain Management är kvantiteten fysiskt tillgänglig för utleveranser i systemet. Om artiklar som har registrerats men ännu inte mottagits *inte* ska kunna utfärdas till försäljningsorder eller tillverkningsorder, bör du överväga att använda lagerstatus, lagerspärr, kvalitetsorder, karantänorder eller reservationsfunktioner för att hantera affärsprocessen.

## <a name="production-costing"></a>Kostnadsredovisning för produktion

### <a name="can-i-use-one-costing-model-for-raw-materials-and-a-different-costing-model-for-finished-goods"></a>Kan jag använda en kostnadsmodell för råmaterial och en annan kostnadsmodell för färdiga varor?

Ja, du kan använda olika kostnadsmodeller för varje artikel. Det fungerar inte för tillverkare att använda en periodisk kostnadsmodell för råmaterial och standardkostnad för halvfabrikat och färdiga varor.

### <a name="how-can-i-drive-overhead-off-machine-costs"></a>Hur kan jag köra omkostnader för maskinkostnader?

Om du vill köra omkostnader för dina maskinkostnader måste du skapa resurser och resursgrupper för varje maskin, enligt dina affärsbehov. Varje resurs eller resursgrupp kan tilldelas kostnadskategorier för att kontrollera kostnaden för maskinen. Varje kostnadskategori kan länkas till en kostnadsgrupp och varje kostnadsgrupp kan användas som grund för beräkning av indirekta kostnader i kostnadsredovisningen.

### <a name="how-do-i-recognize-cost-that-is-related-to-energy-consumption-for-example-water-energy-or-gas-consumption-on-the-costing-sheet"></a>Hur kan jag känna igen kostnader som är relaterade till förbrukning av energi (till exempel vatten, energi eller konsumtion av vatten) i kostnadsredovisningen?

Du kan i allmänhet känna igen kostnader som är relaterade till förbrukning av energi på ett av två sätt:

- Skapa en rad i strukturlistan eller formeln. Normalt skapas den här raden som en serviceartikel och du kan ange måttenheten som du förbrukar i relation till den kvantitet du producerar. På det här sättet kan användaren förbruka en annan summa under produktionsprocessen. Du kan förbruka artiklarna automatiskt baserat på det värde som du väljer i fältet **Avräkningsprincip**.
- Skapa en indirekt kostnad i kostnadsredovisningen. Vanligtvis används det här sättet för att fördela den totala kostnaden för din förbrukning av energi över din produktionsprocess. Du kan använda kostnadsgruppen och absorptionsunderlaget för att anpassa förbrukningen baserat på material eller arbete i flödet, till exempel.

Du bör välja det bästa alternativet utifrån rapporterings-, avstämnings- och driftkraven.

### <a name="can-i-capture-resource-details-in-the-bom-or-formula"></a>Kan jag samla in resursinformation i strukturlistan eller formeln?

Resursinformation kan bara fångas in i en flödesåtgärd. Du kan skapa en serviceartikel som representerar en resurs och tilldela en kostnad för att öka kostnadsberäkningen för en färdig vara, men vi rekommenderar normalt inte det här sättet. I stället rekommenderar vi att du skapar ett enkelt flöde med en rad för att spåra resurskostnader och konfigurera åtgärden så att den förbrukas automatiskt i antingen början eller slutet av tillverkningsordern.

### <a name="can-i-view-the-calculation-details-if-the-cost-is-manually-entered"></a>Kan jag visa beräkningsdetaljer om kostnaden anges manuellt?

Nej Om du anger priset manuellt på sidan **Artikelpris** är knapparna **Visa beräkningsuppgifter** och **Rapportberäkningsuppgifter** inte tillgängliga. Om du väljer knappen **Kostnader samlade efter kostnadsgrupp** för en självkostnad som anges manuellt, visas en summerad rad och alla kostnader rullas upp till den färdiga artikeln.

### <a name="does-the-system-calculate-variances-on-a-production-order-when-i-manually-enter-the-cost"></a>Beräknar systemet avvikelser för en tillverkningsorder när jag registrerar kostnaden manuellt?

Ja, systemet beräknar avvikelser när du manuellt anger en standardkostnad. När du manuellt anger en standardkostnad istället för att beräkna den, betraktas dock all material, flöde och indirekt kostnadsförbrukning i tillverkningsordern som en ersättning. Om det finns ytterligare avvikelser, till exempel förbrukning av extra material eller arbete, registreras de också som avvikelser från produktionsstrukturlistan. Därför rekommenderar vi starkt att du alltid kör en beräkning för artiklar med en strukturlista, ett flöde eller indirekta kostnader.

### <a name="how-can-i-carry-the-variances-from-a-subproduction-order-to-the-parent-production-order"></a>Hur kan jag bära avvikelserna från en delproduktionsorder till den överordnade tillverkningsordern?

När du använder en periodisk kostnadsmodell som FIFO, LIFO eller viktat medelvärde, redovisas kostnaderna från en delproduktion i den heuristiska modell som du har valt för artiklarna. Om du kräver faktisk kostnadsredovisning bör du använda markeringsprincipen för att ange vilken delproduktion som ges till en överordnad tillverkningsorder. Du kan också överväga att använda alternativet **Ekonomiskt lager** för dimensionen **batch** eller **serienummer** i exempelvis spårningsdimensionsgruppen.

### <a name="how-does-the-flushing-principle-affect-consumption"></a>Hur påverkar avräkningsprincip förbrukningen?

Avräkningsprincipen i en strukturlista, formel eller flödesrad styr tiden och tekniken som används för att förbruka artikeln eller arbetet. Om du väljer *Start* förbrukas artikeln eller arbetet automatiskt när du startar tillverkningsordern. Om du väljer *Slutför* förbrukas artikeln eller arbetet automatiskt när du rapporterar tillverkningsordern som avslutad. Om du väljer *Manuell* måste användaren plocka material manuellt eller registrera tiden i en jobb- eller ruttkortsjournal. Strukturlistor och formler har också alternativet *Tillgänglig på plats*. Om du väljer det här alternativet förbrukas artiklarna automatiskt när de har överförts till produktionsgolvplatsen.

### <a name="how-should-i-run-cost-calculations-if-i-have-multi-level-boms-or-formulas"></a>Hur ska jag köra kostnadsberäkningar om jag har strukturlistor eller formler på flera nivåer?

I allmänhet rekommenderar vi att du börjar på den lägsta nivån i strukturlistor eller formler för beräkningen. För att göra filtreringen enklare när du gör masskörning av kostnadsberäkningar kan du använda beräkningsgrupper för att göra det lättare att skilja produkter. Vi rekommenderar även att du kör det periodiska jobbet *Räkna om strukturlistenivåer* innan du börjar masskörningskostnadsberäkningar. Varje organisation bör ta hänsyn till kombinationen av produkter och definiera en strategi som uppfyller specifika behov hos din produkt- och strukturlista eller formelstrukturer.

## <a name="transfer-order-costing"></a>Kostnad för överföringsorder

### <a name="is-there-a-way-to-allocate-freight-to-a-transfer-order-cost"></a>Finns det ett sätt att fördela frakt till en överföringsorderkostnad?

Du kan lägga till avgifter på en överföringsorder när du vill lägga till kostnader. Debiteringskoden definierar debitering och kredit för debiteringen som du lägger till. Du måste först skapa debiteringskoder i modulen **lagerhantering**. Om du vill lägga till en kostnad för en överföringsorder väljer du **Tillägg** på överföringsorderraden som du vill lägga till en kostnad för.

## <a name="variances"></a>Avvikelser

### <a name="can-i-treat-variances-differently-based-on-the-site-or-warehouse"></a>Kan jag behandla avvikelser på olika sätt, baserat på webbplats eller lagerstället?

Det finns inget alternativ för att konfigurera avvikelsekonton per webbplats. När du använder standardkostnadsredovisning för en frisläppt produkt, kan du välja det huvudkonto som används för bokföring av standardkostnadsavvikelser på sidan **bokföring**. Du kan välja att konfigurera kontona för en artikel, en grupp artiklar eller alla artiklar. Du kan även konfigurera en kostnadsgrupp, en grupp med kostnadsgrupper eller alla kostnadsgrupper.

### <a name="can-i-separate-variances-that-are-the-result-of-currency-exchange-rates-from-other-types-of-variances"></a>Kan jag skilja avvikelser som är resultatet av valutakurser från andra typer av avvikelser?

Om en avvikelse är resultatet av en valutakursdifferens mellan inköpsorderpriset och standardkostnaden för en artikel, går det inte att skilja växelkursdifferensen från andra avvikelser.

## <a name="reporting"></a>Rapportering

### <a name="how-many-inventory-value-report-configurations-can-i-create-and-use"></a>Hur många konfigurationer av lagervärde rapporter kan jag skapa och använda?

Det finns ingen gräns för antalet rapportkonfigurationer för lagervärde som du kan skapa. Du bör utvärdera dina specifika rapporteringskrav och skapa antalet konfigurationer som du behöver för att uppfylla dessa krav. Du behöver minst en konfiguration av en lagervärdesrapport för att kunna köra rapporten eller alternativet för rapportlagring.

### <a name="can-i-use-the-inventory-value-report-to-analyze-the-cost-of-an-item-in-each-warehouse"></a>Kan jag använda lagervärdesrapporten när jag analyserar kostnaden för en artikel på respektive lagerställe?

Ja. Du kan aktivera alternativet **Visa** eller **Summa** för varje dimension **lagerställe** i rapportkonfigurationen för lagervärde. Men rapporten visar värden endast för dimensioner där alternativet **Ekonomiskt lager** har aktiverats för lagringsdimensionsgruppen. För övriga dimensioner visar tomma kolumner. Mer information finns i [Exempel och logik rörande värderapport för lager](inventory-value-report-examples.md).

### <a name="how-can-i-view-the-inventory-quantity-as-of-a-specific-date-with-the-weighted-average"></a>Hur kan jag visa lagerkvantiteten från och med ett visst datum med det viktade medelvärdet?

Du kan använda rapporten **Lagerföråldring** som innehåller en kolumn för **Genomsnittlig enhetskostnad** som visar värdet på inventeringen vid ett specifikt datum. Mer information finns i [Exempel och logik på åldersfördelningsrapport för lager](inventory-aging-report.md).

### <a name="how-can-i-view-which-receipt-transactions-are-settled-against-an-issue-transaction"></a>Hur kan jag visa vilka inleveranstransaktioner som kvittas mot en utleveranstransaktion?

Du kan se avräkningarna för en lagertransaktion genom att välja **Kvittningar** eller **Cost explorer** på fliken **Lager** i åtgärdsfönstret för **Lagertransaktion** eller sidan **Lagertransaktion – information**. Om du väljer en inleverans för att visa utleveranserna som hör till transaktionen, visas inte information om Cost explorer. Detaljer visas bara om du väljer en utleveranstransaktion.

### <a name="how-does-the-inventory-value-report-show-items-that-have-a-positive-physical-quantity-and-a-negative-financial-value"></a>Hur visar lagervärdesrapporten artiklar som har en positiv fysisk kvantitet och ett negativt ekonomiskt värde?

I lagervärdesrapporten avgränsas de fysiska och ekonomiska beloppen och kvantiteterna i sina egna kolumner. Värdena som visas i rapporten är från det datumintervall som du valde när du körde rapporten. Vilken nivå av summering som visas beror på inställningarna som du väljer. Om en artikel har transaktioner som fysiskt har mottagits och utfärdats ekonomiskt, summeras kvantiteterna och värdena oberoende av varandra. Om du väljer att visa detaljnivån som transaktioner visas rader för varje inleverans och utleverans separat och de fysiska och ekonomiska kvantiteterna respektive beloppen visas. Mer information finns i [Exempel och logik rörande värderapport för lager](inventory-value-report-examples.md).

### <a name="what-is-the-impact-of-storage-and-tracking-dimension-groups-on-the-inventory-value-report"></a>Hur påverkar lagring och spårning av dimensionsgrupper i lagervärdesrapporten?

Om du aktiverar alternativet **Ekonomiskt värde** för en dimension i en lagrings- eller spårningsdimensionsgrupp, kan du välja alternativet **Visa** eller **Summa** för dimensionen i rapportkonfigurationen för lagervärde. Om du väljer alternativet **Visa** eller **Summa** för en dimension där alternativet **Ekonomiskt värde** inte är valt, kommer kolumnen att lämnas tom i rapportens utdata. Om du har aktiverat alternativet **Ekonomiskt värde** för en dimension i en lagrings- eller spårningsdimensionsgrupp och du inte väljer alternativet **Visa** eller **Summa** i konfigurationen av lagervärderapport, sammanfattas värdena för de valda dimensioner där de spåras ekonomiskt.

### <a name="can-i-customize-the-power-bi-embedded-reports-for-costing"></a>Kan jag anpassa Power BI embedded-rapporter för kostnadsredovisning?

Ja, användare som har rätt säkerhetsbehörigheter kan uppdatera rapportens designarbetsytan för Power BI embedded-rapporter i Supply Chain Management. För mer information, se [Anpassa inbäddade rapporter i analytiska arbetsytor](../../fin-ops-core/dev-itpro/analytics/customize-analytical-workspace.md).

### <a name="where-can-i-view-the-variance-analysis-statement"></a>Var kan jag visa utdraget för avvikelseanalysen?

Du kan nå utdraget för avvikelseanalysen genom att gå till **Kostnadshantering \> Förfrågningar och rapporter \> Lagerredovisning – analysrapporter** eller **Kostnadshantering \> Förfrågningar och rapporter \> Tillverkningsredovisning – analysrapporter**. Båda alternativen öppnar samma rapport och rapporten fungerar på samma sätt.

## <a name="item-prices-and-default-costs"></a>Artikelpriser och standardkostnader

### <a name="can-i-maintain-the-cost-for-each-product-variant"></a>Kan jag underhålla kostnaden för varje produktvariant?

Ja. Du kan aktivera alternativet **Använd självkostnad per variant** på snabbfliken **Hantera kostnad** på sidan **Frisläppt produkt** om du vill aktivera prissättning per produktvariant. (Det här alternativet är endast tillgängligt för produktmästare.) Sedan, på sidan **Artikelpris** (som du kan öppna från antingen **Kostnadsversion** eller sidan **Frisläppt produkt**) kan du välja **Dimensionsvisning** för att ange om du vill visa dimension **Konfiguration**, **Storlek**, **Färg** eller **Format**. Om du vill spara inställningarna och använda de valda dimensionerna varje gång du öppnar sidan, aktiverar du alternativet **Spara inställningar** och väljer sedan **OK**. Du kan bara ange dimensionerna för artiklar där dimensionerna är aktiva i produktgruppen.

### <a name="can-i-maintain-the-cost-for-each-warehouse"></a>Kan jag underhålla kostnaden för varje lagerställe?

Nej, du kan inte underhålla artikelpriset per lagerställe. Du kan emellertid underhålla handelsavtal för inköpspriser eller försäljningspriser per lagerställe. Först väljer du alternativet **För inköpspriser** eller **För försäljningspriser** för dimensionen på sidan **Lagringsdimensionsgrupp**. När du sedan skapar handelsavtalsjournalen och öppnar raderna för dimensionerna väljer du **Lager \> Visa dimensioner** för att välja vilken dimension som ska visas i rutnätet. Om du vill spara inställningarna och använda de valda dimensionerna varje gång du öppnar sidan, aktiverar du alternativet **Spara inställningar** och väljer sedan **OK**. Du kan bara ange dimensionerna för artiklar där dimensionerna är aktiva i produktgruppen.

### <a name="what-are-price-charges"></a>Vilka är prisavgifter?

Prisavgifter utgör ett sätt att lägga ett fast belopp till enhetspriset för artikelpriset eller handelsavtalet. När du anger ett belopp i fältet **Prisavgifter**, kan du också ange ett värde i fältet **Avgiftskvantitet**. Prisavgifterna skrivs av över den avgiftskvantitet som du anger. Aktivera alternativet **Inkl. i pris per enhet** om du vill inkludera priskostnaderna i enhetspriset för artikeln. Det här alternativet är alltid aktiverat för en standardkostnad.

### <a name="how-should-i-configure-prices-for-items-that-are-procured-in-multiple-currencies"></a>Hur ska jag konfigurera priser för artiklar som anskaffas i flera valutor?

Om du anger ett standardpris i **Inköpspris** på sidan **Frisläppt produkt** antas det vara i redovisningsvalutan i redovisningen för den juridiska person som du är i. Likaså om du anger ett inköpspris i en kalkylversion där fältet **Pristyp** anges till *Inköp*, priset antas vara i redovisningsvalutan för din juridiska person. När du skapar en inköpsorder för en leverantör som har en annan valuta, kommer systemet automatiskt att konvertera valutan från redovisningsvalutan till transaktionsvalutan genom att använda den växelkurs som du anger i fältet **Redovisningsvalutans valutakurstyp** i redovisningen.

När du skapar en handelsavtalsjournal kan du ange valutan som du uttrycka priset i på varje rad. Du kan skapa handelsavtal för flera valutor, vissa leverantörer och många andra kombinationer av faktorer. Om du skapar en inköpsorder där handelsavtal finns för valutan du har valt, används det handelsavtal som har matchande valuta i systemet. När du bokför transaktioner som produktinleveranser eller fakturor konverteras beloppet till redovisningens redovisningsvaluta genom att använda den växelkurs för redovisningsvaluta som du anger i redovisningen.

### <a name="how-should-i-configure-costs-for-items-that-are-procured-in-multiple-currencies"></a>Hur ska jag konfigurera kostnader för artiklar som anskaffas i flera valutor?

Kostnader kan inte konfigureras i mer än en valuta. Kostnaden som du anger för artikelpriset eller standardkostnader som du anger i fältet **Pris** på snabbfliken **Hantera kostnad** för sidan **Frisläppt produkt** uttrycks alltid i redovisningsvalutan för redovisningen för den juridiska person som du har valt.

Om din organisation använder standardkostnadsredovisning bör du definiera en strategi för att definiera kostnader när det finns flera valutor. Du bör också definiera en process för att uppdatera kostnaden regelbundet för att minska antalet avvikelser som bokförs.

### <a name="can-i-use-the-profit-setting-on-the-cost-group-page-to-calculate-sales-prices"></a>Kan jag använda inställningen Vinst på sidan Kostnadsgrupp för att beräkna försäljningspriser?

Ja, du kan använda inställningen **Vinst** på sidan **Kostnadsgrupp** för att lägga till en procentsats när försäljningspriserna beräknas genom att använda en kostnadskalkyl. Mer information finns i [Strukturlisteberäkningar](bom-calculations.md).

## <a name="marking"></a>Markering

### <a name="how-does-marking-affect-periodic-costing-models"></a>Hur påverkar markering periodiska kostnadsmodeller?

Om du använder en periodisk kostnadsmodell som FIFO, LIFO eller viktat medelvärde, och du har markerat en inleveranstransaktion mot en utleveranstransaktion, ignoreras artikelns heuristiska modell under lagerstängningsprocessen. I stället används den faktiska inleveranskostnaden för utleveranskostnaden i systemet.

### <a name="what-happens-during-the-inventory-close-when-i-use-marking"></a>Vad händer under lagerstängning när jag använder markering?

När du markerar in- och utleveranser kvittar lagerstängningen de transaktioner som markeras tillsammans. När markering används för att skapa kvittningen sätts fältet **Princip** på sidan **Kvittning** till *Markering*. Om en transaktion markeras innan den uppdateras fysiskt eller ekonomiskt, använder den markerade inleveransens kostnad i stället för den löpande genomsnittliga kostnaden. Om transaktionerna är markerade efter den ekonomiska uppdateringen kommer lagerstängningen och justeringsprocessen att justera emissionskostnaden så att den matchar kvittokostnaden.

### <a name="can-i-manually-mark-transactions-when-i-use-standard-costing-or-moving-average"></a>Kan jag markera transaktioner manuellt när jag använder standardkostnad eller glidande medelvärde?

Nej, du kan inte manuellt markera in- och utleveranser när du använder standardkostnadsredovisning eller glidande medelvärde. Om transaktioner (till exempel direktleverans eller koncerninterna order) markeras automatiskt finns markeringsposten kvar och fungerar som en hård reservation. När du använder standardkostnads- eller rörligt medelvärde, påverkar markeringen av poster emellertid inte kostnaden för artiklarna.

### <a name="how-does-marking-affect-the-profit-and-loss-statement"></a>Hur påverkar markering resultaträkningen?

När du markerar en utleveranstransaktion mot en inleverans matchar utleveranskostnaden den valda inleveransen. När du fysiskt och ekonomiskt lägger upp frågan kommer inlägget att påverka konton **Kostnad för sålda varor, levererade** och **Kostnad för sålda varor, fakturerad** som du anger i lagerbokföringsprofilen. Om en transaktion markeras efter den fysiska eller finansiella uppdateringen, kommer processen *Lagerstängning och justering* kommer att skapa en justering som har en matchande verifikation som justerar **Kostnad för sålda varor, fakturerad** och motbokningar till kontot som du anger för **Kostnad för enheter, fakturerad** (lager).

### <a name="how-does-marking-affect-master-planning"></a>Hur påverkar markering huvudplaneringen?

Fliken **Standarduppdatering** på sidan **Huvudplaneringsparametrar** innehåller ett fält med namnet **Uppdatera markering**. Det alternativ du väljer används när du bekräftar en planerad order som genereras av huvudplaneringen. Följande alternativ är tillgängliga:

- *Nej* – Systemet utför ingen markering.
- *Standard* – Systemet markerar inleveranser mot utleveranser enligt pegging. Posterna i en behovsorder markeras i jämförelse med en uppfyllelseorder. Om någon kvantitet återstår i uppfyllelseordern markeras inte uppfyllelsen.
- *Utökad* – Systemet markerar både kravorder och uppfyllnadsorder, oavsett om någon kvantitet förblir öppen på uppfyllandeordern.

## <a name="negative-inventory"></a><a name="negative-inventory"></a>Negativt lager

### <a name="when-should-i-allow-physical-negative-inventory"></a>När ska jag tillåta fysiskt negativt lager?

I allmänhet rekommenderar vi inte att du tillåter fysiskt negativt lager, eftersom det inte går att ha mindre än 0 (noll) för en materiella artikel i lagerstället. Affärsprocesserna i vissa branscher och affärsscenarier kan dock begränsa åtgärder som kräver att lagret tillåts gå fysiskt negativt. En butik kanske inte vill förhindra försäljning av en artikel som tas med i kassan, även om systemet visar att det inte finns några artiklar tillgängliga. Processtillverkare är ett annat exempel. För dessa tillverkare kan beloppet som förbrukas överstiga det som rekommenderas i formeln. Alternativt kan förbrukningen uppskattas istället för exakt så att förbrukningen överstiger beloppet på en viss plats, till exempel en förbrukning.

När det är möjligt bör du utvärdera affärsprocessen och försöka förbättra den för att se till att lagret inte kan vara negativt. Om du måste tillåta negativt lager bör du ha en tydlig affärsprocess för att korrigera det negativa lagret, eftersom det kan påverka kostnadsredovisningen negativt.

### <a name="when-should-i-allow-financial-negative-inventory"></a>När ska jag tillåta ekonomiskt negativt lager?

Vi rekommenderar att de flesta organisationer tillåter ekonomiskt negativt lager. (I de flesta fall bearbetas inte inköpsorderfakturor innan du kan leverera artiklarna.) Du bör aktivera det här alternativet om du har särskilda affärsprocesser som kräver att försäljningspriset återspeglar den slutliga kostnaden för en inköpsorder. Detta krav kan till exempel gälla för en tillverkningsorderbransch eller i specifika regioner där lagen anger det.

### <a name="what-happens-to-the-cost-of-my-issues-when-the-inventory-is-negative"></a>Vad händer med kostnaden för mina utsproblem när lagret är negativt?

När lagret för din artikel är negativt och du utfärdar fler artiklar än vad du har fysiskt, använder systemet standardartikelpriset för att beräkna löpande medelvärde om du använder en periodisk kostnadsmodell som FIFO, LIFO eller viktat medelvärde. Om inget standardpris anges för artikeln utjämnas lagret med värdet 0 (noll). Detta kan medföra att framtida beräkningar av det löpande medelvärdet eller det rörliga medelvärdet blir felaktiga.

### <a name="can-i-prevent-items-from-being-picked-packed-or-sold-on-sales-orders-and-production-orders-if-there-isnt-enough-on-hand-inventory"></a>Kan jag förhindra att artiklar plockas, packas eller säljs på försäljningsorder och tillverkningsorder om det inte finns tillräckligt med lagerbehållning?

Ja. Vi rekommenderar att du inaktiverar alternativet **Fysiskt negativt** för artikelmodellgruppen för att förhindra att artiklar plockas, packas eller säljs på försäljningsorder och tillverkningsorder.

### <a name="can-i-prevent-items-from-being-invoiced-on-a-sales-order-if-no-purchase-orders-have-been-invoiced-for-the-same-item"></a>Kan jag förhindra att artiklar faktureras på en försäljningsorder om inga inköpsorder har fakturerats för samma artikel?

Ja. Vi rekommenderar att du inaktiverar alternativet **ekonomiskt negativ** för artikelmodellgruppen för att förhindra att artiklar faktureras på en försäljningsorder om inga inköpsorder har fakturerats för samma artikel.

### <a name="how-does-negative-inventory-affect-financial-ratios-such-as-gross-profit-margin"></a>Hur påverkar negativt lager ekonomiska förhållanden såsom bruttovinstmarginal?

När du tillåter att lagret blir negativt kan lagervärdet i balansräkningen och kostnaderna för sålda varor i resultaträkningen få för låg värde, särskilt om inget standardpris har konfigurerats för artiklarna. Därför kan finansiell rapportering och nyckeltal som bruttovinstmarginaler överskattas, eftersom kostnaden är felaktig. Om du använder en periodisk kostnadsmodell som FIFO, LIFO eller viktat medelvärde, kan värdet på ut frågorna justeras när du kör lagerstängning och justeringsprocess efter att de negativa lagerkvantiteterna har korrigerats. Om du använder rörligt medelvärde kan du emellertid inte omvärdera de enskilda transaktionerna.

### <a name="how-should-i-correct-negative-inventory"></a>Hur korrigerar jag negativt lager?

Vi rekommenderar att du ofta övervakar och korrigerar negativt lager när din organisation eller dina affärsbehov anger att du tillåter att lagret går negativt. Du kan korrigera lagervärdena genom att utföra en cykelräkning, bokföra en justering eller bokföra en flyttningsjournal. Om du måste känna igen de oväntade vinsterna i lagret på ett visst redovisningskonto, bör du planera att använda en flyttningsjournal. Annars, när du använder cykelräkningen eller lagerjusteringsprocessen, kommer systemet att bokföra lagerjusteringen till kontot **Lagerinleverans** och motbokning för konton **Lageromkostnad, vinst** som du anger i lagerbokföringsprofilen.

### <a name="do-i-have-to-create-a-new-item-if-my-inventory-has-gone-negative-and-i-use-moving-average"></a>Måste jag skapa en ny artikel om lagret har blivit negativt och jag använder ett glidande medelvärde?

Nej Om din organisation tillåter att lagret blir fysiskt negativt och du använder glidande medelvärde som din lagermodell, kommer systemet att använda reservkostnadssekvensen som tilldelas på sidan **Parametrar för hantering av lager och lagerstyrning** för att avgöra hur kostnaden kommer att tilldelas dina problem. I allmänhet rekommenderar vi att du inte tillåter att lagret går fysiskt negativt. För mer information, se övriga frågor i [Negativt lager](#negative-inventory) i denna artikel.

## <a name="not-stocked-products"></a>Produkter som inte finns i lager

### <a name="can-i-post-sales-order-picking-lists-for-not-stocked-products"></a>Kan jag bokföra plocklistor för försäljningsorder för produkter som inte finns i lager?

När du genererar en plocklista för en försäljningsorder som innehåller artiklar som finns i en artikelmodellgrupp som inte finns i lager, visas inga rader för de artiklar som inte finns i lager. Du kan inte använda mobilappen för Warehouse Management för att bearbeta artiklar som inte finns i lager.

När du genererar en följesedel för en försäljningsorder som innehåller artiklar som finns i en artikelmodellgrupp som inte finns i lager, ställ in fältet **Kvantitet** till *Plockad kvantitet och produkter som inte finns i lager* för att inkludera de ej lagerförda artiklarna i dokumentgenereringen. Om du väljer *Alla* kommer endast artiklar i lager att tas med i följesedeln.

### <a name="should-i-use-a-not-stocked-product-or-a-category-sales-category-or-procurement-category"></a>Ska jag använda en produkt som inte finns i lager eller en kategori (försäljningskategori eller anskaffningskategori)?

Valet mellan en produkt som inte finns i lager och en kategori beror på företagets specifika krav. Produkter som inte finns i lager ger i allmänhet mer kontroll över standardvärden, som kvantiteter och priser på inköpsorder och försäljningsorder. Därför är produkter som inte finns i lager att föredra i scenarier där samma produkt eller tjänst köps in eller säljs mer än en gång. Kategorier är användbara i scenarier där pris, artiklar, beskrivningar och så vidare inte är inkonsekvent från transaktion till transaktion. Kategorier kan också användas på alla produkter för att klassificera typen av produkt som säljs eller köps.

## <a name="service-items"></a>Serviceartiklar

### <a name="what-is-the-difference-between-a-service-item-and-a-not-stocked-product"></a>Vad är skillnaden mellan en serviceartikel och en produkt som inte finns i lager?

En serviceartikel är en produkttyp. När du skapar en nyligen frisläppt produkt kan du konfigurera fältet **Produkttyp** på antingen *Artikel* eller *Tjänst*. *Artikeln* väljs vanligtvis för att visa att artikeln är materiella, medan *Service* normalt väljs för att visa att artikeln är immateriell.

En frisläppt produkt, oavsett om den är en artikel eller tjänsteprodukt, kan lagras eller inte. Inställningen för lagrad eller ej lagrad styrs av artikelmodellgruppen som du väljer för den frisläppta produkten. När du väljer en artikelgrupp som inte finns i lager, skapas inga lagertransaktioner för den relaterade försäljnings- eller inköpsordern.

### <a name="can-i-include-not-stocked-items-in-a-bom"></a>Kan jag ta med artiklar som inte finns i lager i en strukturlista?

Nej, du kan inte inkludera en frisläppt produkt som är länkad till en artikelmodellgrupp där alternativet **I lager** är inaktiverat i en strukturlista eller en formel. Det spelar ingen roll om fältet **Produkttyp** ställs in på *Artikel* eller *Tjänst*. Endast artiklar i lager kan tas med på strukturliste- eller formelrader.

## <a name="costing-modelspecific-questions"></a>Kostnadsmodellspecifika frågor

### <a name="which-costing-model-should-i-use"></a>Vilken kostnadsmodell ska jag använda?

Vilka kostnadsmodeller du bör välja beror på verksamhetens krav. Innan du väljer en kostnadsmodell som ska användas i Supply Chain Management bör du validera att modellen tillåts enligt dina lokala regler. Vi rekommenderar att du validerar ditt val hos en certifierad revisor i din region.

### <a name="can-i-use-more-than-one-costing-model-in-my-organization"></a>Kan jag använda mer än en kostnadsmodell i organisationen?

Ja. Det finns ingen gräns för antalet artikelmodellgrupper eller kostnadsmodeller som du kan välja i Supply Chain Management.

### <a name="can-i-use-more-than-one-costing-model-for-each-item"></a>Kan jag använda mer än en kostnadsmodell för varje artikel?

Nej Du kan bara välja en kostnadsmodell för varje frisläppt produkt. Detta beteende styrs av artikelmodellgruppen. Om du måste använda mer än en kostnadsmodell för att rapportera lagervärden bör du överväga att använda tillägget Global lagerredovisning.

### <a name="when-i-use-manufacturing-execution-which-costing-methodology-should-i-use"></a>När jag använder tillverkningskörning, vilken kostnadsredovisningsmetodik ska jag använda?

Vilka kostnadsmodeller du bör välja beror på verksamhetens krav. Det finns inte någon särskild fördel eller situation där du använder kostnadsmodeller när din organisation även använder tillverkningskörning.

### <a name="when-is-fefo-used"></a>När används FEFO?

Först ut, först ut (FEFO) som inte är en kostnadsredovisningsmetodik. I stället är det en reservationsmetod som ofta används i tillverkningsorganisationer. Du kan aktivera FEFO-reservationer för en artikelmodellgrupp genom att aktivera det **FEFO-datumkontrollerade** alternativet och sedan välja ett värde i fältet **Plockningskriterier**.

### <a name="are-there-performance-benefits-to-selecting-one-costing-model-over-another"></a>Finns det prestandaförmåner att välja en kostnadsmodell över en annan?

I allmänhet har den kostnadsmodell du väljer för en artikel minimal inverkan på systemets generella prestanda. Den tid som krävs för att köra lagerstängningen eller omberäkningsprocessen kan dock påverkas av lagerkostnadsmodellen du väljer. Om du till exempel använder standardkostnad eller rörligt medelvärde påverkas lagerstängningsprocessen mycket mycket av systemet eftersom den inte uppdaterar varje lagertransaktion och skapar kvittningar. En periodisk kostnadsmodell som FIFO, LIFO eller viktat medelvärde kan emellertid öka den tid som krävs för att slutföra lagerstängningsprocessen. Stängningsprocessen kan särskilt vara längre när du anger ett högt antal i fältet **Maximalt antal upprepningar som tillåts per artikel** eller i ett lågt nummer i fältet **Minimibelopp är tillåtet** för processen *Stäng lager*.

### <a name="when-should-i-use-the-fixed-receipt-price-option"></a>När ska jag använda alternativet Fast inleveranspris?

När du markerar kryssrutan **Fast inleveranspris** på sidan **Artikelmodellgrupp** för en artikel, använder systemet inleveranspris som standardkostnad för lagerinleveransen. Om det finns en skillnad mellan inköpspriset och standardvarans självkostnadspris som är konfigurerat för en produkt, kommer skillnaden att bokföras till kontot **Fast inleveransprisdifferens** eller **Fast inleveransprisdifferens** och motbokas till kontot **Motkonto för fast inleveranspris**. (Alla dessa konton anges på sidan **Bokföring**.)

Du bör markera kryssrutan **Fast inleveranspris** när du använder en periodisk kostnadsmodell som FIFO, LIFO eller viktat medelvärde, och du vill att en inköpsprisavvikelse ska spåras i redovisningen om priset för en inleverans skiljer sig från standardartikelkostnaden.

### <a name="moving-average"></a>Glidande medelvärde

### <a name="is-moving-average-the-same-as-a-floating-average"></a>Är glidande medelvärde detsamma som ett flytande medelvärde?

Termerna i glidande medelvärde, flytande medelvärde och löpande medelvärde används ofta synonymt. Av dessa termer är glidande medelvärde den enda officiella kostnadsmodellen som är tillgänglig i Supply Chain Management. Även om löpande medelvärde inte är en officiell kostnadsmodell, är det den teknik som används när du använder en periodisk kostnadsmodell som FIFO, LIFO eller viktat medelvärde. Termen flytande medelvärde används inte i Supply Chain Management och kan ha olika konnotationer i andra system.

### <a name="how-can-i-accommodate-the-difference-between-the-product-receipt-price-and-invoice-price-when-i-use-moving-average"></a>Hur kan jag ta hänsyn till skillnaden mellan produktens inleveranspris och fakturapriset när jag använder glidande medelvärde?

När du använder glidande medelvärde används den fysiska kostnaden (inleveranspris) för att beräkna det glidande medelvärdet för alla utleveranstransaktioner. Om det finns en skillnad mellan den fysiska kostnaden (kvittopris) och den finansiella kostnaden (fakturapris), kommer systemet automatiskt att bokföra skillnaden på huvudkontot som anges för bokföringstypen **Prisdifferens för rörligt genomsnitt** på fliken **Lager** på sidan **Bokföringsprofil för lager**.

### <a name="where-is-the-price-difference-for-moving-average-presented-in-the-general-ledger"></a>Var presenteras prisdifferensen för glidande medelvärde i redovisningen?

När det finns en prisskillnad mellan bokföring av en fysisk uppdatering och en ekonomisk uppdatering för ett kvitto, bokförs skillnaden på huvudkontot som anges för bokföringstypen **Prisdifferens för rörligt genomsnitt** på fliken **Lager** på sidan **Bokföringsprofil för lager**. Mer information finns i [Glidande medelvärde](moving-average.md).

### <a name="when-i-use-moving-average-what-happens-if-there-is-an-issue-before-the-receipt"></a>När jag använder glidande medelvärde, vad händer om det finns en utleverans före inleveransen?

Vanligtvis kan det finnas en utleverans före inleveransen, antingen eftersom du tillåter fysiskt negativt lager för artikelmodellgruppen eller pga. att utleveransen har kvittats. Mer information finns i avsnittet [Negativt lager](#negative-inventory) i denna artikel.

Om du bakåtställer transaktioner bör du noggrant överväga affärsprocessen och åtgärderna för att ta reda på om det finns ett sätt att undvika det här scenariot. Om du bakåtdatera en transaktion för en artikel som använder ett rörligt medelvärde, tilldelar systemet det aktuella rörliga medelvärdet till transaktionen. Senare utleveranser justeras inte. Mer information om glidande medelvärde med bakåtdaterade transaktioner finns i [glidande medelvärde](moving-average.md).

### <a name="standard-costing"></a>Standardkostnadsredovisning

### <a name="what-is-the-difference-between-standard-costing-and-fixed-receipt-price"></a>Vad är skillnaden mellan standardkostnadsredovisning och fast inleveranspris?

Vid standardkostnadsredovisning måste du definiera ett artikelpris och aktivera kostnaden i en kostnadsredovisningsversion. Kostnaden används för alla in- och utleveranser. Avvikelser för inleveranserna till lagret registreras i redovisningen genom att använda de avvikelsekonton för standardkostnad som du anger på fliken **Standardkostnad** på sidan **Lagerbokföringsprofil**.

När du använder ett fast inleveranspris, fastställs dock bara kostnaden för inleveranser och den kostnad som du anger på snabbfliken **Hantera kostnader** på sidan **Frisläppt produkt** används. Skillnader mellan standardkostnaden och inköpsorderpriset medför att inköpsprisavvikelsen bokförs på det fasta inleveransprisets vinst- och förlustkonton. Utleveranser används inte för fasta inleveranspriser. Istället värderas utleveranser till det löpande medelvärdet vid bokföringen (om du inte använder markering) och de omvärderas till den heuristiska modell som du väljer när du kör lagerstängingen.

### <a name="can-i-use-fefo-reservations-with-standard-costing"></a>Kan jag använda FEFO-reservationer med standardkostnadsredovisning?

Ja, du kan använda FEFO-reservationer på en artikelmodellgrupp när du väljer standardkostnadsredovisning. FEFO-reservationer kontrollerar den reservationslogik som används för den fysiska hanteringen av artiklarna, medan standardkostnad styr de fysiska och ekonomiska kostnaderna för en artikel.

### <a name="can-i-upload-pending-prices"></a>Kan jag överföra väntande priser?

Ja, du kan använda Excel-tillägget eller Data Management Framework för att föra över ett pågående pris. Vi rekommenderar att du använder följande enheter:

- Priser för pågående artikel (V2)
- Enhetskostnader för väntande flödeskostnadskategori
- Beräkningsfaktorer för kostnadsredovisningsnod (V2)

### <a name="how-often-can-i-update-the-standard-cost-for-an-item"></a>Hur ofta kan jag uppdatera standardkostnaden för en artikel?

Det finns ingen gräns för hur ofta du kan aktivera en ny standardkostnad. Om du aktiverar en ny kostnad för en artikel samma dag som den senaste kostnaden aktiverades, används den senast aktiverade kostnaden på nya transaktioner eller uppdateringar (till exempel uppdateringar av befintliga transaktioner).

### <a name="can-i-deactivate-or-delete-an-activated-cost"></a>Kan jag inaktivera eller ta bort en aktiverad kostnad?

Nej, du kan inte inaktivera eller ta bort en aktiverad kostnad. Om du har aktiverat en kostnad på fel sätt kan du aktivera en ny kostnad som har rätt kostnad.

### <a name="are-calculation-groups-used-with-standard-costing"></a>Används beräkningsgrupper tillsammans med standardkostnadsredovisning?

Beräkningsgrupper kan användas för alla artiklar, oavsett vilken artikelmodellgrupp du väljer. Beräkningsgrupperna används under kostnadsberäkningen eller kostnadsberäkningsprocessen för att bestämma vilka inställningar som ska användas för artiklarna som du kör beräkningen för. Mer information om beräkningsgrupper finns i [Beräkningsgrupper för strukturlista](bom-calculation-groups.md).

### <a name="when-should-i-use-a-planned-costing-version"></a>När ska jag använda en planerad kostnadsversion?

Kostnadsversioner kan ha typen *Standardkostnad* eller *Planerad kostnad*. Typen *Standardkostnad* används för kostnader som är aktiva i systemet och bokförs i transaktioner. Typen *Planerad kostnad* används för att köra simuleringar på kostnader och påverkar inte kostnaderna för transaktionerna.

### <a name="can-the-total-cost-from-one-entity-be-transferred-to-another-entity-as-the-selling-cost"></a>Kan den totala kostnaden från en enhet överföras till en annan enhet som försäljningskostnad?

Det finns inte ett automatiskt sätt att kopiera kostnader från ett företag till ett annat. Det finns heller inget automatiskt sätt att kopiera kostnader från ett inköpspris till ett försäljningspris. Om din organisation måste utföra en av dessa uppgifter bör du överväga om du kan använda Data Management Framework för att exportera data ur kostnadsversionen och överföra till ett annat företag, antingen som ett försäljningspris i kostnadsversionen eller som ett handelsavtal. Manuell manipulering av filerna kan behövas.

### <a name="what-is-the-best-way-to-copy-planned-costs-to-a-standard-costing-version"></a>Vilket är det bästa sättet att kopiera planerade kostnader till en standardkostnadsversion?

Använd knappen **Kopiera** på sidan **Kostnadsversioner** om du vill kopiera artikelpriser, kostnadskategoripriser eller indirekta kostnader från en kostnadsversion till en annan.
