---
title: Felsöka diskret tillverkning
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med diskret tillverkning.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 2004a48455939855df54c3087a11c8003d825566
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222763"
---
# <a name="troubleshoot-discrete-manufacturing"></a>Felsöka diskret tillverkning

I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med diskret tillverkning.

## <a name="i-receive-the-following-error-message-warehouse-management-processes-are-currently-being-used-if-work-lines-are-not-yet-registered-you-can-cancel-the-created-work-and-any-load-or-shipment-lines-and-then-continue-with-the-picking-or-shipping-process"></a>Följande felmeddelande visas: "lagerställe hanteringsprocesser används för närvarande. Om inte arbetsrader har registrerats ännu kan du annullera det skapade arbetet och eventuella beläggnings- eller försändelserader och sedan fortsätta med plocknings- eller leveransprocessen".

### <a name="issue-description"></a>Problembeskrivning

Det här problemet uppstår om du försöker reservera eller frisläppa arbete för en rad, men lager transaktionen har statusen *plockad*, vilket anger att materialet har plockats.

### <a name="issue-resolution"></a>Problemlösning

Gör så här om du vill åtgärda problemet.

- Ändra tillbaka tillverkningsorderns status till *uppskattad* eller *frisläppt*.
- Öppna informationssidan för relevant produktionsorder. I åtgärdsfönstret på fliken **Lagerställe** i gruppen **Stopp** välj **Stoppa och häva plockning** för att häva plockning för alla plockade transaktioner. Välj sedan **ta bort stopp** för att bearbeta tillverkningsordern.

Här följer en förklaring av funktionerna *Häv plockning* och *Stopp*:

- **Häv plockning** – den här funktionen återför statusen för lagertransaktioner för strukturlisterader och receptrader som har status från *plockad* via *Har beställts*. När arbetet för plockning av råmaterial har slutförts ställs status på raderna in på *plockad*. Denna status förhindrar att tillverkningsordern återställs till statusen *Skapad*. I det här fallet kan du använda funktionen *Häv plockning* för att återställa transaktionerna från *plockad* status och sedan återställa tillverkningsordern till statusen *Skapad*.
- **Stopp** – den här funktionen ställer in en **stoppad** flagga på tillverkningsordern för att förhindra statusuppdatering för ordern. Du kan hitta **Stoppad** på snabbfliken **Distributionslager** på sidan med produktionsuppgifter.

> [!NOTE]
>
> - Knapparna visas bara när tillverkningsordern skapas för artiklar som är aktiverade för lagerprocesser.
> - Gruppen **Stopp** visa bara på **distributionslager** på åtgärdsfönstret på sidan med produktionsorder. Det visas inte på snabbfliken **Lagerställe** för listsidan **Produktionsorder**.

## <a name="the-matching-resource-name-isnt-updated-after-i-change-a-worker-name-in-the-global-address-book"></a>Det matchande resursnamnet uppdateras inte när jag har ändrat arbetsnamnet på en global adressbok.

### <a name="issue-description"></a>Problembeskrivning

Om du ändrar ett arbetarnamn i den globala adressboken uppdateras inte det matchande resursnamnet i resursgruppmall

### <a name="issue-resolution"></a>Problemlösning

Detta scenario stöds för närvarande inte. För att åtgärda problemet måste du uppdatera resursnamnet manuellt.

## <a name="when-i-create-a-new-production-order-i-dont-receive-the-following-message-insert-the-active-version-of-bill-of-material-and-route"></a>När jag skapar en ny tillverkningsorder visas inte följande meddelande: "sätt in den aktiva versionen av strukturlistan och flödet?"

### <a name="issue-description"></a>Problembeskrivning

När du skapar en ny produktionsorder, efter att du har angett artikelnumret, kommer **Webbplats** och **Distributionslager** ställs automatiskt in till standardwebbplatsen och lagret som definieras på sidan **Standardorderinställningar** för färdig varuartikel. Dessutom anges de aktiva strukturliste- och flödesnumren automatiskt. Följande meddelande visas utan att du tillfrågas om dessa värden:

> Vill du infoga aktiv version för strukturlista och flöde?

### <a name="issue-resolution"></a>Problemlösning

Du uppmanas inte att infoga strukturliste- och flödesnummer om du väljer en produkt som en webbplats och ett lagerställe har definierats på sidan **standardorderinställningar**. Du får bara en fråga om dessa värden inte har definierats för den valda produkten.

## <a name="production-orders-arent-shown-on-the-marking-page"></a>Tillverkningsorder visas inte på markeringssidan.

### <a name="issue-description"></a>Problembeskrivning

Vissa tillverkningsorder visas inte på **markeringssidan**.

### <a name="issue-resolution"></a>Problemlösning

Produkter som har följande konfiguration är inte tillgängliga för markering. Därför visas de inte på **markeringssidan**:

- Produkterna definieras som produkter av typen *faktisk/nominell vikt*.
- De aktiveras för de avancerade lagerprocesserna.
- De konfigureras för kontroll med principen för *standardkostnad*.

## <a name="when-i-try-to-end-a-production-order-i-receive-the-following-error-message-calculating-bom-consumptioncost-value-must-be-negative-upon-issue-from-inventory"></a>När jag försöker avsluta en tillverkningsorder visas följande felmeddelande: "beräkning av strukturliste consumptionCost-värdet måste vara negativt vid utleverans från lagret".

Det här problemet har åtgärdats i version 10.0.15.

## <a name="when-the-status-of-a-production-order-is-changed-from-reported-as-finished-to-end-i-receive-the-following-error-messages-update-conflict-the-standard-cost-does-not-match-with-the-financial-inventory-value-after-the-update-and-a-critical-error-has-occurred-in-function-inventcostmovementcheckvariance"></a>När statusen för en tillverkningsorder ändras från rapporterad som färdig till slut visas följande felmeddelanden: "uppdateringskonflikt. Standardkostnaden matchar inte det ekonomiska lagervärdet efter uppdateringen" och "Ett allvarligt fel har uppstått i funktionen InventCostMovement.checkVariance".

Det här problemet beror på att underliggande data har ändrats av en annan process. Processen kommer att försöka uppdatera data upp till fem gånger. Om det fortfarande finns en konflikt efter fem försök visas följande felmeddelanden:

> Uppdateringskonflikt. Standardkostnaden matchar inte det ekonomiska lagervärdet efter uppdateringen.

> Ett allvarligt fel har uppstått i funktionen InventCostMovement.checkVariance.

Detta beteende är av design. Du kan undvika problemet genom att återuppta batch-jobbet. Den ska köras.

Om batchjobbet misslyckas när du har återaktiverat det kontrollerar du att avrundnings precisionen för redovisningens standardvaluta är kompatibel med avrundning som tillämpas på värdena i registret InventSum. Om avrundningsprecisionen har ändrats till ett icke-kompatibelt värde måste du förmodligen ändra tillbaka till ett kompatibelt värde. Leta efter **ModifiedDateTime**. I det här fallet visar värdet normalt att avrundningsprecisionen nyligen ändrades.

## <a name="when-i-release-to-a-warehouse-i-receive-the-following-error-message-item-rm-could-not-be-fully-reserved-ensure-that-the-full-quantity-is-available-or-reserve-the-items-manually-if-the-reservation-field-on-the-bom-line-is-set-to-manual-or-started-could-not-release-the-order-to-warehouse-because-some-materials-could-not-be-reserved-however-the-status-is-updated-to-released"></a>När jag släpper till ett lagerställe visas följande fel meddelande: "objektet RM kunde inte reserveras fullt ut. Se till att hela kvantiteten är tillgänglig, eller reservera artiklarna manuellt om fältet reservation på strukturlisteraden är inställt på manuell eller startad. Det gick inte att släppa ordern till lagerstället eftersom det inte gick att reservera vissa material". Statusen uppdateras dock till frisläppt.

### <a name="issue-description"></a>Problembeskrivning

Om inte alla radartiklar för strukturlistan är fysiskt tillgängliga när en tillverknings order frisläpps, och principen **utleverans till lagerställe** anges till *kräver fullständig reservation* på tillverkningsordern visas följande felmeddelande:

> Objekt RM kunde inte reserveras helt. Se till att hela kvantiteten är tillgänglig, eller reservera artiklarna manuellt om fältet reservation på strukturlisteraden är inställt på manuell eller startad. Det gick inte att släppa ordern till lagerstället eftersom det inte gick att reservera vissa material.

### <a name="issue-resolution"></a>Problemlösning

Detta är avsiktligt och fungerar som förväntat.

## <a name="when-i-try-to-end-a-production-order-and-report-as-finished-i-receive-the-following-error-message-total-good-quantity-reported-as-finished-for-the-production-will-be-1-feedback-for-the-last-operation-is-000-in-total"></a>När jag försöker avsluta en tillverkningsorder och rapportera som färdig visas följande felmeddelande: "total godkänd kvantitet som rapporterats som färdig för produktionen kommer att vara %1. Återrapportering för den senaste operationen är 0,00 sammanlagt".

### <a name="issue-description"></a>Problembeskrivning

När du försöker att bokföra en rapport som färdig journal på en tillverkningsorder visas följande felmeddelande:

> Totalt godkänt antal rapporterat som färdigt för produktionen blir %1. Återrapportering för den senaste operationen är 0,00 sammanlagt.

### <a name="possible-cause"></a>Möjlig orsak

Det här problemet uppstår om kvantiteterna som har bokförts i de senaste operationerna var felaktiga. Om till exempel produktionen startas men den kvantitet som ska startas inte fördelas, bokförs flödeskortjournalen utan några rader. Du bekräftar situationen genom att öppna tillverkningsordern och sedan välja fliken **Vy** och **flödeskort** i åtgärdsfönstret.

### <a name="workaround"></a>Lösning

Du kan lösa det här problemet genom att bokföra ytterligare journaler för de operationer som journalerna inte kunde bokföras för. Starta om tillverkningsordern och välj om du vill bokföra ytterligare journaler. Den här åtgärden startar inte tillverkningsordern, utan då bokförs journalerna. Flödeskortet ska sedan visa de kvantiteter som bokfördes och du bör kunna avsluta tillverkningsorder.

## <a name="can-i-report-a-production-order-as-finished-while-i-report-the-error-quantity-but-not-while-i-report-the-time-or-material-quantity"></a>Kan jag rapportera en tillverkningsorder som färdig medan jag rapporterar en felaktig kvantitet, men inte när jag rapporterar tids- eller materialkvantitet?

Du kan inte rapportera felkvantiteten i en tillverkningsorder om du inte också rapporterar den godkända kvantiteten. Detta scenario stöds **inte**. Uppdateringen rapportera som färdig slutar att fungera när du försöker avsluta tillverkningsordern och följande felmeddelande visas:

> Kvantitet saknad rapporterad som färdig.

## <a name="can-i-trace-the-serial-numbers-of-finished-goods-against-the-serial-numbers-of-consumed-goods"></a>Kan jag spåra serienumren för färdiga varor mot serienumren för förbrukade varor?

Du kan inte spåra serienumren för färdiga varor mot serienummer för material som en tillverkningsorder använder för att göra dessa färdiga varor. Detta scenario stöds för närvarande inte. Lösningen är att skapa tillverkningsorder för kvantiteten 1.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]